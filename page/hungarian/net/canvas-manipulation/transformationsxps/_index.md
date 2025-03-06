---
title: Transzformációk XPS Aspose.Page .NET-hez
linktitle: Transzformációk XPS
second_title: Aspose.Page .NET API
description: A .NET-hez készült Aspose.Page segítségével könnyedén alakíthat át XPS-dokumentumokat. Kövesse lépésről lépésre útmutatónkat a zökkenőmentes átalakításokhoz.
weight: 13
url: /hu/net/canvas-manipulation/transformationsxps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Transzformációk XPS Aspose.Page .NET-hez

## Bevezetés

Üdvözöljük az Aspose.Page for .NET világában. Ez egy hatékony könyvtár, amely lehetővé teszi az XPS-dokumentumok különféle átalakításainak könnyed végrehajtását. Ebben az oktatóanyagban az XPS-dokumentumok Aspose.Page for .NET használatával történő átalakításának folyamatát mutatjuk be. Akár tapasztalt fejlesztő, akár csak kezdő, ez az útmutató végigvezeti Önt az egyes lépéseken, és biztosítja, hogy könnyen megértse a fogalmakat.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következők vannak a helyükön:

-  Aspose.Page for .NET Library: Töltse le és telepítse a könyvtárat innen[Aspose.Page a .NET dokumentációhoz](https://reference.aspose.com/page/net/).

- Fejlesztői környezet: Állítson be egy kompatibilis fejlesztői környezetet, például a Visual Studio-t vagy bármely más .NET fejlesztői eszközt.

- Saját dokumentumkönyvtár: Cserélje ki a kód helyőrzőjét a dokumentumkönyvtár tényleges elérési útjával.

Most pedig ugorjunk bele az oktatóanyagba!

## Névterek importálása

Először is győződjön meg arról, hogy importálja a szükséges névtereket, hogy elérhetővé tegye az Aspose.Page for .NET funkcióit a kódban. Adja hozzá a következő névtereket a szkript elejéhez:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 1. lépés: Hozzon létre egy új XPS-dokumentumot

```csharp
// ExStart:1
// A dokumentumok könyvtárának elérési útja.
string dataDir = "Your Document Directory";

// Hozzon létre új XPS-dokumentumot
XpsDocument doc = new XpsDocument();
```

## 2. lépés: Hozzon létre egy fő vásznat

```csharp
// Hozzon létre fő vásznat, amely minden oldalelemhez közös
XpsCanvas canvas1 = doc.AddCanvas();

// Készítsen bal és felső eltolásokat a fő vásznon
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## 3. lépés: Hozzon létre egy téglalap görbe geometriát

```csharp
// Hozzon létre téglalap görbe geometriát
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

## 4. lépés: Adjon hozzá egy kitöltést a téglalapokhoz

```csharp
// Hozzon létre egy kitöltést a téglalapokhoz
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## 5. lépés: Új vászon hozzáadása átalakítások nélkül

```csharp
// Adjon hozzá új vásznat átalakítások nélkül a fő vászonhoz
XpsCanvas canvas2 = canvas1.AddCanvas();

// Hozzon létre téglalapot ezen a vászonon, és töltse ki
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## 6. lépés: Adjon hozzá egy új vásznat a Fordítási transzformációval

```csharp
// Adjon hozzá új vásznat fordítási transzformációval a fő vászonhoz
XpsCanvas canvas3 = canvas1.AddCanvas();

// Fordítsa le ezt a vásznat, hogy egy új téglalapot helyezzen el az előző téglalap alá
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Fordítsa le ezt a vásznat az oldal jobb oldalára
canvas3.RenderTransform.Translate(500, 0);

// Hozzon létre téglalapot ezen a vászonon, és töltse ki
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

## 7. lépés: Új vászon hozzáadása kettős léptékű transzformációval

```csharp
//Adjon hozzá új vásznat kettős léptékű átalakítással a fő vászonhoz
XpsCanvas canvas4 = canvas1.AddCanvas();

// Fordítsa le ezt a vásznat, hogy egy új téglalapot helyezzen el az előző téglalap alá
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Méretezze ezt a vásznat
canvas4.RenderTransform.Scale(2, 2);

// Hozzon létre téglalapot ezen a vászonon, és töltse ki
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

## 8. lépés: Új vászon hozzáadása pont körüli elforgatással

```csharp
// Új vászon hozzáadása ponttranszformáció körüli elforgatással a fő vászonhoz
XpsCanvas canvas5 = canvas1.AddCanvas();

// Fordítsa le ezt a vásznat, hogy egy új téglalapot helyezzen el az előző téglalap alá
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Forgassa el ezt a vásznat egy pont körül 45 fokkal
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Hozzon létre téglalapot ezen a vászonon, és töltse ki
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

## 9. lépés: Mentse el az eredményül kapott XPS-dokumentumot

```csharp
// Mentse az eredményül kapott XPS-dokumentumot
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

## Következtetés

Gratulálunk! Sikeresen átalakított egy XPS-dokumentumot az Aspose.Page for .NET használatával. Ez az útmutató az alapvető lépéseket ismertette, az előfeltételek felállításától a különféle átalakítások végrehajtásáig. Kísérletezzen ezekkel a technikákkal, és aknázza ki az Aspose.Page for .NET teljes potenciálját projektjeiben.

## GYIK

### 1. kérdés: Az Aspose.Page for .NET kompatibilis az összes .NET fejlesztői környezettel?

1. válasz: Igen, az Aspose.Page for .NET úgy lett kialakítva, hogy zökkenőmentesen működjön különböző .NET fejlesztői környezetekkel, köztük a Visual Studio-val.

### 2. kérdés: Hol találhatok további példákat és dokumentációt az Aspose.Page for .NET-hez?

 A2: Látogassa meg a[Aspose.Page a .NET dokumentációhoz](https://reference.aspose.com/page/net/) átfogó dokumentációért és példákért.

### 3. kérdés: Kipróbálhatom az Aspose.Page-t .NET-hez a vásárlás előtt?

 3. válasz: Igen, felfedezheti az ingyenes próbaverziót, ha felkeresi[Aspose.Page ingyenes próbaverzió](https://releases.aspose.com/).

### 4. kérdés: Hogyan szerezhetek ideiglenes licencet az Aspose.Page for .NET számára?

 4. válasz: Szerezzen ideiglenes engedélyt a webhely meglátogatásával[Ideiglenes jogosítvány](https://purchase.aspose.com/temporary-license/).

### 5. kérdés: Hol vásárolhatom meg az Aspose.Page-t .NET-hez?

 5. válasz: Vásárolja meg az Aspose.Page oldalt .NET-hez itt:[Aspose.Page Buy](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
