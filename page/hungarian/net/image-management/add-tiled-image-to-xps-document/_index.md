---
date: 2026-03-03
description: Tanulja meg, hogyan használja az Aspose.Page for .NET-et képek csempézésére
  XPS-dokumentumokban. Ez a lépésről‑lépésre útmutató bemutatja, hogyan csempézze
  a képeket hatékonyan és növelje a vizuális vonzerőt.
linktitle: Add Tiled Image to XPS Document
second_title: Aspose.Page .NET API
title: Hogyan használjuk az Aspose.Page-t csempézett kép hozzáadásához XPS-dokumentumba
url: /hu/net/image-management/add-tiled-image-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan használjuk az Aspose.Page-et csempézett kép hozzáadásához XPS dokumentumhoz

## Introduction

Ha kíváncsi vagy **hogyan használjuk az Aspose**-t, hogy XPS fájljaid gazdagabb vizuális stílust kapjanak, jó helyen jársz. Ebben az útmutatóban lépésről lépésre bemutatjuk, hogyan **csempézhetünk egy képet** egy XPS dokumentumban az Aspose.Page for .NET segítségével. A végére egy újrahasználható kódrészletet kapsz, amelyet bármely .NET projektbe beilleszthetsz, hogy valós időben csempézett képgrafikát hozz létre.

## Quick Answers
- **Milyen könyvtár szükséges?** Aspose.Page for .NET  
- **Melyik metódus hozza létre a csempézett ecsetet?** `CreateImageBrush` with `TileMode = XpsTileMode.Tile`  
- **Kezelhetem az átlátszatlanságot?** Yes – set `path.Fill.Opacity` (e.g., 0.5f)  
- **Szükség van licencre a teszteléshez?** A temporary license works for evaluation; a full license is required for production.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## What is Aspose.Page and Why Tile Images?

Az Aspose.Page egy erőteljes API, amely lehetővé teszi a fejlesztők számára, hogy XPS, PDF és egyéb oldal‑alapú formátumokat generáljanak, szerkesszenek és rendereljenek a Microsoft Office használata nélkül. Egy kép csempézése — egy bitmap ismétlése egy alakzaton belül — segít nagy területeket kitölteni mintákkal, vízjelekkel vagy háttértextúrákkal, miközben alacsony fájlméretet tart meg.

## How to Use Aspose.Page to Tile Images in XPS Documents

Az alábbiakban egy teljes, azonnal futtatható példát találsz. Minden lépést egyszerű nyelven magyarázunk el a megfelelő kódrészlet előtt, hogy lásd, **miért** fontos az egyes sorok.

### Prerequisites

- **Aspose.Page for .NET** – download and reference the library from the official site [here](https://reference.aspose.com/page/net/).  
- **Development environment** – Visual Studio (any edition) or another .NET IDE you prefer.

### Import Namespaces

Először hozd be a szükséges névtereket, hogy a fordító tudja, hol találja az XPS osztályokat.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

### Step 1: Define the Document Directory

Add meg, hogy hol legyen a generált XPS fájl és a forráskép. Cseréld ki a helyőrzőt egy valós mappára a gépeden.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Step 2: Create a New XPS Document

Hozz létre egy üres XPS dokumentumot, amely a csempézett grafikát fogja tartalmazni.

```csharp
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Step 3: Add a Tiled Image

Itt egy téglalap alakú útvonalat hozunk létre, kitöltjük egy `ImageBrush`‑szel, és beállítjuk az ecsetet csempézési módra. A `TileMode` tulajdonság azt mondja a motornak, hogy a képet vízszintesen és függőlegesen is ismételje. Szükség szerint módosítsd a téglalap koordinátáit vagy a forrásképet.

```csharp
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

### Step 4: Save the Resultant XPS Document

Végül írd a dokumentumot a lemezre. A kimeneti fájl bármely XPS megjelenítővel megnyitható, vagy tovább feldolgozható az Aspose.Page segítségével.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

## Common Issues & Tips

- **Útvonal hibák** – Győződj meg róla, hogy a `dataDir` végén van egy perjel, vagy használd a `Path.Combine`‑t a hiányzó elválasztó elkerüléséhez.  
- **Kép méret eltérések** – A forrásképet elég nagyra kell választani a csempézés területéhez; ellenkező esetben a minta nyúltnak tűnhet.  
- **Átlátszatlanság nem látható** – Egyes megjelenítők figyelmen kívül hagyják az átlátszatlanságot XPS-ben; tesztelj egy olyan megjelenítővel, amely teljesen támogatja az XPS renderelést (pl. XPS Viewer Windows-on).

## Frequently Asked Questions

### Q1: Az Aspose.Page kompatibilis minden .NET fejlesztői környezettel?
A: Igen, az Aspose.Page működik Visual Studio, Rider, VS Code és bármely .NET‑t támogató IDE‑val.

### Q2: Módosíthatom a csempézett kép átlátszatlanságát?
A: Természetesen. A példa beállítja a `path.Fill.Opacity = 0.5f;` értéket – a lebegőpontos értéket 0 (átlátszó) és 1 (átlátszatlan) között változtathatod.

### Q3: Vannak más csempézési módok az Aspose.Page for .NET‑ben?
A: Igen. A `XpsTileMode.Tile` mellett használhatod a `FlipX`, `FlipY` és `FlipXY` módokat is tükrözött minták létrehozásához.

### Q4: Hogyan kezeljem az Aspose.Page ideiglenes licenceit?
A: Lásd a [temporary license](https://purchase.aspose.com/temporary-license/) oldalt az Aspose weboldalán a próbaverzió licenc beszerzésének és alkalmazásának részleteiért.

### Q5: Hol kérhetek segítséget vagy csatlakozhatok az Aspose.Page közösséghez?
A: Látogasd meg az [Aspose.Page fórumot](https://forum.aspose.com/c/page/39), ahol kérdéseket tehetsz fel, kódrészleteket oszthatsz meg, és tanulhatsz más fejlesztőktől.

### Q6: Alkalmazhatom ezt a módszert vízjel hatás létrehozására?
A: Igen. Az átlátszatlanság csökkentésével és egy félig átlátszó kép kiválasztásával a csempézett ecset tökéletesen működik ismétlődő vízjelként.

## Conclusion

Most már tudod, **hogyan használjuk az Aspose**-t csempézett kép hozzáadásához egy XPS dokumentumhoz, az átlátszatlanság szabályozásához, és az eredmény mentéséhez további felhasználásra. Ez a technika ideális háttérmintákhoz, vízjelekhez vagy bármilyen helyzethez, ahol egy ismétlődő grafika vizuális érdeklődést ad anélkül, hogy megnövelné a fájlméretet. Nyugodtan kísérletezz különböző alakzatokkal, képekkel és csempézési módokkal, hogy a projekt igényeinek megfeleljen.

**Last Updated:** 2026-03-03  
**Tested With:** Aspose.Page for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}