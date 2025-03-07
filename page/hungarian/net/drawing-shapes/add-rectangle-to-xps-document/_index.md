---
title: Téglalap hozzáadása XPS-dokumentumhoz az Aspose.Page for .NET segítségével
linktitle: Téglalap hozzáadása az XPS-dokumentumhoz
second_title: Aspose.Page .NET API
description: Fokozza a dokumentumok létrehozását az Aspose.Page for .NET segítségével. Ebből a lépésenkénti oktatóanyagból megtudhatja, hogyan adhat téglalapokat XPS-dokumentumokhoz.
weight: 13
url: /hu/net/drawing-shapes/add-rectangle-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Téglalap hozzáadása XPS-dokumentumhoz az Aspose.Page for .NET segítségével

## Bevezetés

Az Aspose.Page for .NET egy hatékony könyvtár, amely számos szolgáltatást biztosít az XPS (XML Paper Specification) dokumentumokkal való munkavégzéshez .NET alkalmazásokban. Ebben az oktatóanyagban egy téglalap hozzáadására összpontosítunk egy XPS-dokumentumhoz az Aspose.Page for .NET használatával. Kövesse ezt a lépésről lépésre útmutatót a dokumentumkészítési folyamat javításához.

## Előfeltételek

Mielőtt elkezdené ezt az oktatóanyagot, győződjön meg arról, hogy a következő előfeltételeket teljesítette:

1.  Aspose.Page for .NET Library: Győződjön meg arról, hogy az Aspose.Page for .NET könyvtár telepítve van a fejlesztői környezetében. Letöltheti[itt](https://releases.aspose.com/page/net/).

2. Dokumentumkönyvtár: Állítson be egy könyvtárat, ahol tárolni kívánja XPS-dokumentumait.

## Névterek importálása

A .NET-alkalmazásban adja meg az Aspose.Page funkciók használatához szükséges névtereket.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 1. lépés: Állítsa be a dokumentumkönyvtárat

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

## 3. lépés: Adjon hozzá egy téglalapot

```csharp
// ExStart:5
// CMYK (kék) egyszínű, körvonalazott téglalap a bal alsó sarokban
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// Vége:5
```

## 4. lépés: Mentse el a dokumentumot

```csharp
// ExStart:6
// Mentse az eredményül kapott XPS-dokumentumot
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Gratulálunk! Sikeresen hozzáadott egy téglalapot egy XPS-dokumentumhoz az Aspose.Page for .NET használatával.

## Következtetés

Az Aspose.Page for .NET leegyszerűsíti a dokumentumkezelési feladatokat, így a fejlesztők könnyedén hozhatnak létre és módosíthatnak XPS-dokumentumokat. Ez a lépésenkénti útmutató bemutatja, hogyan adjon téglalapot XPS-dokumentumához, amely szilárd alapot biztosít a további felfedezéshez.

## GYIK

### 1. kérdés: Az Aspose.Page kompatibilis az összes .NET alkalmazással?

1. válasz: Igen, az Aspose.Page úgy lett kialakítva, hogy zökkenőmentesen működjön minden .NET-alkalmazással.

### 2. kérdés: Hol találom az Aspose.Page for .NET dokumentációját?

 V2: A dokumentáció elérhető[itt](https://reference.aspose.com/page/net/).

### 3. kérdés: Kipróbálhatom ingyenesen az Aspose.Page for .NET-et a vásárlás előtt?

 V3: Igen, ingyenes próbaverziót kaphat[itt](https://releases.aspose.com/).

### 4. kérdés: Hogyan szerezhetek ideiglenes licencet az Aspose.Page for .NET számára?

 A4: Látogassa meg[ez a link](https://purchase.aspose.com/temporary-license/) ideiglenes engedély megszerzéséhez.

### 5. kérdés: Hol kérhetek közösségi támogatást, vagy hol tehetek fel kérdéseket az Aspose.Page for .NET-hez kapcsolódóan?

 A5: Látogassa meg a[Aspose.Page fórum](https://forum.aspose.com/c/page/39) közösségi támogatásért.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
