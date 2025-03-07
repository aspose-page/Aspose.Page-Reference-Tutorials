---
title: Dodaj wzór kreskowania w języku Java PostScript
linktitle: Dodaj wzór kreskowania w języku Java PostScript
second_title: Aspose.Page API Java
description: Dowiedz się, jak dodawać urzekające wzory kreskowania do dokumentów Java PostScript za pomocą Aspose.Page. Podnieś poziom swoich treści wizualnych bez wysiłku.
weight: 10
url: /pl/java/postscript-hatch-patterns/add-hatch-pattern/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj wzór kreskowania w języku Java PostScript

## Wstęp
świecie programowania w języku Java ulepszanie elementów wizualnych jest powszechnym wymogiem stawianym programistom. Intrygującym ulepszeniem wizualnym jest dodanie wzorów kreskowania do dokumentów PostScript. Ten samouczek poprowadzi Cię przez proces dodawania wzorów kreskowania przy użyciu Aspose.Page dla Java.
## Warunki wstępne
Zanim zagłębisz się w samouczek, upewnij się, że masz następującą konfigurację:
- Środowisko programistyczne Java: Upewnij się, że masz gotowe środowisko programistyczne Java.
-  Biblioteka Aspose.Page dla Java: Pobierz i zainstaluj bibliotekę Aspose.Page dla Java. Możesz znaleźć potrzebne pliki[Tutaj](https://releases.aspose.com/page/java/).
## Importuj pakiety
Aby rozpocząć, zaimportuj wymagane pakiety do swojego projektu Java. Użyj następującego fragmentu kodu:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Krok 1: Skonfiguruj parametry początkowe
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz strumień wyjściowy dla dokumentu PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Twórz opcje zapisywania w formacie A4
PsSaveOptions options = new PsSaveOptions();
// Utwórz nowy dokument PS z otwartą stroną
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```
## Krok 2: Zapisz stan grafiki i przetłumacz
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```
## Krok 3: Utwórz kwadrat dla każdego wzoru
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```
## Krok 4: Ustaw pióro dla konturu kwadratu
```java
BasicStroke stroke = new BasicStroke(2);
```
## Krok 5: Iteracja po wzorach kreskowania
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (kontynuuj podany kod)
}
```
## Krok 6: Przywróć stan grafiki
```java
document.writeGraphicsRestore();
```
## Krok 7: Wypełnij tekst wzorem kreskowania
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```
## Krok 8: Obrysuj tekst wzorem kreskowania
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```
## Krok 9: Zamknij i zapisz dokument
```java
document.closePage();
document.save();
```
Wykonaj poniższe kroki, a pomyślnie dodasz wzory kreskowania do dokumentu Java PostScript za pomocą Aspose.Page.
## Wniosek
Włączenie elementów wizualnych, takich jak wzory kreskowania, może znacznie zwiększyć atrakcyjność aplikacji Java. Aspose.Page dla Java sprawia, że ten proces jest płynny, umożliwiając łatwe tworzenie oszałamiających wizualnie dokumentów PostScript.
## Często zadawane pytania
### Czy mogę używać Aspose.Page dla Java z innymi frameworkami Java?
Tak, Aspose.Page dla Java został zaprojektowany tak, aby bezproblemowo integrować się z różnymi frameworkami Java.
### Czy dostępna jest wersja próbna Aspose.Page dla Java?
 Tak, możesz uzyskać dostęp do bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
### Jak mogę uzyskać tymczasową licencję na Aspose.Page dla Java?
 Możesz nabyć licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
### Gdzie mogę znaleźć więcej samouczków i wsparcia dla Aspose.Page dla Java?
 Poznaj[Aspose.Page dla forum Java](https://forum.aspose.com/c/page/39) za tutoriale i wsparcie społeczności.
### Czy istnieje obszerne źródło dokumentacji dla Aspose.Page dla Java?
 Tak, zapoznaj się z dokumentacją[Tutaj](https://reference.aspose.com/page/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
