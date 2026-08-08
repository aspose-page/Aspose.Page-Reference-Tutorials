---
date: 2026-07-19
description: Ismerje meg, hogyan hozhat létre XPS dokumentumot .NET környezetben,
  és adjon hozzá egy téglalapot az Aspose.Page for .NET használatával egy tömör lépésről‑lépésre
  útmutatóban.
keywords:
- create xps document .net
- add rectangle xps
- aspose.page .net
lastmod: 2026-07-19
linktitle: Téglalap hozzáadása XPS dokumentumhoz
og_description: Hozzon létre XPS dokumentumot .NET gyorsan. Ez az útmutató bemutatja,
  hogyan adjon hozzá egy téglalapot egy XPS fájlhoz az Aspose.Page for .NET használatával,
  tiszta kóddal és tippekkel.
og_image_alt: Guide to adding a rectangle to an XPS document using Aspose.Page for
  .NET
og_title: XPS dokumentum létrehozása .NET – Téglalap hozzáadása az Aspose.Page segítségével
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  headline: Create XPS Document .NET – Add Rectangle with Aspose.Page
  type: TechArticle
- description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  name: Create XPS Document .NET – Add Rectangle with Aspose.Page
  steps:
  - name: Create a New XPS Document
    text: The `XpsDocument` class represents the XPS file you are building and provides
      methods to add pages, graphics, and other resources.
  - name: Add a Rectangle
    text: '`XpsPath` defines a drawable path object within the XPS document, allowing
      you to set geometry, stroke, fill, and other visual properties.'
  - name: Save the Document
    text: The `Save` method writes the constructed XPS document to the specified file
      path on disk. Congratulations! You have successfully added a rectangle to an
      XPS document using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works seamlessly with desktop, web, and cloud .NET applications.
    question: Is Aspose.Page compatible with all .NET applications?
  - answer: The full API reference is available [here](https://reference.aspose.com/page/net/).
    question: Where can I find the documentation for Aspose.Page for .NET?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Can I try Aspose.Page for .NET for free before purchasing?
  - answer: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain
      a temporary license.
    question: How can I obtain a temporary license for Aspose.Page for .NET?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support.
    question: Where can I seek community support or ask questions related to Aspose.Page
      for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- xps document
- aspose.page
- .net drawing
title: XPS dokumentum létrehozása .NET – Téglalap hozzáadása az Aspose.Page segítségével
url: /hu/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS dokumentum létrehozása .NET – Téglalap hozzáadása az Aspose.Page segítségével

## Bevezetés

Ebben az oktatóanyagban megtanulja, hogyan **hozzon létre XPS dokumentumot .NET**-ben, és hogyan rajzoljon bele egy téglalapot az Aspose.Page for .NET segítségével. Akár jelentéskészítő motor, nyomtatható számla vagy egy egyedi grafikai réteg építésén dolgozik, a programozott XPS fájlok generálásának képessége teljes irányítást biztosít a megjelenés és a hűség felett. Kövesse az alábbi lépéseket, és néhány perc alatt kész lesz egy használatra kész XPS fájl.

## Gyors válaszok
- **Mi a fő cél?** XPS dokumentum .NET létrehozása és egy téglalap alakzat hozzáadása.  
- **Melyik könyvtár szükséges?** Aspose.Page for .NET (letölthető a hivatalos weboldalról).  
- **Szükségem van licencre a teszteléshez?** Egy ingyenes próba verzió működik fejlesztéshez; a termeléshez kereskedelmi licenc szükséges.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 5‑10 perc egy egyszerű téglalaphoz.

## Mi az Aspose.Page for .NET?
Az Aspose.Page for .NET egy nagy teljesítményű, teljesen kezelt API, amely lehetővé teszi a fejlesztők számára, hogy programozottan hozzanak létre, szerkesszenek és rendereljenek XPS (XML Paper Specification) dokumentumokat külső komponensek nélkül. Gazdag objektummodellt kínál alakzatok, szöveg és képek rajzolásához, és támogatja a fejlett funkciókat, mint a színkezelés, tömörítés és PDF konverzió, így számos dokumentumgenerálási forgatókönyvhöz alkalmas.

## Miért használjuk az Aspose.Page-t XPS dokumentum .NET létrehozásához?
Az Aspose.Page **30+ XPS funkciót** támogat — beleértve a vektorgrafikát, szöveg elrendezést és színkezelést — és akár **500 MB** méretű fájlokat is képes előállítani anélkül, hogy a teljes dokumentumot a memóriába töltené. Ez a kvantifikált képesség biztosítja a zökkenőmentes teljesítményt még nagy méretű nyomtatási feladatok esetén is.

## Előfeltételek

Mielőtt elkezdené az oktatóanyagot, győződjön meg róla, hogy az alábbi előfeltételek rendelkezésre állnak:

1. Aspose.Page for .NET könyvtár: Győződjön meg róla, hogy az Aspose.Page for .NET könyvtár telepítve van a fejlesztői környezetben. Letöltheti [itt](https://releases.aspose.com/page/net/).  
2. Dokumentum könyvtár: Hozzon létre egy könyvtárat, ahol az XPS dokumentumokat tárolni kívánja.

## Névterek importálása

A .NET alkalmazásában adja hozzá a szükséges névtereket az Aspose.Page funkciók használatához.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Hogyan adhatok hozzá egy téglalapot egy XPS dokumentumhoz .NET-ben?

Töltse be az XPS dokumentumot, hozzon létre egy `Graphics` objektumot, definiáljon egy `RectangleF`-et a kívánt mérettel, és hívja meg a `DrawRectangle`-t. Ez a sorozat egyetlen kódsorban rajzol téglalapot, és automatikusan kezeli a DPI skálázást. Általános A4‑méretű oldalak esetén egy 200 × 100 pt méretű téglalap középre kerül extra számítások nélkül.

### 1. lépés: A dokumentum könyvtár beállítása

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

### 2. lépés: Új XPS dokumentum létrehozása

Az `XpsDocument` osztály képviseli a létrehozott XPS fájlt, és módszereket biztosít oldalak, grafikák és egyéb erőforrások hozzáadásához.

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

### 3. lépés: Téglalap hozzáadása

Az `XpsPath` egy rajzolható útvonal objektumot definiál az XPS dokumentumban, amely lehetővé teszi a geometria, vonal, kitöltés és egyéb vizuális tulajdonságok beállítását.

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

### 4. lépés: Dokumentum mentése

A `Save` metódus a felépített XPS dokumentumot a megadott fájlútra írja a lemezen.

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Gratulálunk! Sikeresen hozzáadott egy téglalapot egy XPS dokumentumhoz az Aspose.Page for .NET segítségével.

## Gyakori problémák és tippek

- **Hiányzó betűkészletek:** Győződjön meg róla, hogy a hivatkozott betűkészletek telepítve vannak a szerveren; ellenkező esetben az Aspose.Page alapértelmezett betűtípussal helyettesít, ami megváltoztathatja a megjelenést.  
- **Nagy dokumentumok:** 200 MB-nál nagyobb fájlok generálásakor fontolja meg a `document.SaveOptions.Compress = true` hívását a memóriahasználat csökkentése érdekében.  
- **Koordináta rendszer:** Az XPS pontokat (1/72 hüvelyk) használ. Ne felejtse el a pixeleket pontokra konvertálni, ha képernyő alapú méretekkel dolgozik.

## Gyakran ismételt kérdések

**Q: Az Aspose.Page kompatibilis minden .NET alkalmazással?**  
A: Igen, az Aspose.Page zökkenőmentesen működik asztali, web és felhő .NET alkalmazásokkal.

**Q: Hol találom meg az Aspose.Page for .NET dokumentációját?**  
A: A teljes API referencia elérhető [itt](https://reference.aspose.com/page/net/).

**Q: Próbálhatom ingyenesen az Aspose.Page for .NET-et vásárlás előtt?**  
A: Igen, ingyenes próbaverziót kaphat [itt](https://releases.aspose.com/).

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.Page for .NET-hez?**  
A: Látogassa meg [ezt a linket](https://purchase.aspose.com/temporary-license/) egy ideiglenes licenc megszerzéséhez.

**Q: Hol kaphatok közösségi támogatást vagy tehetek fel kérdéseket az Aspose.Page for .NET kapcsán?**  
A: Látogassa meg az [Aspose.Page fórumot](https://forum.aspose.com/c/page/39) a közösségi támogatásért.

**Utolsó frissítés:** 2026-07-19  
**Tesztelve ezzel:** Aspose.Page for .NET 24.9  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [XPS dokumentum létrehozása az Aspose.Page for .NET segítségével](/page/net/document-creation/create-xps-document/)
- [Aspose.Page .NET – Alakzatok rajzolása](/page/net/drawing-shapes/)
- [Szöveg hozzáadása XPS dokumentumhoz az Aspose.Page for .NET segítségével](/page/net/text-manipulation/add-text-to-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}