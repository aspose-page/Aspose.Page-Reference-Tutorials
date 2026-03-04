---
date: 2025-12-25
description: Dowiedz się, jak dodać pionowy gradient w Java XPS przy użyciu Aspose.Page.
  Postępuj zgodnie z tym przewodnikiem krok po kroku, aby zwiększyć atrakcyjność wizualną
  swojego dokumentu.
linktitle: How to Add Vertical Gradient in Java XPS
second_title: Aspose.Page Java API
title: Jak dodać pionowy gradient w Java XPS
url: /pl/java/xps-gradient-addition/vertical/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dodać pionowy gradient w Java XPS

## Wprowadzenie
W tym samouczku odkryjesz **jak dodać pionowy gradient** do dokumentów XPS podczas pracy w Javie. Zastosowanie pionowego gradientu może znacząco poprawić wizualny efekt Twoich raportów, faktur lub dowolnych treści do druku. Przejdziemy przez każdy krok, od skonfigurowania projektu po zapisanie ostatecznego pliku XPS, używając potężnej biblioteki Aspose.Page for Java.

## Szybkie odpowiedzi
- **Co robi pionowy gradient?** Tworzy płynne przejście kolorów od góry do dołu kształtu.  
- **Jakiej biblioteki wymaga?** Aspose.Page for Java (do pobrania z oficjalnej strony).  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji.  
- **Czy jest kompatybilny z Java 8+?** Tak, API obsługuje Java 8 i nowsze wersje.  
- **Jak długo trwa implementacja?** Zazwyczaj poniżej 10 minut po skonfigurowaniu środowiska.

## Wymagania wstępne
Zanim przejdziemy do kodu, upewnij się, że masz następujące elementy:

- Działające środowisko programistyczne Java (JDK 8 lub nowszy).  
- Biblioteka Aspose.Page for Java. Możesz ją pobrać [tutaj](https://releases.aspose.com/page/java/).  
- Podstawową znajomość koncepcji programowania w Javie.  

## Importowanie pakietów
Zacznij od zaimportowania niezbędnych pakietów do swojego projektu Java. Upewnij się, że biblioteka Aspose.Page for Java została dodana do classpath projektu.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Import Aspose.Page for Java
```

## Krok 1: Inicjalizacja dokumentu
Rozpocznij od utworzenia nowego dokumentu XPS. Ten obiekt będzie przechowywać wszystkie elementy rysunkowe, które dodasz później.

```java
// Initialize document
XpsDocument doc = new XpsDocument();
```

## Krok 2: Utworzenie ścieżki z pionowym gradientem
Następnie zdefiniuj prostokątną ścieżkę i zastosuj pionowy gradient liniowy. Punkty zatrzymania gradientu określają kolory i ich pozycje wzdłuż osi pionowej.

```java
// Create a path with geometry
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Define vertical gradient stops
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
// Apply the vertical gradient to the path
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## Krok 3: Zapisanie dokumentu
Na koniec zapisz plik XPS na dysku. Powstały plik będzie zawierał prostokąt wypełniony pionowym gradientem, który zdefiniowałeś.

```java
// Save the document
doc.save(dataDir + "VerticalGradient.xps");
```

Gratulacje! Pomyślnie nauczyłeś się **jak dodać pionowy gradient** do dokumentu Java XPS przy użyciu Aspose.Page.

## Dlaczego używać pionowego gradientu?
- **Poprawiona estetyka:** Gradienty dodają głębi i nowoczesnego wyglądu statycznym kształtom.  
- **Spójność marki:** Gładko dopasuj kolory firmowe na wszystkich stronach.  
- **Łatwa personalizacja:** Zmieniaj kolory lub pozycje punktów zatrzymania bez konieczności ponownego projektowania grafiki.

## Typowe problemy i rozwiązywanie
- **Gradient nie jest widoczny:** Sprawdź, czy punkty początkowy i końcowy `LinearGradientBrush` są prawidłowo ustawione dla pionowej orientacji.  
- **Plik nie został zapisany:** Upewnij się, że `dataDir` wskazuje na folder z prawami zapisu i że masz uprawnienia do zapisu plików.  
- **Biblioteka nie znaleziona:** Sprawdź ponownie, czy plik JAR Aspose.Page jest dołączony do ścieżki budowania projektu.

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.Page for Java w projektach komercyjnych?**  
A: Tak, Aspose.Page for Java jest dostępny do użytku komercyjnego. Możesz go kupić [tutaj](https://purchase.aspose.com/buy).

**Q: Czy dostępna jest darmowa wersja próbna Aspose.Page for Java?**  
A: Tak, możesz uzyskać darmową wersję próbną [tutaj](https://releases.aspose.com/).

**Q: Gdzie mogę znaleźć dokumentację Aspose.Page for Java?**  
A: Dokumentacja jest dostępna [tutaj](https://reference.aspose.com/page/java/).

**Q: Jak mogę uzyskać tymczasową licencję dla Aspose.Page for Java?**  
A: Uzyskaj tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/).

**Q: Potrzebujesz pomocy lub masz pytania?**  
A: Odwiedź społeczność Aspose.Page [forum](https://forum.aspose.com/c/page/39).

---

**Ostatnia aktualizacja:** 2025-12-25  
**Testowano z:** Aspose.Page for Java 24.12 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}