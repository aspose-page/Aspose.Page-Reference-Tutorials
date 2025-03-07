---
title: Adja hozzá a Vízszintes színátmenetet az XPS-hez az Aspose.Page for .NET segítségével
linktitle: Vízszintes színátmenet hozzáadása az XPS-hez
second_title: Aspose.Page .NET API
description: Ismerje meg, hogyan adhat lenyűgöző vízszintes színátmeneteket XPS-dokumentumaihoz az Aspose.Page for .NET használatával. Emelje fel a vizuális vonzerőt könnyedén.
weight: 13
url: /hu/net/gradient-fills/add-horizontal-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adja hozzá a Vízszintes színátmenetet az XPS-hez az Aspose.Page for .NET segítségével

## Bevezetés

Ebben az oktatóanyagban megvizsgáljuk, hogyan javítható az XPS-dokumentumok vízszintes színátmenet hozzáadásával az Aspose.Page for .NET segítségével. Az Aspose.Page for .NET egy hatékony könyvtár, amely az XPS (XML Paper Specification) dokumentumok zökkenőmentes kezelését biztosítja .NET alkalmazásokban. A színátmenetek hozzáadása vizuális vonzerőt kölcsönöz a dokumentumoknak, és ez az útmutató lépésről lépésre végigvezeti a folyamaton.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

1.  Aspose.Page for .NET Library: Győződjön meg arról, hogy az Aspose.Page for .NET könyvtár telepítve van a fejlesztői környezetében. Letöltheti a[Aspose.Page a .NET dokumentációhoz](https://reference.aspose.com/page/net/).

2. Fejlesztési környezet: Állítson be megfelelő fejlesztői környezetet, beleértve egy kódszerkesztőt, például a Visual Studio-t.

## Névterek importálása

Kezdje azzal, hogy importálja a szükséges névtereket a projektbe. Ezek a névterek elengedhetetlenek az Aspose.Page for .NET használatához:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Most bontsuk fel a megadott példát több lépésre.

## 1. lépés: Állítsa be a dokumentumkönyvtár elérési útját

```csharp
// ExStart:3
// A dokumentumok könyvtárának elérési útja.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## 2. lépés: Hozzon létre egy új XPS-dokumentumot

```csharp
// ExStart:4
// Hozzon létre új XPS-dokumentumot
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## 3. lépés: Inicializálja a gradiens megállókat

```csharp
// ExStart:5
// Az XpsGradientStop listájának inicializálása
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// Vége:5
```

## 4. lépés: Hozzon létre egy új útvonalat

```csharp
// ExStart:6
//Hozzon létre új útvonalat a geometria rövidítés formájában történő meghatározásával
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## 5. lépés: Mentse el az eredményül kapott XPS-dokumentumot

```csharp
// ExStart:7
// Mentse az eredményül kapott XPS-dokumentumot
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

Sikeresen hozzáadott egy vízszintes színátmenetet XPS-dokumentumához az Aspose.Page for .NET segítségével.

## Következtetés

Az XPS-dokumentumok színátmenetekkel történő javítása nemcsak vizuális vonzerőt javít, hanem vonzóbb felhasználói élményt is biztosít. Az Aspose.Page for .NET leegyszerűsíti ezt a folyamatot, lehetővé téve, hogy könnyedén érjen el professzionális eredményeket.

## GYIK

### 1. kérdés: Hol találom az Aspose.Page oldalt a .NET dokumentációhoz?

 V1: Megtalálhatja a dokumentációt[itt](https://reference.aspose.com/page/net/).

### 2. kérdés: Hogyan tölthetem le az Aspose.Page-t .NET-hez?

 2. válasz: A könyvtárat letöltheti a[Aspose.Page a .NET letöltési oldalához](https://releases.aspose.com/page/net/).

### 3. kérdés: Hol vásárolhatom meg az Aspose.Page-t .NET-hez?

 3. válasz: Az Aspose.Page .NET számára megvásárolható a következő webhelyről:[vásárlási oldal](https://purchase.aspose.com/buy).

### 4. kérdés: Van ingyenes próbaverzió?

 V4: Igen, ingyenes próbaverziót kaphat a webhelyről[itt](https://releases.aspose.com/).

### 5. kérdés: Hogyan szerezhetek ideiglenes licencet az Aspose.Page .NET-hez?

 5. válasz: Ideiglenes engedélyt szerezhet be[ez a link](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
