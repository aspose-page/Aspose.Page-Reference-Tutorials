---
date: 2026-09-04
description: Dowiedz się, jak dodać gradient w Java PostScript przy użyciu Aspose.Page
  Java, tworząc diagonal color transitions przy użyciu LinearGradientPaint dla żywych
  dokumentów.
keywords:
- how to add gradient
- diagonal gradient java
- Aspose.Page Java
- LinearGradientPaint
- Java PostScript graphics
lastmod: 2026-09-04
linktitle: 'Jak dodać gradient: diagonal gradient w Java PostScript przy użyciu Aspose.Page
  Java'
og_description: Dowiedz się, jak dodać gradient w Java PostScript przy użyciu Aspose.Page
  Java. Ten przewodnik pokazuje, jak stworzyć diagonal gradient przy użyciu LinearGradientPaint
  w kilku prostych krokach.
og_image_alt: Code example creating a diagonal gradient in a PostScript document using
  Aspose.Page for Java
og_title: Jak dodać gradient w Java PostScript przy użyciu Aspose.Page Java
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to add gradient in Java PostScript with Aspose.Page Java,
    creating diagonal color transitions using LinearGradientPaint for vibrant documents.
  headline: 'How to add gradient: diagonal gradient in Java PostScript using Aspose.Page
    Java'
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for Java provides a full set of drawing primitives, text
      rendering, and image handling capabilities.
    question: Can I use this library for other graphic operations in Java?
  - answer: Absolutely. You can download a fully functional trial from the [Aspose
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page Java?
  - answer: The official API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find documentation for Aspose.Page Java?
  - answer: Licenses can be bought directly from the [Aspose purchase portal](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Page Java?
  - answer: Visit the community‑run [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for help from both Aspose engineers and fellow developers.
    question: Need assistance or have questions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- LinearGradientPaint
- document graphics
title: 'Jak dodać gradient: diagonal gradient w Java PostScript przy użyciu Aspose.Page
  Java'
url: /pl/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj gradient skośny w Java PostScript przy użyciu Aspose.Page Java

## Wprowadzenie
If you’re looking to enrich a PostScript file with a smooth diagonal color transition, **Aspose.Page Java** makes it surprisingly easy. In this tutorial you’ll learn **how to add gradient** effects step‑by‑step, using the `LinearGradientPaint` class from Java 2D. By the end you’ll have a ready‑to‑run snippet that creates a PostScript document with a vibrant diagonal gradient, and you’ll understand why this approach is more maintainable than hand‑coding raw PostScript commands.

## Jak dodać gradient w Java PostScript
Adding a gradient might sound like a graphics‑only task, but with Aspose.Page you get full control over the underlying PostScript commands while staying in pure Java. This section explains why the approach works and what you gain compared to hand‑coding raw PostScript.

## Szybkie odpowiedzi
- **What library is required?** Aspose.Page for Java.  
- **Which class creates the gradient?** `LinearGradientPaint`.  
- **Can I change the colors?** Yes – modify the `Color[]` array.  
- **Do I need a license for production?** A commercial license is required; a free trial is available.  
- **How long does the implementation take?** Around 10 minutes for a basic gradient.

## Czym jest Aspose.Page Java?
Aspose.Page Java is a full‑featured API that lets developers generate, edit, and convert PostScript and PDF files without any external software. The library supports **50+ input and output formats** and can process documents with **500+ pages** while keeping memory usage under 100 MB.

## Dlaczego używać gradientu skośnego?
A diagonal gradient adds depth and visual interest to charts, banners, or any graphic element that needs a modern look. Because the gradient runs from one corner to the opposite, it works well for backgrounds, button skins, and decorative shapes, giving a professional finish without extra image assets.

## Wymagania wstępne
Before you start, make sure you have:

- Java Development Kit (JDK) 8 or higher.  
- An IDE such as Eclipse, IntelliJ IDEA, or VS Code.  
- **Aspose.Page for Java** library – download the latest version from the [official download page](https://releases.aspose.com/page/java/).

## Importowanie pakietów
The `java.awt` package provides the core graphics classes, while the `com.aspose.page` package gives you access to PostScript‑specific APIs.

The `LinearGradientPaint` class is Aspose.Page’s bridge to Java 2D gradient functionality.  
`AffineTransform` enables rotation and scaling of the gradient so it aligns diagonally.

```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Krok 1: utwórz strumień wyjściowy dla dokumentu PostScript
First, define the folder where the file will be saved and open a `FileOutputStream`. This stream receives the generated PostScript data.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## Krok 2: utwórz opcje zapisu z rozmiarem A4
`PsSaveOptions` lets you specify page size, resolution, and other output settings. Here we use the default A4 size, which is 595 × 842 points at 72 dpi.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## Krok 3: utwórz nowy dokument PS
The `PsDocument` class represents a PostScript document and provides methods to create pages and draw graphics.  
Instantiate a `PsDocument` using the output stream and the save options. The `false` flag tells the constructor not to automatically open a new page – we’ll do that later.

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Krok 4: utwórz prostokąt
Define the rectangle that will receive the gradient fill. The rectangle’s position (200, 100) and size (200 × 100) are chosen to make the gradient clearly visible.

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Krok 5: utwórz transformację gradientu
An `AffineTransform` lets us rotate, scale, and translate the gradient so that it runs diagonally across the rectangle. The math below calculates the hypotenuse and adjusts the scaling ratio accordingly.

```java
// Create the gradient transform. Scale components must be equal to the rectangle width and height.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate gradient, then scale and translate for visible color transition
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```

## Krok 6: utwórz skośny liniowy gradient
`LinearGradientPaint` is the core class that generates the color transition. It spans from the rectangle’s top‑left to its bottom‑right, using the previously defined transform. The `MultipleGradientPaint.CycleMethod.NO_CYCLE` ensures the gradient does not repeat.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## Krok 7: ustaw farbę i wypełnij prostokąt
Apply the gradient paint to the document and fill the rectangle shape. This step renders the diagonal color transition onto the PostScript page.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Krok 8: zamknij bieżącą stronę i zapisz dokument
Finally, close the page, flush the stream, and save the file. The resulting `DiagonalGradient_outPS.ps` file can be opened with any PostScript viewer.

```java
// Close current page and save the document
document.closePage();
document.save();
```

## Typowe problemy i wskazówki
- **Gradient appears flat** – double‑check the rotation angle; a 45° rotation creates a true diagonal.  
- **Colors look washed out** – ensure you’re using `MultipleGradientPaint.ColorSpaceType.SRGB` for accurate color rendering.  
- **File not found error** – verify that `dataDir` points to an existing folder and that the application has write permissions.  
- **Large documents cause memory spikes** – use `PsSaveOptions.setCompress(true)` to reduce memory footprint.

## Najczęściej zadawane pytania

**Q: Can I use this library for other graphic operations in Java?**  
A: Yes, Aspose.Page for Java provides a full set of drawing primitives, text rendering, and image handling capabilities.

**Q: Is there a free trial available for Aspose.Page Java?**  
A: Absolutely. You can download a fully functional trial from the [Aspose free trial page](https://releases.aspose.com/).

**Q: Where can I find documentation for Aspose.Page Java?**  
A: The official API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: How can I purchase a license for Aspose.Page Java?**  
A: Licenses can be bought directly from the [Aspose purchase portal](https://purchase.aspose.com/buy).

**Q: Need assistance or have questions?**  
A: Visit the community‑run [Aspose.Page forum](https://forum.aspose.com/c/page/39) for help from both Aspose engineers and fellow developers.

---

**Last Updated:** 2026-09-04  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose

## Powiązane samouczki

- [Utwórz gradient promienisty w PostScript przy użyciu Aspose.Page dla Java](/page/java/postscript-gradient-addition/)
- [Jak dodać gradient w Java PostScript przy użyciu Linear Gradient Paint](/page/java/postscript-gradient-addition/horizontal/)
- [Utwórz gradient PostScript w Java – Dodaj gradient pionowy](/page/java/postscript-gradient-addition/vertical/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}