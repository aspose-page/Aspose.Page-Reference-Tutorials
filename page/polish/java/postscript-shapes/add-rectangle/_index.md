---
date: 2025-12-11
description: Dowiedz się, jak rysować prostokątne kształty w Java PostScript przy
  użyciu Aspose.Page. Ten przewodnik krok po kroku pokazuje, jak ustawić farbę, ustawić
  kolor prostokąta w Javie oraz tworzyć żywe grafiki.
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: Jak narysować prostokąt w Java PostScript przy użyciu Aspose.Page
url: /pl/java/postscript-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak rysować prostokąt w Java PostScript przy użyciu Aspose.Page

## Introduction
Jeśli potrzebujesz **how to draw rectangle** kształtów wewnątrz pliku Java PostScript, trafiłeś we właściwe miejsce. W tym samouczku przeprowadzimy Cię przez użycie Aspose.Page for Java do dodawania kolorowych prostokątów, kontrolowania ich wypełnienia i obrysu oraz zapisywania wyniku jako dokumentu PostScript. Zobaczysz dokładnie **how to set paint**, jak zdefiniować geometrię prostokąta i dlaczego takie podejście jest idealne do programowego generowania grafiki do druku.

## Quick Answers
- **Jakiej biblioteki wymaga?** Aspose.Page for Java  
- **Czy mogę zmienić kolory prostokąta?** Tak – użyj `setPaint` z dowolnym `java.awt.Color`  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna działa do testów; licencja jest wymagana w produkcji  
- **Jaki rozmiar strony jest użyty w przykładzie?** A4 (domyślne `PsSaveOptions`)  
- **Czy kod jest kompatybilny z Java 8+?** Absolutnie – używa standardowych klas AWT  

## Prerequisites
Zanim zanurzysz się w samouczek, upewnij się, że masz spełnione następujące wymagania:
- Podstawowa znajomość programowania w języku Java.  
- Zainstalowana biblioteka Aspose.Page for Java. Jeśli nie, pobierz ją z [dokumentacji Aspose.Page for Java](https://reference.aspose.com/page/java/).  
- Środowisko programistyczne Java skonfigurowane na Twoim komputerze.

## Import Packages
W swoim projekcie Java rozpocznij od zaimportowania niezbędnych pakietów:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## How to Draw Rectangle in Java PostScript
Poniżej znajduje się kompletny przepływ pracy podzielony na przejrzyste kroki. Każdy krok zawiera krótkie wyjaśnienie, po którym następuje oryginalny blok kodu (bez zmian).

### Step 1: Set Paint for Filling Rectangle  
**How to set paint** – wybieramy pomarańczowy kolor wypełnienia dla pierwszego prostokąta.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Set paint for filling rectangle
document.setPaint(Color.ORANGE);        
// Fill the first rectangle
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```

### Step 2: Set Paint for Stroking Rectangle  
**Set rectangle color java** – teraz zmieniamy farbę na czerwony i definiujemy szerokość obrysu.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### Step 3: Close Current Page and Save Document  
Po narysowaniu zamykamy stronę i zapisujemy plik.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Why Use Aspose.Page for Rectangle Graphics?
- **Cross‑platform**: Generuje standardowy PostScript działający na każdej drukarce.  
- **Fine‑grained control**: Możesz niezależnie ustawiać kolory wypełnienia, kolory obrysu i szerokości linii.  
- **No external dependencies**: Używa wyłącznie wbudowanych klas geometrii AWT.  

## Common Issues & Tips
- **File path errors** – upewnij się, że `dataDir` kończy się separatorem plików (`/` lub `\\`).  
- **License exceptions** – wersja próbna dodaje znak wodny; uzyskaj pełną licencję do użytku produkcyjnego.  
- **Color visibility** – niektóre drukarki mogą inaczej interpretować niektóre wartości RGB; najpierw przetestuj prosty czarny prostokąt.

## Conclusion
W tym przewodniku pokazaliśmy, jak **how to draw rectangle** kształty w dokumencie Java PostScript, omówiliśmy **how to set paint** i pokazaliśmy, jak **set rectangle color java** przy użyciu Aspose.Page. Śmiało eksperymentuj z różnymi kształtami, kolorami i stylami linii, aby tworzyć bogatą grafikę do druku dla raportów, faktur lub własnych wydruków.

## Frequently Asked Questions

### Can I use Aspose.Page for Java with other programming languages?
Aspose.Page głównie obsługuje Javę, ale podobne biblioteki są dostępne dla innych języków.

### Is there a trial version of Aspose.Page for Java available?
Tak, możesz przetestować funkcje Aspose.Page for Java za pomocą [free trial version](https://releases.aspose.com/).

### Where can I find additional help and discussions?
Odwiedź [Aspose.Page forum](https://forum.aspose.com/c/page/39), aby dołączyć do społeczności i uzyskać pomoc.

### How can I obtain a temporary license for Aspose.Page for Java?
Uzyskaj tymczasową licencję [here](https://purchase.aspose.com/temporary-license/).

### Where can I purchase a licensed version of Aspose.Page for Java?
Kup licencjonowaną wersję [here](https://purchase.aspose.com/buy).

**Additional Q&A**

**Q:** *Can I change the rectangle size dynamically?*  
**A:** Yes – simply modify the `Rectangle2D.Float(x, y, width, height)` parameters before calling `fill` or `draw`.

**Q:** *Is it possible to add text inside the rectangle?*  
**A:** Absolutely. After drawing the rectangle, use `document.drawString(...)` with the desired font and position.

**Q:** *Does Aspose.Page support other shapes like circles or polygons?*  
**A:** Yes, the API provides methods such as `drawEllipse` and `drawPolygon` for a variety of vector graphics.

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}