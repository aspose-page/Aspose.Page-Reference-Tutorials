---
title: Dodaj gradient poziomy w języku Java PostScript
linktitle: Dodaj gradient poziomy w języku Java PostScript
second_title: Aspose.Page API Java
description: Dowiedz się, jak dodać gradient poziomy w Java PostScript za pomocą Aspose.Page dla Java. Twórz oszałamiające wizualnie dokumenty bez wysiłku.
type: docs
weight: 11
url: /pl/java/postscript-gradient-addition/horizontal/
---
## Wstęp
Witamy w tym kompleksowym samouczku na temat dodawania gradientu poziomego w Java PostScript przy użyciu Aspose.Page dla Java. Aspose.Page to potężna biblioteka Java, która umożliwia programistom pracę z PostScriptem i innymi formatami dokumentów. W tym samouczku przeprowadzimy Cię przez proces tworzenia dokumentu PostScript z poziomym gradientem, korzystając z przykładów krok po kroku.
## Warunki wstępne
Przed przystąpieniem do samouczka upewnij się, że spełniasz następujące wymagania wstępne:
- Zestaw Java Development Kit (JDK) zainstalowany na komputerze.
- Aspose.Page dla biblioteki Java. Można go pobrać z[Dokumentacja Java Aspose.Page](https://reference.aspose.com/page/java/).
## Importuj pakiety
Rozpocznij od zaimportowania niezbędnych pakietów do projektu Java. Pakiety te są kluczowe dla pracy z Aspose.Page.
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

```
## Krok 1: Utwórz prostokąt
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz strumień wyjściowy dla dokumentu PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Twórz opcje zapisywania w formacie A4
PsSaveOptions options = new PsSaveOptions();
// Utwórz nowy dokument PS z otwartą stroną
PsDocument document = new PsDocument(outPsStream, options, false);
//Utwórz prostokąt
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Krok 2: Utwórz poziomą, liniową farbę gradientową
```java
// Utwórz poziomą, liniową farbę gradientową. Składniki skali w transformacji muszą być równe szerokości i wysokości prostokąta.
// Składniki translacji są przesunięciami prostokąta.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Ustaw farbę
document.setPaint(paint);
```
## Krok 3: Wypełnij prostokąt
```java
// Wypełnij prostokąt
document.fill(rectangle);
```
## Krok 4: Wypełnij tekst gradientem
```java
// Wypełnij tekst gradientem
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```
## Krok 5: Obrysuj tekst gradientem
```java
// Obrysuj tekst gradientem
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## Wniosek
Gratulacje! Pomyślnie dodałeś poziomy gradient w Java PostScript przy użyciu Aspose.Page dla Java. Ten samouczek zawiera szczegółowy przewodnik krok po kroku, który pomoże Ci stworzyć atrakcyjne wizualnie dokumenty PostScript.
## Często Zadawane Pytania
### Czy mogę używać Aspose.Page dla Java w projektach komercyjnych?
Tak, Aspose.Page dla Java może być używany w projektach komercyjnych. Aby uzyskać szczegółowe informacje na temat licencji, odwiedź stronę[Złóż. Kup](https://purchase.aspose.com/buy).
### Czy dostępny jest bezpłatny okres próbny?
 Tak, możesz uzyskać dostęp do bezpłatnej wersji próbnej Aspose.Page dla Java[Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć dodatkową dokumentację i wsparcie?
 Odwiedzić[Dokumentacja Java Aspose.Page](https://reference.aspose.com/page/java/) dla kompleksowych zasobów. Aby uzyskać wsparcie społeczności, sprawdź[Forum Aspose.Page](https://forum.aspose.com/c/page/39).
### Jak mogę uzyskać licencję tymczasową?
 Licencję tymczasową można uzyskać od[Złóż. Kup](https://purchase.aspose.com/temporary-license/).
### Jakie są wymagania systemowe Aspose.Page dla Java?
 Patrz[dokumentacja](https://reference.aspose.com/page/java/) szczegółowe wymagania systemowe.