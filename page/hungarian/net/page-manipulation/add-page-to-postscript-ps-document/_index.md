---
date: 2026-03-03
description: Tanulja meg, hogyan állíthat be egyedi oldalméretet, és hogyan adhat
  hozzá egy második PS oldalt egy PostScript dokumentumhoz az Aspose.Page for .NET
  használatával.
linktitle: Add Page to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Egyéni oldalméret beállítása PS dokumentumban az Aspose.Page segítségével
url: /hu/net/page-manipulation/add-page-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Oldal hozzáadása PostScript (PS) dokumentumhoz az Aspose.Page segítségével

## Bevezetés

A .NET fejlesztés során a **egyedi oldalméret beállítása** és a **második PS oldal hozzáadása** egy PostScript (PS) dokumentumhoz finomhangolt vezérlést biztosít a generált nyomatok, jelentések vagy grafikák elrendezése felett. Az Aspose.Page for .NET egyszerűvé teszi ezt a feladatot egy tiszta, objektum‑orientált API-val. Ebben az útmutatóban megtanulja, hogyan hozhat létre többoldalas PS fájlt, hogyan definiálhat egyedi méretet minden oldalra, és hogyan mentheti az eredményt – mindezt néhány C# sorral.

## Gyors válaszok
- **Beállíthatok egyedi oldalméretet?** Igen – egyszerűen adja meg a szélességet és magasságot az oldal megnyitásakor.  
- **Hogyan adhatok hozzá egy második PS oldalt?** Hívja meg a `document.OpenPage(width, height)` metódust a második alkalommal.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Szükségem van licencre?** Egy ideiglenes licenc teszteléshez elegendő; a teljes licenc a termeléshez kötelező.  
- **Hol tölthetem le az Aspose.Page-t?** Az alább található hivatalos letöltési oldalról.

## Előfeltételek

Mielőtt elkezdené a gyakorlati példát, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

- A .NET fejlesztés alapjainak ismerete.  
- Visual Studio telepítve van a gépén.  
- Aspose.Page for .NET könyvtár, amelyet letölthet [itt](https://releases.aspose.com/page/net/).  
- A teszteléshez preferált dokumentumkönyvtár.

## Névterek importálása

Győződjön meg róla, hogy a projektjében szerepelnek a szükséges névterek az Aspose.Page funkcióinak eléréséhez. A példában a névterek implicit módon vannak beillesztve, de fontos, hogy ellenőrizze és a projekt felépítése szerint módosítsa őket.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 1. lépés: A projekt beállítása

Hozzon létre egy új .NET projektet a Visual Studio-ban, és állítsa be a szükséges konfigurációkat. Ne felejtse el hivatkozni az Aspose.Page könyvtárra a projektben.

## Egyedi oldalméret beállítása és második PS oldal hozzáadása

Ez a szakasz pontosan bemutatja, hogyan **állíthat be egyedi oldalméretet** minden oldalra, és hogyan **adhat hozzá egy második ps oldalt** ugyanahhoz a dokumentumhoz.

### 2. lépés: A dokumentum inicializálása

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "document1.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create a new 2-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, 2);
```

### 3. lépés: Az első oldal hozzáadása (alapértelmezett méret)

```csharp
    // Add the first page
    document.OpenPage();

    // Add content

    // Close the first page
    document.ClosePage();
```

### 4. lépés: A második oldal hozzáadása eltérő (egyedi) mérettel

```csharp
    // Add the second page with a different size
    document.OpenPage(400, 700);

    // Add content

    // Close the second page
    document.ClosePage();
```

### 5. lépés: A dokumentum mentése

```csharp
    // Save the document
    document.Save();
}
// ExEnd:1
```

Kövesse ezeket a lépéseket pontosan, és sikeresen **beállítja az egyedi oldalméretet**, valamint **hozzáad egy második PS oldalt** egy PostScript dokumentumhoz az Aspose.Page for .NET használatával.

## Miért fontos ez

- **Precíz elrendezés** – Az egyedi oldalméretek lehetővé teszik a nyomtató specifikációinak pontos egyezését vagy egyedi brosúraformátumok létrehozását.  
- **Több oldal** – A második (vagy több) oldal hozzáadása lehetővé teszi a többoldalas jelentéseket külső egyesítő eszközök nélkül.  
- **Keresztplatformos** – A generált PS fájl bármely PostScript‑kompatibilis eszközön megjeleníthető, vagy később PDF‑re konvertálható.

## Gyakori hibák és hibaelhárítás

- **Helytelen útvonal** – Győződjön meg róla, hogy a `dataDir` útvonal elválasztóval végződik, vagy használja a `Path.Combine` metódust.  
- **Licencproblémák** – Érvényes licenc hiányában a könyvtár vízjelet helyezhet el, vagy korlátozhatja az oldalak számát.  
- **Mértékegység‑zavar** – A szélesség és magasság pontban (1 pont = 1/72 hüvelyk) van megadva. Ennek megfelelően állítsa be.

## Gyakran ismételt kérdések

**Q1: Az Aspose.Page kompatibilis-e különböző dokumentumformátumokkal?**  
A1: Az Aspose.Page elsősorban a PostScript dokumentumok manipulálására fókuszál. Más formátumokhoz más Aspose könyvtárakat érdemes felfedezni.

**Q2: Testreszabhatom az oldalméretet az Aspose.Page-ben?**  
A2: Természetesen! Ahogy a gyakorlati példában látható, megadhat különböző méreteket minden oldalhoz a saját igényei szerint.

**Q3: Hol találok további példákat és dokumentációt?**  
A3: Látogasson el a [dokumentáció](https://reference.aspose.com/page/net/) oldalra, ahol átfogó információkat és számos példát talál.

**Q4: Hogyan szerezhetek ideiglenes licencet az Aspose.Page-hez?**  
A4: Látogassa meg [ezt a linket](https://purchase.aspose.com/temporary-license/), ahol teszteléshez ideiglenes licencet szerezhet.

**Q5: Hol kérhetek közösségi támogatást vagy tehetek fel kérdéseket?**  
A5: Csatlakozzon az [Aspose.Page közösségi fórumhoz](https://forum.aspose.com/c/page/39), hogy más fejlesztőkkel kapcsolatba léphessen, tapasztalatokat osszon meg, és segítséget kapjon.

---

**Utoljára frissítve:** 2026-03-03  
**Tesztelve a következővel:** Aspose.Page 24.11 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}