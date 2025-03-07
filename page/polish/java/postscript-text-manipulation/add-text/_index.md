---
title: Manipulacja tekstem w Aspose.Page w Javie
linktitle: Dodaj tekst w języku Java PostScript
second_title: Aspose.Page API Java
description: Poznaj możliwości Aspose.Page dla Java w naszym samouczku na temat dodawania tekstu do dokumentów PostScript. Naucz się z łatwością korzystać z czcionek systemowych i niestandardowych.
weight: 10
url: /pl/java/postscript-text-manipulation/add-text/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Manipulacja tekstem w Aspose.Page w Javie

## Wstęp
Witamy w naszym przewodniku krok po kroku dotyczącym dodawania tekstu w języku Java PostScript przy użyciu Aspose.Page dla języka Java. Aspose.Page dla Java to potężna biblioteka, która pozwala programistom z łatwością manipulować dokumentami PostScript. W tym samouczku przeprowadzimy Cię przez proces dodawania tekstu, używania czcionek systemowych i niestandardowych, obrysowywania tekstu i dodawania obrysów, aby uzyskać atrakcyjny wizualnie efekt.
## Warunki wstępne
Przed przystąpieniem do samouczka upewnij się, że spełniasz następujące wymagania wstępne:
- Podstawowa znajomość programowania w języku Java.
-  Zainstalowana biblioteka Aspose.Page dla Java. Można go pobrać z[Aspose.Page dla strony pobierania Java](https://releases.aspose.com/page/java/).
-  Niezbędne czcionki dostępne w określonym folderze. Dodatkowe informacje można znaleźć w[Aspose.Page dla dokumentacji Java](https://reference.aspose.com/page/java/).
## Importuj pakiety
W swoim projekcie Java zaimportuj niezbędne pakiety dla Aspose.Page dla Java:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```
## Krok 1: Skonfiguruj dokument
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Utwórz strumień wyjściowy dla dokumentu PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Twórz opcje zapisywania w formacie A4
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// Tekst do zapisania w pliku PS
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Utwórz nowy 1-stronicowy dokument PS
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Krok 2: Używanie czcionki systemowej do wypełniania tekstu
```java
// Używanie czcionki systemowej do wypełniania tekstu
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Wypełnij tekst domyślnym lub już zdefiniowanym kolorem (czarny)
document.fillText(str, font, 50, 100);
// Wypełnij tekst kolorem niebieskim
document.fillText(str, font, 50, 150, Color.BLUE);
```
## Krok 3: Używanie niestandardowej czcionki do wypełniania tekstu
```java
// Używanie niestandardowej czcionki do wypełniania tekstu
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Wypełnij tekst domyślnym lub już zdefiniowanym kolorem (czarny)
document.fillText(str, drFont, 50, 200);
// Wypełnij tekst kolorem niebieskim
document.fillText(str, drFont, 50, 250, Color.BLUE);
```
## Krok 4: Obrysowywanie tekstu czcionką systemową
```java
// Używanie czcionki systemowej do obrysowania tekstu
document.outlineText(str, font, 50, 300);
// Obrysuj tekst niebiesko-fioletowym pisakiem o szerokości 2 punktów
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Wypełnij tekst kolorem pomarańczowym i obrysuj niebieskim piórem o szerokości 2 punktów
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```
## Krok 5: Obrysowywanie tekstu niestandardową czcionką
```java
// Używanie niestandardowej czcionki do obrysowywania tekstu
document.outlineText(str, drFont, 50, 450);
// Obrysuj tekst niebiesko-fioletowym pisakiem o szerokości 2 punktów
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Wypełnij tekst kolorem pomarańczowym i obrysuj niebieskim piórem o szerokości 2 punktów
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```
## Krok 6: Zapisz dokument
```java
// Zamknij bieżącą stronę
document.closePage();
// Zapisz dokument
document.save();
```
## Wniosek
Gratulacje! Pomyślnie nauczyłeś się dodawać tekst w Java PostScript przy użyciu Aspose.Page dla Java. Eksperymentuj z różnymi czcionkami, kolorami i opcjami konturowania, aby jeszcze bardziej ulepszyć swój dokument.
## Często Zadawane Pytania
### Czy mogę używać własnych niestandardowych czcionek w Aspose.Page dla Java?
 Tak, możesz używać czcionek niestandardowych, określając nazwę i rozmiar czcionki w pliku`DrFont` klasa.
### Jak mogę zmienić kolor tekstu?
 Możesz ustawić żądany kolor za pomocą`Color` class podczas wypełniania lub konspektu tekstu.
### Czy można dodać wiele stron do dokumentu PostScript?
Absolutnie! Możesz utworzyć wiele stron, powtarzając kroki tworzenia i zapisywania dokumentu.
###  Jaki jest cel`ExternalFontCache` class?
`ExternalFontCache` służy do pobierania niestandardowych czcionek, zapewniając ich dostępność do manipulacji tekstem.
### Czy mogę zastosować różne obrysy do zaznaczonego tekstu?
 Tak, możesz dostosować szerokość i kolor obrysu za pomocą`Stroke` klasa i`Color` klasy, odpowiednio.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
