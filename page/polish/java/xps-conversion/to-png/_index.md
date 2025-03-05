---
title: Konwertuj XPS na PNG w Javie
linktitle: Konwertuj XPS na PNG w Javie
second_title: Aspose.Page API Java
description: Bez wysiłku konwertuj XPS na PNG w Javie za pomocą Aspose.Page. Usprawnij zadania związane z dokumentami dzięki temu niezawodnemu i przyjaznemu dla programistów rozwiązaniu.
type: docs
weight: 13
url: /pl/java/xps-conversion/to-png/
---
## Wstęp
W dynamicznym świecie tworzenia oprogramowania często pojawia się potrzeba konwersji dokumentów XPS (Specyfikacja papieru XML) na obrazy PNG (Portable Network Graphics). Aby bezproblemowo wykonać to zadanie w Javie, Aspose.Page zapewnia potężne rozwiązanie. W tym samouczku omówimy proces konwersji XPS do PNG za pomocą Aspose.Page dla Java.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że masz skonfigurowane następujące wymagania wstępne:
1. Zestaw Java Development Kit (JDK): Upewnij się, że masz zainstalowany pakiet JDK w swoim systemie.
2.  Aspose.Page dla Java: Pobierz i zainstaluj bibliotekę Aspose.Page. Możesz znaleźć link do pobrania[Tutaj](https://releases.aspose.com/page/java/).
3. Zintegrowane środowisko programistyczne (IDE): Wybierz środowisko IDE zgodne z Javą, takie jak IntelliJ IDEA lub Eclipse.
## Importuj pakiety
W swoim projekcie Java zaimportuj niezbędne pakiety, aby móc korzystać z funkcjonalności Aspose.Page. Dodaj następujące instrukcje importu na początku pliku Java:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Krok 1: Ustaw katalog dokumentów
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
```
## Krok 2: Załaduj dokument XPS
```java
// Załaduj dokument XPS
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Krok 3: Zainicjuj opcje
```java
// Zainicjuj obiekt opcji z niezbędnymi parametrami.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## Krok 4: Utwórz urządzenie renderujące
```java
// Utwórz urządzenie renderujące dla formatu PDF
ImageDevice device = new ImageDevice();
```
## Krok 5: Zapisz i wykonaj iterację
```java
// Zapisz dokument XPS w formacie PNG, korzystając z opcji i urządzenia
document.save(device, options);
//Iteruj po partycjach dokumentów (dokumenty stałe, w kategoriach XPS)
for (int i = 0; i < device.getResult().length; i++) {
    // Iteruj po stronach partycji
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Zainicjuj strumień wyjściowy obrazu
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Napisz obraz
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Zamknij strumień
        imageStream.close();
    }
}
```
Wykonując poniższe kroki, możesz bez wysiłku konwertować dokumenty XPS na obrazy PNG za pomocą Aspose.Page dla Java.
## Wniosek
Podsumowując, Aspose.Page dla Java upraszcza proces konwersji XPS do PNG, zapewniając programistom niezawodne i wydajne narzędzie. Włącz tę bibliotekę do swoich projektów Java, aby usprawnić zadania związane z manipulacją dokumentami.
## Często zadawane pytania
### Czy mogę używać Aspose.Page dla Java w projektach komercyjnych?
 Tak, Aspose.Page jest produktem komercyjnym. Możesz znaleźć informacje o licencjach[Tutaj](https://purchase.aspose.com/buy).
### Czy dostępny jest bezpłatny okres próbny?
 Tak, możesz skorzystać z bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć dokumentację Aspose.Page dla Java?
 Dostępna jest obszerna dokumentacja[Tutaj](https://reference.aspose.com/page/java/).
### Jak uzyskać tymczasową licencję do celów testowych?
 Możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
### Czy istnieją fora społeczności do dyskusji w Aspose.Page?
 Tak, odwiedź fora społeczności[Tutaj](https://forum.aspose.com/c/page/39).