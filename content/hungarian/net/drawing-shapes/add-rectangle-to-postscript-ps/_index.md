---
title: Adjon hozzá téglalapot a PostScripthez (PS) az Aspose.Page for .NET segítségével
linktitle: Téglalap hozzáadása a PostScript-hez (PS)
second_title: Aspose.Page .NET API
description: Fokozza a dokumentumok létrehozását .NET-ben az Aspose.Page segítségével. Ismerje meg lépésről lépésre, hogyan adhat téglalapokat PostScript (PS) fájlokhoz.
type: docs
weight: 12
url: /hu/net/drawing-shapes/add-rectangle-to-postscript-ps/
---
## Bevezetés

Ha javítani szeretné dokumentumkészítési képességeit .NET-ben, az Aspose.Page hatékony megoldást kínál a PostScript dokumentumok kezelésére. Ebben az oktatóanyagban végigvezetjük a téglalapok PostScript-dokumentumokhoz való hozzáadásának folyamatán az Aspose.Page for .NET használatával.

## Előfeltételek

Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

-  Aspose.Page for .NET Library: Töltse le és telepítse az Aspose.Page for .NET könyvtárat innen:[itt](https://releases.aspose.com/page/net/).

- Fejlesztői környezet: Győződjön meg arról, hogy a gépen be van állítva .NET fejlesztői környezet.

## Névterek importálása

A kódolás megkezdése előtt feltétlenül importálja a szükséges névtereket a szükséges osztályok és metódusok eléréséhez:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Most bontsuk fel a példát több lépésre:

## 1. lépés: Állítsa be a dokumentumkönyvtárat

```csharp
// ExStart:1
// A dokumentumok könyvtárának elérési útja.
string dataDir = "Your Document Directory";
```

Ebben a lépésben cserélje ki a "Dokumentumkönyvtár" elemet arra az elérési útra, ahová menteni szeretné a PostScript-dokumentumot.

## 2. lépés: Hozzon létre kimeneti adatfolyamot a PostScript-dokumentumhoz

```csharp
//Kimeneti adatfolyam létrehozása PostScript-dokumentumhoz
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Itt létrehozunk egy kimeneti adatfolyamot a PostScript dokumentumhoz, és megadjuk a fájl nevét ("AddRectangle_outPS.ps"). Módosítsa a fájl nevét és helyét saját igényei szerint.

## 3. lépés: Állítsa be a mentési beállításokat és hozzon létre PS-dokumentumot

```csharp
//Hozzon létre mentési beállításokat A4-es méretben
PsSaveOptions options = new PsSaveOptions();

// Hozzon létre új 1 oldalas PS-dokumentumot
PsDocument document = new PsDocument(outPsStream, options, false);
```

Állítsa be a mentési beállításokat a kívánt oldalméret megadásával (ebben az esetben A4). Ezután hozzon létre egy új egyoldalas PostScript-dokumentumot.

## 4. lépés: Téglalap hozzáadása és kitöltése

```csharp
//Grafikus útvonal létrehozása az első téglalapból
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Állítsa be a festéket
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Töltse ki a téglalapot
document.Fill(path);
```

Itt létrehozunk egy grafikus útvonalat, amely az első téglalapot ábrázolja, beállítjuk a festék színét (jelen esetben narancssárga), és kitöltjük a téglalapot.

## 5. lépés: Adjon hozzá egy másik téglalapot és körvonalat

```csharp
//Hozzon létre grafikus útvonalat a második téglalapból
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Állítsa be a löketet
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//A téglalap körvonalazása (körvonalazása).
document.Draw(path);
```

Az előző lépéshez hasonlóan létrehozunk egy grafikus útvonalat a második téglalaphoz, beállítjuk a körvonal színét (3-as vastagságú piros), és körvonalazzuk a téglalapot.

## 6. lépés: Zárja be az oldalt, és mentse el a dokumentumot

```csharp
//Az aktuális oldal bezárása
document.ClosePage();

//Mentse el a dokumentumot
document.Save();
```

Végül zárja be az aktuális oldalt, és mentse a teljes dokumentumot.

## Következtetés

Gratulálunk! Sikeresen hozzáadott téglalapokat egy PostScript-dokumentumhoz az Aspose.Page for .NET használatával. Ez az oktatóanyag a legfontosabb lépéseket ismertette, a fejlesztői környezet beállításától a végleges dokumentum mentéséig.

## GYIK

### 1. kérdés: Testreszabhatom a téglalapok színeit?

V1: Igen, testreszabhatja a színeket a paraméterek beállításával a`SolidBrush` és`Pen` osztályok.

### 2. kérdés: Az Aspose.Page kompatibilis más dokumentumformátumokkal?

2. válasz: Igen, az Aspose.Page különféle dokumentumformátumokat támogat, beleértve az XPS-t és a PostScript-et.

### 3. kérdés: Hogyan adhatok szöveget a dokumentumhoz?

 A3: Használhatja a`TextFragment` osztályt az Aspose.Page-ben, hogy szöveget adjon a dokumentumhoz.

### 4. kérdés: Hol találhatok további példákat és dokumentációt?

 4. válasz: Fedezze fel a dokumentációt[itt](https://reference.aspose.com/page/net/) és látogassa meg a[Aspose.Page fórum](https://forum.aspose.com/c/page/39) közösségi támogatásért.

### 5. kérdés: Kipróbálhatom az Aspose.Page oldalt vásárlás előtt?

 V5: Igen, beszerezhet egy ingyenes próbaverziót[itt](https://releases.aspose.com/) , és hosszabb használat esetén fontolja meg a[ideiglenes engedély](https://purchase.aspose.com/temporary-license/).
