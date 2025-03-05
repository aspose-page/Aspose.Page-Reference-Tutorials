---
title: Dodaj gradient poziomy w Java XPS
linktitle: Dodaj gradient poziomy w Java XPS
second_title: Aspose.Page API Java
description: Dowiedz się, jak dodać oszałamiający poziomy gradient do dokumentów XPS w Javie za pomocą Aspose.Page. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby zapewnić bezproblemową integrację.
type: docs
weight: 11
url: /pl/java/xps-gradient-addition/horizontal/
---
## Wstęp
Witamy w tym przewodniku krok po kroku dotyczącym dodawania gradientu poziomego w Java XPS przy użyciu Aspose.Page dla Java. Aspose.Page dla Java to potężna biblioteka, która umożliwia programistom płynną pracę z dokumentami XPS (Specyfikacja papieru XML).
W tym samouczku przeprowadzimy Cię przez proces tworzenia aplikacji Java umożliwiającej dodanie gradientu poziomego do dokumentu XPS. Aby to osiągnąć z łatwością, wykonaj poniższe czynności.
## Warunki wstępne
Zanim zaczniesz, upewnij się, że spełnione są następujące warunki wstępne:
1. Środowisko programistyczne Java: Upewnij się, że w systemie jest zainstalowana Java. Jeśli nie, pobierz i zainstaluj najnowszą wersję Java ze strony[Java.com](https://www.java.com).
2.  Biblioteka Aspose.Page dla Java: Musisz mieć bibliotekę Aspose.Page dla Java. Można go pobrać z[Aspose.Page dla dokumentacji Java](https://reference.aspose.com/page/java/).
## Importuj pakiety
Zacznij od zaimportowania niezbędnych pakietów dla aplikacji Java. Dołącz bibliotekę Aspose.Page for Java do swojego projektu. Można to zrobić dodając następujące linie kodu:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```
## Krok 1: Zainicjuj dokument
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
//Zainicjuj dokument
XpsDocument doc = new XpsDocument();
```
## Krok 2: Utwórz gradient poziomy
```java
// Gradient poziomy
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```
## Krok 3: Dodaj ścieżkę z gradientem
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```
## Krok 4: Zapisz dokument
```java
doc.save(dataDir + "HorizontalGradient.xps");
```
W razie potrzeby powtórz te kroki, dostosowując parametry w zależności od konkretnych wymagań.
## Wniosek
Gratulacje! Pomyślnie dodałeś gradient poziomy do dokumentu XPS przy użyciu Aspose.Page dla Java. Ten samouczek stanowi kompleksowy przewodnik dla programistów chcących ulepszyć swoje aplikacje Java za pomocą efektów gradientu.
## Często zadawane pytania
### P: Czy mogę zastosować wiele gradientów w jednym dokumencie XPS?
Tak, możesz dodać wiele ścieżek z różnymi gradientami, aby tworzyć złożone projekty.
### P: Czy Aspose.Page jest kompatybilny z najnowszymi wersjami Java?
Aspose.Page dla Java jest regularnie aktualizowany, aby zapewnić kompatybilność z najnowszymi wydaniami Java.
### P: Czy w Aspose.Page dostępne są inne typy gradientów?
Tak, oprócz gradientów liniowych, Aspose.Page obsługuje gradienty promieniowe, aby uzyskać bardziej zróżnicowane efekty.
### P: Czy mogę dostosować kolory i położenie punktów gradientu?
Absolutnie! Masz pełną kontrolę nad kolorami i położeniem każdego przystanku gradientu.
### P: Czy istnieje forum społecznościowe dla Aspose.Page, na którym mogę szukać pomocy?
 Tak, możesz odwiedzić[Forum Aspose.Page](https://forum.aspose.com/c/page/39) aby nawiązać kontakt ze społecznością i uzyskać pomoc.