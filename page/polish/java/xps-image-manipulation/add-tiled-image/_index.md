---
date: 2026-05-30
description: Dowiedz się, jak utworzyć dokument XPS w Javie przy użyciu Aspose.Page
  i dodać tiled image bez wysiłku dzięki temu przewodnikowi krok po kroku. Jak szybko
  tworzyć pliki XPS.
keywords:
- how to create xps
- add tiled image java
- Aspose.Page XPS tutorial
linktitle: Dodaj tiled image w Java XPS
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  headline: How to Create XPS Document with a Tiled Image in Java
  type: TechArticle
- description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  name: How to Create XPS Document with a Tiled Image in Java
  steps:
  - name: Set Up Your Project
    text: Add the Aspose.Page JAR files to your project’s classpath and verify the
      import statements compile without errors.
  - name: Create XPS Document
    text: '`XpsDocument` is the core container that holds pages, paths, and resources.
      Instantiate it with the desired page size, then you can start adding graphical
      elements.'
  - name: Define the Tiled Image Path
    text: Place the image you want to tile (e.g., `R08LN_NN.jpg`) inside the directory
      referenced by `dataDir`. The image will be used as a brush pattern.
  - name: Add Tiled Image
    text: Create a rectangular path and fill it with an `XpsImageBrush`. By setting
      the tile mode to `Tile`, the image repeats across the rectangle. Adjust the
      source and destination rectangles to control tile size and positioning.
  - name: Save the Document
    text: Persist the XPS file to disk. The output file will contain the tiled image
      you just defined and can be opened with any XPS viewer. Repeat these steps whenever
      you need to **add tiled image** to other pages or shapes within the same XPS
      document.
  type: HowTo
- questions:
  - answer: It provides a high‑level API to generate and manipulate XPS documents
      in Java.
    question: What does Aspose.Page do?
  - answer: Yes – use `XpsImageBrush` with `XpsTileMode.Tile`.
    question: Can I tile an image?
  - answer: A temporary or commercial license is required for production use.
    question: Do I need a license?
  - answer: Any JDK 8+ is compatible.
    question: What Java version is supported?
  - answer: Roughly 10–15 minutes for a basic tiled‑image scenario.
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.Page Java API
title: Jak utworzyć dokument XPS z tiled image w Javie
url: /pl/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć dokument XPS z obrazem kafelkowanym w Javie

## Wstęp
Tworzenie dokumentów XPS programowo jest podstawową umiejętnością dla programistów Java, którzy potrzebują wydrukowalnego, niezależnego od urządzenia wyjścia. **Jak tworzyć pliki XPS** efektywnie odpowiada Aspose.Page for Java, które ukrywa szczegóły niskopoziomowej specyfikacji XML Paper Specification i pozwala skupić się na projekcie wizualnym. W tym przewodniku zobaczysz dokładnie, jak utworzyć dokument XPS, dodać obraz kafelkowany jako tło lub wzór oraz zapisać wynik — wszystko przy użyciu zwięzłego, gotowego do produkcji kodu.

## Szybkie odpowiedzi
- **Co robi Aspose.Page?** Zapewnia wysokopoziomowe API do generowania i manipulowania dokumentami XPS w Javie.  
- **Czy mogę kafelkować obraz?** Tak – użyj `XpsImageBrush` z `XpsTileMode.Tile`.  
- **Czy potrzebna jest licencja?** Wymagana jest tymczasowa lub komercyjna licencja do użytku produkcyjnego.  
- **Jaką wersję Javy obsługuje?** Każdy JDK 8+ jest kompatybilny.  
- **Jak długo trwa implementacja?** Około 10–15 minut dla podstawowego scenariusza z obrazem kafelkowanym.

## Co oznacza „utworzyć dokument XPS”?
`XpsDocument` jest obiektem najwyższego poziomu Aspose.Page, który reprezentuje pojedynczy plik XPS w pamięci. Zawiera strony, zasoby i metadane, umożliwiając programowe budowanie dokumentu. Utworzenie dokumentu XPS oznacza zainicjowanie tej klasy, dodanie elementów wizualnych i ostateczne wywołanie `save`, aby zapisać plik o stałym układzie na dysku. Takie podejście eliminuje ręczną obsługę XML i zapewnia zgodność ze specyfikacją XML Paper Specification.

## Dlaczego dodać obraz kafelkowany?
Kafelkowanie powiela grafikę w określonym obszarze, co jest idealne dla teł, znaków wodnych lub wypełnień wzorem. Używając `XpsTileMode.Tile` obraz powtarza się automatycznie bez ręcznego duplikowania, co oszczędza czas programisty i zapewnia spójne renderowanie na każdym urządzeniu. Obrazy kafelkowane także utrzymują mały rozmiar pliku, ponieważ ten sam zasób bitmapy jest ponownie wykorzystywany, a nie osadzany wielokrotnie.

## Wymagania wstępne
Zanim zanurzysz się w temat, upewnij się, że masz:

1. **Java Development Kit (JDK)** – zainstalowany JDK 8 lub nowszy.  
2. **Aspose.Page for Java** – pobierz ze [strony internetowej](https://releases.aspose.com/page/java/).  
3. **Katalog zapisu** – miejsce, w którym zostanie zapisany wygenerowany plik XPS.

## Importowanie pakietów
W swoim projekcie Java zaimportuj niezbędne klasy:

`XpsDocument` jest głównym obiektem reprezentującym plik XPS.  
`XpsImageBrush` maluje kształty przy użyciu źródła obrazu.  
`XpsTileMode` określa sposób kafelkowania obrazu.  
`Rectangle2D` opisuje prostokątny obszar pozycjonowania.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Przewodnik krok po kroku

### Krok 1: Konfiguracja projektu
Dodaj pliki JAR Aspose.Page do classpath swojego projektu i sprawdź, czy instrukcje importu kompilują się bez błędów.

### Krok 2: Utworzenie dokumentu XPS
`XpsDocument` jest podstawowym kontenerem, który przechowuje strony, ścieżki i zasoby. Zainicjuj go z żądanym rozmiarem strony, a następnie możesz zaczynać dodawać elementy graficzne.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Krok 3: Definicja ścieżki obrazu kafelkowanego
Umieść obraz, który chcesz kafelkować (np. `R08LN_NN.jpg`) w katalogu wskazywanym przez `dataDir`. Obraz zostanie użyty jako wzorzec pędzla.

### Krok 4: Dodanie obrazu kafelkowanego
Utwórz prostokątną ścieżkę i wypełnij ją `XpsImageBrush`. Ustawiając tryb kafelkowania na `Tile`, obraz powtarza się w całym prostokącie. Dostosuj prostokąty źródłowy i docelowy, aby kontrolować rozmiar i pozycję kafelków.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### Krok 5: Zapis dokumentu
Zachowaj plik XPS na dysku. Plik wyjściowy będzie zawierał właśnie zdefiniowany obraz kafelkowany i będzie można go otworzyć w dowolnej przeglądarce XPS.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Powtarzaj te kroki, gdy będziesz musiał **dodać obraz kafelkowany** do innych stron lub kształtów w tym samym dokumencie XPS.

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|---------|-------------|
| Obraz się nie wyświetla | Sprawdź, czy ścieżka do pliku (`dataDir + "R08LN_NN.jpg"`) jest prawidłowa i czy obraz jest dostępny. |
| Wzór kafelkowy jest rozciągnięty | Dostosuj wartości `Rectangle2D` źródłowego i docelowego, aby kontrolować rozmiar kafelka. |
| Przezroczystość nie działa | Upewnij się, że przezroczystość pędzla jest ustawiona **po** skonfigurowaniu trybu kafelkowania. |

## Najczęściej zadawane pytania

**Q:** Czy Aspose.Page jest kompatybilny ze wszystkimi wersjami Javy?  
**A:** Aspose.Page obsługuje Java 8 do Java 21; pełną matrycę kompatybilności znajdziesz [tutaj](https://reference.aspose.com/page/java/).

**Q:** Czy mogę używać Aspose.Page w projektach komercyjnych?  
**A:** Tak, do użytku produkcyjnego wymagana jest licencja komercyjna. Opcje zakupu są wymienione [tutaj](https://purchase.aspose.com/buy).

**Q:** Czy dostępna jest darmowa wersja próbna?  
**A:** Pełnoprawna darmowa wersja próbna może zostać pobrana ze strony wydania Aspose [tutaj](https://releases.aspose.com/).

**Q:** Gdzie mogę uzyskać wsparcie społeczności?  
**A:** Dołącz do forum społeczności Aspose.Page pod adresem [forum](https://forum.aspose.com/c/page/39), aby zadawać pytania i dzielić się przykładami.

**Q:** Jak uzyskać tymczasową licencję do oceny?  
**A:** Tymczasowe licencje są udostępniane na żądanie poprzez portal Aspose [tutaj](https://purchase.aspose.com/temporary-license/).

## Zakończenie
Masz teraz kompletny, gotowy do produkcji proces **tworzenia dokumentów XPS** z obrazami kafelkowanymi przy użyciu Aspose.Page for Java. Dzięki wykorzystaniu `XpsImageBrush` i `XpsTileMode.Tile` możesz generować bogatą, powtarzalną grafikę bez zwiększania rozmiaru pliku. Eksperymentuj z różnymi rozmiarami kafelków, poziomami przezroczystości i kształtami, aby tworzyć zaawansowane układy dokumentów. Następnie spróbuj dodać kształty wektorowe lub nakładki tekstowe, aby jeszcze bardziej wzbogacić swoje pliki XPS.

---

**Ostatnia aktualizacja:** 2026-05-30  
**Testowano z:** Aspose.Page for Java 24.12 (latest)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [How to Add Image to Java XPS Documents – A Simple Guide with Aspose.Page](/page/java/xps-image-manipulation/add-image/)
- [Aspose.Page Java - Add Pages to XPS Tutorial](/page/java/xps-page-manipulation/add-page/)
- [Convert XPS to PDF in Java using Aspose.Page Java](/page/java/file-merging/xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}