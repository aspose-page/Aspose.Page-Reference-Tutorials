---
title: Dodaj gradient pionowy w języku Java PostScript
linktitle: Dodaj gradient pionowy w języku Java PostScript
second_title: Aspose.Page API Java
description: Zapoznaj się z przewodnikiem krok po kroku dotyczącym dodawania gradientów pionowych w języku Java PostScript za pomocą Aspose.Page dla języka Java. Bez wysiłku ulepszaj swoje dokumenty dzięki żywym efektom wizualnym.
weight: 14
url: /pl/java/postscript-gradient-addition/vertical/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj gradient pionowy w języku Java PostScript

## Wstęp
Witamy w tym przewodniku krok po kroku dotyczącym dodawania gradientu pionowego w Java PostScript przy użyciu Aspose.Page dla Java. Jeśli chcesz wzbogacić swój dokument o przyciągające wzrok gradienty, ten samouczek jest dla Ciebie. Aspose.Page dla Java zapewnia potężne narzędzia do płynnego manipulowania dokumentami PostScript.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Zestaw Java Development Kit (JDK) zainstalowany na komputerze.
-  Aspose.Page dla biblioteki Java. Możesz go pobrać[Tutaj](https://releases.aspose.com/page/java/).
## Importuj pakiety
Aby rozpocząć, w projekcie Java zaimportuj niezbędne pakiety:
```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
Podzielmy teraz proces dodawania gradientu pionowego w języku Java PostScript na kilka kroków.
## Krok 1: Skonfiguruj katalog dokumentów
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
```
## Krok 2: Utwórz strumień wyjściowy dla dokumentu PostScript
```java
// Utwórz strumień wyjściowy dla dokumentu PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```
## Krok 3: Utwórz opcje zapisu w formacie A4
```java
// Twórz opcje zapisywania w formacie A4
PsSaveOptions options = new PsSaveOptions();
```
## Krok 4: Utwórz nowy dokument PS
```java
// Utwórz nowy dokument PS z otwartą stroną
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Krok 5: Utwórz prostokąt
```java
//Utwórz prostokąt
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Krok 6: Skonfiguruj kolory i ułamki gradientu
```java
// Utwórz tablice kolorów i ułamków dla gradientu.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```
## Krok 7: Utwórz transformację gradientową
```java
// Utwórz transformację gradientową. Składniki skali w transformacji muszą być równe szerokości i wysokości prostokąta.
// Składniki translacji są przesunięciami prostokąta.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Obróć gradient o 90 stopni wokół początku
transform.rotate(90 * (Math.PI / 180));
```
## Krok 8: Utwórz pionową, liniową farbę gradientową
```java
// Utwórz pionową, liniową farbę gradientową.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## Krok 9: Ustaw farbę i wypełnij prostokąt
```java
// Ustaw farbę
document.setPaint(paint);
// Wypełnij prostokąt
document.fill(rectangle);
```
## Krok 10: Zamknij bieżącą stronę i zapisz dokument
```java
// Zamknij bieżącą stronę
document.closePage();
// Zapisz dokument
document.save();
```
Gratulacje! Pomyślnie dodałeś pionowy gradient do dokumentu Java PostScript za pomocą Aspose.Page dla Java.
## Wniosek
tym samouczku zbadaliśmy proces ulepszania dokumentów za pomocą żywych gradientów pionowych przy użyciu Aspose.Page dla Java. Teraz możesz przenieść manipulację dokumentami na wyższy poziom, dodając oszałamiające efekty wizualne.
## Często Zadawane Pytania
### Czy mogę używać Aspose.Page dla Java z innymi bibliotekami Java?
Tak, Aspose.Page dla Java został zaprojektowany tak, aby bezproblemowo współpracować z innymi bibliotekami Java.
### Czy dostępna jest bezpłatna wersja próbna Aspose.Page dla Java?
 Tak, możesz skorzystać z bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć dodatkową dokumentację?
 Dostępna jest szczegółowa dokumentacja[Tutaj](https://reference.aspose.com/page/java/).
### Jak mogę kupić Aspose.Page dla Java?
 Możesz kupić Aspose.Page dla Java[Tutaj](https://purchase.aspose.com/buy).
### Czy istnieje forum do dyskusji na temat Aspose.Page?
 Tak, możesz dołączyć do forum społeczności[Tutaj](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
