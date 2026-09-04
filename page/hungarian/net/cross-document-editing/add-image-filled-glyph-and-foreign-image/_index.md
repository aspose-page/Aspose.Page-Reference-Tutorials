---
date: 2026-06-30
description: Ismerje meg, hogyan hozhat létre XPS dokumentumot .NET-ben, és adhat
  hozzá image‑filled glyph‑eket vagy foreign image‑eket az Aspose.Page for .NET segítségével
  néhány egyszerű lépésben.
keywords:
- create xps document .net
- image filled glyph
- foreign image
linktitle: Image Filled Glyph és Foreign Image hozzáadása
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create XPS document .NET and add image‑filled glyphs or
    foreign images using Aspose.Page for .NET in a few easy steps.
  headline: Create XPS Document .NET – Add Image Filled Glyph & Foreign Image with
    Aspose.Page
  type: TechArticle
- questions:
  - answer: Over 25 image formats and the ability to process XPS files up to 500 MB
      without full memory loading.
    question: What does Aspose.Page support?
  - answer: 'Just two lines: create an `ImageBrush` and assign it to a `Glyph`.'
    question: How many lines of code to add an image‑filled glyph?
  - answer: Yes, a commercial license removes evaluation watermarks.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are compatible?
  - answer: Absolutely – you can import the font collection from the first document
      into the second.
    question: Can I reuse fonts from another XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: XPS dokumentum létrehozása .NET – Image Filled Glyph és Foreign Image hozzáadása
  az Aspose.Page segítségével
url: /hu/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS dokumentum létrehozása .NET – Képpel kitöltött glif és külső kép hozzáadása az Aspose.Page segítségével

## Bevezetés

A .NET fejlesztésben a **create XPS document .NET** feladatok gyakoriak, amikor magas minőségű, felbontásfüggetlen grafikára van szükség. Az Aspose.Page for .NET ezt egyszerűvé teszi, és lehetővé teszi, hogy XPS fájlokat gazdagítsunk képpel kitöltött glifekkel, vagy képeket hozzunk be egy másik XPS dokumentumból. A bemutató végére tudni fogod, hogyan hozz létre két XPS dokumentumot, hogyan töltsd ki a glifeket képekkel, és hogyan használd újra ezeket a képeket dokumentumok között – tökéletes számlák, tanúsítványok vagy bármilyen vizuálisan gazdag kimenet generálásához.

## Gyors válaszok
- **Mi támogat az Aspose.Page?** Több mint 25 képformátum, és képes XPS fájlok 500 MB-ig történő feldolgozására teljes memória betöltés nélkül.  
- **Hány sor kód szükséges egy képpel kitöltött glif hozzáadásához?** Csak két sor: egy `ImageBrush` létrehozása és egy `Glyph`-hez való hozzárendelése.  
- **Szükségem van licencre a termeléshez?** Igen, egy kereskedelmi licenc eltávolítja a kiértékelési vízjeleket.  
- **Mely .NET verziók kompatibilisek?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Újra felhasználhatom egy másik XPS betűkészleteit?** Természetesen – importálhatod az első dokumentum betűkészlet-gyűjteményét a másodikba.

## Hogyan hozol létre XPS dokumentumot az Aspose.Page .NET használatával?

Töltsd be az Aspose.Page könyvtárat, példányosíts egy `XpsDocument`-et, adj hozzá egy oldalt, és hívd meg a `Save`-et – ez a teljes munkafolyamat három tömör utasításban. Az API automatikusan kezeli az oldal méretét, DPI-t és az erőforrás-kezelést, így nem kell alacsony szintű XPS struktúrákat kezelned. Ez a megközelítés egyoldalas szórólapoktól több száz oldalas katalógusokig skálázható.

## Előkövetelmények

- **Aspose.Page for .NET** – töltsd le [itt](https://releases.aspose.com/page/net/).  
- **Egy .NET IDE** – Visual Studio, Rider, vagy VS Code a C# kiegészítővel.  
- **Egy mappa a dokumentumaid számára** – a kódrészletekben **Your Document Directory**-ként hivatkozunk rá.

## Névterek importálása

Az `Aspose.Page.XPS` névtér biztosítja a fő XPS dokumentumosztályokat, míg az `Aspose.Page.XPS.XpsModel` tartalmazza a modell elemeket, például glifeket és ecseteket. Importáld őket a fájlod tetején:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Mi az a képpel kitöltött glif?

A glif egy vektoros alakzat, amely szilárd színnel, színátmenettel vagy egy képes ecsettel (image brush) jeleníthető meg. Amikor egy `ImageBrush`-t alkalmazol, a glif belseje a megadott képpel van kitöltve, lehetővé téve összetett vizuális hatásokat anélkül, hogy az egész oldalt raszterizálnád.

## 1. lépés: Az első XPS dokumentum létrehozása

Az `XpsDocument` egy XPS csomagot képvisel, és a belépési pont a XPS fájlok létrehozásához és mentéséhez. Kezd az első XPS dokumentum létrehozásával, amely a képpel kitöltött glifeket fogja tartalmazni.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

## 2. lépés: Glifek hozzáadása az első dokumentumhoz

Az `XpsGlyphs` egy glifgyűjteményt (szövegkaraktereket) definiál, amelyeket egy oldalra lehet helyezni. Adj glifeket az első dokumentumhoz, megadva a betűtípust, méretet, stílust és pozíciót.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## 3. lépés: Glifek kitöltése képes ecsettel

Az `ImageBrush` egy területet képpel fest, lehetővé téve minták vagy képek kitöltését alakzatokban. Töltsd ki a glifeket egy képes ecsettel, a data könyvtáradból származó képet felhasználva.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## 4. lépés: A második XPS dokumentum létrehozása

Az `XpsDocument` egy új XPS fájl létrehozására szolgál, amely oldalakat, erőforrásokat és tartalmat tartalmazhat. Most hozd létre a második XPS dokumentumot, amely az első dokumentumból származó glifeket fogja tartalmazni.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

## 5. lépés: Glifek hozzáadása az első dokumentum betűtípusával

A `Font` egy betűtípust jelöl, amelyet XPS dokumentumban a szöveg megjelenítéséhez használnak. Adj glifeket a második dokumentumhoz, az első dokumentumból kinyert betűtípust felhasználva. A betűkészlet megosztásával alacsony fájlméretet és vizuális konzisztenciát biztosítasz.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## 6. lépés: Képes ecset létrehozása az első dokumentum kitöltéséből

Az `ImageBrush` létrehozható egy meglévő kitöltésből, hogy ugyanazt a képet dokumentumok között újra felhasználhasd. Hozz létre egy képes ecsetet az első dokumentum kitöltéséből, és használd a glifek kitöltésére a második dokumentumban. Ez a „külső kép” technika lehetővé teszi a grafika újrahasználatát a forrásfájl duplikálása nélkül.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## 7. lépés: Dokumentumok mentése

A `Save` az XPS csomagot egy fájlba írja, beágyazva az összes erőforrást. Mentsd el az első és a második XPS dokumentumot is a kimeneti mappába. A `Save` metódus az XPS csomagot írja, beágyazva az összes erőforrást és megőrizve a képpel kitöltött glifeket.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Gyakori problémák és megoldások

| Probléma | Miért fordul elő | Megoldás |
|----------|------------------|----------|
| **Kép nem jelenik meg a glifben** | Az `ImageBrush` helytelen URI-val lett létrehozva, vagy a kép mérete meghaladja a glif határait. | Ellenőrizd a kép útvonalát, és opcionálisan állítsd be `ImageBrush.Stretch = Stretch.Uniform`. |
| **Betűk hiányoznak a második dokumentumban** | A betűkészlet erőforrások nem lettek exportálva az első XPS-ből. | Használd a `firstDoc.Fonts.SaveTo(secondDoc.Fonts)`-t a glifek hozzáadása előtt. |
| **Teljesítménycsökkenés nagy fájlok esetén** | Nagy képek betöltése memóriába minden glifhez. | Használj egyetlen `ImageBrush` példányt az összes glifhez, vagy méretezd le a képet a használat előtt. |

## Gyakran ismételt kérdések

### Q1: Használhatok különböző képformátumokat a glifek kitöltéséhez?

A1: Igen, az Aspose.Page támogatja a PNG, JPEG, BMP, GIF, TIFF és további formátumokat – összesen több mint 25 formátumot.

### Q2: Hogyan testreszabhatom tovább a glifek megjelenését?

A2: Vizsgáld meg a `Glyph.Stroke`, `Glyph.FillOpacity` és `Glyph.Transform` tulajdonságokat, hogy beállítsd a körvonalakat, átlátszóságot és a forgatást.

### Q3: Alkalmas-e az Aspose.Page nagy dokumentumkészletek kezelésére?

A3: Teljes mértékben. A könyvtár több száz oldalas XPS fájlokat dolgoz fel streaminggel, így a memóriahasználat 100 MB alatt marad még 500 oldalas dokumentumok esetén is.

### Q4: Alkalmazhatok különböző stílusokat egyedi glifekre?

A4: Igen, minden `Glyph` példány saját `Fill`, `Stroke` és `Transform` tulajdonságokkal rendelkezik, ami lehetővé teszi egyedi glif-stílusok alkalmazását.

### Q5: Mik az előnyei az Aspose.Page használatának más XPS eszközökkel szemben?

A5: Az Aspose.Page több mint 25 képformátumot támogat, 500 MB-ig terjedő fájlokat dolgoz fel teljes memória betöltés nélkül, és 100 % .NET‑natív API-t biztosít – így nincs szükség COM interopra vagy külső eszközökre.

---

**Legutóbb frissítve:** 2026-06-30  
**Tesztelve ezzel:** Aspose.Page 24.11 for .NET  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó oktatóanyagok

- [XPS dokumentum létrehozása – Aspose.Page for .NET](/page/net/document-creation/)
- [Kép hozzáadása XPS dokumentumhoz az Aspose.Page for .NET segítségével](/page/net/image-management/add-image-to-xps-document/)
- [Glif klón hozzáadása és szín módosítása az Aspose.Page for .NET segítségével](/page/net/cross-document-editing/add-glyph-clone-and-change-color/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}