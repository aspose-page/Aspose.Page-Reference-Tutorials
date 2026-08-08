---
date: 2026-05-25
description: Dowiedz się, jak dodać gradient do dokumentów XPS w Javie przy użyciu
  Aspose.Page. Ten przewodnik krok po kroku pokazuje, jak dodać gradient diagonalny,
  zastosować linear gradient brushes oraz tworzyć profesjonalne pliki XPS.
keywords:
- how to add gradient
- Aspose.Page Java
- diagonal gradient XPS
linktitle: Dodaj gradient diagonalny w Java XPS
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to add gradient to XPS documents in Java using Aspose.Page.
    This step‑by‑step guide shows how to add a diagonal gradient, apply linear gradient
    brushes, and produce professional XPS files.
  headline: 'How to Add Gradient: Diagonal Gradient in Java XPS'
  type: TechArticle
- questions:
  - answer: Create a `XpsLinearGradientBrush`, define gradient stops, and assign it
      to the shape’s `Fill` property as shown in Step 6.
    question: How do I **how to add gradient** to an existing XPS shape?
  - answer: It generates a brush definition in the XPS package that references the
      start/end points and a collection of gradient stops, which the viewer renders
      as a smooth color transition.
    question: What does **apply linear gradient** actually do behind the scenes?
  - answer: Yes, the Aspose.Page API includes methods for adding images, text, and
      custom shapes—simply explore the `XpsDocument` class for additional helpers.
    question: Is there a quick way to **how to use aspose** for other XPS features?
  - answer: Absolutely. Define any geometry using `createPathGeometry` and then set
      its `Fill` to a gradient brush.
    question: Can I **add gradient path** to non‑rectangular shapes?
  - answer: Only marginally; gradient definitions are lightweight XML entries within
      the XPS package.
    question: Does the gradient affect file size significantly?
  type: FAQPage
second_title: Aspose.Page Java API
title: 'Jak dodać gradient: Gradient diagonalny w Java XPS'
url: /pl/java/xps-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dodać gradient: gradient diagonalny w Java XPS

## Wprowadzenie
We współczesnym rozwoju Java, opanowanie **jak dodać gradient** do dokumentów XPS nadaje Twoim raportom wykończenie, które przyciąga wzrok i wyróżnia się. Ten samouczek przeprowadzi Cię przez tworzenie pliku XPS od podstaw, dodawanie gradientu diagonalnego oraz zapisywanie wyniku — wszystko przy użyciu Aspose.Page for Java. Zrozumiesz, dlaczego gradienty są ważne, zobaczysz dokładne wywołania API i otrzymasz praktyczne wskazówki, jak uniknąć typowych pułapek.

## Szybkie odpowiedzi
- **Jaka jest podstawowa biblioteka?** Aspose.Page for Java  
- **Która metoda dodaje gradient?** `createLinearGradientBrush` z przystankami gradientu  
- **Czy potrzebna jest licencja?** Wersja próbna działa w fazie rozwoju; licencja komercyjna jest wymagana w produkcji  
- **Jak długo trwa implementacja?** Około 10‑15 minut dla podstawowego gradientu diagonalnego  
- **Czy mogę używać tego z innymi frameworkami Java?** Tak, API jest niezależne od frameworku  

## Czym jest gradient diagonalny w dokumencie XPS?
Gradient diagonalny to płynne przejście kolorów, które biegnie od jednego narożnika kształtu do przeciwległego, tworząc skośny efekt wizualny. W XPS efekt ten jest definiowany przez liniowy pędzel gradientowy zawierający uporządkowane przystanki gradientu określające kolory i względne pozycje wzdłuż linii diagonalnej.

## Dlaczego dodać gradient diagonalny przy użyciu Aspose.Page?
Aspose.Page zapewnia **100 % wierność renderowania** gradientów we wszystkich ponad 20 przeglądarkach XPS oraz obsługuje **30+ funkcji XPS**, takich jak tekst, obrazy i kształty wektorowe. API ukrywa złożoność składni XPS, pozwalając skupić się na projekcie, jednocześnie gwarantując, że ten sam plik wygląda identycznie na platformach Windows, macOS i Linux.

## Wymagania wstępne
- Podstawowa znajomość programowania w Javie.  
- Zainstalowany JDK na komputerze.  
- Biblioteka Aspose.Page for Java – pobierz ją **[tutaj](https://releases.aspose.com/page/java/)**.  
- IDE, takie jak IntelliJ IDEA lub Eclipse.

## Importowanie pakietów
Rozpocznij od zaimportowania klas, które będą potrzebne. Te importy dają dostęp do geometrii, obsługi gradientów i tworzenia dokumentów XPS.

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```

## Krok 1: Skonfiguruj swój projekt
Utwórz nowy projekt Java w wybranym IDE i dodaj pliki JAR Aspose.Page do ścieżki kompilacji projektu.

## Krok 2: Określ katalog dokumentu
Podaj miejsce, w którym zostanie zapisany wygenerowany plik XPS.

```java
String dataDir = "Your Document Directory";
```

## Krok 3: Utwórz dokument XPS
`XpsDocument` jest podstawowym obiektem reprezentującym plik XPS w pamięci. Jego utworzenie daje płótno, na którym można dodawać strony, kształty i pędzle.

```java
XpsDocument doc = new XpsDocument();
```

## Krok 4: Dodaj ścieżkę gradientu diagonalnego
Utwórz prostokątną ścieżkę, która otrzyma gradient. Geometria ścieżki używa prostych poleceń move‑line‑close.  
XpsPath definiuje kształt wektorowy w dokumencie XPS, taki jak prostokąt lub niestandardowa geometria.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```

## Krok 5: Zdefiniuj liniowe przystanki gradientu
Ustaw kolory i ich pozycje. Każdy przystanek określa punkt w gradiencie, w którym pojawia się konkretny kolor.  
XpsGradientStop reprezentuje pojedynczy przystanek koloru w gradiencie, określając kolor i jego offset.

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... repeat for other colors and positions
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```

## Krok 6: Zastosuj liniowy gradient do ścieżki
`XpsLinearGradientBrush` to typ pędzla Aspose.Page służący do liniowych przejść kolorów. Przyjmuje dwa punkty definiujące kierunek gradientu oraz kolekcję przystanków gradientu określających kolory wzdłuż tej linii.

```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## Krok 7: Zapisz dokument
Zachowaj plik XPS na dysku. Plik będzie zawierał prostokąt wypełniony zdefiniowanym gradientem diagonalnym.

```java
doc.save(dataDir + "LinearGradient.xps");
```

## Jak dodać gradient w Java XPS?
Wczytaj `XpsDocument`, utwórz `XpsLinearGradientBrush` z punktem początkowym `(0,0)` i końcowym `(width,height)`, dołącz przystanki gradientu, przypisz pędzel do właściwości `Fill` kształtu i na koniec wywołaj `save`. Ten zwięzły przepływ pozwala osadzić gradient diagonalny w kilku wywołaniach API, utrzymując kod czystym i łatwym w utrzymaniu.

## Typowe pułapki i wskazówki
- **Kierunek gradientu** – upewnij się, że punkty początkowy i końcowy pędzla odzwierciedlają pożądaną diagonalę; zamiana ich odwróci gradient.  
- **Precyzja kolorów** – Aspose używa formatu ARGB; uwzględnij kanał alfa, jeśli potrzebna jest przezroczystość.  
- **Ścieżka pliku** – zawsze używaj ścieżki bezwzględnej lub sprawdź, czy ścieżka względna wskazuje na istniejący katalog z prawami zapisu.

## Dodatkowe FAQ

**Q: Jak **dodać gradient** do istniejącego kształtu XPS?**  
A: Create a `XpsLinearGradientBrush`, define gradient stops, and assign it to the shape’s `Fill` property as shown in Step 6.

**Q: Co właściwie robi **apply linear gradient** w tle?**  
A: It generates a brush definition in the XPS package that references the start/end points and a collection of gradient stops, which the viewer renders as a smooth color transition.

**Q: Czy istnieje szybki sposób na **how to use aspose** dla innych funkcji XPS?**  
A: Yes, the Aspose.Page API includes methods for adding images, text, and custom shapes—simply explore the `XpsDocument` class for additional helpers.

**Q: Czy mogę **add gradient path** do kształtów nie‑prostokątnych?**  
A: Absolutely. Define any geometry using `createPathGeometry` and then set its `Fill` to a gradient brush.

**Q: Czy gradient znacząco wpływa na rozmiar pliku?**  
A: Only marginally; gradient definitions are lightweight XML entries within the XPS package.

---

**Ostatnia aktualizacja:** 2026-05-25  
**Testowano z:** Aspose.Page for Java 24.11  
**Autor:** Aspose

## Powiązane samouczki

- [Dodawanie gradientu XPS w Aspose Page](/page/java/xps-gradient-addition/)
- [Java XPS Text Addition - Aspose.Page Tutorial](/page/java/xps-text-manipulation/add-text/)
- [Jak dodać obraz do dokumentów Java XPS – prosty przewodnik z Aspose.Page](/page/java/xps-image-manipulation/add-image/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}