---
title: Adja hozzá a Circle Ellipse-t az XPS-dokumentumhoz az Aspose.Page segítségével .NET-hez
linktitle: Adja hozzá a Circle Ellipse-t az XPS-dokumentumhoz
second_title: Aspose.Page .NET API
description: Növelje az XPS-dokumentumokat élénk sugárirányú színátmenetekkel az Aspose.Page for .NET segítségével. Kövesse lépésről lépésre szóló útmutatónkat a lenyűgöző vizuális effektusokért.
type: docs
weight: 11
url: /hu/net/drawing-shapes/add-circle-ellipse-to-xps-document/
---
## Bevezetés

A vizuálisan tetszetős XPS dokumentumok létrehozása gyakori követelmény a különböző alkalmazásokban. Az Aspose.Page for .NET hatékony szolgáltatáskészletet kínál az XPS-dokumentumok hatékony kezeléséhez. Ebben az oktatóanyagban egy kör ellipszis hozzáadására összpontosítunk egy XPS-dokumentumhoz az Aspose.Page for .NET használatával. Kövesse az alábbi lépéseket, hogy XPS-dokumentumait élénk sugárirányú színátmenetekkel javítsa.

## Előfeltételek

Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételeket teljesítette:

-  Az Aspose.Page telepítve a .NET könyvtárhoz. Letöltheti innen[itt](https://releases.aspose.com/page/net/).
- Fejlesztői környezet, lehetőleg Visual Studio vagy bármilyen más .NET fejlesztőeszköz.
- C# programozási alapismeretek.

## Névterek importálása

A kezdéshez adja meg a szükséges névtereket a C# kódban:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Most bontsuk fel a példát több lépésre:

## 1. lépés: Állítsa be a dokumentumot

```csharp
// ExStart:1
// A dokumentumok könyvtárának elérési útja.
string dataDir = "Your Document Directory";
// Hozzon létre új XPS-dokumentumot
XpsDocument doc = new XpsDocument();
```

Itt inicializálunk egy új XPS-dokumentumot az Aspose.Page for .NET használatával.

## 2. lépés: Határozza meg a Radial Gradient Ellipse

```csharp
// Radiális gradiens simított ellipszis a bal alsó sarokban
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 0, 255), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), .25f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 255, 0), .5f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 255, 0), .75f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), 1f));

XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250"));
```

Ez a lépés magában foglalja egy radiális gradiens ellipszis meghatározását különböző színmegállókkal.

## 3. lépés: Állítsa be a Radial Gradient Brush ecsetet

```csharp
path.Stroke = doc.CreateRadialGradientBrush(new PointF(575f, 125f), new PointF(575f, 100f), 75f, 50f);
((XpsGradientBrush)path.Stroke).SpreadMethod = XpsSpreadMethod.Reflect;
((XpsGradientBrush)path.Stroke).GradientStops.AddRange(stops);
stops.Clear();
```

Itt az ellipszis löketét sugárirányú gradiens ecsettel állítjuk be, biztosítva a szükséges paramétereket.

## 4. lépés: Állítsa be a löketvastagságot

```csharp
path.StrokeThickness = 12f;
```

Ez a lépés magában foglalja az ütés vastagságának beállítását a jobb megjelenítés érdekében.

## 5. lépés: Mentse el az eredményül kapott XPS-dokumentumot

```csharp
// Mentse az eredményül kapott XPS-dokumentumot
doc.Save(dataDir + "AddEllipse_outXPS.xps");
// ExEnd:1
```

Végül mentse el a módosított XPS dokumentumot a kívánt helyre.

## Következtetés

Gratulálunk! Sikeresen hozzáadott egy sugárirányú színátmenetekkel rendelkező körellipszist az XPS-dokumentumhoz az Aspose.Page for .NET használatával. Kísérletezzen különböző paraméterekkel és színekkel, hogy elérje a kívánt vizuális effektusokat a dokumentumokban.

## GYIK

### 1. kérdés: Használhatom az Aspose.Page for .NET oldalt más dokumentumformátumokkal?

1. válasz: A .NET-hez készült Aspose.Page kifejezetten az XPS-dokumentumkezeléssel foglalkozik. Más formátumok esetén fontolja meg a kapcsolódó Aspose-könyvtárak használatát.

### 2. kérdés: Rendelkezésre áll ideiglenes licenc tesztelési célokra?

 2. válasz: Igen, ideiglenes engedélyt szerezhet a teszteléshez, ha ellátogat[ez a link](https://purchase.aspose.com/temporary-license/).

### 3. kérdés: Hol találhatok további segítséget és beszélgetéseket?

 A3: Látogassa meg a[Aspose.Page fórum](https://forum.aspose.com/c/page/39) közösségi támogatásra és beszélgetésekre.

### 4. kérdés: Rendelkezésre állnak-e referenciaként szolgáló mintadokumentumok?

 A4: Fedezze fel a[dokumentáció](https://reference.aspose.com/page/net/) átfogó példákért és útmutatókért.

### 5. kérdés: Megvásárolhatom az Aspose.Page oldalt .NET-hez?

 V5: Igen, megvásárolhatja a könyvtárat[itt](https://purchase.aspose.com/buy).