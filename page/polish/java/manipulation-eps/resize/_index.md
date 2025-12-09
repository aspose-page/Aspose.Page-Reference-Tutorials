---
date: 2025-12-02
description: Dowiedz się, jak łatwo zmienić rozmiar plików EPS w Javie za pomocą Aspose.Page.
  Ten przewodnik krok po kroku pokazuje, jak zmieniać rozmiar EPS przy użyciu punktów,
  cali, milimetrów lub procentów.
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
Jeśli szukasz niezawodnego sposobu **jak zmienić rozmiar EPS** programowo, trafiłeś we właściwe miejsce. W tym samouczku przeprowadzimy Cię przez proces zmiany rozmiaru obrazów EPS w Javie przy użyciu biblioteki Aspose.Page. Niezależnie od tego, czy chcesz podwoić rozmiar, zmniejszyć go do określonego wymiaru, czy pracować w procentach, poniższe kroki dają pełną kontrolę nad wymiarami wyjściowymi.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebuję?** Aspose.Page for Java  
- **Czy mogę zmieniać rozmiar w punktach, calach lub milimetrach?** Tak – API obsługuje wszystkie trzy jednostki oraz procenty.  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna wystarczy do testów; licencja jest wymagana w produkcji.  
- **Jakiej wersji Javy potrzebuję?** Java 8 lub nowsza.  
- **Czy kod jest wątkowo‑bezpieczny?** Każda instancja `PsDocument` jest odizolowana, więc możesz przetwarzać pliki równolegle.

## Wymagania wstępne
Zanim przejdziesz do kodu, upewnij się, że masz następujące elementy:

- Zainstalowany Java Development Kit (JDK).  
- Bibliotekę Aspose.Page for Java. Możesz ją pobrać **[tutaj](https://releases.aspose.com/page/java/)**.  
- Podstawową znajomość programowania w Javie.  

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

## Jak zmienić rozmiar EPS używając punktów
Poniżej znajduje się kompletny, krok‑po‑kroku przykład, który podwaja rozmiar pliku EPS przy użyciu punktów jako jednostki miary.

### Krok 1: Ustawienie strumienia wejściowego
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Krok 2: Inicjalizacja obiektu `PsDocument`
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Krok 3: Pobranie bieżącego rozmiaru obrazu EPS
```java
Dimension oldSize = doc.extractEpsSize();
```

### Krok 4: Utworzenie strumienia wyjściowego dla zmienionego pliku
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Krok 5: Zmiana rozmiaru i zapis EPS przy użyciu punktów
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## Jak zmienić rozmiar EPS używając cali
Ten sam pięcio‑krokowy schemat ma zastosowanie; wystarczy zamienić `Units.Points` na `Units.Inches` i dostosować współczynnik skalowania w razie potrzeby.

## Jak zmienić rozmiar EPS używając milimetrów
Ponownie, postępuj według tych samych kroków, zamieniając jednostkę na `Units.Millimeters`. Jest to przydatne, gdy potrzebne są wymiary w systemie metrycznym dla procesów drukarskich.

## Jak zmienić rozmiar EPS używając procentów
Dla skalowania procentowego pozostaw jednostkę jako `Units.Percent`. Pomnóż oryginalną szerokość i wysokość przez żądany procent (np. `0.5` dla zmniejszenia o 50 %).

## Typowe pułapki i wskazówki
- **Zawsze zamykaj strumienie** – W kodzie produkcyjnym owijaj strumienie w `try‑with‑resources`, aby uniknąć blokad plików.  
- **Zachowaj proporcje** – Mnoż oba wymiary (szerokość i wysokość) tym samym współczynnikiem, chyba że celowo chcesz wprowadzić zniekształcenie.  
- **Sprawdź DPI** – Zmiana rozmiaru nie wpływa na DPI; jeśli potrzebujesz innego DPI, dostosuj je osobno po zmianie rozmiaru.

## Zakończenie
Teraz wiesz **jak zmienić rozmiar EPS** w Javie przy użyciu Aspose.Page, niezależnie od tego, czy preferujesz punkty, cale, milimetry czy procenty. Ta elastyczność pozwala zintegrować manipulację EPS z automatycznymi pipeline’ami, aplikacjami desktopowymi lub usługami po stronie serwera.

## Najczęściej zadawane pytania

**P: Czy mogę używać tej biblioteki do innych formatów obrazów?**  
O: Nie, Aspose.Page jest wyspecjalizowane wyłącznie w plikach PostScript i EPS.

**P: Czy dostępna jest darmowa wersja próbna Aspose.Page for Java?**  
O: Tak, możesz wypróbować darmową wersję **[tutaj](https://releases.aspose.com/)**.

**P: Gdzie mogę znaleźć dodatkową pomoc i dyskusje?**  
O: Odwiedź **[forum Aspose.Page](https://forum.aspose.com/c/page/39)**, aby uzyskać wsparcie społeczności.

**P: Jak mogę uzyskać tymczasową licencję?**  
O: Tymczasową licencję możesz pobrać **[tutaj](https://purchase.aspose.com/temporary-license/)**.

**P: Czy dostępne są przykładowe projekty?**  
O: Tak, sprawdź dokumentację **[tutaj](https://reference.aspose.com/page/java/)**.

---

**Ostatnia aktualizacja:** 2025-12-02  
**Testowano z:** Aspose.Page for Java 24.12 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}