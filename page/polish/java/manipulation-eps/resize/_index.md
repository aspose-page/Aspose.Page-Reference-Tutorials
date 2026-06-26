---
date: 2026-02-07
description: Dowiedz się, jak zmienić rozmiar plików EPS w Javie i zmienić wymiary
  EPS przy użyciu Aspose.Page. Ten przewodnik krok po kroku pokazuje, jak zmieniać
  rozmiar EPS za pomocą punktów, cali, milimetrów lub procentów.
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: Jak zmienić rozmiar plików EPS w Javie przy użyciu Aspose.Page
url: /pl/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak zmienić rozmiar plików EPS w Javie przy użyciu Aspose.Page

## Wprowadzenie
Jeśli szukasz niezawodnego sposobu **how to resize EPS** na programowe zmienianie rozmiaru plików EPS, trafiłeś we właściwe miejsce. W tym samouczku przeprowadzimy Cię przez proces zmiany rozmiaru obrazów EPS w Javie przy użyciu biblioteki Aspose.Page. Niezależnie od tego, czy potrzebujesz podwoić rozmiar, zmniejszyć go do określonego wymiaru, czy pracować w procentach, poniższe kroki dają pełną kontrolę nad wymiarami wyjściowymi. Zrozumienie **how to resize eps** jest niezbędne, gdy musisz dostosować grafikę do różnych układów druku lub rozdzielczości ekranu.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebujesz?** Aspose.Page for Java  
- **Czy mogę zmieniać rozmiar używając punktów, cali lub milimetrów?** Tak – API obsługuje wszystkie trzy jednostki oraz procenty.  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna działa do testów; licencja jest wymagana w produkcji.  
- **Jaka wersja Javy jest wymagana?** Java 8 lub nowsza.  
- **Czy kod jest bezpieczny wątkowo?** Każda instancja `PsDocument` jest odizolowana, więc możesz przetwarzać pliki równolegle.  

## Co to jest EPS i dlaczego zmieniać jego rozmiar?
Encapsulated PostScript (EPS) to popularny format grafiki wektorowej używany w publikacji i druku. Czasami oryginalny plik EPS jest tworzony w rozmiarze, który nie odpowiada docelowemu wyjściu – na przykład logo zaprojektowane w 72 pt może wymagać 144 pt dla większej broszury. Znajomość **how to resize eps** pozwala zachować jakość wektorową przy dostosowywaniu wymiarów do dowolnego przepływu pracy.

## Dlaczego używać Aspose.Page do zmiany rozmiaru EPS?
- **Pełna kontrola nad jednostkami** – punkty, cale, milimetry lub procenty.  
- **Brak zewnętrznych zależności** – czyste API Java, bez bibliotek natywnych.  
- **Wysoka wydajność** – odpowiednia do przetwarzania wsadowego na serwerach.  
- **Zachowuje wierność wektora** – wynik pozostaje skalowalny bez rasteryzacji.

## Wymagania wstępne
Zanim przejdziemy do kodu, upewnij się, że masz następujące elementy:

- Java Development Kit (JDK) zainstalowany na Twoim komputerze.  
- Biblioteka Aspose.Page for Java. Możesz ją pobrać **[here](https://releases.aspose.com/page/java/)**.  
- Podstawowa znajomość programowania w Javie.  

## Importowanie pakietów
W swoim projekcie Java dołącz wymagane importy, aby móc pracować z obiektami Aspose.Page oraz standardowymi strumieniami I/O.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## Jak zmienić wymiary EPS przy użyciu różnych jednostek
Biblioteka pozwala **change eps dimensions** po prostu poprzez wybranie odpowiedniego wyliczenia `Units`. Poniżej przeprowadzimy Cię przez ten sam pięcioetapowy schemat dla punktów, cali, milimetrów i procentów. Jedyną zmianą jest jednostka przekazywana do `resizeEps`.

## Jak zmienić rozmiar EPS używając punktów
Poniżej znajduje się kompletny, krok po kroku przykład, który podwaja rozmiar pliku EPS używając punktów jako jednostki miary.

### Krok 1: Przygotuj strumień wejściowy
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Krok 2: Zainicjalizuj obiekt `PsDocument`
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Krok 3: Pobierz aktualny rozmiar obrazu EPS
```java
Dimension oldSize = doc.extractEpsSize();
```

### Krok 4: Utwórz strumień wyjściowy dla zmienionego pliku
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Krok 5: Zmień rozmiar i zapisz EPS używając punktów
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## Jak zmienić rozmiar EPS używając cali
Ten sam pięcioetapowy schemat ma zastosowanie; wystarczy zamienić `Units.Points` na `Units.Inches` i dostosować współczynnik skalowania do żądanej wartości w calach.

## Jak zmienić rozmiar EPS używając milimetrów
Ponownie, postępuj zgodnie z tymi samymi krokami, zamieniając jednostkę na `Units.Millimeters`. Jest to przydatne, gdy potrzebne są wymiary w systemie metrycznym dla procesów drukowania.

## Jak zmienić rozmiar EPS używając procentów
Dla skalowania opartego na procentach, pozostaw jednostkę jako `Units.Percent`. Pomnóż oryginalną szerokość i wysokość przez żądany procent (np. `0.5` dla zmniejszenia o 50 %).

## Częste pułapki i wskazówki
- **Zawsze zamykaj strumienie** – W kodzie produkcyjnym owiń strumienie w try‑with‑resources, aby uniknąć blokad plików.  
- **Zachowaj proporcje** – Pomnóż zarówno szerokość, jak i wysokość tym samym współczynnikiem, chyba że celowo chcesz wprowadzić zniekształcenie.  
- **Sprawdź DPI** – Zmiana rozmiaru nie zmienia DPI; jeśli potrzebujesz innego DPI, dostosuj je osobno po zmianie rozmiaru.  
- **Bezpieczeństwo wątków** – Utwórz nowy `PsDocument` dla każdego wątku; współdzielenie tej samej instancji może prowadzić do nieoczekiwanych rezultatów.  

## Najczęściej zadawane pytania

**Q: Czy mogę używać tej biblioteki do innych formatów obrazów?**  
A: Nie, Aspose.Page jest specjalizowany wyłącznie w plikach PostScript i EPS.

**Q: Czy dostępna jest darmowa wersja próbna Aspose.Page for Java?**  
A: Tak, możesz wypróbować darmową wersję **[here](https://releases.aspose.com/)**.

**Q: Gdzie mogę znaleźć dodatkową pomoc i dyskusje?**  
A: Odwiedź **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**, aby uzyskać wsparcie społeczności.

**Q: Jak mogę uzyskać tymczasową licencję?**  
A: Tymczasową licencję możesz uzyskać **[here](https://purchase.aspose.com/temporary-license/)**.

**Q: Czy dostępne są przykładowe projekty?**  
A: Tak, sprawdź dokumentację **[here](https://reference.aspose.com/page/java/)**.

---

**Last Updated:** 2026-02-07  
**Testowano z:** Aspose.Page for Java 24.12 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}