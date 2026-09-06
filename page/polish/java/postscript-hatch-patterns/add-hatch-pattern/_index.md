---
date: 2026-08-18
description: Dowiedz się, jak dodać wzór kreskowania do plików Java PostScript przy
  użyciu Aspose.Page Java. Ten przewodnik krok po kroku pokazuje kompletny kod i wskazówki.
keywords:
- how to add hatch pattern
- Aspose.Page Java
- PostScript hatch patterns
- Java graphics API
lastmod: 2026-08-18
linktitle: Dodaj wzór kreskowania w Java PostScript
og_description: Dowiedz się, jak dodać wzór kreskowania w Java PostScript przy użyciu
  Aspose.Page. Postępuj zgodnie z tym przewodnikiem krok po kroku, aby szybko tworzyć
  grafiki wypełnione kreskowaniem.
og_image_alt: Screenshot of Java code adding hatch pattern to a PostScript file with
  Aspose.Page
og_title: Jak dodać wzór kreskowania w Java PostScript – przewodnik Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to add hatch pattern to Java PostScript files using Aspose.Page
    Java. This step‑by‑step guide shows the complete code and tips.
  headline: How to add hatch pattern in Java PostScript
  type: TechArticle
- questions:
  - answer: Yes, the library is framework‑agnostic and works with Spring, Jakarta
      EE, Android (limited), and plain Java SE.
    question: Can I use Aspose.Page Java with other Java frameworks?
  - answer: Absolutely. Download a free 30‑day trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is a trial version available for Aspose.Page Java?
  - answer: Request a temporary license [temporary license request page](https://purchase.aspose.com/temporary-license/).
      It removes evaluation watermarks.
    question: How do I obtain a temporary license for development?
  - answer: Visit the official forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39)
      for additional examples and Q&A.
    question: Where can I find more tutorials and community support?
  - answer: Yes, the full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Is there comprehensive documentation for all classes and methods?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Java
- Aspose.Page
- PostScript
- hatch pattern
title: Jak dodać wzór kreskowania w Java PostScript
url: /pl/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dodać wzór kreskowy w Java PostScript

## Wprowadzenie
Jeśli pracujesz z **Aspose.Page Java** i zastanawiasz się **jak dodać wzór kreskowy** do swojego wyjścia PostScript, wzory kreskowe są szybkim i elastycznym rozwiązaniem. W tym samouczku przeprowadzimy Cię przez **dodawanie wzorów kreskowych** w dokumencie PostScript, wyjaśnimy, dlaczego są przydatne, i przedstawimy kompletny, gotowy do uruchomienia przykład kodu. Po zakończeniu będziesz w stanie tworzyć wizualnie atrakcyjne kształty i tekst wypełnione kreskami przy użyciu kilku linii Java.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebuję?** Aspose.Page for Java (SDK „aspose page java”).  
- **Jaki efekt wizualny dodajemy?** Wzory kreskowe (np. linie ukośne, krzyżowe).  
- **Czy potrzebna jest licencja do uruchomienia przykładu?** Darmowa wersja próbna działa w fazie rozwoju; licencja jest wymagana w produkcji.  
- **Ile linii kodu?** Około 70 linii, podzielonych na czytelne kroki.  
- **Czy mogę użyć tego samego podejścia dla PDF?** Tak — Aspose.Page obsługuje wiele formatów wyjściowych, w tym PDF.

## Czym jest wzór kreskowy?
Wzór kreskowy to wektorowe wypełnienie składające się z powtarzających się linii lub kształtów, które tworzą efekt tekstury. Ponieważ jest definiowany matematycznie, wzór skaluje się bez utraty jakości, co czyni go idealnym do druku wysokiej rozdzielczości i wyjścia monochromatycznego.

## Dlaczego używać wzorów kreskowych z Aspose.Page Java?
Aspose.Page obsługuje **ponad 10 formatów wyjściowych** (w tym PostScript, PDF, EPS, SVG i XPS) i może renderować wypełnienia kreskowe w dokumentach do **500 stron** bez ładowania całego pliku do pamięci. Oznacza to szybką wydajność, niski zużycie pamięci i spójne wyniki wizualne we wszystkich obsługiwanych formatach.

## Jak dodać wzór kreskowy – przegląd
Wzory kreskowe to wektorowe tekstury, które renderują się czysto przy każdej rozdzielczości i dobrze sprawdzają się na drukarkach monochromatycznych. Korzystając z Aspose.Page Java, możesz stosować te wzory do kształtów, ścieżek i nawet tekstu, nie zajmując się niskopoziomowymi poleceniami PostScript.

## Wymagania wstępne
Przed rozpoczęciem upewnij się, że masz:

- **Środowisko programistyczne Java** – JDK 8 lub wyższy oraz wybrane IDE.  
- **Aspose.Page for Java library** – Pobierz najnowszy plik JAR z oficjalnej **strony pobierania Aspose.Page for Java** [here](https://releases.aspose.com/page/java/).  
- Możesz również przeglądać inne wydania Aspose [here](https://releases.aspose.com/).  
- **Uprawnienia zapisu** do folderu, w którym zostanie zapisany wygenerowany plik PostScript.

## Importowanie pakietów
Importy poniżej obejmują standardowe klasy Java AWT dla prymitywów graficznych, takich jak kolory, pióra i kształty geometryczne, a także klasy Aspose.Page, które dostarczają model dokumentu, definicje stylów kreskowych oraz opcje zapisu niezbędne do wygenerowania pliku PostScript.  
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Czym jest klasa `Document`?
Klasa `Document` jest obiektem najwyższego poziomu w Aspose.Page, który reprezentuje pojedynczy plik PostScript w pamięci. Wszystkie operacje rysunkowe są wykonywane za pośrednictwem tego obiektu.

## Jak skonfigurować strumień wyjściowy?
Aby zapisać wynik, utwórz `FileOutputStream` wskazujący na żądaną ścieżkę pliku; strumień ten obsługuje niskopoziomowe zapisy bajtów. `PsSaveOptions` konfiguruje sposób zapisu dokumentu, w tym rozmiar strony i kompresję. Następnie zainicjuj `Document` z obiektem `PsSaveOptions`, który określa rozmiar strony, kompresję i inne ustawienia specyficzne dla PostScript.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## Jak zapisać stan grafiki i przetłumaczyć początek układu współrzędnych?
Zapisanie stanu grafiki przechwytuje bieżącą macierz przekształceń, obszar przycięcia i atrybuty rysowania, umożliwiając późniejsze przywrócenie. Po zapisaniu wywołaj `translate(x, y)` na obiekcie graficznym, aby przesunąć początek do wygodnego miejsca dla rysowania siatki kwadratów z kreskami.  
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Jak utworzyć wielokrotnego użytku kwadrat dla każdego wzoru?
`Rectangle2D` reprezentuje prostokątny kształt określony pozycją i rozmiarem. Tworząc jedną instancję odpowiadającą wymiarom komórki, możesz ją ponownie używać dla każdego kwadratu wypełnionego kreskami, zmniejszając alokację obiektów i utrzymując pętlę rysowania wydajną.  
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Jak ustawić pióro dla obrysu kwadratu wzoru?
`BasicStroke` opisuje grubość obrysu, wzór kreskowy i zakończenia dla wektorowych kształtów. Użycie pióra `BasicStroke` o grubości 2 punktów zapewnia wyraźną ramkę wokół każdego kwadratu wypełnionego kreskami, co sprawia, że wypełnienie jest wizualnie oddzielone od sąsiednich kwadratów.  
```java
BasicStroke stroke = new BasicStroke(2);
```

## Jak iterować przez wzory kreskowe?
`HatchStyle` jest wyliczeniem, które wymienia wszystkie predefiniowane wzory kreskowe, takie jak diagonalne, krzyżowe i kropkowane. Iteracja po `HatchStyle.values()` pozwala kolejno zastosować każdy wzór, wypełnić prostokąt `HatchBrush`, a następnie narysować jego obrys.  
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Jak przywrócić stan grafiki po rysowaniu?
Wywołanie `restore()` na obiekcie graficznym przywraca macierz przekształceń i ustawienia rysowania do stanu zapisanego wcześniej, zapobiegając kumulacji translacji lub skalowania, które mogłyby wpłynąć na kolejne operacje rysunkowe. Dzięki temu późniejsza zawartość zaczyna się od oryginalnego układu współrzędnych i używa domyślnych atrybutów.  
```java
document.writeGraphicsRestore();
```

## Jak wypełnić tekst wzorem kreskowym?
`TextFragment` reprezentuje fragment tekstu, który może być pozycjonowany i stylizowany niezależnie. Przypisując `HatchBrush` z wybranym `HatchStyle` do wypełnienia fragmentu, znaki tekstu są renderowane przy użyciu tekstury kreskowej zamiast jednolitego koloru.  
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Jak obrysować tekst innym stylem kreskowym?
`HatchBrush` może być również używany do rysowania obrysu. Aby narysować obrys, ustaw pióro fragmentu na `HatchBrush` z innym `HatchStyle` (np. 70 % kreskowanie) i zwiększ grubość pióra za pomocą `setStrokeWidth`. To renderuje granicę tekstu własnym wzorem kreskowym, zachowując wypełniony środek.  
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Jak zamknąć i zapisać dokument?
`document.save()` zapisuje dokument w pamięci do określonego strumienia wyjściowego. Po zakończeniu wszystkich poleceń rysunkowych wywołaj tę metodę, a następnie zamknij `FileOutputStream`, aby zwolnić zasoby systemowe i zapewnić prawidłowe zapisanie pliku na dysku.  
```java
document.closePage();
document.save();
```

Postępuj zgodnie z tymi krokami, a uzyskasz plik PostScript prezentujący pełny zestaw wzorów kreskowych zastosowanych zarówno do kształtów, jak i tekstu — wszystko napędzane przez **aspose page java**.

## Typowe pułapki i wskazówki
- **Błędy ścieżek plików** – Upewnij się, że `dataDir` kończy się odpowiednim separatorem plików (`/` lub `\`).  
- **Nieobsługiwane kolory** – Niektóre starsze interpretery PostScript mogą nie obsługiwać niektórych przestrzeni kolorów; trzymaj się podstawowego RGB dla maksymalnej kompatybilności.  
- **Ostrzeżenia licencyjne** – Uruchomienie przykładu bez ważnej licencji wstawi znak wodny do wyniku.

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.Page Java z innymi frameworkami Java?**  
A: Tak, biblioteka jest niezależna od frameworków i działa z Spring, Jakarta EE, Android (ograniczone) oraz czystym Java SE.

**Q: Czy dostępna jest wersja próbna Aspose.Page Java?**  
A: Oczywiście. Pobierz darmową 30‑dniową wersję próbną [Aspose trial download page](https://releases.aspose.com/).

**Q: Jak uzyskać tymczasową licencję do rozwoju?**  
A: Złóż wniosek o tymczasową licencję [temporary license request page](https://purchase.aspose.com/temporary-license/). Usunie ona znaki wodne oceny.

**Q: Gdzie mogę znaleźć więcej samouczków i wsparcie społeczności?**  
A: Odwiedź oficjalne forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) w celu uzyskania dodatkowych przykładów i pytań‑odpowiedzi.

**Q: Czy istnieje pełna dokumentacja wszystkich klas i metod?**  
A: Tak, pełna referencja API jest dostępna [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Czy mogę renderować ten sam wzór kreskowy do PDF zamiast PostScript?**  
A: Oczywiście. Zmień `PsSaveOptions` na `PdfSaveOptions` (lub ich odpowiednik), a reszta kodu pozostanie niezmieniona.

**Q: Co zrobić, gdy wygenerowany plik jest pusty?**  
A: Sprawdź, czy strumień wyjściowy wskazuje na zapisywalny katalog oraz czy `document.save()` jest wywoływane po wszystkich operacjach rysunkowych.

---

**Last Updated:** 2026-08-18  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## Powiązane samouczki

- [Utwórz wzór tekstury w PostScript – Aspose.Page Java](/page/java/postscript-texture-patterns/)
- [Jak dodać gradient: Gradient diagonalny w Java PostScript przy użyciu Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Jak przekonwertować PostScript na PDF przy użyciu Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}