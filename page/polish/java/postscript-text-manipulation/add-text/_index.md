---
date: 2025-12-14
description: Dowiedz się, jak ustawić kolor tekstu w Javie przy użyciu Aspose.Page
  for Java, dodać tekst do PostScript oraz zastosować obrysowy tekst dla bogatego
  formatowania dokumentu.
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: Ustaw kolor tekstu w Javie z Aspose.Page – Przewodnik manipulacji tekstem
url: /pl/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw kolor tekstu w Javie przy użyciu Aspose.Page – Przewodnik manipulacji tekstem

## Wprowadzenie
Witamy w naszym przewodniku krok po kroku dotyczącym **set text color java** podczas pracy z plikami PostScript przy użyciu Aspose.Page for Java. Aspose.Page for Java to potężna biblioteka, która pozwala programistom tworzyć i **generate postscript file** dokumenty, manipulować czcionkami oraz precyzyjnie stylizować tekst. W tym tutorialu nauczysz się, jak dodawać tekst, zmieniać jego kolor, dostosowywać rozmiar i nawet **apply stroke text**, aby uzyskać wykończenie.

## Szybkie odpowiedzi
- **Jaka biblioteka pozwala mi ustawić kolor tekstu w Javie?** Aspose.Page for Java.
- **Czy mogę używać czcionek systemowych i własnych?** Yes, both are supported.
- **Jak zmienić rozmiar tekstu?** By specifying the font size when creating the `Font` or `DrFont`.
- **Czy można jednocześnie obrysować i wypełnić tekst?** Absolutely – use `fillAndStrokeText`.
- **Jaki format wyjściowy generuje ten tutorial?** A PostScript (`.ps`) document.

## Co to jest „set text color java”?
Ustawienie koloru tekstu w Javie oznacza zdefiniowanie obiektu `Color`, którego silnik renderujący (tutaj Aspose.Page) używa przy rysowaniu znaków na stronie. Ta operacja jest niezbędna do tworzenia wizualnie odróżniających się dokumentów, szczególnie przy programowym generowaniu **postscript documents**.

## Dlaczego warto używać Aspose.Page for Java?
- **Pełna kontrola** nad generowaniem PostScript bez potrzeby natywnego interpretera PostScript.
- **Wsparcie zarówno dla czcionek systemowych, jak i zewnętrznych**, umożliwiając osadzenie dowolnej typografii.
- **Łatwe API** do wypełniania, obrysowywania i **fill and stroke text**, zapewniające elastyczność w stylizacji.
- **Cross‑platform** kompatybilność – napisz raz, uruchom wszędzie tam, gdzie działa Java.

## Wymagania wstępne
Zanim zanurzysz się w temat, upewnij się, że masz:

- Podstawową wiedzę z programowania w Javie.
- Zainstalowaną bibliotekę Aspose.Page for Java. Możesz ją pobrać ze [strony pobierania Aspose.Page for Java](https://releases.aspose.com/page/java/).
- Niezbędne czcionki dostępne w określonym folderze. Dodatkowe szczegóły znajdują się w [dokumentacji Aspose.Page for Java](https://reference.aspose.com/page/java/).

## Importowanie pakietów
W swoim projekcie Java zaimportuj niezbędne pakiety dla Aspose.Page for Java:

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

## Krok 1: Konfiguracja dokumentu
Najpierw tworzymy nowy **PostScript document** i konfigurujemy opcje wyjściowe.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// A text to write to PS file
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Jak ustawić kolor tekstu w Javie przy użyciu czcionki systemowej
Teraz demonstrujemy **set text color java** przy użyciu czcionki dostarczonej przez system.

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **Tip:** Metoda `fillText` automatycznie używa bieżącego koloru, jeśli nie przekażesz argumentu `Color`, który domyślnie jest czarny.

## Używanie własnej czcionki i zmiana rozmiaru tekstu
Możesz także **change text size** i użyć własnej czcionki przechowywanej w folderze czcionek.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Obrysowywanie (Stroke) tekstu – zastosowanie Stroke Text
Obrysowanie tekstu nadaje mu wyraźną krawędź. Tutaj **apply stroke text** przy użyciu `BasicStroke`.

```java
// Using system font for outlining text
document.outlineText(str, font, 50, 300);
// Outline text with blue‑violet colored 2‑points width pen
Stroke stroke = new BasicStroke(2);
Color strokeColor = new Color(138, 43, 226); // blue‑violet
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```

## Obrysowywanie tekstu własną czcionką
Ta sama technika działa z własnymi czcionkami.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Krok 6: Zapis dokumentu
Na koniec zamknij stronę i zapisz plik na dysku.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|----------|
| **Font not found** | Upewnij się, że plik czcionki znajduje się w `necessary_fonts` i ścieżka do folderu została poprawnie dodana za pomocą `options.setAdditionalFontsFolders`. |
| **Color not applied** | Sprawdź, czy wywołujesz przeciążenie `fillText` lub `outlineText`, które zawiera argument `Color`. |
| **Stroke appears too thin** | Zwiększ szerokość `BasicStroke` (np. `new BasicStroke(3)`). |
| **Document not opening** | Potwierdź, że wygenerowany plik `.ps` jest zapisany z prawidłowym rozszerzeniem i że Twój przeglądarka obsługuje PostScript. |

## Najczęściej zadawane pytania

**Q:** Czy mogę używać własnych czcionek z Aspose.Page for Java?  
A: Tak, możesz używać własnych czcionek, podając nazwę i rozmiar czcionki w klasie `DrFont`.

**Q:** Jak mogę zmienić kolor tekstu?  
A: Możesz ustawić żądany kolor przy użyciu klasy `Color` podczas wypełniania lub obrysowywania tekstu.

**Q:** Czy można dodać wiele stron do dokumentu PostScript?  
A: Oczywiście! Możesz tworzyć wiele stron, powtarzając kroki tworzenia dokumentu i zapisu.

**Q:** Jaki jest cel klasy `ExternalFontCache`?  
A: `ExternalFontCache` służy do pobierania własnych czcionek, zapewniając ich dostępność do manipulacji tekstem.

**Q:** Czy mogę zastosować różne obrysy do tekstu z obrysem?  
A: Tak, możesz dostosować szerokość i kolor obrysu przy użyciu klasy `Stroke` oraz klasy `Color`.

## Podsumowanie
Gratulacje! Teraz wiesz, jak **set text color java**, zmieniać rozmiary czcionek, **apply stroke text** oraz **create postscript document** przy użyciu Aspose.Page for Java. Eksperymentuj z różnymi czcionkami, kolorami i stylami obrysów, aby uzyskać profesjonalnie wyglądające wyjście PostScript.

---

**Ostatnia aktualizacja:** 2025-12-14  
**Testowano z:** Aspose.Page for Java 23.12 (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}