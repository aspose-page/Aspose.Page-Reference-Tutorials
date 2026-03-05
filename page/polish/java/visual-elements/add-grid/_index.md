---
date: 2026-03-05
description: Dowiedz się, jak dodać siatkę przy użyciu Visual Brush w Javie z Aspose.Page.
  Skorzystaj z przewodnika krok po kroku, aby łatwo ulepszyć wygląd dokumentu.
linktitle: Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: Jak dodać siatkę przy użyciu Visual Brush w Javie
url: /pl/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dodać siatkę przy użyciu Visual Brush w Javie

## Wprowadzenie
Jeśli szukasz **jak dodać siatkę** do dokumentów generowanych w Javie, funkcja Visual Brush w Aspose.Page czyni to zaskakująco proste. W tym samouczku przeprowadzimy Cię przez każdy krok, wyjaśnimy, dlaczego Visual Brush jest idealny dla wzorów siatek i pokażemy kompletny, działający przykład.

## Szybkie odpowiedzi
- **Co to jest Visual Brush?** Reużywalny element wizualny, który może być rozmieszczany w kafelkach lub rozciągany, aby wypełnić obszar.  
- **Dlaczego używać siatki?** Siatki pomagają strukturyzować układy, tworzyć wzory tła lub podświetlać sekcje w dokumentach XPS.  
- **Wymagania wstępne?** Java JDK, Aspose.Page for Java oraz podstawowa znajomość grafiki w Javie.  
- **Jak długo trwa implementacja?** Około 10‑15 minut po skonfigurowaniu biblioteki.  
- **Czy mogę dostosować kolory?** Tak – kontrolujesz kolory wypełnienia, przezroczystość i rozmiar kafelka bezpośrednio w kodzie.

## Dlaczego używać Visual Brush do dodania siatki?
Visual Brush pozwala zdefiniować mały element wizualny (tzw. „kafelek”) raz, a następnie powtarzać go na dowolnym kształcie. To podejście jest oszczędne pod względem pamięci i utrzymuje kod w czystości, szczególnie gdy trzeba zastosować ten sam wzór na wielu płótnach.

## Wymagania wstępne
Zanim przejdziemy do kodu, upewnij się, że masz następujące wymagania wstępne:
- Podstawowa znajomość programowania w Javie.  
- Zainstalowana biblioteka Aspose.Page. Możesz ją pobrać z [dokumentacji Aspose.Page for Java](https://reference.aspose.com/page/java/).  
- Zainstalowany Java Development Kit (JDK) na Twoim komputerze.

## Importowanie pakietów
Upewnij się, że w swoim projekcie Java zaimportowano niezbędne pakiety:
```java
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsTileMode;
import com.aspose.xps.XpsVisualBrush;
```

### Krok 1: Konfiguracja projektu
Najpierw utwórz instancję `XpsDocument` i wskaż folder, w którym zostanie zapisany wynik.
```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### Krok 2: Utworzenie magenta siatki Visual Brush
Tworzymy mały magenta kafelek, który będzie powtarzany. Geometria ścieżki definiuje kształt kafelka.
```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### Krok 3: Definiowanie geometrii dla magenta siatki Visual Brush
Tutaj opisujemy obszar, który otrzyma kafelkowany pędzel.
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### Krok 4: Utworzenie nowego płótna
Do dokumentu dodawane jest nowe płótno, a my stosujemy transformację translacji, aby siatka pojawiła się w wybranym miejscu.
```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### Krok 5: Dodanie siatki do płótna
Teraz wiążemy Visual Brush z geometrią i ustawiamy tryb kafelkowania.
```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### Krok 6: Dodanie czerwonego przezroczystego prostokąta
Aby zademonstrować warstwowanie, nakładamy półprzezroczysty czerwony prostokąt na siatkę.
```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### Krok 7: Zapisanie wynikowego dokumentu XPS
Na koniec zapisz plik XPS na dysku.
```java
doc.save(dataDir + "AddGrid_out.xps");
```

Postępuj zgodnie z tymi krokami, a pomyślnie dodasz atrakcyjną wizualnie siatkę przy użyciu Visual Brush w swojej aplikacji Java z Aspose.Page.

## Typowe przypadki użycia
- **Tła raportów:** Dodaj subtelne wzory siatek do raportów finansowych lub inżynieryjnych, aby poprawić czytelność.  
- **Szablony projektowe:** Twórz wielokrotnego użytku szablony stron, w których ta sama siatka powtarza się na wielu stronach.  
- **Podświetlanie sekcji:** Nakładaj kolorowe siatki, aby przyciągnąć uwagę do konkretnych obszarów dokumentu.

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|----------|
| **Siatka jest rozciągnięta** | Sprawdź, czy `TileMode` jest ustawiony na `XpsTileMode.Tile` oraz czy prostokąty źródłowy i docelowy mają ten sam rozmiar. |
| **Kolory wyglądają nieprawidłowo** | Upewnij się, że używasz prawidłowych wartości RGBA przy tworzeniu pędzla jednolitego koloru (`createColor(alpha, red, green, blue)`). |
| **Dokument nie został zapisany** | Sprawdź, czy `dataDir` wskazuje istniejący folder z prawami zapisu oraz czy masz odpowiednie uprawnienia systemu plików. |

## Zakończenie
Gratulacje! Nauczyłeś się **jak dodać siatkę** przy użyciu Visual Brush w Aspose.Page w Javie. Ta technika daje precyzyjną kontrolę nad renderowaniem wzorów, jednocześnie utrzymując kod czystym i łatwym do utrzymania.

## Najczęściej zadawane pytania
### Czy Aspose.Page nadaje się do profesjonalnego generowania dokumentów?
Tak, Aspose.Page to solidna biblioteka zaprojektowana do profesjonalnego generowania dokumentów w Javie.

### Czy mogę dostosować kolory siatki przy użyciu Visual Brush?
Oczywiście! Visual Brush pozwala malować różnymi kolorami, zapewniając elastyczność w dostosowywaniu.

### Gdzie mogę znaleźć dodatkowe wsparcie dla Aspose.Page?
Odwiedź [forum Aspose.Page](https://forum.aspose.com/c/page/39), aby uzyskać wsparcie społeczności i dyskusje.

### Czy dostępna jest darmowa wersja próbna Aspose.Page?
Tak, możesz uzyskać dostęp do [darmowej wersji próbnej](https://releases.aspose.com/), aby zapoznać się z funkcjami Aspose.Page.

### Jak mogę uzyskać tymczasową licencję na Aspose.Page?
Uzyskaj [tymczasową licencję](https://purchase.aspose.com/temporary-license/) do celów testowych.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-03-05  
**Testowano z:** Aspose.Page for Java (latest release)  
**Autor:** Aspose  

---