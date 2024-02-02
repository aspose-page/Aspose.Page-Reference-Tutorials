---
title: Adjon csempézett képet az XPS-dokumentumhoz az Aspose.Page for .NET segítségével
linktitle: Adjon hozzá csempézett képet az XPS-dokumentumhoz
second_title: Aspose.Page .NET API
description: Fedezze fel a csempézett képek egyszerű hozzáadását XPS-dokumentumokhoz az Aspose.Page for .NET segítségével. Növelje a vizuális vonzerőt, és készítsen lenyűgöző dokumentumokat.
type: docs
weight: 12
url: /hu/net/image-management/add-tiled-image-to-xps-document/
---
## Bevezetés

Szeretné javítani XPS-dokumentumait tetszetős csempézett képek hozzáadásával? Az Aspose.Page for .NET lehetővé teszi a fejlesztők számára, hogy ezt zökkenőmentesen elérjék. Ebben a lépésenkénti útmutatóban végigvezetjük a mozaikkép XPS-dokumentumhoz való hozzáadásának folyamatán az Aspose.Page for .NET használatával.

## Előfeltételek

Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételeket teljesítette:

-  Aspose.Page .NET-hez: Győződjön meg arról, hogy telepítve van az Aspose.Page könyvtár. Megtalálhatja a részletes dokumentációt és letöltheti a könyvtárat[itt](https://reference.aspose.com/page/net/).
- Fejlesztési környezet: Állítsa be a kívánt .NET fejlesztői környezetet, például a Visual Studio-t.

## Névterek importálása

Kezdésként importálja a szükséges névtereket a projektbe. Ez biztosítja, hogy hozzáférjen az Aspose.Page használatához szükséges osztályokhoz és metódusokhoz. Adja hozzá a következő névtereket a kód elejéhez:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Most bontsuk fel a példát több lépésre.

## 1. lépés: Határozza meg a dokumentumkönyvtárat

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "Your Document Directory";
```

Győződjön meg arról, hogy a „Dokumentumkönyvtár” kifejezést a tényleges elérési útra cseréli, ahová az XPS-dokumentumot menteni kívánja.

## 2. lépés: Hozzon létre egy új XPS-dokumentumot

```csharp
// Hozzon létre új XPS-dokumentumot
XpsDocument doc = new XpsDocument();
```

 Példányosítson egy új XPS-dokumentumot a`XpsDocument` osztály.

## 3. lépés: Adjon hozzá egy csempézett képet

```csharp
// Csempe kép
// ImageBrush kitöltött téglalap a jobb felső sarokban lent
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

Ez a lépés egy csempézett képet ad hozzá az XPS-dokumentumhoz. Állítsa be a koordinátákat és a képfájl elérési útját igényei szerint.

## 4. lépés: Mentse el az eredményül kapott XPS-dokumentumot

```csharp
// Mentse az eredményül kapott XPS-dokumentumot
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

Mentse el a módosított XPS-dokumentumot a megadott könyvtárba.

## Következtetés

Gratulálunk! Sikeresen megtanulta, hogyan adhat hozzá csempézett képet XPS-dokumentumhoz az Aspose.Page for .NET használatával. Ez az egyszerű, de hatékony funkció lehetővé teszi, hogy könnyedén fokozza dokumentumai vizuális vonzerejét.

## GYIK

### 1. kérdés: Az Aspose.Page kompatibilis az összes .NET fejlesztői környezettel?

1. válasz: Igen, az Aspose.Page úgy lett kialakítva, hogy zökkenőmentesen működjön együtt különböző .NET fejlesztői környezetekkel, beleértve a Visual Studiót is.

### 2. kérdés: Beállíthatom a csempézett kép átlátszatlanságát?

2. válasz: Természetesen, ahogy a példában is látható, beállíthatja a kitöltött téglalap átlátszatlanságát a`Opacity` ingatlan.

### 3. kérdés: Rendelkezésre állnak más csempemódok az Aspose.Page-ben .NET-hez?

 3. válasz: Igen, az Aspose.Page különböző csempe módokat biztosít. Ebben az oktatóanyagban használtuk`XpsTileMode.Tile`, de más lehetőségeket is felfedezhet a dokumentációban.

### 4. kérdés: Hogyan kezelhetem az Aspose.Page ideiglenes licenceit?

 A4: Lásd a[ideiglenes engedély](https://purchase.aspose.com/temporary-license/) oldal az Aspose webhelyen, ahol útmutatást talál az ideiglenes licencek megszerzéséhez és megvalósításához.

### 5. kérdés: Hol kérhetek segítséget, vagy csatlakozhatok az Aspose.Page közösséghez?

 A5: Látogassa meg a[Aspose.Page fórum](https://forum.aspose.com/c/page/39) kapcsolatba lépni a közösséggel, kérdéseket feltenni és megoldásokat találni.