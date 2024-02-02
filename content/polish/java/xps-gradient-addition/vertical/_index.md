---
title: Dodaj gradient pionowy w Java XPS
linktitle: Dodaj gradient pionowy w Java XPS
second_title: Aspose.Page API Java
description: Dowiedz się, jak dodać gradient pionowy do dokumentów Java XPS za pomocą Aspose.Page. Zwiększ atrakcyjność wizualną bez wysiłku. Wewnątrz instrukcja krok po kroku.
type: docs
weight: 12
url: /pl/java/xps-gradient-addition/vertical/
---
## Wstęp
tym samouczku omówimy, jak dodać gradient pionowy w Java XPS przy użyciu Aspose.Page dla Java. Dodanie gradientów do dokumentów XPS może poprawić atrakcyjność wizualną treści, czyniąc ją bardziej wciągającą i estetyczną.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Działające środowisko programistyczne Java.
-  Aspose.Page dla biblioteki Java. Można go pobrać z[Tutaj](https://releases.aspose.com/page/java/).
- Podstawowa znajomość programowania w języku Java.
## Importuj pakiety
Zacznij od zaimportowania niezbędnych pakietów dla swojego projektu Java. Upewnij się, że w zależnościach projektu uwzględniłeś bibliotekę Aspose.Page for Java.
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
        
// Zaimportuj Aspose.Page dla Java
```
## Krok 1: Zainicjuj dokument
Rozpocznij od zainicjowania dokumentu XPS. Stanowi to podstawę do dodawania elementów, takich jak ścieżki i gradienty, do dokumentu.
```java
// Zainicjuj dokument
XpsDocument doc = new XpsDocument();
```
## Krok 2: Utwórz ścieżkę z pionowym gradientem
Utwórzmy teraz ścieżkę z pionowym nachyleniem. Obejmuje to zdefiniowanie geometrii ścieżki i określenie przystanków gradientu.
```java
// Utwórz ścieżkę z geometrią
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Zdefiniuj przystanki gradientu pionowego
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
//Zastosuj gradient pionowy do ścieżki
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## Krok 3: Zapisz dokument
Na koniec zapisz dokument XPS z dodanym pionowym gradientem w wybranym katalogu.
```java
// Zapisz dokument
doc.save(dataDir + "VerticalGradient.xps");
```
Gratulacje! Pomyślnie dodałeś gradient pionowy do dokumentu Java XPS za pomocą Aspose.Page.
## Wniosek
Ulepszanie dokumentów XPS gradientami może znacznie poprawić ich atrakcyjność wizualną. Aspose.Page dla Java upraszcza ten proces, umożliwiając łatwe tworzenie wspaniałych dokumentów.

### Często zadawane pytania
### Czy mogę używać Aspose.Page dla Java w projektach komercyjnych?
 Tak, Aspose.Page dla Java jest dostępny do użytku komercyjnego. Możesz go kupić[Tutaj](https://purchase.aspose.com/buy).
### Czy dostępna jest bezpłatna wersja próbna Aspose.Page dla Java?
 Tak, możesz uzyskać dostęp do bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć dokumentację Aspose.Page dla Java?
 Dokumentacja jest dostępna[Tutaj](https://reference.aspose.com/page/java/).
### Jak mogę uzyskać tymczasową licencję na Aspose.Page dla Java?
 Uzyskaj tymczasową licencję[Tutaj](https://purchase.aspose.com/temporary-license/).
### Potrzebujesz pomocy lub masz pytania?
 Odwiedź społeczność Aspose.Page[forum](https://forum.aspose.com/c/page/39).