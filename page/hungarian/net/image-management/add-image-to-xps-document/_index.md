---
title: Kép hozzáadása XPS-dokumentumhoz az Aspose.Page for .NET segítségével
linktitle: Kép hozzáadása az XPS-dokumentumhoz
second_title: Aspose.Page .NET API
description: Fedezze fel a képek zökkenőmentes integrációját XPS-dokumentumokba az Aspose.Page for .NET segítségével. Kövesse lépésről lépésre útmutatónkat a zökkenőmentes fejlesztés érdekében.
type: docs
weight: 11
url: /hu/net/image-management/add-image-to-xps-document/
---
## Bevezetés

A .NET-fejlesztés világában általános követelmény a képek XPS dokumentumokba való beépítése. Az Aspose.Page for .NET leegyszerűsíti ezt a folyamatot, és hatékony eszközkészletet kínál az XPS-dokumentumok könnyed manipulálásához és javításához. Ez az oktatóanyag végigvezeti Önt a kép XPS-dokumentumhoz való hozzáadásának lépésein az Aspose.Page for .NET használatával.

## Előfeltételek

Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

1.  Aspose.Page for .NET Library: Töltse le és telepítse a könyvtárat innen[Aspose.Page .NET dokumentáció](https://reference.aspose.com/page/net/).

2. Fejlesztői környezet: .NET fejlesztői környezet beállítása, például a Visual Studio.

3. Mintakép: rendelkezzen egy minta képfájllal (pl. "QL_logo_color.tif"), amelyet hozzá szeretne adni az XPS-dokumentumhoz.

## Névterek importálása

Kezdje a szükséges névterek importálásával a .NET-projektbe. Ezek a névterek létfontosságúak az Aspose.Page for .NET szolgáltatásainak használatához.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 1. lépés: Állítsa be a dokumentumkönyvtárat

Kezdje a dokumentumkönyvtár elérési útjának megadásával. Ez a lépés biztosítja, hogy a projekt tudja, hová kell keresni és menteni a fájlokat.

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
// ExEnd:1
```

## 2. lépés: Hozzon létre XPS-dokumentumot

Hozzon létre egy új XPS-dokumentumot az Aspose.Page for .NET használatával.

```csharp
// ExStart:1
XpsDocument doc = new XpsDocument();
// ExEnd:1
```

## 3. lépés: Kép hozzáadása az XPS-dokumentumhoz

Most adjuk hozzá a képet az XPS-dokumentumhoz. Ebben a példában egy „QL_logo_color.tif” nevű mintaképet fogunk használni.

```csharp
// ExStart:1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// ExEnd:1
```

## 4. lépés: Mentse el az eredményül kapott XPS-dokumentumot

Mentse el az XPS-dokumentumot a hozzáadott képpel.

```csharp
// ExStart:1
doc.Save(dataDir + "AddImage_outXPS.xps");
// ExEnd:1
```

Sikeresen hozzáadott egy képet egy XPS-dokumentumhoz az Aspose.Page for .NET használatával!

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk, hogyan használhatjuk ki az Aspose.Page-t .NET-hez a képek zökkenőmentes beépítése érdekében XPS-dokumentumokba. Ez a lépésenkénti útmutató zökkenőmentes integrációs folyamatot biztosít, és javítja a .NET fejlesztési képességeit.

## GYIK

### 1. kérdés: Az Aspose.Page for .NET kompatibilis a legújabb .NET-keretrendszer-verziókkal?

 1. válasz: Az Aspose.Page for .NET úgy lett kialakítva, hogy kompatibilis legyen a .NET keretrendszer verzióinak széles skálájával, beleértve a legújabb kiadásokat is. Utal[dokumentáció](https://reference.aspose.com/page/net/) konkrét részletekért.

### 2. kérdés: Használhatom az Aspose.Page for .NET oldalt Windows és Linux környezetben is?

2. válasz: Igen, az Aspose.Page for .NET platformfüggetlen, így Windows és Linux környezetben is használható.

### 3. kérdés: Vannak-e licencelési lehetőségek az Aspose.Page for .NET számára?

 3. válasz: Igen, felfedezheti a licencelési lehetőségeket, és vásárolhat[itt](https://purchase.aspose.com/buy).

### 4. kérdés: Elérhető ingyenes próbaverzió az Aspose.Page számára .NET-hez?

 4. válasz: Igen, ingyenesen kipróbálhatja az Aspose.Page for .NET oldalt a[ingyenes próbaverzió](https://releases.aspose.com/).

### 5. kérdés: Hol kérhetek segítséget vagy kapcsolatba léphetek az Aspose.Page for .NET közösségével?

 A5: Látogassa meg a[Aspose.Page a .NET fórumhoz](https://forum.aspose.com/c/page/39) kapcsolatba lépni a közösséggel és támogatást kapni.