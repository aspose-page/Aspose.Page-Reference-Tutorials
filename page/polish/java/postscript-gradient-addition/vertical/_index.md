---
date: 2026-02-13
description: Dowiedz się, jak tworzyć gradienty PostScript w Javie przy użyciu Aspose.Page.
  Ten przewodnik krok po kroku pokazuje, jak łatwo dodać pionowy gradient do dokumentów
  PostScript.
linktitle: Add Vertical Gradient in Java PostScript
second_title: Aspose.Page Java API
title: Utwórz gradient PostScript w Javie – Dodaj gradient pionowy
url: /pl/java/postscript-gradient-addition/vertical/
weight: 14
---

 heading same but translate.

## Introduction -> "Wprowadzenie"

... translate paragraph.

Let's translate step by step.

I'll produce final content now.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz gradient PostScript w Javie – Dodaj pionowy gradient

## Wprowadzenie
W tym kompleksowym samouczku dowiesz się, jak **utworzyć gradient PostScript w Javie** przy użyciu Aspose.Page for Java. Dodanie pionowego gradientu może sprawić, że Twoje dokumenty będą wyglądały bardziej żywo i profesjonalnie, a przy kilku linijkach kodu osiągniesz oszałamiające efekty wizualne. Przeprowadzimy Cię przez każdy krok, wyjaśnimy, dlaczego każdy element ma znaczenie, i podamy praktyczne wskazówki, aby uniknąć typowych pułapek. Po zakończeniu tego przewodnika będziesz w stanie generować pliki PostScript z płynnymi, przyciągającymi wzrok pionowymi przejściami kolorów.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebuję?** Aspose.Page for Java  
- **Czy mogę dostosować kolory?** Tak, można użyć dowolnego `java.awt.Color`  
- **Czy obsługiwana jest rotacja?** Tak, gradient można obrócić przy użyciu `AffineTransform`  
- **Jaki format wyjściowy jest generowany?** Standardowy plik PostScript (.ps)  
- **Czy potrzebna jest licencja do produkcji?** Tak, wymagana jest licencja komercyjna  

## Dlaczego dodać pionowy gradient do dokumentu PostScript?
Pionowe gradienty nadają Twoim stronom głębi bez zwiększania rozmiaru pliku. Są idealne do:

* Nagłówków lub stopek raportów, które potrzebują subtelnego tła.  
* Wyróżniania sekcji w podręcznikach technicznych lub białych księgach.  
* Zapewniania nowoczesnego wyglądu wykresom, diagramom lub ulotkom promocyjnym.

Ponieważ gradient jest definiowany w formie wektorowej, wynik pozostaje ostry przy każdej rozdzielczości.

## Wymagania wstępne
Zanim przejdziesz do samouczka, upewnij się, że masz spełnione następujące wymagania:
- Zainstalowany Java Development Kit (JDK).  
- Biblioteka Aspose.Page for Java. Możesz ją pobrać [tutaj](https://releases.aspose.com/page/java/).

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

## Jak utworzyć gradient PostScript w Javie
Poniżej znajduje się przewodnik krok po kroku, który dokładnie pokazuje, jak **utworzyć gradient PostScript w Javie** przy użyciu API Aspose.Page.

### Krok 1: Skonfiguruj katalog dokumentu
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Krok 2: Utwórz strumień wyjściowy dla dokumentu PostScript
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### Krok 3: Utwórz opcje zapisu z rozmiarem A4
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### Krok 4: Utwórz nowy dokument PS
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Krok 5: Utwórz prostokąt
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### Krok 6: Ustaw kolory i frakcje dla gradientu
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### Krok 7: Utwórz transformację gradientu
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### Krok 8: Utwórz pionowy gradient liniowy
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### Krok 9: Ustaw farbę i wypełnij prostokąt
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### Krok 10: Zamknij bieżącą stronę i zapisz dokument
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Gratulacje! Pomyślnie dodałeś pionowy gradient do swojego dokumentu PostScript w Javie przy użyciu Aspose.Page for Java.

## Typowe problemy i rozwiązania
- **Gradient wydaje się płaski:** Upewnij się, że skalowanie w `AffineTransform` odpowiada wymiarom prostokąta.  
- **Kolory wyglądają wyblakłe:** Sprawdź, czy używasz właściwego `ColorSpaceType` (SRGB) oraz czy tablica frakcji jest uporządkowana od 0.0 do 1.0.  
- **Plik nie został wygenerowany:** Zweryfikuj, czy katalog wyjściowy (`dataDir`) istnieje i aplikacja ma uprawnienia do zapisu.  

## Najczęściej zadawane pytania
### Czy mogę używać Aspose.Page for Java z innymi bibliotekami Java?
Tak, Aspose.Page for Java jest zaprojektowany tak, aby współpracować bezproblemowo z innymi bibliotekami Java.

### Czy dostępna jest darmowa wersja próbna Aspose.Page for Java?
Tak, darmową wersję próbną można uzyskać [tutaj](https://releases.aspose.com/).

### Gdzie mogę znaleźć dodatkową dokumentację?
Szczegółowa dokumentacja jest dostępna [tutaj](https://reference.aspose.com/page/java/).

### Jak mogę kupić Aspose.Page for Java?
Zakup Aspose.Page for Java można zrealizować [tutaj](https://purchase.aspose.com/buy).

### Czy istnieje forum dyskusyjne dotyczące Aspose.Page?
Tak, możesz dołączyć do forum społeczności [tutaj](https://forum.aspose.com/c/page/39).

## Dodatkowe często zadawane pytania

**P: Czy mogę tworzyć gradienty w innych kierunkach (poziome, diagonalne)?**  
O: Oczywiście. Dostosuj punkty początkowe i końcowe w `LinearGradientPaint` oraz zmień kąt rotacji w `AffineTransform`.

**P: Czy to działa również przy zapisie do PDF?**  
O: Ta sama logika gradientu może być zastosowana przy zapisie do PDF, używając `PdfSaveOptions` zamiast `PsSaveOptions`.

**P: Jak dynamicznie zmienić rozmiar gradientu?**  
O: Oblicz wymiary prostokąta w czasie wykonywania i przekaż te wartości zarówno do `Rectangle2D`, jak i do konstruktora `AffineTransform`.

---

**Ostatnia aktualizacja:** 2026-02-13  
**Testowano z:** Aspose.Page for Java 24.11 (najnowsza)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}