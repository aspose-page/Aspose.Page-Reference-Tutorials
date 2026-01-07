---
date: 2026-01-07
description: Tanulja meg, hogyan hozhat létre XPS dokumentumot .NET‑ben az Aspose.Page
  használatával. Ez az útmutató bemutatja a képpel kitöltött glifek és idegen képek
  hozzáadását a gazdagabb dokumentumvizualizáció érdekében.
linktitle: Add Image Filled Glyph & Foreign Image
second_title: Aspose.Page .NET API
title: XPS dokumentum létrehozása .NET‑ben az Aspose.Page segítségével – Képpel kitöltött
  glif és külső kép
url: /hu/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS dokumentum létrehozása .NET-ben az Aspose.Page segítségével – Képpel kitöltött glif & külső kép

## Bevezetés

Ha **create XPS document .NET** alkalmazásokat szeretne létrehozni, amelyek kifinomultak és professzionálisak, az Aspose.Page olyan eszközöket biztosít, amelyekkel közvetlenül a glifekbe ágyazhat képeket, és újra felhasználhat grafikus erőforrásokat a dokumentumok között. Ebben az útmutatóban végigvezetjük a két XPS fájl létrehozását, a glifek képpel kitöltését egy image brush-szal, majd ennek a brush-nek a második dokumentumban való újrahasználatát. A végére megérti, miért takarít meg ez a megközelítés memóriát, egyszerűsíti a stíluskezelést, és kreatív lehetőségeket nyit meg jelentések, számlák vagy bármilyen nyomtatható tartalom számára.

## Gyors válaszok
- **Miről szól ez az útmutató?** Képpel kitöltött glifek hozzáadása és azok XPS dokumentumok között való újrahasználata az Aspose.Page for .NET segítségével.  
- **Melyik elsődleges kulcsszót célozza meg?** `create xps document .net`.  
- **Előfeltételek?** .NET fejlesztői környezet, Aspose.Page for .NET, és egy mappa az XPS fájljaihoz.  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 10‑15 perc egy működő prototípushoz.  
- **Használhatok más képtípusokat?** Igen – bármely, a .NET `System.Drawing.Image` által támogatott formátum.

## Előfeltételek

Mielőtt belemerülne a kódba, győződjön meg róla, hogy a következők készen állnak:

- **Aspose.Page for .NET** – töltse le a legújabb könyvtárat [innen](https://releases.aspose.com/page/net/).  
- **Fejlesztői környezet** – Visual Studio 2022 (vagy bármely IDE, amely támogatja a .NET 6+ verziót).  
- **Dokumentum könyvtár** – hozzon létre egy mappát a gépén, amely a bemeneti képeket és a generált XPS fájlokat tartalmazza; a példákban **Your Document Directory**-ként hivatkozunk rá.

## Névterek importálása

Kezdje el a XPS objektumokkal és a rajzolási segédeszközökkel dolgozáshoz szükséges névterek betöltésével.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Lépésről‑lépésre útmutató

### 1. lépés: Az első XPS dokumentum létrehozása

Először egy üres XPS dokumentumot hozunk létre, amely a képpel kitöltött glifet fogja tartalmazni.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

### 2. lépés: Glifek hozzáadása az első dokumentumhoz

Ezután adjon hozzá egy glifet (egy szöveges karaktert), amelyet később egy image brush-szal töltünk ki.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### 3. lépés: Glifek kitöltése image brush-szal

Itt egy `ImageBrush`-t hozunk létre egy adatkönyvtárunkban található TIFF fájlból, és alkalmazzuk a glifre. A brush tile módra van állítva, így a kép ismétlődik, ha a glif területe meghaladja a kép méretét.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

### 4. lépés: A második XPS dokumentum létrehozása

Most egy második XPS dokumentumot hozunk létre, amely újra felhasználja az első dokumentumból származó glif stílust és image brush-t.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

### 5. lépés: Glifek hozzáadása az első dokumentumból származó betűtípussal

A második dokumentumhoz glifet adunk hozzá, az első dokumentumból származó pontos betűtípus objektumot újra felhasználva. Ez biztosítja a vizuális konzisztenciát mindkét fájlban.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

### 6. lépés: Image brush létrehozása az első dokumentum kitöltéséből

A kép újbóli betöltése helyett a `glyphs1` brush-át klónozzuk, és a `glyphs2`-nek rendeljük. Ez bemutatja, hogyan hozhat létre **create XPS document .NET** munkafolyamatokat, amelyek hatékonyan osztják meg az erőforrásokat.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

### 7. lépés: Dokumentumok mentése

Végül mentse mindkét XPS fájlt a lemezre. Most már bármely XPS megjelenítővel megnyithatja őket, hogy lássa a képpel kitöltött glif hatást.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Miért használjon képpel kitöltött glifeket, amikor XPS dokumentumot hoz létre .NET-ben?

- **Vizualis hatás** – Alakítsa át az egyszerű szöveget grafikus elemekkel gazdag tartalommá, anélkül, hogy a teljes oldalt raszterizálná.  
- **Erőforrás újrafelhasználás** – Ossza meg a brush-eket és betűtípusokat több dokumentum között, csökkentve a memóriahasználatot.  
- **Rugalmasság** – Tile, stretch vagy rotate (csempézés, nyújtás vagy forgatás) az image brush-t, hogy egyedi mintákat vagy márkázást érjen el.

## Gyakori problémák és tippek

- **Fájlútvonal hibák** – Győződjön meg róla, hogy a `dataDir` egy útvonal-elválasztóval (`\` vagy `/`) végződik, amely megfelel az operációs rendszerének.  
- **Nem támogatott képtípusok** – Az Aspose.Page legjobban a TIFF, PNG és JPEG formátumokkal működik. Más formátumok használata előtt konvertálja őket.  
- **TileMode nem alkalmazott** – Ellenőrizze, hogy a `TileMode` beállítása előtt `XpsImageBrush`-ra cast-olja; ellenkező esetben a tulajdonság figyelmen kívül marad.

## Gyakran Ismételt Kérdések

### Q1: Használhatok különböző képtípusokat a glifek kitöltéséhez?

**A:** Igen, az Aspose.Page támogatja a TIFF, PNG, JPEG, BMP és GIF formátumokat. Csak adja meg a megfelelő fájlkiterjesztést a `CreateImageBrush` hívásban.

### Q2: Hogyan testreszabhatom tovább a glifek megjelenését?

**A:** Tekintse meg a `XpsGlyphs` további tulajdonságait, például az `Opacity`, `RenderTransform` és `Stroke` értékeket a finomhangoláshoz.

### Q3: Alkalmas az Aspose.Page nagy dokumentumkészletek kezelésére?

**A:** Teljesen. A könyvtár magas teljesítményű forgatókönyvekre van optimalizálva, és ezrek XPS fájlját képes feldolgozni kötegelt feladatokban.

### Q4: Alkalmazhatok különböző stílusokat egyedi glifekre?

**A:** Igen. Minden `XpsGlyphs` példány saját fill, stroke és transformation értékekkel rendelkezhet, ami részletes vezérlést biztosít.

### Q5: Mik a előnyei az Aspose.Page használatának más dokumentumfeldolgozó eszközökkel szemben?

**A:** Az Aspose.Page egy teljes, licencmentes API-t kínál XPS létrehozásához, manipulálásához és konvertálásához, kiterjedt dokumentációval és 24/7 támogatással.

---

**Utolsó frissítés:** 2026-01-07  
**Tesztelve:** Aspose.Page 24.12 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}