---
date: 2026-03-13
description: Dowiedz się, jak dodać gradient do dokumentów XPS w Javie przy użyciu
  Aspose.Page oraz jak dostosować przystanki gradientu, aby uzyskać oszałamiające
  efekty poziome.
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: Jak dodać gradient – gradient poziomy w Java XPS
url: /pl/java/xps-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dodać gradient – Gradient poziomy w Java XPS

## Wprowadzenie
Witamy w tym przewodniku krok po kroku dotyczącym **dodawania gradientu** do dokumentu XPS przy użyciu Javy. W tym tutorialu dowiesz się, jak dodać gradient poziomy, dlaczego ma to znaczenie dla estetyki wizualnej oraz jak **dostosować zatrzymania gradientu** w celu precyzyjnej kontroli kolorów. Aspose.Page for Java upraszcza pracę z dokumentami XPS (XML Paper Specification), pozwalając skupić się na projektowaniu, a nie na niskopoziomowej obsłudze plików.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebuję?** Aspose.Page for Java  
- **Która wersja Javy działa?** Dowolny runtime Java 8+  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna wystarcza do rozwoju; licencja komercyjna jest wymagana w produkcji  
- **Czy mogę zmienić kierunek gradientu?** Tak – wystarczy zmodyfikować punkty początkowy/końcowy pędzla liniowego  
- **Czy można dodać wiele gradientów?** Oczywiście – powtórz kroki tworzenia ścieżki z różnymi pędzlami  

## Co to jest gradient poziomy w XPS?
Gradient poziomy to płynne przejście kolorów od lewej do prawej wzdłuż kształtu. W XPS jest on reprezentowany przez pędzel gradientu liniowego, który interpoluje pomiędzy zdefiniowanymi **zatrzymaniami gradientu**. Efekt ten jest powszechnie używany w banerach, przyciskach i wypełnieniach tła.

## Dlaczego warto używać Aspose.Page for Java?
- **Pełne wsparcie XPS** – tworzenie, edycja i renderowanie bez narzędzi firm trzecich.  
- **Proste API** – obiekty wysokiego poziomu takie jak `XpsDocument`, `XpsPath` i `XpsGradientBrush` ukrywają złożoność XML.  
- **Wydajność** – zoptymalizowane pod kątem dużych dokumentów i przetwarzania wsadowego.  

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

1. **Środowisko programistyczne Java** – zainstaluj najnowszy JDK z [java.com](https://www.java.com).  
2. **Bibliotekę Aspose.Page for Java** – pobierz plik JAR z [dokumentacji Aspose.Page for Java](https://reference.aspose.com/page/java/).  

## Importowanie pakietów
Rozpocznij od zaimportowania niezbędnych klas. Importy te dają dostęp do tworzenia dokumentów, obsługi gradientów oraz podstawowej geometrii.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## Krok 1: Inicjalizacja dokumentu XPS
Utwórz nową instancję `XpsDocument` i wskaż folder, w którym chcesz zapisać wynik.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## Krok 2: Utworzenie gradientu poziomego
Zdefiniuj listę **zatrzymań gradientu**, które kontrolują kolor i pozycję każdego punktu przejścia. Poniższy przykład buduje żywy, przypominający tęczę gradient.

```java
// Horizontal gradient
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```

### Jak dostosować zatrzymania gradientu
- **Kolor** – użyj `doc.createColor(alpha, red, green, blue)`, aby ustawić dowolną wartość ARGB.  
- **Pozycja** – drugi argument (`float` od `0` do `1`) określa, gdzie zatrzymanie pojawia się wzdłuż linii gradientu. Dostosuj te wartości, aby przesunąć kolory w lewo lub w prawo.

## Krok 3: Dodanie ścieżki z gradientem
Utwórz prostokątną ścieżkę, zastosuj transformację w razie potrzeby i wypełnij ją pędzlem gradientu liniowego. Pędzel używa dwóch punktów (`(10,0)` do `(228,0)`), co daje efekt poziomy. Ponieważ współrzędne Y są identyczne, pędzel działa jako **pędzel gradientu poziomego**.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**Wskazówka:** Ponowne użycie tej samej listy `stops` dla wielu ścieżek może poprawić wydajność, ale pamiętaj, aby przed dodaniem nowych zatrzymań wywołać `clear()`.

## Krok 4: Zapisanie dokumentu
Zachowaj plik XPS na dysku. Teraz możesz otworzyć go w dowolnym przeglądarce XPS, aby zobaczyć działający gradient poziomy.

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## Jak zastosować wiele gradientów
Jeśli chcesz **zastosować wiele gradientów** w jednym dokumencie XPS, po prostu powtórz kroki „Utworzenie gradientu poziomego” i „Dodanie ścieżki z gradientem” dla każdego nowego kształtu. Użyj nowej listy obiektów `XpsGradientStop` (lub wyczyść istniejącą listę) i przypisz nowy `LinearGradientBrush` z własnymi punktami początkowym i końcowym. Takie podejście pozwala nakładać gradienty, tworzyć złożone tła lub podkreślać różne elementy UI na jednej stronie.

## Dlaczego to ma znaczenie – Korzyści z pędzla gradientu poziomego
- **Głębia wizualna:** Pędzel gradientu poziomego dodaje subtelną trójwymiarowość bez dodatkowych obrazów.  
- **Efektywność rozmiaru pliku:** Gradienty są przechowywane jako definicje wektorowe, co utrzymuje plik XPS lekki.  
- **Skalowalność:** Ponieważ gradient jest wektorowy, skaluje się czysto na wyświetlaczach o wysokiej rozdzielczości.  

## Typowe problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|-------|--------|-----|
| Gradient wygląda jak jednolity kolor | Nie dodano zatrzymań gradientu lub pędzel nie został ustawiony | Upewnij się, że `path.setFill(...)` używa `LinearGradientBrush` oraz że zatrzymania są dodane przez `getGradientStops().addAll(stops)`. |
| Kolory wydają się przytłumione | Nieprawidłowa wartość alfa (pierwszy parametr) | Użyj `255` dla w pełni nieprzezroczystych kolorów, chyba że wymagana jest przezroczystość. |
| Rozmiar ścieżki jest nieprawidłowy | Nieprawidłowe wartości macierzy transformacji | Dostosuj parametry macierzy (`scaleX, skewY, skewX, scaleY, translateX, translateY`). |

## Najczęściej zadawane pytania

**P: Czy mogę zastosować wiele gradientów w jednym dokumencie XPS?**  
O: Tak, możesz dodać wiele ścieżek, każdą z własnym pędzlem gradientu, aby stworzyć złożone, warstwowe projekty.

**P: Czy Aspose.Page jest kompatybilny z najnowszymi wersjami Javy?**  
O: Aspose.Page for Java jest regularnie aktualizowane i działa z Java 8 oraz nowszymi wersjami.

**P: Czy dostępne są inne typy gradientów w Aspose.Page?**  
O: Oprócz gradientów liniowych, Aspose.Page obsługuje także gradienty radialne dla okrągłych przejść kolorów.

**P: Czy mogę dostosować kolory i pozycje zatrzymań gradientu?**  
O: Oczywiście! Masz pełną kontrolę nad każdym zatrzymaniem – zarówno nad jego kolorem ARGB, jak i nad pozycją w zakresie 0‑1.

**P: Czy istnieje forum społecznościowe Aspose.Page, gdzie mogę uzyskać pomoc?**  
O: Tak, możesz odwiedzić [forum Aspose.Page](https://forum.aspose.com/c/page/39), aby połączyć się ze społecznością i uzyskać wsparcie.

---

**Ostatnia aktualizacja:** 2026-03-13  
**Testowano z:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}