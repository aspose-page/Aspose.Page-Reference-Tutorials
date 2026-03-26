---
date: 2026-03-26
description: Tudja meg, hogyan hozhat létre PostScript dokumentumot .NET-ben textúra-csempézési
  mintákkal az Aspose.Page segítségével. Kövesse lépésről‑lépésre útmutatónkat, hogy
  gazdag textúrákat adjon PS fájljaihoz.
linktitle: Create PostScript .NET document with texture tiling
second_title: Aspose.Page .NET API
title: PostScript .NET dokumentum létrehozása textúra csempézéssel
url: /hu/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PostScript .NET dokumentum létrehozása textúra csempézéssel

## Hogyan hozhatunk létre PostScript dokumentumot .NET-ben textúra csempézéssel

Ebben az oktatóanyagban megtanulja, hogyan **hozzon létre PostScript dokumentumot .NET-ben**, és hogyan gazdagítsa azt egy textúra csempézési mintával az Aspose.Page könyvtár segítségével. Lépésről lépésre végigvezetjük a projekt beállításától a szöveg textúra ecsettel való kitöltéséig és körvonalazásáig, hogy percek alatt vizuálisan vonzó PS fájlokat készíthessen.

## Gyors válaszok
- **Melyik könyvtárat használja?** Aspose.Page for .NET  
- **Használhatok .NET Core‑t?** Igen, a könyvtár támogatja a .NET Core‑t és a .NET 5/6‑ot  
- **Milyen képformátumok működnek a textúrához?** Bármely, a System.Drawing által támogatott formátum (BMP, PNG, JPEG, stb.)  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 10‑15 perc egy alap példához  
- **Szükség van licencre?** Egy ingyenes próba verzió teszteléshez elegendő; a termeléshez licenc szükséges  

## Előfeltételek

- [Visual Studio](https://visualstudio.microsoft.com/) telepítve a gépére.  
- Alapvető C# programozási ismeretek.  
- Töltse le és telepítse az [Aspose.Page for .NET library](https://releases.aspose.com/page/net/) könyvtárat.  
- Egy kép fájl a textúra mintához (pl. **TestTexture.bmp**).

## Névterek importálása

A C# fájlban importálja a szükséges névtereket, hogy a fordító tudja, honnan vegye a használt típusokat:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 1. lépés: Dokumentum könyvtár beállítása

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Cserélje le a **Your Document Directory** értéket arra a mappára, ahová a generált PS fájlt menteni szeretné.

## 2. lépés: Kimeneti adatfolyam létrehozása a PS dokumentumhoz

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

Ez a blokk megnyit egy fájl adatfolyamot, beállítja az oldal méretét (alapértelmezés szerint A4), és létrehoz egy új **PsDocument** példányt, amelyre rajzolni fogunk.

## 3. lépés: Textúra csempézési minta alkalmazása

```csharp
// Create a Bitmap object from the image file
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Create texture brush from the image
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    // Add scaling in X direction to the pattern
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Set this texture brush as the current paint
    document.SetPaint(brush);
}
```

Itt betöltjük a bitmapet, egy **TextureBrush**‑ba csomagoljuk, opcionálisan vízszintesen nyújtjuk, majd a **PsDocument**‑nek megadjuk, hogy ezt az ecsetet használja a további rajzolási műveletekhez.

## 4. lépés: Téglalap útvonal létrehozása és kitöltése

```csharp
// Create rectangle path
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Fill rectangle
document.Fill(path);
```

Egy egyszerű téglalapot definiálunk, és a korábban beállított textúra ecsettel töltjük ki.

## 5. lépés: Körvonal beállítása és rajzolás

```csharp
// Get current paint
Brush paint = document.GetPaint();

// Set red stroke
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Stroke the rectangle
document.Draw(path);
```

Lekérdezzük a jelenlegi festéket (a textúra ecsetet), létrehozunk egy piros tollat a körvonalhoz, és megrajzoljuk a téglalap szegélyét.

## 6. lépés: Szöveg kitöltése és körvonalazása textúra mintával

```csharp
// Fill text with texture pattern                
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Outline text with texture pattern
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

Ez a lépés bemutatja a **fill and stroke text** (kitöltés és körvonalazás) képességet: az „ABC” karakterek a textúra ecsettel vannak kitöltve, majd körvonalazva, ami erőteljes vizuális hatást eredményez.

## 7. lépés: Dokumentum mentése és lezárása

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Az oldal lezárása befejezi a rajzolási parancsokat, a `Save()` pedig a PostScript fájlt a lemezre írja.

## Gyakori problémák és megoldások

- **A textúra helytelenül nyúlik** – Állítsa a `Matrix` értékeket az X/Y irányú méretezés szabályozásához.  
- **A kép nem található** – Ellenőrizze, hogy a `dataDir` a megfelelő mappára mutat, és a fájlnév pontosan egyezik, beleértve a kis‑ és nagybetűket is.  
- **A színek torzak** – Ne feledje, hogy a PostScript egy eszköz‑független színtérrel dolgozik; használjon megfelelő `Color` objektumokat, amelyek helyesen térképeződnek.

## Gyakran ismételt kérdések

**K:** Használhatok más képformátumokat a textúra mintához?  
**V:** Igen, bármely, a `System.Drawing.Bitmap` által támogatott formátum (BMP, PNG, JPEG, GIF, stb.) működik.

**K:** Az Aspose.Page kompatibilis a .NET Core‑ral?  
**V:** Teljesen. A könyvtár fut .NET Framework‑ön, .NET Core‑on és .NET 5/6‑on is.

**K:** Hogyan változtathatom meg a textúrázott téglalap méretét?  
**V:** Módosítsa a `RectangleF` értékeket a téglalap‑létrehozási lépésben (pl. `new RectangleF(0, 0, 300, 150)`).

**K:** Alkalmazhatok több textúra mintát egy dokumentumban?  
**V:** Igen. Egyszerűen hozzon létre egy új `TextureBrush`‑t egy másik képpel, és hívja meg újra a `SetPaint`‑t a következő alakzat vagy szöveg rajzolása előtt.

**K:** Hol találok további példákat és API referenciát?  
**V:** Látogassa meg az [Aspose.Page Fórumot](https://forum.aspose.com/c/page/39) a közösségi segítségért, valamint a hivatalos [dokumentációt](https://reference.aspose.com/page/net/) a részletes API használathoz.

## Összegzés

Most már tudja, hogyan **hozzon létre PostScript dokumentumot .NET-ben**, és hogyan alkalmazzon egy textúra csempézési mintát, beleértve a **szöveg kitöltését és körvonalazását** a textúrával. Kísérletezzen különböző képekkel, méretezési mátrixokkal és rajzolási primitívekkel, hogy egyedi stílusú PS fájlokat készítsen jelentésekhez, szórólapokhoz vagy bármilyen grafikai igényű kimenethez.

---

**Utolsó frissítés:** 2026-03-26  
**Tesztelt verzió:** Aspose.Page 24.11 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}