---
title: Konwertuj XPS na JPEG w Javie
linktitle: Konwertuj XPS na JPEG w Javie
second_title: Aspose.Page API Java
description: Dowiedz się, jak przekonwertować XPS na JPEG w Javie za pomocą Aspose.Page. Obszerny przewodnik zawierający instrukcje krok po kroku umożliwiające bezproblemową integrację.
type: docs
weight: 11
url: /pl/java/xps-conversion/to-jpeg/
---
## Wstęp
tym samouczku omówimy, jak konwertować pliki XPS (Specyfikacja papieru XML) na obrazy JPEG za pomocą Aspose.Page dla Java. Aspose.Page to potężna biblioteka Java, która umożliwia programistom płynną pracę z XPS i innymi formatami dokumentów. Ten przewodnik krok po kroku pomoże Ci zrozumieć proces i wdrożyć go w aplikacjach Java.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Środowisko programistyczne Java: Upewnij się, że na komputerze jest skonfigurowane środowisko programistyczne Java.
-  Biblioteka Aspose.Page dla Java: Pobierz i zainstaluj bibliotekę Aspose.Page dla Java. Możesz znaleźć drogę do biblioteki[Tutaj](https://releases.aspose.com/page/java/).
- Przykładowy dokument XPS: Przygotuj przykładowy dokument XPS, który chcesz przekonwertować na format JPEG.
## Importuj pakiety
Rozpocznij od zaimportowania niezbędnych pakietów do klasy Java:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Krok 1: Zainicjuj ścieżki i dokument XPS
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Zainicjuj strumień wejściowy XPS
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Krok 2: Ustaw opcje JpegSave
```java
// Zainicjuj obiekt opcji z niezbędnymi parametrami.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## Krok 3: Utwórz urządzenie renderujące
```java
// Utwórz urządzenie renderujące dla formatu PDF
ImageDevice device = new ImageDevice();
```
## Krok 4: Zapisz XPS jako JPEG
```java
document.save(device, options);
```
## Krok 5: Iteruj i zapisuj strony JPEG
```java
//Iteruj po partycjach dokumentów (dokumenty stałe, w kategoriach XPS)
for (int i = 0; i < device.getResult().length; i++) {
    // Iteruj po stronach partycji
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Zainicjuj strumień wyjściowy obrazu
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // Napisz obraz
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //zamknij strumień
        imageStream.close();
    }
}
```
Ta seria kroków skutecznie przekonwertuje dokument XPS na obrazy JPEG, każdy zapisany osobno.
## Wniosek
Gratulacje! Pomyślnie nauczyłeś się konwertować XPS na JPEG w Javie za pomocą Aspose.Page. Proces ten jest nieoceniony dla programistów pracujących z konwersją dokumentów w aplikacjach Java.
## Często Zadawane Pytania

### P: Czy Aspose.Page nadaje się do projektów komercyjnych?
 O: Tak, Aspose.Page jest produktem komercyjnym z dostępnymi opcjami licencjonowania. Sprawdzać[Tutaj](https://purchase.aspose.com/buy) dla szczegółów.
### P: Czy mogę wypróbować Aspose.Page przed zakupem?
 Odp.: Tak, możesz uzyskać bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/).
### P: Gdzie mogę znaleźć dokumentację Aspose.Page?
 Odp.: Dokumentacja jest dostępna[Tutaj](https://reference.aspose.com/page/java/).
### P: Jak mogę uzyskać wsparcie dla Aspose.Page?
 O: Odwiedź[Forum Aspose.Page](https://forum.aspose.com/c/page/39) za wsparcie społecznościowe.
### P: Czy potrzebuję tymczasowej licencji do testowania?
 Odp.: Tak, możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).