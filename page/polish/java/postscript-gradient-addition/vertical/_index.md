---
date: 2025-12-09
description: Dowiedz się, jak tworzyć gradienty PostScript w Javie przy użyciu Aspose.Page.
  Ten przewodnik krok po kroku pokazuje, jak łatwo dodać pionowy gradient do dokumentów
  PostScript.
linktitle: Add Vertical Gradient in Java PostScript
second_title: Aspose.Page Java API
title: Utwórz gradient PostScript w Javie – Dodaj gradient pionowy
url: /pl/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz gradient PostScript w Javie – Dodaj gradient pionowy

## Introduction
W tym obszernym samouczku dowiesz się, jak **utworzyć gradient PostScript w Javie** przy użyciu Aspose.Page for Java. Dodanie gradientu pionowego może sprawić, że Twoje dokumenty będą wyglądały bardziej żywo i profesjonalnie, a przy kilku linijkach kodu osiągniesz oszałamiające efekty wizualne. Przeprowadzimy Cię przez każdy krok, wyjaśnimy, dlaczego każdy element ma znaczenie, i podamy praktyczne wskazówki, aby uniknąć typowych pułapek.  
W tym przewodniku **utworzymy gradient postscript w Javie** krok po kroku.

## Quick Answers
- **What library is needed?** Aspose.Page for Java  
- **Can I customize colors?** Tak, można użyć dowolnego `java.awt.Color`  
- **Is rotation supported?** Tak, możesz obrócić gradient przy użyciu `AffineTransform`  
- **What output format is produced?** Standardowy plik PostScript (.ps)  
- **Do I need a license for production?** Tak, wymagana jest licencja komercyjna  

## Prerequisites
Zanim zagłębisz się w samouczek, upewnij się, że spełniasz następujące wymagania:
- Zainstalowany Java Development Kit (JDK) na Twoim komputerze.  
- Biblioteka Aspose.Page for Java. Możesz ją pobrać [tutaj](https://releases.aspose.com/page/java/).

## Import Packages
W swoim projekcie Java zaimportuj niezbędne pakiety, aby rozpocząć:
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

Teraz rozbijmy proces dodawania gradientu pionowego w PostScript w Javie na kilka kroków.

## How to create PostScript gradient Java
Poniżej znajduje się przewodnik krok po kroku, który dokładnie pokazuje, jak **utworzyć gradient PostScript w Javie** przy użyciu API Aspose.Page.

### Step 1: Set up Your Document Directory
Krok 1: Skonfiguruj katalog dokumentu
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Step 2: Create Output Stream for PostScript Document
Krok 2: Utwórz strumień wyjściowy dla dokumentu PostScript
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### Step 3: Create Save Options with A4 Size
Krok 3: Utwórz opcje zapisu z rozmiarem A4
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### Step 4: Create a New PS Document
Krok 4: Utwórz nowy dokument PS
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Step 5: Create a Rectangle
Krok 5: Utwórz prostokąt
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### Step 6: Set Up Colors and Fractions for the Gradient
Krok 6: Skonfiguruj kolory i frakcje dla gradientu
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### Step 7: Create the Gradient Transform
Krok 7: Utwórz transformację gradientu
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### Step 8: Create Vertical Linear Gradient Paint
Krok 8: Utwórz pionowy gradient liniowy
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### Step 9: Set Paint and Fill the Rectangle
Krok 9: Ustaw farbę i wypełnij prostokąt
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### Step 10: Close Current Page and Save the Document
Krok 10: Zamknij bieżącą stronę i zapisz dokument
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Gratulacje! Pomyślnie dodałeś gradient pionowy do swojego dokumentu PostScript w Javie przy użyciu Aspose.Page for Java.

## Why use vertical gradients in PostScript?
Gradienty pionowe nadają Twoim stronom głębi i atrakcyjności wizualnej bez znaczącego zwiększania rozmiaru pliku. Są szczególnie przydatne do:
- Nagłówków i stopek raportów  
- Wypełnień tła wykresów lub diagramów  
- Wyróżniania sekcji w dokumentach technicznych  

## Common Issues and Solutions
- **Gradient wygląda płasko:** Upewnij się, że skalowanie `AffineTransform` odpowiada wymiarom prostokąta.  
- **Kolory wyglądają wyblakłe:** Sprawdź, czy używasz właściwego `ColorSpaceType` (SRGB) oraz czy tablica frakcji jest uporządkowana od 0.0 do 1.0.  
- **Plik nie został wygenerowany:** Sprawdź, czy katalog wyjściowy (`dataDir`) istnieje i aplikacja ma uprawnienia do zapisu.  

## Frequently Asked Questions
### Can I use Aspose.Page for Java with other Java libraries?
Tak, Aspose.Page for Java jest zaprojektowany tak, aby współpracować bezproblemowo z innymi bibliotekami Java.

### Is there a free trial available for Aspose.Page for Java?
Tak, możesz uzyskać darmową wersję próbną [tutaj](https://releases.aspose.com/).

### Where can I find additional documentation?
Szczegółowa dokumentacja jest dostępna [tutaj](https://reference.aspose.com/page/java/).

### How can I purchase Aspose.Page for Java?
Możesz kupić Aspose.Page for Java [tutaj](https://purchase.aspose.com/buy).

### Is there a forum for Aspose.Page discussions?
Tak, możesz dołączyć do forum społeczności [tutaj](https://forum.aspose.com/c/page/39).

## Additional Frequently Asked Questions

**Q: Can I create other gradient directions (horizontal, diagonal)?**  
A: Oczywiście. Dostosuj punkty początkowy i końcowy w `LinearGradientPaint` oraz zmień kąt rotacji w `AffineTransform`.

**Q: Does this work with PDF output as well?**  
A: Ta sama logika gradientu może być zastosowana przy zapisie do PDF, używając `PdfSaveOptions` zamiast `PsSaveOptions`.

**Q: How do I change the gradient size dynamically?**  
A: Oblicz wymiary prostokąta w czasie wykonywania i przekaż te wartości zarówno do `Rectangle2D`, jak i do konstruktora `AffineTransform`.

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.Page for Java 24.11 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}