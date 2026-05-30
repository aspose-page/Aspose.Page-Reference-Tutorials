---
date: 2026-01-18
description: Ismerje meg, hogyan hozhat létre PostScript dokumentumot .NET-ben, és
  adjon hozzá téglalapokat az Aspose.Page for .NET használatával. Lépésről lépésre
  útmutató kódrészletekkel.
linktitle: Add Rectangle to PostScript (PS)
second_title: Aspose.Page .NET API
title: Postscript dokumentum létrehozása .net – Téglalap hozzáadása az Aspose.Page
  segítségével
url: /hu/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Téglalap hozzáadása a PostScript (PS) fájlhoz az Aspose.Page for .NET segítségével

## Introduction

Ha **postscript dokumentumot .net** szeretnél létrehozni, az Aspose.Page erőteljes megoldást kínál a PostScript fájlok kezelésére. Ebben az útmutatóban végigvezetünk a téglalapok hozzáadásán egy PostScript dokumentumhoz az Aspose.Page for .NET használatával, így szilárd alapot adva a gazdagabb grafika generálásához.

## Quick Answers
- **Milyen könyvtárra van szükségem?** Aspose.Page for .NET.
- **Létrehozhatok-e PostScript dokumentumot a semmiből?** Igen – az API lehetővé teszi a PS fájlok programozott építését.
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Szükségem van licencre a fejlesztéshez?** A ingyenes próba verzió teszteléshez megfelelő; licenc szükséges a termeléshez.
- **Mennyi időt vesz igénybe a megvalósítás?** Általában 10 perc alatt a alapvető alakzatokhoz.

## What is creating a postscript document .net?
A PostScript dokumentum létrehozása .NET-ben azt jelenti, hogy programozottan generálunk egy .ps fájlt, amely leírja az oldal tartalmát – szöveget, grafikát vagy alakzatokat – az Aspose.Page API használatával. Ez a megközelítés ideális szerver‑oldali grafika generáláshoz, automatizált jelentéskészítéshez, vagy bármely olyan esethez, ahol pontos kontrollra van szükség a kimeneti formátum felett.

## Why use Aspose.Page for .NET?
- **Teljes kontroll a grafika felett** – alakzatok rajzolása, színek beállítása és vonalak alkalmazása alacsony szintű PS szintaxis nélkül.
- **Keresztplatformos** – működik Windows, Linux és macOS környezetekben.
- **Nincsenek külső függőségek** – a könyvtár belsőleg kezeli a PS generálást.
- **Gazdag dokumentáció és példák** – gyorsan belevághatsz.

## Prerequisites

- **Aspose.Page for .NET Library** – töltsd le és telepítsd innen: [here](https://releases.aspose.com/page/net/).
- **Fejlesztői környezet** – Visual Studio, VS Code vagy bármely .NET‑kompatibilis IDE.

## Import Namespaces

Mielőtt elkezdenéd a kódolást, importáld a szükséges osztályokat tartalmazó névtereket:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Most bontsuk le a példát világos, számozott lépésekre.

## 1. lépés: A dokumentum könyvtár beállítása

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Cseréld le a `"Your Document Directory"` értéket arra a mappára, ahol a létrehozott PS fájlt menteni szeretnéd.

## 2. lépés: Kimeneti stream létrehozása a PostScript dokumentumhoz

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Ez a stream a **AddRectangle_outPS.ps** fájlra mutat. Nyugodtan átnevezheted a fájlt vagy megváltoztathatod a helyét, ahogy szükséges.

## 3. lépés: Mentési beállítások megadása és a PS dokumentum létrehozása

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Itt azt mondjuk az Aspose.Page-nek, hogy A4-es oldalméretet használjon, és egyoldalas dokumentumot hozzon létre.

## 4. lépés: Kitöltött téglalap hozzáadása

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

Definiálunk egy téglalapot a (250, 100) koordinátán, 150 szélességgel és 100 magassággal, beállítunk egy narancssárga ecsetet, és kitöltjük az alakzatot.

## 5. lépés: Kontúrozott téglalap hozzáadása

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

A második téglalap az oldal alján jön létre, ezúttal egy 3‑pontos piros vonallal.

## 6. lépés: Az oldal lezárása és a dokumentum mentése

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Az oldal lezárása befejezi a rajzot, a `Save()` pedig a PS fájlt a lemezre írja.

## Gyakori problémák és tippek

- **Helytelen fájl útvonal** – Győződj meg róla, hogy a `dataDir` útvonal elválasztóval (`\\` vagy `/`) végződik, vagy használd a `Path.Combine`‑t.
- **Hiányzó licenc** – Egy termelési környezetben alkalmazd az Aspose licencet a dokumentum létrehozása előtt, hogy elkerüld a kiértékelési vízjeleket.
- **Szín láthatóság** – Ha a téglalap üresnek tűnik, ellenőrizd, hogy az ecset vagy a toll színei kontrasztban vannak-e az oldal háttérrel.

## Gyakran Ismételt Kérdések

**Q:** Testreszabhatom a téglalapok színeit?  
**A:** Természetesen. Módosítsd a `Color.Orange` vagy `Color.Red` értékeket a `SolidBrush` és `Pen` konstruktorokban bármely `System.Drawing.Color` értékre, amit szeretnél.

**Q:** Az Aspose.Page kompatibilis más dokumentumformátumokkal?  
**A:** Igen. A PostScript mellett az Aspose.Page támogatja az XPS és EPS generálást is.

**Q:** Hogyan adhatok szöveget ugyanahhoz a dokumentumhoz?  
**A:** Használd a `TextFragment` osztályt a szöveg kívánt koordinátákra helyezéséhez, majd hívd a `document.Draw(textFragment)` metódust.

**Q:** Hol találok további példákat és a teljes API referenciát?  
**A:** Tekintsd meg a dokumentációt [here](https://reference.aspose.com/page/net/) és csatlakozz a közösséghez az [Aspose.Page fórumon](https://forum.aspose.com/c/page/39).

**Q:** Kipróbálhatom az Aspose.Page‑t vásárlás előtt?  
**A:** Igen, töltsd le az ingyenes próbaverziót [here](https://releases.aspose.com/). Hosszabb értékeléshez fontold meg a [temporary license](https://purchase.aspose.com/temporary-license/) lehetőséget.

---

**Utolsó frissítés:** 2026-01-18  
**Tesztelt verzió:** Aspose.Page 24.12 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}