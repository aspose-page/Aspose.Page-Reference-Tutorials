---
date: 2026-09-09
description: Dowiedz się, jak stworzyć radial gradient w Java PostScript przy użyciu
  Aspose.Page. Ten przewodnik krok po kroku pokazuje, jak dodać color stops gradient,
  ustawić radii i szybko wygenerować plik PS.
keywords:
- how to create radial gradient
- add color stops gradient
- Aspose.Page Java
- Java PostScript gradient
- radial gradient tutorial
lastmod: 2026-09-09
linktitle: Opanowanie radial gradients w Java
og_description: Dowiedz się, jak stworzyć radial gradient w Java PostScript przy użyciu
  Aspose.Page. Ten przewodnik wyjaśnia, jak dodać color stops gradient, ustawić radii
  i wygenerować plik PS w kilka minut.
og_image_alt: Guide showing how to add a radial gradient to a Java PostScript file
  with Aspose.Page
og_title: Jak stworzyć radial gradient w Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  headline: How to create radial gradient in Java PostScript
  type: TechArticle
- description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  name: How to create radial gradient in Java PostScript
  steps:
  - name: create a rectangle and open a PS document
    text: '`PsDocument` is Aspose.Page''s class that represents a PostScript document
      and provides methods to draw shapes, text, and images. We start by creating
      an output stream, configuring the page size (A4 by default), and defining a
      rectangle that will host the gradient. > **Pro tip:** Adjust the rectangle'
  - name: define colors and fractions
    text: 'A radial gradient is built from *color stops* (the colors) and *fractions*
      (the relative positions of those stops). Here we create an array of six colors
      and their corresponding fractions. > **Why this matters:** By tweaking `fractions`
      you control how quickly the colors transition, enabling subtle '
  - name: create radial gradient paint
    text: '`RadialGradientPaint` is the core class that describes a radial color gradient,
      including center point, radius, focus point, fractions, colors, cycle method,
      and color space. Now we build the `RadialGradientPaint` object using the arrays
      defined above. > **Note:** `transform` can be `null` if you do'
  - name: set paint and fill the rectangle
    text: With the paint ready, we tell the `PsDocument` to use it and then fill the
      rectangle we defined earlier. At this point the PostScript page contains a rectangle
      smoothly filled with the radial gradient we configured.
  - name: close and save the document
    text: Finally, close the current page and write the file to disk. Open `RadialGradient1_outPS.ps`
      in any PostScript viewer (e.g., Ghostscript) and you’ll see the gradient rendered
      exactly as defined.
  type: HowTo
- questions:
  - answer: Yes. A commercial license is required for production use. You can purchase
      one from the [Aspose licensing page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for Java in commercial projects?
  - answer: The full documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find the official API reference?
  - answer: Absolutely. Download a trial version from the [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is a free trial available for testing?
  - answer: A temporary license can be requested from the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Join the Aspose.Page community forum at [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- radial gradient
- Aspose.Page
- Java PostScript
- gradient programming
- color stops
title: Jak stworzyć radial gradient w Java PostScript
url: /pl/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć gradient promienisty w Java PostScript przy użyciu Aspose.Page

## Wprowadzenie
Jeśli potrzebujesz **utworzyć gradient promienisty** w pliku PostScript, trafiłeś we właściwe miejsce. W tym samouczku przeprowadzimy Cię przez każdy krok niezbędny do wygenerowania dokumentu PostScript zawierającego płynny gradient promienisty, przy użyciu **Aspose.Page for Java**. Po zakończeniu zrozumiesz API, zobaczysz kompletny działający przykład i będziesz wiedział, jak dostosować kolory, pozycje i promienie dla dowolnego scenariusza projektowego.

## Szybkie odpowiedzi
- **Jaką bibliotekę tworzy gradienty promieniste w PostScript?** Aspose.Page for Java.  
- **Jak długo trwa implementacja?** Około 10‑15 minut dla podstawowego przykładu.  
- **Czy potrzebuję licencji, aby uruchomić kod?** Darmowa wersja próbna działa w fazie rozwoju; licencja komercyjna jest wymagana w produkcji.  
- **Która wersja Java jest obsługiwana?** Java 8 lub wyższa.  
- **Czy mogę zmienić kształt gradientu?** Tak – dostosuj promień i punkt centralny w konstruktorze `RadialGradientPaint`.

## Jak utworzyć gradient promienisty w Java

Załaduj swój projekt Java, zaimportuj wymagane klasy i postępuj zgodnie z poniższym przewodnikiem krok po kroku. Główna odpowiedź polega na tym, że tworzysz instancję `RadialGradientPaint` z określonymi punktami kolorów, a następnie stosujesz ją do prostokąta rysowanego na `PsDocument`. To podejście dwuelementowe obsługuje wszystkie niskopoziomowe polecenia PostScript za Ciebie.

## Czym jest gradient promienisty?
`RadialGradientPaint` jest klasą Java AWT, która definiuje okrągłe przejście kolorów od punktu centralnego na zewnątrz. Tworzy płynne przejście wielu punktów kolorów, co czyni go idealnym do reflektorów, miękkich teł lub każdego efektu, w którym kolory promieniują z punktu ogniskowego.

## Dlaczego używać Aspose.Page do gradientów promienistych?
Aspose.Page daje pełną kontrolę programistyczną nad wyjściem PostScript, jednocześnie zajmując się ciężarem niskopoziomowej składni PS. Obsługuje **ponad 50 formatów wejścia i wyjścia**, może renderować dokumenty wielostronicowe bez ładowania całego pliku do pamięci i działa na każdym systemie operacyjnym wspierającym Java 8+. Ta wymierna zdolność czyni go niezawodnym wyborem dla generowania grafiki klasy korporacyjnej.

## Wymagania wstępne
- **Java Development Kit (JDK) 8+** – sprawdź poleceniem `java -version`.  
- **Aspose.Page for Java** – pobierz najnowszy JAR z oficjalnej [Aspose.Page download page](https://releases.aspose.com/page/java/).  
- **IDE według własnego wyboru** – Eclipse, IntelliJ IDEA lub VS Code z rozszerzeniami Java.  
- **Folder zapisywalny** – miejsce, w którym zostanie zapisany wygenerowany plik `.ps`.

## Import pakietów
Najpierw zaimportuj potrzebne klasy. Pakiet `java.awt` dostarcza obiekty gradientu, natomiast `com.aspose.eps` zawiera klasy obsługujące dokumenty PostScript.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Przewodnik krok po kroku

### Krok 1: utwórz prostokąt i otwórz dokument PS
Klasa `PsDocument` z Aspose.Page reprezentuje dokument PostScript i udostępnia metody do rysowania kształtów, tekstu i obrazów. Zaczynamy od utworzenia strumienia wyjściowego, skonfigurowania rozmiaru strony (domyślnie A4) i zdefiniowania prostokąta, który będzie zawierał gradient.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **Wskazówka:** Dostosuj współrzędne prostokąta (`200, 100, 200, 200`), aby umieścić gradient w dowolnym miejscu na stronie.

### Krok 2: zdefiniuj kolory i frakcje
Gradient promienisty jest budowany z *punktów kolorów* (colors) i *frakcji* (relative positions). Tutaj tworzymy tablicę sześciu kolorów i ich odpowiadających frakcji.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Dlaczego to ma znaczenie:** Modyfikując `fractions`, kontrolujesz tempo przejścia kolorów, co umożliwia subtelne lub dramatyczne efekty.

### Krok 3: utwórz obiekt RadialGradientPaint
Klasa `RadialGradientPaint` jest podstawową klasą opisującą radialny gradient kolorów, w tym punkt środkowy, promień, punkt ogniskowy, frakcje, kolory, metodę cyklu i przestrzeń kolorów. Teraz budujemy obiekt `RadialGradientPaint` przy użyciu wcześniej zdefiniowanych tablic.

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **Uwaga:** `transform` może być `null`, jeśli nie potrzebujesz dodatkowego skalowania lub rotacji. Śmiało eksperymentuj z `AffineTransform`, aby uzyskać pochyłe gradienty.

### Krok 4: ustaw farbę i wypełnij prostokąt
Gdy farba jest gotowa, instruujemy `PsDocument`, aby jej użył, a następnie wypełniamy wcześniej zdefiniowany prostokąt.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

W tym momencie strona PostScript zawiera prostokąt płynnie wypełniony gradientem promienistym, który skonfigurowałeś.

### Krok 5: zamknij i zapisz dokument
Na koniec zamykamy bieżącą stronę i zapisujemy plik na dysku.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Otwórz `RadialGradient1_outPS.ps` w dowolnym przeglądarce PostScript (np. Ghostscript) i zobaczysz gradient wyświetlony dokładnie tak, jak został zdefiniowany.

## Typowe problemy i rozwiązania
| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|-------|--------------------------|------------|
| Gradient wyświetla się jako jednolity kolor | tablica `fractions` nie zaczyna się od `0.0f` ani nie kończy na `1.0f` | Upewnij się, że pierwsza frakcja to `0.0f`, a ostatnia to `1.0f`. |
| Kolory wyglądają na wyblakłe | użycie niewłaściwego `ColorSpaceType` | Przełącz na `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB`, aby uzyskać bardziej żywe wyjście. |
| Nie wygenerowano pliku wyjściowego | ścieżka `FileOutputStream` jest nieprawidłowa lub nie ma uprawnień do zapisu | Sprawdź, czy `dataDir` istnieje i aplikacja ma uprawnienia do zapisu. |

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.Page for Java w projektach komercyjnych?**  
A: Tak. Licencja komercyjna jest wymagana do użycia w produkcji. Możesz ją zakupić na [stronie licencjonowania Aspose](https://purchase.aspose.com/buy).

**Q: Gdzie mogę znaleźć oficjalną dokumentację API?**  
A: Pełna dokumentacja jest dostępna [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Czy dostępna jest darmowa wersja próbna do testów?**  
A: Oczywiście. Pobierz wersję próbną z [strony wydań Aspose.Page](https://releases.aspose.com/).

**Q: Jak uzyskać tymczasową licencję do oceny?**  
A: Tymczasową licencję można zamówić na [stronie żądania tymczasowej licencji](https://purchase.aspose.com/temporary-license/).

**Q: Gdzie mogę uzyskać wsparcie społeczności?**  
A: Dołącz do forum społeczności Aspose.Page pod adresem [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## Podsumowanie
Teraz wiesz **jak utworzyć gradient promienisty** w dokumencie Java PostScript przy użyciu Aspose.Page. Dostosowując rozmiar prostokąta, punkty kolorów i promień gradientu, możesz tworzyć niezliczone efekty wizualne — od subtelnych wypełnień tła po wyraziste efekty świetlne. Śmiało eksperymentuj z różnymi wartościami `AffineTransform`, aby obracać lub pochylać gradient, oraz łącz tę technikę z tekstem i obrazami, aby uzyskać bogatsze wyjścia PDF lub EPS.

---

**Last Updated:** 2026-09-09  
**Tested With:** Aspose.Page for Java latest (as of writing)  
**Author:** Aspose

## Powiązane samouczki

- [Wypełnij kształt gradientem: Przykład radialny Java PostScript](/page/java/postscript-gradient-addition/radial2/)
- [Utwórz gradient PostScript w Java — Dodaj gradient pionowy](/page/java/postscript-gradient-addition/vertical/)
- [Samouczek przezroczystości Aspose.Page — Dodaj przezroczystość w Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}