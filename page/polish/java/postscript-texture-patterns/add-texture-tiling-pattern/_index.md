---
title: Dodaj wzór kafelkowania tekstury w języku Java PostScript
linktitle: Dodaj wzór kafelkowania tekstury w języku Java PostScript
second_title: Aspose.Page API Java
description: łatwością dodawaj wzory kafelków tekstur do dokumentów PostScript za pomocą Aspose.Page dla Java. Zapoznaj się z naszym przewodnikiem dotyczącym bezproblemowej integracji, aby poznać kreatywne możliwości.
weight: 10
url: /pl/java/postscript-texture-patterns/add-texture-tiling-pattern/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj wzór kafelkowania tekstury w języku Java PostScript

## Wstęp
W środowisku programowania w języku Java tworzenie skomplikowanych wzorów i tekstur w dokumentach PostScript jest powszechnym wymogiem. Aspose.Page dla Java okazuje się wartościowym narzędziem pozwalającym bez wysiłku osiągnąć to zadanie. W tym samouczku przeprowadzimy Cię przez proces dodawania wzoru kafelków tekstury do dokumentu Java PostScript za pomocą Aspose.Page.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Podstawowa znajomość języka programowania Java.
- Znajomość struktury dokumentu PostScript.
-  Zainstalowana biblioteka Aspose.Page dla Java. Możesz go pobrać[Tutaj](https://releases.aspose.com/page/java/).
## Importuj pakiety
Zacznij od zaimportowania niezbędnych pakietów dla swojego projektu Java:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Krok 1: Utwórz dokument PostScript
Rozpocznij od utworzenia nowego dokumentu PostScript, określając strumień wyjściowy i opcje zapisywania. Upewnij się, że masz skonfigurowane niezbędne ścieżki.
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz strumień wyjściowy dla dokumentu PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTextureTilingPattern_outPS.ps");
// Twórz opcje zapisywania w formacie A4
PsSaveOptions options = new PsSaveOptions();
// Utwórz nowy dokument PS z otwartą stroną
PsDocument document = new PsDocument(outPsStream, options, false);
// Utwórz nowy dokument PS z otwartą stroną
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Krok 2: Skonfiguruj środowisko graficzne
Skonfiguruj środowisko graficzne, tłumacząc początek i tworząc BufferedImage z pliku obrazu tekstury.
```java
document.writeGraphicsSave();
document.translate(200, 100);
// Utwórz obiekt BufferedImage z pliku obrazu
BufferedImage image = ImageIO.read(new File(dataDir + "TestTexture.bmp"));
```
## Krok 3: Utwórz pędzel tekstury
Zdefiniuj pędzel tekstury z obrazu, określając obszar, który ma zostać pokryty teksturą.
```java
// Utwórz obszar obrazu o podwójnej szerokości
Rectangle2D.Float imageArea = new Rectangle2D.Float(0, 0, image.getWidth() * 2, image.getHeight());
// Utwórz pędzel tekstury z obrazu
TexturePaint paint = new TexturePaint(image, imageArea);
```
## Krok 4: Narysuj i wypełnij kształty
Utwórz prostokąt i wypełnij go zdefiniowanym pędzlem teksturowym. Dodatkowo narysuj i obrysuj kształt, aby uzyskać atrakcyjność wizualną.
```java
// Utwórz prostokąt
Rectangle2D.Float shape = new Rectangle2D.Float(0, 0, 200, 100);
// Ustaw ten pędzel tekstury jako bieżącą farbę
document.setPaint(paint);
// Wypełnij prostokąt
document.fill(shape);
document.setPaint(Color.RED);
document.setStroke(new BasicStroke(2));
document.draw(shape);
```
## Krok 5: Dodaj tekst ze wzorem tekstury
Dodaj tekst do dokumentu i wypełnij/obrysuj go wzorem tekstury. W razie potrzeby dostosuj czcionkę, położenie i inne parametry.
```java
// Wypełnij tekst wzorem tekstury
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
// Obrysuj tekst wzorem tekstury
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## Krok 6: Zapisz i zamknij
Zakończ proces zamykając bieżącą stronę, zapisując dokument i zapewniając bezproblemową realizację.
```java
// Zamknij bieżącą stronę
document.closePage();
// Zapisz dokument
document.save();
```
## Wniosek
Gratulacje! Pomyślnie dodałeś wzór kafelkowania tekstury do dokumentu Java PostScript przy użyciu Aspose.Page dla Java. Zachęcamy do zapoznania się z dalszymi opcjami dostosowywania i uwolnienia pełnego potencjału tej potężnej biblioteki.

## Często zadawane pytania
### Czy Aspose.Page dla Java jest odpowiedni dla początkujących?
Absolutnie! Aspose.Page dla Java zapewnia obszerną dokumentację, dzięki czemu jest dostępna dla programistów na wszystkich poziomach umiejętności.
### Czy mogę zintegrować Aspose.Page for Java z moim istniejącym projektem Java?
 Tak, możesz łatwo zintegrować Aspose.Page for Java ze swoim projektem, postępując zgodnie z dostarczoną dokumentacją[Tutaj](https://reference.aspose.com/page/java/).
### Gdzie mogę znaleźć wsparcie lub omówić zapytania związane z Aspose.Page?
 Odwiedzić[Forum Aspose.Page](https://forum.aspose.com/c/page/39) nawiązać kontakt ze społecznością i poprosić o pomoc.
### Czy dostępna jest bezpłatna wersja próbna Aspose.Page dla Java?
 Tak, możesz skorzystać z bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
### Jak mogę uzyskać tymczasową licencję na Aspose.Page dla Java?
 Odwiedzać[ten link](https://purchase.aspose.com/temporary-license/) w celu uzyskania licencji tymczasowej.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
