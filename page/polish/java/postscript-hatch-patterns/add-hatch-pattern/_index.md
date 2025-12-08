---
date: 2025-12-08
description: „Dowiedz się, jak dodawać wzory kreskowania do dokumentów Java PostScript
  przy użyciu Aspose.Page Java. Ten przewodnik krok po kroku pokazuje, jak efektywnie
  dodawać grafikę z wzorami kreskowania.”
language: pl
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: 'Aspose.Page Java: Dodaj wzór kreskowy w Java PostScript'
url: /java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodawanie wzoru kreskowego w Java PostScript

## Wprowadzenie
Jeśli pracujesz z **Aspose.Page Java** i potrzebujesz wzbogacić wyjście PostScript o tekstury graficzne, wzory kreskowe są szybkim i elastycznym rozwiązaniem. W tym samouczku przeprowadzimy Cię krok po kroku **jak dodać wzory kreskowe** do dokumentu PostScript, wyjaśnimy, dlaczego są przydatne, i przedstawimy kompletny, gotowy do uruchomienia przykład kodu. Po zakończeniu będziesz w stanie tworzyć atrakcyjne wizualnie kształty i tekst wypełnione kreskami przy użyciu kilku linii Javy.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebuję?** Aspose.Page for Java (SDK „aspose page java”).  
- **Jaki efekt wizualny dodajemy?** Wzory kreskowe (np. linie ukośne, krzyżowe).  
- **Czy potrzebna jest licencja do uruchomienia przykładu?** Darmowa wersja próbna wystarczy do rozwoju; licencja jest wymagana w środowisku produkcyjnym.  
- **Ile linii kodu?** Około 70 linii, podzielonych na przejrzyste kroki.  
- **Czy mogę użyć tego samego podejścia dla PDF?** Tak — Aspose.Page obsługuje wiele formatów wyjściowych, w tym PDF.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

- **Środowisko programistyczne Java** – JDK 8 lub nowszy oraz wybrane IDE.  
- **Bibliotekę Aspose.Page for Java** – Pobierz najnowszy plik JAR z oficjalnej strony [tutaj](https://releases.aspose.com/page/java/).  
- **Uprawnienia do zapisu** w folderze, w którym zostanie zapisany wygenerowany plik PostScript.

## Importowanie pakietów
Najpierw dodaj wymagane klasy do swojego projektu. Te importy zapewniają dostęp do prymitywów rysunkowych, obsługi kolorów oraz API Aspose.Page.

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

## Krok 2: Zapisz stan grafiki i przesuń układ
Zapisanie stanu grafiki pozwala później powrócić do pierwotnego układu współrzędnych, a `translate` przesuwa początek do wygodnego punktu startowego.

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Krok 3: Utwórz kwadrat dla każdego wzoru
Zdefiniuj wielokrotnego użytku prostokąt, który będzie reprezentował każdą komórkę wypełnioną kreskami.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Krok 4: Ustaw pióro dla obrysu kwadratu wzoru
`BasicStroke` o grubości 2 punktów zapewnia wyraźny obrys wokół każdego kwadratu.

```java
BasicStroke stroke = new BasicStroke(2);
```

## Krok 5: Iteracja przez wzory kreskowe
Przejdź przez wszystkie wartości w wyliczeniu `HatchStyle`, wypełnij każdy kwadrat odpowiednią teksturą, a następnie narysuj jego obrys. To jest serce funkcjonalności **dodawania wzoru kreskowego**.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Krok 6: Przywrócenie stanu grafiki
Wróć do pierwotnego układu współrzędnych po zakończeniu rysowania siatki kwadratów.

```java
document.writeGraphicsRestore();
```

## Krok 7: Wypełnienie tekstu wzorem kreskowym
Tutaj pokazujemy, jak pomalować tekst przy użyciu tekstury kreskowej. Przykład wypełnia słowo „ABC” wzorem krzyżowym ukośnym.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Krok 8: Obrysowanie tekstu wzorem kreskowym
Teraz obrysowujemy ten sam tekst, ale używamy stylu kreskowego 70 % i grubszego pióra.

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

Postępuj zgodnie z tymi krokami, a otrzymasz plik PostScript prezentujący pełny zestaw wzorów kreskowych zastosowanych zarówno do kształtów, jak i tekstu — wszystko napędzane przez **aspose page java**.

## Dlaczego warto używać wzorów kreskowych z Aspose.Page Java?
- **Rozróżnienie wizualne** – Wypełnienia kreskowe działają nawet, gdy drukarki są ograniczone do wyjścia monochromatycznego.  
- **Wydajność** – Tekstury są generowane w locie, więc unikasz dużych plików graficznych.  
- **Obsługa wielu formatów** – Ten sam kod może celować w PDF, EPS lub SVG przy minimalnych zmianach.

## Częste pułapki i wskazówki
- **Błędy ścieżek plików** – Upewnij się, że `dataDir` kończy się odpowiednim separatorem (`/` lub `\`).  
- **Nieobsługiwane kolory** – Niektóre starsze interpretery PostScript mogą nie radzić sobie z niektórymi przestrzeniami kolorów; trzymaj się podstawowego RGB dla maksymalnej kompatybilności.  
- **Ostrzeżenia licencyjne** – Uruchomienie przykładu bez ważnej licencji spowoduje dodanie znaku wodnego do wyniku.

## Zakończenie
Włączenie wzorów kreskowych może znacząco poprawić czytelność i estetykę rysunków technicznych, map czy dowolnych grafik generowanych w Javie. Dzięki **Aspose.Page Java** otrzymujesz zwięzłe API, które abstrahuje niskopoziomowe polecenia PostScript, pozwalając skupić się na projekcie, a nie na szczegółach formatu pliku.

## Najczęściej zadawane pytania

**P: Czy mogę używać Aspose.Page Java z innymi frameworkami Java?**  
O: Tak, biblioteka jest niezależna od frameworków i działa z Spring, Jakarta EE, Android (z ograniczeniami) oraz czystym Java SE.

**P: Czy dostępna jest wersja próbna Aspose.Page Java?**  
O: Oczywiście. Pobierz darmową 30‑dniową wersję próbną [tutaj](https://releases.aspose.com/).

**P: Jak uzyskać tymczasową licencję do rozwoju?**  
O: Zamów tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/). Usunie ona znaki wodne z wersji ewaluacyjnej.

**P: Gdzie mogę znaleźć więcej samouczków i wsparcie społeczności?**  
O: Odwiedź oficjalne forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) w poszukiwaniu dodatkowych przykładów i pytań‑odpowiedzi.

**P: Czy istnieje pełna dokumentacja wszystkich klas i metod?**  
O: Tak, pełna referencja API jest dostępna [tutaj](https://reference.aspose.com/page/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2025-12-08  
**Testowano z:** Aspose.Page for Java 24.12 (najnowsza w momencie pisania)  
**Autor:** Aspose