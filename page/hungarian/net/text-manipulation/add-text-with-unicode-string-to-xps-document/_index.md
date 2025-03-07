---
title: Szöveg hozzáadása Unicode karakterlánccal az XPS-dokumentumhoz az Aspose.Page segítségével
linktitle: Szöveg hozzáadása Unicode karakterlánccal az XPS-dokumentumhoz
second_title: Aspose.Page .NET API
description: Fedezze fel az Aspose.Page .NET-hez nyújtotta lehetőségeket lépésenkénti útmutatónkkal az XPS-dokumentumok Unicode-szöveg hozzáadásához.
weight: 12
url: /hu/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Szöveg hozzáadása Unicode karakterlánccal az XPS-dokumentumhoz az Aspose.Page segítségével

## Bevezetés

A .NET-fejlesztés folyamatosan változó környezetében az Aspose.Page az XPS-dokumentumok kezelésének hatékony eszközeként tűnik ki. Számos funkciója közül értékes az a képesség, hogy egy XPS-dokumentumhoz Unicode-karakterláncokkal szöveget adjunk hozzá. Ez a lépésenkénti útmutató végigvezeti Önt a folyamaton, és biztosítja, hogy hatékonyan kihasználja ezt a képességet.

## Előfeltételek

Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételeket teljesítette:

- A .NET fejlesztés alapvető ismerete.
- A Visual Studio telepítve van a gépedre.
-  Aspose.Page a .NET könyvtárhoz. Letöltheti innen[itt](https://releases.aspose.com/page/net/).

## Névterek importálása

Kezdésként győződjön meg róla, hogy importálja a szükséges névtereket a projektbe. Ez biztosítja az Aspose.Page használatához szükséges osztályokat és funkciókat. Íme a lényeges névterek:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 1. lépés: Állítsa be a dokumentumot

Először is hozzon létre egy új XPS-dokumentumot, amelybe hozzá kell adni a Unicode szöveget. Kövesse az alábbi kódrészletet:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "Your Document Directory";
// Hozzon létre új XPS-dokumentumot
XpsDocument doc = new XpsDocument();
```

## 2. lépés: Unicode szöveg hozzáadása

Most adjunk Unicode szöveget az XPS-dokumentumhoz. Ez a példa az Arial betűtípust használja, a betűméretet 20-ra állítja, és a szöveget koordinátákra (400f, 200f) helyezi el. A Unicode karakterlánc ebben az esetben a "TEN. rof SPX.esopsA". Tekintse meg az alábbi kódrészletet:

```csharp
// Szöveg hozzáadása
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## 3. lépés: Mentse el a dokumentumot

A Unicode szöveg hozzáadása után mentse el az eredményül kapott XPS-dokumentumot. Íme az utolsó lépés:

```csharp
// Mentse az eredményül kapott XPS-dokumentumot
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Gratulálunk! Sikeresen hozzáadta a Unicode szöveget egy XPS-dokumentumhoz az Aspose.Page for .NET használatával.

## Következtetés

Ebben az oktatóanyagban az Aspose.Page for .NET segítségével Unicode-szöveg XPS-dokumentumokhoz való hozzáadásának folyamatát vizsgáltuk. Ez a funkció lehetővé teszi a változatos és dinamikus dokumentumok létrehozását a .NET környezetben.

## GYIK

### 1. kérdés: Az Aspose.Page kompatibilis a legújabb .NET keretrendszerekkel?

1. válasz: Igen, az Aspose.Page rendszeresen frissül a legújabb .NET keretrendszerekkel való kompatibilitás biztosítása érdekében.

### 2. kérdés: Testreszabhatom a betűtípus stílusát és méretét szöveg hozzáadásakor?

A2: Abszolút! A mellékelt példakód lehetővé teszi a betűstílus, -méret és egyéb attribútumok egyszerű testreszabását.

### 3. kérdés: Hol találhatok további dokumentációt az Aspose.Page-hez?

 V3: Olvassa el a dokumentációt[itt](https://reference.aspose.com/page/net/) átfogó információkért és példákért.

### 4. kérdés: Vannak ingyenes források az Aspose.Page használatához?

 A4: Igen, felfedezheti a[Aspose.Page fórum](https://forum.aspose.com/c/page/39) közösségi támogatásra és beszélgetésekre.

### 5. kérdés: Rendelkezésre áll-e próbaverzió a vásárlás előtt?

 A5: Természetesen! Hozzáférhet az ingyenes próbaverzióhoz[itt](https://releases.aspose.com/) vásárlás előtt.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
