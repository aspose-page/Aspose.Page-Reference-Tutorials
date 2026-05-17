---
date: 2026-02-25
description: Fejlessze a PostScript dokumentumokat lineáris színátmenetes téglalappal
  az Aspose.Page for .NET használatával. Kövesse lépésről‑lépésre útmutatónkat, hogy
  megtanulja a színátmenetes kitöltésű szöveget és a körvonalas szöveg színátmenetét.
linktitle: Add Horizontal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Lineáris gradienttérral ellátott téglalap hozzáadása a PostScript (PS) fájlhoz
  az Aspose.Page segítségével
url: /hu/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
weight: 12
---

 content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Linear Gradient téglalap hozzáadása PostScript (PS) dokumentumhoz az Aspose.Page segítségével

## Bevezetés

Üdvözöljük ebben az átfogó útmutatóban, amely a **linear gradient rectangle** hozzáadásáról szól a PostScript (PS) dokumentumokhoz az Aspose.Page for .NET használatával. Az Aspose.Page egy erőteljes könyvtár, amely lehetővé teszi dokumentumok létrehozását, módosítását és renderelését számos formátumban, és ma arra összpontosítunk, hogyan hozhatunk szemrevaló gradienteket a PS fájljaiba.

### Gyors válaszok
- **Mi a linear gradient rectangle feladata?** Egy téglalap alakú területet tölt ki egy sima színátmenettel az egyik oldalról a másikra.  
- **Melyik API kezeli a gradient kitöltésű szöveget?** `LinearGradientBrush` kombinálva a `SetPaint` és `FillAndStrokeText` metódusokkal.  
- **Lehet-e gradienttel körvonalazni a szöveget?** Igen – használja a `SetStroke`-ot egy gradient ecsettel, és hívja meg az `OutlineText`-et.  
- **Szükség van licencre a termeléshez?** Egy kereskedelmi Aspose.Page licenc szükséges a nem értékelő használathoz.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Előfeltételek

Mielőtt belemerülnénk, győződjön meg róla, hogy rendelkezik a következőkkel:

- Aspose.Page for .NET könyvtár: Győződjön meg arról, hogy a könyvtár hivatkozásként szerepel a projektben. Letöltheti a [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/) oldalról.
- Dokumentum könyvtár: Hozzon létre egy mappát a lemezen, ahol a generált PS fájl mentésre kerül, és cserélje le a **“Your Document Directory”** szöveget a kódban a megfelelő útvonalra.

## Névterek importálása

A kezdéshez importálja azokat a névtereket, amelyek hozzáférést biztosítanak a rajzoláshoz és a PS‑specifikus osztályokhoz:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Mi az a Linear Gradient Rectangle?

A **linear gradient rectangle** egyszerűen egy téglalap alakú forma, amelynek belsejét lineáris gradienttel festik – a színek egyenes vonalon, általában balról jobbra (vízszintesen) vagy felülről lefelé (vertikálisan) átmennek. Az Aspose.Page-ben ezt egy `GraphicsPath`-szal definiált téglalap és egy `LinearGradientBrush` kombinációjával érheti el, amely leírja a színátmenetet.

## Miért használjunk Gradient kitöltésű szöveget és Outline Text Gradient-et?

- **Vizuális vonzerő:** A gradienttel kitöltött szöveg mélységet és modern stílust ad a jelentéseknek, számláknak vagy promóciós anyagoknak.  
- **Márka konzisztencia:** Illessze a vállalati színeket pontos ARGB értékekkel.  
- **Sokoldalúság:** Ugyanaz az ecset újra felhasználható alakzatok kitöltésére, szöveg kitöltésére és körvonal gradientekhez, csökkentve a kódmásolást.

## 1. lépés: Dokumentum előkészítése

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## 2. lépés: Gradient téglalap és színek definiálása

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // Create graphics path from the first rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    // Create linear gradient brush with rectangle as bounds, start, and end colors
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## 3. lépés: Transzformáció beállítása az ecsethez

```csharp
    // Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    // Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Set transform
    brush.Transform = brushTransform;
```

## 4. lépés: Paint beállítása és a téglalap kitöltése

```csharp
    // Set paint
    document.SetPaint(brush);

    // Fill the rectangle
    document.Fill(path);
```

## Hogyan alkalmazzunk Gradient kitöltésű szöveget

```csharp
    // Fill text with gradient
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## Outline Text Gradient használata

```csharp
    // Set current stroke
    document.SetStroke(new Pen(brush, 5));
    // Outline text with gradient
    document.OutlineText("ABC", font, 200, 400);
```

## 7. lépés: Az aktuális oldal bezárása és a dokumentum mentése

```csharp
    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Gratulálunk! Sikeresen hozzáadott egy **linear gradient rectangle** elemet egy PostScript dokumentumhoz, és ugyanazt az ecsetet használta **gradient kitöltésű szöveg** és egy **outline text gradient** esetén.

## Gyakori felhasználási esetek és tippek

- **Jelentésfejek:** Nagy szövegrészek kitöltése gradientekkel a szekciócímek kiemeléséhez.  
- **Márka logók:** Logó alakzatok újraalkotása gradient kitöltéssel a konzisztens márkaépítéshez.  
- **Pro tipp:** Használja újra ugyanazt a `LinearGradientBrush` példányt több rajzolási hívásnál, hogy a színek tökéletesen összehangoltak legyenek az alakzatok és a szöveg között.

## Gyakran ismételt kérdések

### Q1: Can I apply gradients to other shapes besides rectangles?
**A:** Igen, gradienteket alkalmazhat bármely, a `GraphicsPath` által definiált alakzatra. Egyszerűen adjon hozzá köröket, sokszögeket vagy egyedi útvonalakat, mielőtt meghívná a `document.Fill(path)`-t.

### Q2: How can I change the gradient colors?
**A:** Módosítsa a `Color.FromArgb` értékeket a `LinearGradientBrush` létrehozásakor. Az első szín a kezdő, a második a gradient vége.

### Q3: Is Aspose.Page compatible with different document formats?
**A:** Teljes mértékben. Az Aspose.Page támogatja az XPS, PS, PDF és több egyéb vektoros formátumot. Tekintse meg a hivatalos dokumentációt a teljes listáért.

### Q4: Can I use Aspose.Page for commercial projects?
**A:** Igen, kereskedelmi licencelés elérhető. A részletekért tekintse meg a vásárlási oldalt: [here](https://purchase.aspose.com/buy).

### Q5: Where can I find community support?
**A:** Csatlakozzon az Aspose.Page közösségi fórumához: [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

---

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.Page 24.10 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}