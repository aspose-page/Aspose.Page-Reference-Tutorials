---
date: 2026-01-12
description: Tanulja meg, hogyan menthet PostScript fájlt, és hozhat létre PostScript
  dokumentumot az Aspose.Page for .NET használatával, valamint hogyan alkalmazhat
  több átalakítást dinamikus grafikákhoz.
linktitle: Transformations PS
second_title: Aspose.Page .NET API
title: PostScript fájl mentése az Aspose.Page Transformations (.NET) segítségével
url: /hu/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PostScript fájl mentése Aspose.Page átalakításokkal (.NET)

## Introduction

Ebben az útmutatóban megtudja, hogyan **mentse a PostScript fájlt** az Aspose.Page for .NET használata közben. Lépésről lépésre végigvezetjük a PostScript dokumentum létrehozásán, több átalakítás (fordítás, méretezés, forgatás és nyírás) alkalmazásán, majd a végeredmény mentésén. A végére magabiztosan tud majd dinamikus grafikákat programozott módon készíteni, és pontosan tudni fogja, hol kell elhelyezni az egyes átalakításokat a grafikai állapotban.

## Quick Answers
- **Mit hozhatok létre?** Egy teljes funkcionalitású PostScript dokumentum átalakított grafikákkal.  
- **Melyik könyvtár szükséges?** Aspose.Page for .NET (letölthető a hivatalos weboldalról).  
- **Hogyan menthetem a fájlt?** Használja a `PsDocument.Save()` metódust a grafikai állapotok beállítása után.  
- **Alkalmazhatok több átalakítást?** Igen – kombinálja őket a `Transform` segítségével vagy sorozatos hívásokkal.  
- **Szükséges licenc?** Egy ingyenes próba verzió fejlesztéshez megfelelő; a termeléshez kereskedelmi licenc szükséges.

## What is a “save postscript file” operation?

A PostScript fájl mentése azt jelenti, hogy a memóriában felépített rajzolási parancsokat egy `.ps` fájlba írja le a lemezen. A fájlt ezután bármely PostScript interpreter, nyomtató vagy megjelenítő képes renderelni.

## Why use Aspose.Page for .NET to create postscript document?

Az Aspose.Page egy magas szintű, eszközfüggetlen API-t biztosít, amely elrejti az alacsony szintű PostScript szintaxist. A következőket kapja:
- Erősen típusos C# objektumok útvonalakhoz, ecsetekhez és átalakításokhoz.  
- Automatikus grafikai állapot verem kezelése (mentés/visszaállítás).  
- Teljes támogatás összetett transzformációs mátrixokhoz manuális számítások nélkül.  

## Prerequisites

Mielőtt elkezdené, ellenőrizze, hogy rendelkezik:
- **Aspose.Page for .NET** könyvtár integrálva a projektjébe. Szerezze be a [letöltési hivatkozásról](https://releases.aspose.com/page/net/).  
- Egy írható mappa, ahol a generált `.ps` fájl tárolva lesz. Cserélje le a kódban lévő helyőrző útvonalat a saját könyvtárára.

## Import Namespaces

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Most vizsgáljuk meg lépésről lépésre az egyes átalakításokat.

## No Transformations

### Step 1: Create Output Stream

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Create save options with default values
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Create graphics path from the rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Set paint in graphics state on upper level
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Fill the first rectangle that is on the upper-level graphics state and without any transformations
    document.Fill(path);

    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Ez a kódrészlet egy **PostScript dokumentumot** hoz létre egyetlen narancssárga téglalappal, és **menti a PostScript fájlt** anélkül, hogy bármilyen átalakítást alkalmazna.

## Translation

### Step 1: Save Graphics State

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

A grafikai állapot mentése lehetővé teszi, hogy visszatérjen az objektumok mozgatása után.

### Step 2: Translate Graphics State

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

Az eltolás minden, ezt a hívást követően rajzolt elemet 250 egységgel jobbra helyez.

### Step 3: Fill Rectangle with Translation Transformation

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

Most egy kék téglalap jelenik meg 250 ponttal a narancssárga jobb oldalán.

### Step 4: Restore Graphics State

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

A visszaállítás visszaadja a koordináta rendszert az eredeti helyzetbe, így a későbbi rajzolás nem lesz befolyásolva az eltolás által.

## Scaling

> *Követheti ugyanazt a mintát—állapot mentése, `Scale` alkalmazása, rajzolás, majd visszaállítás.*  
> **Pro tipp:** Használjon nem egyenletes méretezést (`Scale(sx, sy)`) az objektumok egyetlen irányban történő nyújtásához.

## Rotation

> *Forgassa a kiindulási pont vagy egy egyéni forgáspont körül a `Rotate(angle)` használatával.*  
> **Pro tipp:** Kombinálja a `Translate`-et a forgatás előtt, hogy egy meghatározott pont körül forgassa.

## Shearing

> *A nyírási átalakítások (`Shear(shx, shy)`) döntik a formákat, hasznosak dőlt hatásokhoz.*  

## Complex Transformations

> *Haladó esetekben építsen egy egyedi `Matrix`-et, és adja át a `Transform(matrix)`-nek.*  
> Itt **több átalakítást alkalmazhat** egyetlen lépésben.

## Conclusion

Megtanulta, hogyan **mentse a PostScript fájlt**, **hozzon létre PostScript dokumentumot**, és **alkalmazzon több átalakítást** az Aspose.Page for .NET segítségével. Kísérletezzen különböző átalakítási sorrendekkel, kombinálja őket, és figyelje meg, hogyan alakul a grafika.

## Frequently Asked Questions

**Q: Hogyan alkalmazhatok több átalakítást egyetlen objektumra?**  
A: Használja a `Transform` metódust egy egyedi `Matrix`-szel, amely a kívánt sorrendben kombinálja a fordítást, méretezést, forgatást vagy nyírást.

**Q: Megtekinthetem az átalakításokat a dokumentum mentése előtt?**  
A: Igen—renderelje a `PsDocument`-et egy képre, vagy használjon PostScript megjelenítőt a kimenet ellenőrzéséhez a `Save()` hívása előtt.

**Q: Lehetséges átalakításokat alkalmazni a dokumentum egyes elemeire?**  
A: Természetesen. Mentse a grafikai állapotot az elem rajzolása előtt, alkalmazza a kívánt átalakítást, rajzoljon, majd állítsa vissza az állapotot.

**Q: Vannak teljesítménybeli szempontok összetett átalakítások esetén?**  
A: Az összetett mátrixok növelik a CPU terhelését. Tartsa az átalakításokat a lehető legegyszerűbbnek, és használja újra a mentett állapotokat, ha sok hasonló objektumot rajzol.

**Q: Hogyan kaphatok támogatást vagy segítséget az Aspose.Page‑hez kapcsolódó kérdésekhez?**  
A: Látogassa meg az [Aspose.Page fórumot](https://forum.aspose.com/c/page/39) a közösségi segítségért, vagy vegye fel a kapcsolatot közvetlenül az Aspose támogatással.

---

**Last Updated:** 2026-01-12  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}