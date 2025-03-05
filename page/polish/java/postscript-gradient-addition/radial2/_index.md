---
title: Gradient radialny Java PostScript z Aspose.Page
linktitle: Gradient radialny Java PostScript z Aspose.Page
second_title: Aspose.Page API Java
description: Zapoznaj się z przewodnikiem krok po kroku dotyczącym dodawania gradientu radialnego w języku Java PostScript przy użyciu Aspose.Page w celu uzyskania oszałamiającej grafiki w aplikacjach Java.
type: docs
weight: 13
url: /pl/java/postscript-gradient-addition/radial2/
---
## Wstęp
Witamy w naszym przewodniku krok po kroku dotyczącym dodawania Radial Gradient 2 w Java PostScript przy użyciu Aspose.Page dla Java. Ten samouczek przeprowadzi Cię przez proces tworzenia dokumentu PostScript z pięknym gradientem promieniowym, wzbogacającym aplikacje Java o atrakcyjną wizualnie grafikę.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Praktyczna znajomość programowania w języku Java.
- Zainstalowano zestaw Java Development Kit (JDK) na komputerze.
-  Aspose.Page dla biblioteki Java, którą można pobrać z witryny[Dokumentacja Java Aspose.Page](https://reference.aspose.com/page/java/).
## Importuj pakiety
W swoim projekcie Java zaimportuj niezbędne pakiety dla Aspose.Page:
```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Krok 1: Skonfiguruj katalog dokumentów
Zdefiniuj ścieżkę do katalogu dokumentów:
```java
String dataDir = "Your Document Directory";
```
## Krok 2: Utwórz strumień wyjściowy
Utwórz strumień wyjściowy dla dokumentu PostScript:
```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```
## Krok 3: Utwórz opcje zapisu
Utwórz opcje zapisywania w formacie A4:
```java
PsSaveOptions options = new PsSaveOptions();
```
## Krok 4: Utwórz dokument PS
Utwórz nowy dokument PS z otwartą stroną:
```java
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Krok 5: Utwórz krąg
Zdefiniuj okrąg za pomocą klasy Ellipse2D.Float:
```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```
## Krok 6: Zdefiniuj kolory gradientu
Utwórz tablice kolorów i ułamków dla gradientu promieniowego:
```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```
## Krok 7: Utwórz AffineTransform
Utwórz AffineTransform dla gradientu promieniowego:
```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```
## Krok 8: Utwórz promieniową farbę gradientową
Utwórz RadialGradientPaint z określonymi parametrami:
```java
RadialGradientPaint paint = new RadialGradientPaint(new Point2D.Float(64, 64), 68, new Point2D.Float(24, 24),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## Krok 9: Ustaw okrąg farby i wypełnienia
Nałóż farbę i wypełnij okrąg gradientem promieniowym:
```java
document.setPaint(paint);
document.fill(circle);
```
## Krok 10: Zamknij stronę i zapisz dokument
Zamknij bieżącą stronę i zapisz dokument:
```java
document.closePage();
document.save();
```
Gratulacje! Pomyślnie dodałeś Radial Gradient 2 w Java PostScript przy użyciu Aspose.Page dla Java.
## Wniosek
W tym samouczku omówiliśmy, jak ulepszyć aplikacje Java za pomocą gradientów radialnych w dokumentach PostScript. Aspose.Page dla Java zapewnia potężny zestaw narzędzi do tworzenia oszałamiającej grafiki, dzięki czemu możesz przenieść swoje projekty Java na wyższy poziom.
## Często zadawane pytania
### P: Gdzie mogę znaleźć dokumentację Aspose.Page dla Java?
 Odp.: Dokumentacja jest dostępna[Tutaj](https://reference.aspose.com/page/java/).
### P: Jak mogę pobrać Aspose.Page dla Java?
 O: Możesz pobrać go z[strona z wydaniami](https://releases.aspose.com/page/java/).
### P: Czy dostępny jest bezpłatny okres próbny?
 Odp.: Tak, możesz uzyskać dostęp do bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
### P: Czy mogę uzyskać tymczasową licencję na Aspose.Page dla Java?
 Odpowiedź: Tak, możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
### P: Gdzie mogę szukać wsparcia społeczności i brać udział w dyskusjach?
 O: Odwiedź[Forum Aspose.Page](https://forum.aspose.com/c/page/39).