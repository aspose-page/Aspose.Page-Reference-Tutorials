---
date: 2026-09-14
description: Dowiedz się, jak stworzyć gradient PostScript w Java przy użyciu Aspose.Page.
  Ten przewodnik krok po kroku pokazuje, jak dodać gradient pionowy do pliku PostScript
  w zaledwie kilku wierszach kodu Java.
keywords:
- create postscript gradient java
- vertical gradient java
- aspose.page gradient
- postscript graphics java
- java postscript tutorial
lastmod: 2026-09-14
linktitle: Dodaj gradient pionowy w Java PostScript
og_description: Dowiedz się, jak stworzyć gradient PostScript w Java przy użyciu Aspose.Page.
  Ten przewodnik krok po kroku pokazuje, jak dodać gradient pionowy do pliku PostScript
  w zaledwie kilku wierszach kodu Java.
og_image_alt: Tutorial showing how to create a vertical PostScript gradient in Java
  using Aspose.Page
og_title: Tworzenie gradientu PostScript w Java – gradient pionowy
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  headline: Create postscript gradient java – vertical gradient
  type: TechArticle
- description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  name: Create postscript gradient java – vertical gradient
  steps:
  - name: set up your document directory
    text: '`File` objects represent the folder where the output will be written. The
      directory must exist before the stream is opened, otherwise an `IOException`
      is thrown.'
  - name: create output stream for PostScript document
    text: '`FileOutputStream` writes the binary PostScript data to disk. Using a `try‑with‑resources`
      block guarantees that the stream is closed even if an exception occurs.'
  - name: create save options with A4 size
    text: '`PsSaveOptions` lets you specify page size, DPI, and whether to embed fonts.
      Setting the size to A4 (595 × 842 points) matches most printable documents.'
  - name: create a new PS document
    text: '`Document` is the top‑level object that represents a single PostScript
      file in memory. All drawing commands are issued against this object.'
  - name: create a rectangle
    text: '`Rectangle2D.Double` defines the area that will be filled with the gradient.
      The rectangle’s coordinates are expressed in points (1 point = 1/72 inch).'
  - name: set up colors and fractions for the gradient
    text: A `float[]` array defines the position of each color stop (from 0.0 to 1.0).
      `Color` objects hold the actual RGB values. You can use any `java.awt.Color`
      you like.
  - name: create the gradient transform
    text: '`AffineTransform` scales and rotates the gradient. For a pure vertical
      gradient you only need to scale the Y‑axis; rotation can be added later if desired.'
  - name: create vertical linear gradient paint
    text: '`LinearGradientPaint` ties together the rectangle, the color stops, and
      the transform. This object is later passed to the graphics context.'
  - name: set paint and fill the rectangle
    text: '`Graphics2D.setPaint` applies the gradient, and `fill` renders it inside
      the rectangle you defined earlier.'
  - name: close current page and save the document
    text: Calling `document.save` writes the entire PostScript stream to the output
      file and releases all native resources. Congratulations! You’ve successfully
      added a vertical gradient to your Java PostScript document using Aspose.Page
      for Java.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly alongside other
      Java libraries such as Apache Commons or Spring.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can get a free trial [free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Detailed documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: You can purchase Aspose.Page for Java [Aspose.Page purchase page](https://purchase.aspose.com/buy).
    question: How can I purchase Aspose.Page for Java?
  - answer: Yes, you can join the community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Is there a forum for Aspose.Page discussions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- postscript gradient
- aspose.page
- java graphics
- vertical gradient
- document processing
title: Tworzenie gradientu PostScript w Java – gradient pionowy
url: /pl/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz gradient postscript w Java – gradient pionowy

## Wprowadzenie
Aspose.Page for Java to biblioteka umożliwiająca programowe tworzenie i manipulację plikami PostScript i PDF. W tym kompleksowym samouczku nauczysz się, jak **create postscript gradient java** przy użyciu tej biblioteki. Dodanie pionowego gradientu może sprawić, że Twoje dokumenty będą wyglądały bardziej żywo i profesjonalnie, a przy kilku linijkach kodu osiągniesz oszałamiające efekty wizualne. Przeprowadzimy Cię krok po kroku, wyjaśnimy, dlaczego każdy element ma znaczenie, i podamy praktyczne wskazówki, aby uniknąć typowych pułapek. Po zakończeniu tego przewodnika będziesz w stanie generować pliki PostScript z płynnymi, przyciągającymi wzrok pionowymi przejściami kolorów.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebujesz?** Aspose.Page for Java  
- **Czy mogę dostosować kolory?** Tak, można użyć dowolnego `java.awt.Color`  
- **Czy obsługiwana jest rotacja?** Tak, możesz obrócić gradient przy użyciu `AffineTransform`  
- **Jaki format wyjściowy jest generowany?** Standardowy plik PostScript (.ps)  
- **Czy potrzebna jest licencja do produkcji?** Tak, wymagana jest licencja komercyjna  

## Dlaczego dodać pionowy gradient do dokumentu PostScript?
Dodanie pionowego gradientu nadaje Twoim stronom głębię, poprawia hierarchię wizualną i utrzymuje niewielki rozmiar pliku, ponieważ gradient jest definiowany w formie wektorowej, a nie jako obrazy rastrowe. Ta technika jest idealna dla nagłówków raportów, podręczników technicznych lub wszelkich ulotek, które potrzebują nowoczesnego wyglądu bez utraty skalowalności.

## Prerequisites
Zanim zanurzysz się w samouczek, upewnij się, że spełniasz następujące wymagania:
- Zainstalowany Java Development Kit (JDK) na Twoim komputerze.  
- Biblioteka Aspose.Page for Java. Możesz ją pobrać ze [strony wydania Aspose.Page for Java](https://releases.aspose.com/page/java/).

## Importowanie pakietów
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

Teraz przejdźmy krok po kroku przez proces dodawania pionowego gradientu.

## Jak utworzyć gradient postscript w Java
Załaduj środowisko Java, utwórz instancję `PsSaveOptions` i wywołaj `Document.save` – to podstawowa sekwencja, która tworzy plik PostScript z pionowym gradientem. API zajmuje się interpolacją kolorów, przekształceniami współrzędnych i zapisem stron, więc musisz skupić się jedynie na zdefiniowaniu prostokąta i parametrów gradientu.

### Krok 1: skonfiguruj katalog dokumentu
Obiekty `File` reprezentują folder, w którym zostanie zapisany wynik. Katalog musi istnieć przed otwarciem strumienia, w przeciwnym razie zostanie zgłoszony `IOException`.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Krok 2: utwórz strumień wyjściowy dla dokumentu PostScript
`FileOutputStream` zapisuje binarne dane PostScript na dysku. Użycie bloku `try‑with‑resources` zapewnia zamknięcie strumienia nawet w przypadku wystąpienia wyjątku.
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### Krok 3: utwórz opcje zapisu z rozmiarem A4
`PsSaveOptions` pozwala określić rozmiar strony, DPI oraz czy osadzać czcionki. Ustawienie rozmiaru na A4 (595 × 842 punktów) odpowiada większości dokumentów do druku.
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### Krok 4: utwórz nowy dokument PS
`Document` jest obiektem najwyższego poziomu, który reprezentuje pojedynczy plik PostScript w pamięci. Wszystkie polecenia rysowania są wydawane na tym obiekcie.
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Krok 5: utwórz prostokąt
`Rectangle2D.Double` definiuje obszar, który zostanie wypełniony gradientem. Współrzędne prostokąta wyrażane są w punktach (1 punkt = 1/72 cala).
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### Krok 6: skonfiguruj kolory i frakcje dla gradientu
Tablica `float[]` definiuje pozycję każdego punktu kolorowego (od 0.0 do 1.0). Obiekty `Color` przechowują rzeczywiste wartości RGB. Możesz użyć dowolnego `java.awt.Color`, jaki chcesz.
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### Krok 7: utwórz transformację gradientu
`AffineTransform` skaluje i obraca gradient. Dla czystego pionowego gradientu potrzebujesz jedynie skalowania osi Y; rotację można dodać później, jeśli jest potrzebna.
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### Krok 8: utwórz pionowy gradient liniowy
`LinearGradientPaint` łączy prostokąt, punkty kolorowe i transformację. Ten obiekt jest później przekazywany do kontekstu graficznego.
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### Krok 9: ustaw farbę i wypełnij prostokąt
`Graphics2D.setPaint` stosuje gradient, a `fill` renderuje go wewnątrz wcześniej zdefiniowanego prostokąta.
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### Krok 10: zamknij bieżącą stronę i zapisz dokument
Wywołanie `document.save` zapisuje cały strumień PostScript do pliku wyjściowego i zwalnia wszystkie zasoby natywne.
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Gratulacje! Pomyślnie dodałeś pionowy gradient do swojego dokumentu PostScript w Java przy użyciu Aspose.Page for Java.

## Typowe problemy i rozwiązania
- **Gradient wygląda płasko:** Upewnij się, że skalowanie `AffineTransform` odpowiada wymiarom prostokąta.  
- **Kolory wyglądają wyblakłe:** Sprawdź, czy używasz właściwego `ColorSpaceType` (SRGB) i czy tablica frakcji jest uporządkowana od 0.0 do 1.0.  
- **Plik nie został wygenerowany:** Sprawdź, czy katalog wyjściowy (`dataDir`) istnieje i aplikacja ma uprawnienia do zapisu.  

## Najczęściej zadawane pytania

**P: Czy mogę używać Aspose.Page for Java z innymi bibliotekami Java?**  
Tak, Aspose.Page for Java jest zaprojektowany tak, aby współpracować bezproblemowo z innymi bibliotekami Java, takimi jak Apache Commons czy Spring.

**P: Czy dostępna jest darmowa wersja próbna Aspose.Page for Java?**  
Tak, możesz uzyskać darmową wersję próbną na [stronie pobierania wersji próbnej](https://releases.aspose.com/).

**P: Gdzie mogę znaleźć dodatkową dokumentację?**  
Szczegółowa dokumentacja jest dostępna w [referencji API Aspose.Page Java](https://reference.aspose.com/page/java/).

**P: Jak mogę kupić Aspose.Page for Java?**  
Możesz zakupić Aspose.Page for Java na [stronie zakupu Aspose.Page](https://purchase.aspose.com/buy).

**P: Czy istnieje forum dyskusyjne Aspose.Page?**  
Tak, możesz dołączyć do forum społeczności [forum społeczności Aspose.Page](https://forum.aspose.com/c/page/39).

## Dodatkowe często zadawane pytania

**P: Czy mogę tworzyć gradienty w innych kierunkach (poziomy, diagonalny)?**  
Oczywiście. Dostosuj punkty początkowe i końcowe w `LinearGradientPaint` oraz zmień kąt obrotu w `AffineTransform`.

**P: Czy to działa również przy wyjściu PDF?**  
Ta sama logika gradientu może być zastosowana przy zapisie do PDF, używając `PdfSaveOptions` zamiast `PsSaveOptions`.

**P: Jak dynamicznie zmienić rozmiar gradientu?**  
Oblicz wymiary prostokąta w czasie wykonywania i przekaż te wartości zarówno do konstruktora `Rectangle2D`, jak i `AffineTransform`.

---

**Last Updated:** 2026-09-14  
**Tested With:** Aspose.Page for Java 24.11 (latest)  
**Author:** Aspose

## Powiązane samouczki

- [Utwórz gradient radialny w PostScript przy użyciu Aspose.Page for Java](/page/java/postscript-gradient-addition/)
- [Jak skonwertować PostScript do PDF przy użyciu Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [Samouczek przezroczystości Aspose.Page – Dodaj przezroczystość w Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}