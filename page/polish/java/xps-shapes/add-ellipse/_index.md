---
title: Dodaj promieniową elipsę gradientową za pomocą Aspose.Page
linktitle: Dodaj elipsę w Java XPS
second_title: Aspose.Page API Java
description: Zapoznaj się z przewodnikiem krok po kroku dotyczącym dodawania promieniowej elipsy z obrysowanym gradientem w języku Java XPS przy użyciu Aspose.Page dla języka Java. Ulepsz swoje tworzenie dokumentów bez wysiłku.
weight: 10
url: /pl/java/xps-shapes/add-ellipse/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj promieniową elipsę gradientową za pomocą Aspose.Page

## Wstęp
Witamy w naszym przewodniku krok po kroku dotyczącym dodawania elipsy w Java XPS przy użyciu Aspose.Page dla Java. Aspose.Page to potężna biblioteka Java, która umożliwia programistom bezproblemową pracę z dokumentami XPS. W tym samouczku przeprowadzimy Cię przez proces tworzenia elipsy z obrysowanym gradientem promieniowym i zapisywania jej jako dokumentu XPS.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:
- Zestaw Java Development Kit (JDK) zainstalowany na komputerze.
-  Pobrano bibliotekę Aspose.Page dla Java. Możesz to dostać[Tutaj](https://releases.aspose.com/page/java/).
- Wybrany przez Ciebie edytor kodu (Eclipse, IntelliJ itp.) do pisania i wykonywania kodu Java.
## Importuj pakiety
Upewnij się, że masz zaimportowane niezbędne pakiety do projektu Java, aby móc korzystać z Aspose.Page. Dodaj następujące instrukcje importu na górze pliku Java:
```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```
## Krok 1: Skonfiguruj katalog dokumentów
Zdefiniuj ścieżkę do katalogu dokumentów, w którym zostanie zapisany dokument XPS:
```java
String dataDir = "Your Document Directory";
```
## Krok 2: Utwórz dokument XPS
Zainicjuj nowy dokument XPS, używając następującego kodu:
```java
XpsDocument doc = new XpsDocument();
```
## Krok 3: Zdefiniuj promieniowe punkty gradientu
Utwórz listę przystanków gradientu dla obrysowanej elipsy z gradientem promieniowym:
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```
## Krok 4: Utwórz geometrię ścieżki
Zdefiniuj elipsę z promieniowym gradientem, używając geometrii ścieżki:
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```
## Krok 5: Dodaj płótno i ścieżkę
Dodaj nowe płótno do dokumentu i dołącz ścieżkę ze zdefiniowaną geometrią:
```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```
## Krok 6: Ustaw obrys i gradient
Skonfiguruj obrys ścieżki za pomocą promieniowego pędzla gradientowego:
```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```
## Krok 7: Ustaw grubość obrysu
Określ grubość obrysu ścieżki:
```java
path.setStrokeThickness(12f);
```
## Krok 8: Zapisz dokument
Zapisz wynikowy dokument XPS:
```java
doc.save(dataDir + "AddEllipse_out.xps");
```
Gratulacje! Pomyślnie dodałeś obrysowaną elipsę z gradientem promieniowym w Java XPS przy użyciu Aspose.Page dla Java.
## Wniosek
W tym samouczku omówiliśmy kroki tworzenia dokumentu XPS z atrakcyjną wizualnie elipsą z promieniowym gradientem. Aspose.Page dla Java upraszcza manipulowanie dokumentami XPS, zapewniając programistom potężny zestaw narzędzi.
## Często Zadawane Pytania
### Czy mogę używać Aspose.Page dla Java z innymi bibliotekami Java?
Tak, Aspose.Page for Java można bezproblemowo zintegrować z innymi bibliotekami Java.
### Czy Aspose.Page nadaje się do przetwarzania dokumentów na dużą skalę?
Absolutnie! Aspose.Page został zaprojektowany do wydajnej obsługi przetwarzania dokumentów na dużą skalę.
### Gdzie mogę znaleźć więcej tutoriali i przykładów Aspose.Page dla Java?
 Odwiedzić[Aspose.Page dla dokumentacji Java](https://reference.aspose.com/page/java/)obszerne tutoriale i przykłady.
### Jak mogę uzyskać tymczasową licencję na Aspose.Page dla Java?
 Możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
### Czy istnieją fora społeczności do dyskusji w Aspose.Page?
 Tak, dołącz do[Forum społeczności Aspose.Page](https://forum.aspose.com/c/page/39) aby nawiązać współpracę z innymi programistami i uzyskać pomoc.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
