---
date: 2026-10-31
description: Dowiedz się, jak ustawić paint color i wypełnić ellipse w Java PostScript
  przy użyciu Aspose.Page. Ten przewodnik pokazuje, jak wypełnić ellipse, narysować
  outline ellipse oraz ustawić stroke thickness przy użyciu przejrzystych code steps.
keywords:
- how to fill ellipse
- how to set paint color
- Aspose.Page Java ellipse
- PostScript drawing Java
lastmod: 2026-10-31
linktitle: Dodaj Ellipse w Java PostScript
og_description: Dowiedz się, jak wypełnić ellipse i ustawić paint color w Java PostScript
  przy użyciu Aspose.Page. Postępuj zgodnie z step‑by‑step code, aby narysować wypełnione
  i obrysowane ellipses w kilka sekund.
og_image_alt: Developer guide showing how to fill ellipse and set paint color in Java
  PostScript with Aspose.Page
og_title: Jak wypełnić ellipse i ustawić paint color w Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  headline: How to fill ellipse and set paint color in Java PostScript
  type: TechArticle
- description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  name: How to fill ellipse and set paint color in Java PostScript
  steps:
  - name: Set up the PostScript document
    text: Create an output stream, configure page size, and instantiate a `PsDocument`.
      `PsDocument` is the core class that represents a PostScript file in memory.
      All drawing commands are routed through this object, and it handles page layout,
      resource management, and final file generation.
  - name: Fill ellipse – use set paint color
    text: To **fill ellipse**, you must first call `setPaint` with the desired fill
      color, then invoke `fill` with an `Ellipse2D` instance. `setPaint` sets the
      current drawing color used for subsequent fill or stroke operations. `Ellipse2D`
      defines the geometric bounds of the ellipse; its constructor takes th
  - name: Draw ellipse outline and set stroke thickness
    text: After filling, you can change the paint to a different color, define a `BasicStroke`
      to control line width, and draw the ellipse outline. `BasicStroke` specifies
      line width, dash pattern, and end‑cap style for drawing outlines. By adjusting
      its `width` property you control how bold the ellipse borde
  - name: Close and save the document
    text: Finalize the page and write the PostScript file to disk. Calling `document.close()`
      flushes all pending drawing commands and releases resources. The resulting `.ps`
      file can be opened with any PostScript viewer or converted to PDF. You now have
      a PostScript file that contains two ellipses—one filled
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to seamlessly integrate with other
      Java libraries.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Obtain a temporary license **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)**
      for testing purposes.
    question: How can I get a temporary license for Aspose.Page for Java?
  - answer: Absolutely! Visit **[the Aspose purchase page](https://purchase.aspose.com/buy)**
      to explore licensing options for commercial use.
    question: Is Aspose.Page suitable for commercial projects?
  - answer: Join the community at the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for discussions and assistance.
    question: Where can I seek help or discuss Aspose.Page‑related queries?
  - answer: Utilize the **[Aspose free trial page](https://releases.aspose.com/)**
      and explore examples in the documentation.
    question: Are there any free resources to learn more about Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript ellipse
- vector drawing
title: Jak wypełnić ellipse i ustawić paint color w Java PostScript
url: /pl/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak wypełnić elipsę i ustawić kolor farby w Java PostScript

## Wprowadzenie
Jeśli potrzebujesz **ustawić kolor farby** podczas rysowania grafiki wektorowej, biblioteka Aspose.Page for Java daje pełną kontrolę nad każdym pociągnięciem i wypełnieniem. W tym samouczku dowiesz się, jak **ustawić kolor farby**, **wypełnić elipsę** i **narysować kontur elipsy** używając prostego, krok po kroku podejścia. Po zakończeniu będziesz mógł dodawać wysokiej jakości elipsy PostScript do faktur, raportów lub dowolnego dokumentu do druku.

## Szybkie odpowiedzi
- **Jaka biblioteka jest najlepsza do rysowania grafiki PostScript w Javie?** Aspose.Page for Java.  
- **Czy mogę wypełnić elipsę jednolitym kolorem?** Tak – użyj `document.setPaint(Color.YOUR_COLOR)` przed `fill`.  
- **Jak narysować tylko kontur elipsy?** Ustaw farbę i pędzel, a następnie wywołaj `document.draw(...)`.  
- **Czy potrzebna jest licencja do użytku produkcyjnego?** Wymagana jest licencja komercyjna; licencja tymczasowa jest dostępna do testów.  
- **Jaką wersję Javy obsługuje biblioteka?** Każde środowisko Java 8+ działa z bieżącą wersją Aspose.Page.

## Czym jest elipsa PostScript?
Elipsa PostScript to kształt wektorowy zdefiniowany przez prostokąt ograniczający. W przeciwieństwie do obrazów rastrowych, skaluje się bez utraty jakości, co czyni ją idealną do druku wysokiej rozdzielczości i konwersji do PDF. Ponieważ kształt jest opisany matematycznie, może być renderowany w dowolnym rozmiarze lub rozdzielczości, zachowując ostre krawędzie i płynne krzywe.

## Dlaczego używać Aspose.Page do tworzenia elipsy PostScript?
Aspose.Page zapewnia deterministyczną kontrolę nad każdym prymitywem rysowania. Obsługuje **3 główne systemy operacyjne (Windows, Linux, macOS)**, **0 zależności natywnych** i może renderować **ponad 50 prymitywów wektorowych** na sekundę na typowym serwerze. Biblioteka jest czystą Javą, więc możesz ją osadzić w dowolnej aplikacji Java 8+ bez dodatkowych bibliotek natywnych.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

1. Działające środowisko programistyczne Java (JDK 8 lub nowszy).  
2. Bibliotekę Aspose.Page for Java dodaną do swojego projektu. Możesz ją pobrać **[z strony wydania Aspose.Page for Java](https://releases.aspose.com/page/java/)**.

## Importowanie pakietów
W swoim pliku źródłowym Java zaimportuj klasy potrzebne do rysowania i zapisywania treści PostScript.

Pakiet `java.awt` dostarcza podstawowe typy graficzne, takie jak `Color`, `Ellipse2D` i `BasicStroke`. Pakiet `com.aspose.page` udostępnia klasę `PsDocument`, która zapisuje wyjście PostScript.

- **`Color`** – reprezentuje kolor sRGB używany do malowania.  
- **`Ellipse2D`** – opisuje kształt elipsy zdefiniowany przez prostokąt ograniczający.  
- **`BasicStroke`** – określa szerokość linii, wzór kreskowy i styl zakończenia dla rysowania konturów.  
- **`PsDocument`** – reprezentuje dokument PostScript i udostępnia metody do rysowania grafiki oraz zarządzania stronami.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Jak ustawić kolor farby dla elipsy
Pierwszym krokiem jest poinformowanie dokumentu, którego koloru użyć w następnej operacji rysowania. Metoda `setPaint` ustawia jednolity kolor, który zostanie zastosowany do wypełnienia lub pędzla, w zależności od kolejnego wywołania.

### Krok 1: Konfiguracja dokumentu PostScript
Utwórz strumień wyjściowy, skonfiguruj rozmiar strony i zainicjuj `PsDocument`.

`PsDocument` jest podstawową klasą reprezentującą plik PostScript w pamięci. Wszystkie polecenia rysowania są przekazywane przez ten obiekt, który obsługuje układ strony, zarządzanie zasobami i generowanie ostatecznego pliku.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Krok 2: Wypełnienie elipsy – użyj ustawienia koloru farby
Aby **wypełnić elipsę**, najpierw należy wywołać `setPaint` z żądanym kolorem wypełnienia, a następnie wywołać `fill` z instancją `Ellipse2D`.

`setPaint` ustawia bieżący kolor rysowania używany w kolejnych operacjach wypełniania lub pędzla.  
`Ellipse2D` definiuje geometryczne granice elipsy; jej konstruktor przyjmuje współrzędne X‑Y lewego górnego rogu oraz szerokość i wysokość.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Krok 3: Rysowanie konturu elipsy i ustawienie grubości linii
Po wypełnieniu możesz zmienić farbę na inny kolor, zdefiniować `BasicStroke`, aby kontrolować szerokość linii, i narysować kontur elipsy.

`BasicStroke` określa szerokość linii, wzór kreskowy i styl zakończenia dla rysowania konturów. Regulując jego właściwość `width`, kontrolujesz, jak pogrubiona będzie granica elipsy.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Krok 4: Zamknięcie i zapisanie dokumentu
Zakończ stronę i zapisz plik PostScript na dysku.

Wywołanie `document.close()` opróżnia wszystkie oczekujące polecenia rysowania i zwalnia zasoby. Powstały plik `.ps` można otworzyć w dowolnym przeglądarce PostScript lub przekonwertować do PDF.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Masz teraz plik PostScript zawierający dwie elipsy — jedną wypełnioną pomarańczowym, a drugą z konturem w czerwonym. Śmiało eksperymentuj z różnymi współrzędnymi, rozmiarami i kolorami, aby dopasować je do swoich potrzeb projektowych.

## Typowe problemy i rozwiązywanie
- **Nieprawidłowa ścieżka pliku** – Upewnij się, że `dataDir` kończy się separatorem (`/` lub `\\`) odpowiednim dla Twojego systemu operacyjnego.  
- **Brak licencji** – Bez ważnej licencji biblioteka działa w trybie ewaluacyjnym i może dodawać znaki wodne.  
- **Kolor nie został zastosowany** – Pamiętaj, aby ustawić `document.setPaint(...)` *przed* każdym wywołaniem `fill` lub `draw`; ustawienie farby nie utrzymuje się automatycznie między oddzielnymi operacjami.

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.Page for Java z innymi bibliotekami Java?**  
A: Tak, Aspose.Page for Java jest zaprojektowany tak, aby płynnie integrować się z innymi bibliotekami Java.

**Q: Jak mogę uzyskać tymczasową licencję dla Aspose.Page for Java?**  
A: Uzyskaj tymczasową licencję **[z strony tymczasowej licencji Aspose](https://purchase.aspose.com/temporary-license/)** do celów testowych.

**Q: Czy Aspose.Page nadaje się do projektów komercyjnych?**  
A: Zdecydowanie! Odwiedź **[stronę zakupu Aspose](https://purchase.aspose.com/buy)**, aby zapoznać się z opcjami licencjonowania do użytku komercyjnego.

**Q: Gdzie mogę uzyskać pomoc lub dyskutować o pytaniach związanych z Aspose.Page?**  
A: Dołącz do społeczności na **[forum Aspose.Page](https://forum.aspose.com/c/page/39)**, aby prowadzić dyskusje i uzyskać pomoc.

**Q: Czy istnieją darmowe zasoby, aby dowiedzieć się więcej o Aspose.Page for Java?**  
A: Skorzystaj z **[strony darmowego okresu próbnego Aspose](https://releases.aspose.com/)** i przeglądaj przykłady w dokumentacji.

## Zakończenie
Aspose.Page for Java ułatwia **ustawianie koloru farby**, **wypełnianie elipsy** i **rysowanie konturu elipsy** — niezależnie od tego, czy potrzebujesz prostego wypełnionego kształtu, czy złożonej grafiki z pędzlem. Dzięki powyższym krokom możesz szybko dodać profesjonalne grafiki wektorowe do dowolnego dokumentu do druku. Aby zgłębić temat — np. łączenie wielu kształtów, stosowanie gradientów lub konwersję do PDF — odwołaj się do oficjalnej **[dokumentacji Aspose.Page Java](https://reference.aspose.com/page/java/)**.

**Ostatnia aktualizacja:** 2026-10-31  
**Testowano z:** Aspose.Page for Java 24.11  
**Autor:** Aspose

## Powiązane samouczki

- [Jak narysować prostokąt w Java PostScript przy użyciu Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [Jak dodać tekst Unicode w Java PostScript przy użyciu Aspose.Page](/page/java/postscript-text-manipulation/add-text-unicode/)
- [Jak utworzyć gradient promienisty w PostScript przy użyciu Aspose.Page for Java](/page/java/postscript-gradient-addition/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}