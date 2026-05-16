---
date: 2026-02-15
description: Dowiedz się, jak dodać wzór kreskowania do plików PostScript w Javie
  przy użyciu Aspose.Page Java. Ten przewodnik krok po kroku pokazuje kompletny kod
  i wskazówki.
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: Jak dodać wzór kreskowania w Java PostScript przy użyciu Aspose.Page
url: /pl/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

 produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dodać wzór kreskowania w Java PostScript

## Wprowadzenie
Jeśli pracujesz z **Aspose.Page Java** i zastanawiasz się **jak dodać wzór kreskowania** do swojego wyjścia PostScript, wzory kreskowania są szybkim i elastycznym rozwiązaniem. W tym samouczku przeprowadzimy Cię przez **jak dodać wzory kreskowania** do dokumentu PostScript, wyjaśnimy, dlaczego są przydatne, i przedstawimy kompletny, gotowy do uruchomienia przykład kodu. Po zakończeniu będziesz w stanie tworzyć atrakcyjne wizualnie kształty i tekst wypełnione kreskami przy użyciu kilku linii Java.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebuję?** Aspose.Page for Java (the “aspose page java” SDK).  
- **Jaki efekt wizualny dodajemy?** Wzory kreskowania (np. linie ukośne, krzyżowe).  
- **Czy potrzebna jest licencja do uruchomienia przykładu?** Darmowa wersja próbna działa w środowisku deweloperskim; licencja jest wymagana w produkcji.  
- **Ile linii kodu?** Około 70 linii, podzielonych na przejrzyste kroki.  
- **Czy mogę użyć tego samego podejścia dla PDF‑ów?** Tak — Aspose.Page obsługuje wiele formatów wyjściowych, w tym PDF.

## Jak dodać wzór kreskowania — przegląd
Wzory kreskowania to tekstury wektorowe, które renderują się czysto przy każdej rozdzielczości i dobrze sprawdzają się na drukarkach monochromatycznych. Korzystając z Aspose.Page Java, możesz stosować te wzory do kształtów, ścieżek, a nawet tekstu, nie zajmując się niskopoziomowymi poleceniami PostScript.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

- **Środowisko programistyczne Java** – JDK 8 lub wyższy oraz wybrane IDE.  
- **Biblioteka Aspose.Page for Java** – Pobierz najnowszy plik JAR ze strony oficjalnej [tutaj](https://releases.aspose.com/page/java/).  
- **Uprawnienia zapisu** do folderu, w którym zostanie zapisany wygenerowany plik PostScript.

## Importowanie pakietów
Najpierw wprowadź wymagane klasy do swojego projektu. Te importy dają dostęp do prymitywów rysunkowych, obsługi kolorów i API Aspose.Page.

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

## Krok 1: Ustawienie początkowych parametrów
Utwórz strumień wyjściowy, skonfiguruj rozmiar strony (A4) i zdefiniuj kilka zmiennych układu, które będą ponownie używane przy rysowaniu każdego kwadratu wypełnionego kreskami.

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

## Krok 2: Zapisz stan graficzny i przesuń układ współrzędnych
Zapisanie stanu graficznego pozwala nam później wrócić do pierwotnego układu współrzędnych, natomiast `translate` przesuwa początek do wygodnego punktu startowego.

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Krok 3: Utwórz kwadrat dla każdego wzoru
Zdefiniuj wielokrotnego użytku prostokąt, który będzie reprezentował każdą komórkę wypełnioną kreskami.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Krok 4: Ustaw pióro dla obramowania kwadratu wzoru
`BasicStroke` o grubości 2 punktów zapewnia wyraźne obramowanie wokół każdego kwadratu.

```java
BasicStroke stroke = new BasicStroke(2);
```

## Krok 5: Iteracja przez wzory kreskowania
Przejdź przez każdą wartość w wyliczeniu `HatchStyle`, wypełnij każdy kwadrat odpowiadającą teksturą i narysuj jego obramowanie. To jest rdzeń funkcjonalności **dodawania wzoru kreskowania**.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Krok 6: Przywrócenie stanu graficznego
Wróć do pierwotnego układu współrzędnych po zakończeniu rysowania siatki kwadratów.

```java
document.writeGraphicsRestore();
```

## Krok 7: Wypełnienie tekstu wzorem kreskowania
Tutaj demonstrujemy, jak pomalować tekst przy użyciu tekstury kreskowania. Przykład wypełnia słowo „ABC” wzorem krzyżowo‑ukośnym.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Krok 8: Obramowanie tekstu wzorem kreskowania
Teraz obramowujemy ten sam tekst, ale tym razem używając stylu kreskowania 70 % i grubszego pióra.

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Krok 9: Zamknięcie i zapis dokumentu
Zakończ stronę, zapisz plik na dysku i zwolnij zasoby.

```java
document.closePage();
document.save();
```

Postępuj zgodnie z tymi krokami, a otrzymasz plik PostScript prezentujący pełny zestaw wzorów kreskowania zastosowanych zarówno do kształtów, jak i tekstu — wszystko napędzane przez **aspose page java**.

## Dlaczego używać wzorów kreskowania z Aspose.Page Java?
- **Wyróżnienie wizualne** – Wypełnienia kreskowane działają nawet przy drukarkach ograniczonych do wyjścia monochromatycznego.  
- **Wydajność** – Tekstury są generowane w locie, co eliminuje duże pliki graficzne.  
- **Wsparcie wielu formatów** – Ten sam kod może generować PDF, EPS lub SVG przy minimalnych zmianach.

## Częste problemy i wskazówki
- **Błędy ścieżek plików** – Upewnij się, że `dataDir` kończy się odpowiednim separatorem (`/` lub `\`).  
- **Nieobsługiwane kolory** – Niektóre starsze interpretery PostScript mogą nie obsługiwać niektórych przestrzeni kolorów; używaj podstawowego RGB dla maksymalnej kompatybilności.  
- **Ostrzeżenia licencyjne** – Uruchomienie przykładu bez ważnej licencji spowoduje dodanie znaku wodnego do wyniku.

## Zakończenie
Włączenie wzorów kreskowania może znacząco poprawić czytelność i estetykę rysunków technicznych, map czy dowolnych grafik generowanych w Javie. Z **Aspose.Page Java** otrzymujesz zwięzłe API, które abstrahuje niskopoziomowe polecenia PostScript, pozwalając skupić się na projekcie, a nie na szczegółach formatu. Teraz wiesz **jak dodać wzór kreskowania** do swoich dokumentów PostScript — eksperymentuj z różnymi wartościami `HatchStyle`, aby uzyskać dokładnie taki wygląd, jaki potrzebujesz.

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.Page Java z innymi frameworkami Java?**  
A: Tak, biblioteka jest niezależna od frameworków i działa z Spring, Jakarta EE, Android (ograniczone) oraz czystym Java SE.

**Q: Czy dostępna jest wersja próbna Aspose.Page Java?**  
A: Oczywiście. Pobierz darmową 30‑dniową wersję próbną [tutaj](https://releases.aspose.com/).

**Q: Jak uzyskać tymczasową licencję do rozwoju?**  
A: Poproś o tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/). Usunie ona znaki wodne z wersji ewaluacyjnych.

**Q: Gdzie mogę znaleźć więcej samouczków i wsparcia społeczności?**  
A: Odwiedź oficjalne forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) w celu uzyskania dodatkowych przykładów i pytań‑odpowiedzi.

**Q: Czy istnieje pełna dokumentacja wszystkich klas i metod?**  
A: Tak, pełna referencja API jest dostępna [tutaj](https://reference.aspose.com/page/java/).

**Q: Czy mogę renderować ten sam wzór kreskowania do PDF zamiast PostScript?**  
A: Oczywiście. Zmień `PsSaveOptions` na `PdfSaveOptions` (lub ich odpowiednik), a reszta kodu pozostaje niezmieniona.

**Q: Co zrobić, gdy wygenerowany plik jest pusty?**  
A: Sprawdź, czy strumień wyjściowy wskazuje na katalog z prawami zapisu oraz czy wywołano `document.save()` po wszystkich operacjach rysunkowych.

---

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}