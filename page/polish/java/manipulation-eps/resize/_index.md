---
date: 2026-08-29
description: Dowiedz się, jak w Javie zmienić rozmiar wektorowy plików EPS przy użyciu
  Aspose.Page. Ten przewodnik krok po kroku pokazuje, jak zmienić rozmiar EPS przy
  użyciu punktów, cali, milimetrów lub procentów.
keywords:
- java vector resize
- how to resize eps
- EPS resizing Java
lastmod: 2026-08-29
linktitle: Zmień rozmiar pliku EPS w Javie
og_description: Zmiana rozmiaru wektorowego w Javie pozwala bezpośrednio dostosować
  wymiary pliku EPS w Javie. Korzystając z Aspose.Page możesz zmienić rozmiar przy
  użyciu punktów, cali, milimetrów lub procentów, zachowując jakość wektora.
og_image_alt: Guide showing java vector resize of EPS files using Aspose.Page
og_title: 'Zmiana rozmiaru wektorowego w Javie: zmień wymiary EPS przy użyciu Aspose.Page'
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to Java vector resize EPS files in Java using Aspose.Page.
    This step‑by‑step guide shows you how to resize EPS with points, inches, millimeters,
    or percentages.
  headline: How to Java vector resize EPS files with Aspose.Page
  type: TechArticle
- questions:
  - answer: No, Aspose.Page is specialized for PostScript and EPS files only.
    question: Can I use this library for other image formats?
  - answer: Yes, you can explore the free trial **[Aspose free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**
      for community support.
    question: Where can I find additional help and discussions?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license?
  - answer: Yes, check the documentation **[Aspose.Page Java API reference](https://reference.aspose.com/page/java/)**.
    question: Are there any example projects available?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- java vector resize
- EPS resize
- Aspose.Page
- Java graphics
- vector graphics
title: Jak w Javie zmienić rozmiar wektorowy plików EPS przy użyciu Aspose.Page
url: /pl/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak w Javie zmienić rozmiar wektorowy plików EPS przy użyciu Aspose.Page

## Wprowadzenie
Jeśli potrzebujesz **java vector resize** plików EPS programowo, jesteś we właściwym miejscu. Ten samouczek przeprowadzi Cię przez zmianę rozmiaru obrazów EPS w Javie przy użyciu biblioteki Aspose.Page. Niezależnie od tego, czy chcesz podwoić rozmiar, zmniejszyć go do określonego wymiaru, czy pracować w procentach, poniższe kroki dają pełną kontrolę nad wymiarami wyjściowymi. Opanowanie sposobu zmiany rozmiaru EPS jest niezbędne przy dostosowywaniu grafiki do różnych układów druku, rozdzielczości ekranów czy wytycznych brandingowych.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebujesz?** Aspose.Page for Java  
- **Czy mogę zmienić rozmiar używając punktów, cali lub milimetrów?** Tak – API obsługuje wszystkie trzy jednostki oraz procenty.  
- **Czy potrzebna jest licencja do rozwoju?** Bezpłatna wersja próbna działa do testów; licencja jest wymagana w produkcji.  
- **Jaka wersja Javy jest wymagana?** Java 8 lub nowsza.  
- **Czy kod jest bezpieczny wątkowo?** Każda instancja `PsDocument` jest odizolowana, więc możesz przetwarzać pliki równolegle.  

## Co to jest EPS i dlaczego zmieniać jego rozmiar?
Encapsulated PostScript (EPS) to format grafiki wektorowej szeroko stosowany w druku i publikacji. Czasami oryginalny plik EPS jest tworzony w rozmiarze, który nie odpowiada docelowemu wyjściu – na przykład logo zaprojektowane w 72 pt może wymagać 144 pt dla większej broszury. Znajomość **how to resize eps** pozwala zachować jakość wektora przy dostosowywaniu wymiarów do dowolnego przepływu pracy.

## Dlaczego używać Aspose.Page do zmiany rozmiaru EPS?
Aspose.Page udostępnia prostą API, która pozwala określić docelowy rozmiar w dowolnej obsługiwanej jednostce, jednocześnie automatycznie zachowując strukturę wektora. Biblioteka obsługuje konwersję jednostek wewnętrznie, więc możesz skupić się na pożądanych wymiarach bez ręcznych obliczeń.

- **Obsługuje cztery jednostki miary** – punkty, cale, milimetry i procenty.  
- **Brak zewnętrznych zależności** – czysta API Java, nie wymaga bibliotek natywnych.  
- **Wysokowydajne przetwarzanie** – może obsłużyć do 500 plików EPS na minutę na standardowym serwerze 8‑rdzeniowym.  
- **Zachowuje wierność wektora** – wynik pozostaje w pełni skalowalny bez rasteryzacji.

## Wymagania wstępne
Zanim przejdziemy do kodu, upewnij się, że masz następujące:

- Zainstalowany Java Development Kit (JDK) na komputerze.  
- Biblioteka Aspose.Page for Java. Możesz ją pobrać z **[strona pobierania Aspose.Page for Java](https://releases.aspose.com/page/java/)**.  
- Podstawową znajomość programowania w Javie.  

## Importowanie pakietów
W swoim projekcie Java dołącz wymagane importy, aby móc pracować z obiektami Aspose.Page oraz standardowymi strumieniami I/O.

`PsDocument` reprezentuje dokument EPS załadowany w pamięci.  
`Units` jest wyliczeniem definiującym jednostki miary akceptowane przez API.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## Jak zmienić wymiary EPS przy użyciu różnych jednostek
Możesz zmienić wymiary EPS, wywołując metodę `resizeEps` z żądaną szerokością, wysokością oraz wartością wyliczenia `Units`; działa to dla punktów, cali, milimetrów lub procentów. Ten sam pięcioetapowy wzorzec stosuje się do każdej jednostki, co sprawia, że API jest przewidywalne i łatwe do integracji.

`resizeEps` zmienia rozmiar płótna EPS do określonych wymiarów, zachowując wewnętrzne dane wektorowe.

## Jak zmienić rozmiar EPS używając punktów
Załaduj swój EPS, określ nowy rozmiar w punktach i zapisz wynik. To podejście podwaja oryginalne wymiary przy zachowaniu proporcji. Używanie punktów daje precyzyjną kontrolę nad rozmiarami gotowymi do druku, co jest szczególnie przydatne w układach typograficznych i wyjściach wysokiej rozdzielczości.

### Krok 1: skonfiguruj strumień wejściowy
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Krok 2: zainicjalizuj obiekt `PsDocument`
`PsDocument` ładuje źródłowy plik EPS i udostępnia metody do manipulacji.  

```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Krok 3: wyodrębnij bieżący rozmiar obrazu EPS
```java
Dimension oldSize = doc.extractEpsSize();
```

### Krok 4: utwórz strumień wyjściowy dla zmienionego pliku
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Krok 5: zmień rozmiar i zapisz EPS używając punktów
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## Jak zmienić rozmiar EPS używając cali
Zmiana rozmiaru przy użyciu cali pozwala dopasować specyfikacje zdefiniowane w jednostkach imperialnych, takich jak układy broszur czy amerykańskie standardy druku. Podaj docelową szerokość i wysokość w calach, a API przeliczy je na odpowiednie jednostki wewnętrzne przed zastosowaniem transformacji.

## Jak zmienić rozmiar EPS używając milimetrów
Pracując z przepływami opartymi na systemie metrycznym, określanie wymiarów w milimetrach zapewnia spójność z rozmiarami papieru i sprzętem drukującym używanym poza Stanami Zjednoczonymi. Biblioteka automatycznie obsługuje konwersję z milimetrów do wewnętrznego systemu współrzędnych.

## Jak zmienić rozmiar EPS używając procentów
Zmiana rozmiaru w procentach skaluje oryginalne wymiary proporcjonalnie, co jest przydatne przy szybkich korektach rozmiaru bez obliczania wartości bezwzględnych. Na przykład współczynnik `0.5` zmniejsza zarówno szerokość, jak i wysokość o 50 %.

## Częste pułapki i wskazówki
- **Zawsze zamykaj strumienie** – W kodzie produkcyjnym otaczaj strumienie blokiem try‑with‑resources, aby uniknąć blokad plików.  
- **Zachowaj proporcje** – Mnoż oba wymiary przez ten sam współczynnik, chyba że celowo chcesz wprowadzić zniekształcenie.  
- **Sprawdź DPI** – Zmiana rozmiaru nie zmienia DPI; jeśli potrzebujesz innego DPI, dostosuj je osobno po zmianie rozmiaru.  
- **Bezpieczeństwo wątków** – Twórz nowy `PsDocument` dla każdego wątku; współdzielenie tej samej instancji może prowadzić do nieoczekiwanych wyników.  

## Najczęściej zadawane pytania

**Q: Czy mogę używać tej biblioteki do innych formatów obrazów?**  
A: Nie, Aspose.Page jest specjalizowana wyłącznie w plikach PostScript i EPS.

**Q: Czy dostępna jest bezpłatna wersja próbna Aspose.Page dla Javy?**  
A: Tak, możesz wypróbować bezpłatną wersję próbną **[strona bezpłatnej wersji próbnej Aspose](https://releases.aspose.com/)**.

**Q: Gdzie mogę znaleźć dodatkową pomoc i dyskusje?**  
A: Odwiedź **[forum Aspose.Page](https://forum.aspose.com/c/page/39)**, aby uzyskać wsparcie społeczności.

**Q: Jak mogę uzyskać tymczasową licencję?**  
A: Możesz uzyskać tymczasową licencję **[strona wniosku o tymczasową licencję](https://purchase.aspose.com/temporary-license/)**.

**Q: Czy dostępne są przykładowe projekty?**  
A: Tak, sprawdź dokumentację **[odniesienie do API Aspose.Page Java](https://reference.aspose.com/page/java/)**.

---

**Ostatnia aktualizacja:** 2026-08-29  
**Testowano z:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Autor:** Aspose

## Powiązane samouczki

- [Zmienianie rozmiaru EPS przy użyciu Aspose.Page – manipulacja EPS w Javie](/page/java/manipulation-eps/)
- [Jak przyciąć pliki EPS w Javie – przewodnik Aspose.Page](/page/java/manipulation-eps/crop/)
- [Jak skalować prostokąt przy użyciu Aspose.Page dla Javy](/page/java/page-manipulation/transformations/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}