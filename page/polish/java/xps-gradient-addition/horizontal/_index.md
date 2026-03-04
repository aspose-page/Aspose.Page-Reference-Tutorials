---
date: 2025-12-25
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

# Jak dodać gradient – poziomy gradient w Java XPS

## Wprowadzenie
Witamy w tym przewodniku krok po kroku, jak **dodać gradient** do dokumentu XPS przy użyciu Javy. W tym tutorialu dowiesz się, jak dodać poziomy gradient, dlaczego ma to znaczenie dla wizualnego wykończenia oraz jak **dostosować stopnie gradientu** dla precyzyjnej kontroli kolorów. Aspose.Page for Java ułatwia pracę z dokumentami XPS (XML Paper Specification), pozwalając skupić się na projektowaniu, a nie na niskopoziomowej obsłudze plików.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebujesz?** Aspose.Page for Java  
- **Która wersja Java działa?** Dowolny runtime Java 8+  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji  
- **Czy mogę zmienić kierunek gradientu?** Tak – wystarczy zmodyfikować punkty początkowy/końcowy liniowego pędzla  
- **Czy można dodać wiele gradientów?** Absolutnie – powtórz kroki tworzenia ścieżki z różnymi pędzlami  

## Co to jest poziomy gradient w XPS?
Poziomy gradient to płynne przejście kolorów od lewej do prawej wzdłuż kształtu. W XPS jest reprezentowany przez liniowy pędzel gradientowy, który interpoluje pomiędzy zdefiniowanymi **stopniami gradientu**. Ten efekt wizualny jest powszechnie używany w banerach, przyciskach i wypełnieniach tła.

## Dlaczego używać Aspose.Page for Java?
- **Pełne wsparcie XPS** – tworzenie, edycja i renderowanie bez narzędzi firm trzecich.  
- **Proste API** – obiekty wysokiego poziomu takie jak `XpsDocument`, `XpsPath` i `XpsGradientBrush` ukrywają złożoność XML.  
- **Wydajność** – zoptymalizowane pod kątem dużych dokumentów i przetwarzania wsadowego.  

## Prerequisites
Before you begin, ensure you have:

1. **Środowisko programistyczne Java** – Zainstaluj najnowszy JDK z [java.com](https://www.java.com).  
2. **Biblioteka Aspose.Page for Java** – Pobierz plik JAR z [dokumentacji Aspose.Page for Java](https://reference.aspose.com/page/java/).  

## Importowanie pakietów
Start by importing the necessary classes. These imports give you access to document creation, gradient handling, and basic geometry.

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
Create a fresh `XpsDocument` instance and point to the folder where you want to save the result.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## Krok 2: Utworzenie poziomego gradientu
Define a list of **gradient stops** that control the color and position of each transition point. The example below builds a vibrant rainbow‑like gradient.

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

### Jak dostosować stopnie gradientu
- **Kolor** – Użyj `doc.createColor(alpha, red, green, blue)`, aby ustawić dowolną wartość ARGB.  
- **Pozycja** – Drugi argument (`float` od `0` do `1`) określa, gdzie stop pojawia się wzdłuż linii gradientu. Dostosuj te wartości, aby przesunąć kolory w lewo lub w prawo.

## Krok 3: Dodanie ścieżki z gradientem
Create a rectangular path, apply a transform if needed, and fill it with the linear gradient brush. The brush uses two points (`(10,0)` to `(228,0)`) to produce a horizontal effect.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**Wskazówka:** Ponowne użycie tej samej listy `stops` dla wielu ścieżek może poprawić wydajność, ale pamiętaj, aby wywołać `clear()` przed dodaniem nowych stopów.

## Krok 4: Zapisanie dokumentu
Persist the XPS file to disk. You can now open it with any XPS viewer to see the horizontal gradient in action.

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## Częste problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| Gradient wygląda na jednolity | Nie dodano stopów gradientu lub pędzel nie został ustawiony | Upewnij się, że `path.setFill(...)` używa `LinearGradientBrush` i że stopy są dodane poprzez `getGradientStops().addAll(stops)`. |
| Kolory wyglądają przytłumione | Nieprawidłowa wartość alfa (pierwszy parametr) | Użyj `255` dla w pełni nieprzezroczystych kolorów, chyba że wymagana jest przezroczystość. |
| Rozmiar ścieżki jest nieprawidłowy | Wartości macierzy transformacji są nieprawidłowe | Dostosuj parametry macierzy (`scaleX, skewY, skewX, scaleY, translateX, translateY`). |

## Najczęściej zadawane pytania

**Q: Czy mogę zastosować wiele gradientów w jednym dokumencie XPS?**  
A: Tak, możesz dodać wiele ścieżek, z których każda ma własny pędzel gradientowy, aby stworzyć złożone, warstwowe projekty.

**Q: Czy Aspose.Page jest kompatybilny z najnowszymi wersjami Java?**  
A: Aspose.Page for Java jest regularnie aktualizowany i działa z Java 8 oraz nowszymi wersjami.

**Q: Czy w Aspose.Page dostępne są inne typy gradientów?**  
A: Oprócz gradientów liniowych, Aspose.Page obsługuje także gradienty radialne dla okrągłych przejść kolorów.

**Q: Czy mogę dostosować kolory i pozycje stopów gradientu?**  
A: Absolutnie! Masz pełną kontrolę nad kolorem ARGB każdego stopu oraz jego względną pozycją (zakres 0‑1).

**Q: Czy istnieje forum społecznościowe Aspose.Page, gdzie mogę uzyskać pomoc?**  
A: Tak, możesz odwiedzić [forum Aspose.Page](https://forum.aspose.com/c/page/39), aby połączyć się ze społecznością i uzyskać wsparcie.

---

**Ostatnia aktualizacja:** 2025-12-25  
**Testowano z:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}