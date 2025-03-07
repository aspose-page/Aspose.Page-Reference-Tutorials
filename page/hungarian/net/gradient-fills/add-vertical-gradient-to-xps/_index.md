---
title: Adjon hozzá függőleges színátmenetet az XPS-hez az Aspose.Page for .NET segítségével
linktitle: Függőleges színátmenet hozzáadása az XPS-hez
second_title: Aspose.Page .NET API
description: Ismerje meg, hogyan javíthat XPS-dokumentumokat függőleges színátmenetekkel az Aspose.Page for .NET használatával. Kövesse lépésenkénti útmutatónkat a zökkenőmentes integráció érdekében.
weight: 15
url: /hu/net/gradient-fills/add-vertical-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adjon hozzá függőleges színátmenetet az XPS-hez az Aspose.Page for .NET segítségével

## Bevezetés

Üdvözöljük ebben a lépésenkénti oktatóanyagban arról, hogyan adhat hozzá függőleges színátmenetet XPS-dokumentumhoz az Aspose.Page for .NET használatával. Az Aspose.Page egy hatékony API, amely lehetővé teszi, hogy XPS (XML Paper Specification) fájlokkal dolgozzon .NET-alkalmazásaiban. Ebben az oktatóanyagban végigvezetjük az új XPS-dokumentum létrehozásának, az elérési úthoz függőleges színátmenet hozzáadásának és az eredmény mentésének folyamatán.

## Előfeltételek

Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

-  Aspose.Page for .NET Library: Győződjön meg arról, hogy az Aspose.Page for .NET könyvtár telepítve van a fejlesztői környezetében. Letöltheti[itt](https://releases.aspose.com/page/net/).

- Fejlesztési környezet: Állítson be .NET fejlesztői környezetet a kívánt IDE-vel, például a Visual Studio-val.

Most kezdjük el függőleges színátmenet hozzáadásával egy XPS-dokumentumhoz az Aspose.Page for .NET használatával.

## Névterek importálása

A .NET-alkalmazásban adja meg az Aspose.Page osztályok és metódusok eléréséhez szükséges névtereket.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## 1. lépés: Állítsa be a dokumentumkönyvtárat

Mielőtt elkezdené, állítsa be a dokumentumkönyvtár elérési útját, ahová menteni szeretné az eredményül kapott XPS-dokumentumot.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## 2. lépés: Hozzon létre egy új XPS-dokumentumot

Inicializáljon egy új XPS-dokumentumot a következő kóddal:

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## 3. lépés: Határozza meg a gradiens megállókat

Hozzon létre egy listát a gradiens megállókról, megadva az egyes megállók színét és pozícióját. Ebben a példában egy függőleges gradienst definiálunk öt megállóval.

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// Vége:5
```

## 4. lépés: Hozzon létre egy útvonalat a színátmenettel

Határozzon meg egy útvonalat a geometriájának megadásával, és alkalmazzon rá egy lineáris színátmenetes ecsetet.

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## 5. lépés: Mentse el az eredményül kapott XPS-dokumentumot

Mentse el a módosított XPS-dokumentumot a megadott könyvtárba.

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

Gratulálunk! Sikeresen hozzáadott egy függőleges színátmenetet egy XPS-dokumentumhoz az Aspose.Page for .NET használatával.

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk, hogyan használhatjuk fel az Aspose.Page for .NET-et az XPS-dokumentumok függőleges színátmenetekkel történő javítására. Az Aspose.Page leegyszerűsíti az összetett feladatokat, így a fejlesztők zökkenőmentesen kezelhetik az XPS-fájlokat .NET-alkalmazásaikban.

## GYIK

### 1. kérdés: Az Aspose.Page kompatibilis a Visual Studio 2019 programmal?

1. válasz: Igen, az Aspose.Page kompatibilis a Visual Studio 2019 programmal. Győződjön meg arról, hogy a könyvtár megfelelő verziója van telepítve.

### 2. kérdés: Használhatom az Aspose.Page oldalt kereskedelmi projektekhez?

 V2: Igen, az Aspose.Page használható kereskedelmi projektekhez. Látogatás[itt](https://purchase.aspose.com/buy) az engedélyezési lehetőségek feltárására.

### 3. kérdés: Van ingyenes próbaverzió?

 3. válasz: Igen, megkaphatja az Aspose.Page ingyenes próbaverzióját[itt](https://releases.aspose.com/).

### 4. kérdés: Hol találom az Aspose.Page dokumentációját?

 A4: A dokumentáció elérhető[itt](https://reference.aspose.com/page/net/).

### 5. kérdés: Hogyan kaphatok támogatást vagy tehetek fel kérdéseket?

 A5: Látogassa meg a[Aspose.Page fórum](https://forum.aspose.com/c/page/39) közösségi támogatásért.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
