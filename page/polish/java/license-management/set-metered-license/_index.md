---
date: 2026-09-24
description: Dowiedz się, jak używać Aspose.Page do konwersji EPS na PNG w Javie,
  skonfigurować licencję rozliczaną i efektywnie zapisać plik PNG w kodzie Java.
keywords:
- aspose page convert eps
- write png file java
- metered license java
- eps to png conversion
lastmod: 2026-09-24
linktitle: Ustaw Metered License w Javie
og_description: Aspose.Page konwertuje EPS na PNG w Javie z metered license. Ten przewodnik
  pokazuje krok po kroku, jak skonfigurować licencjonowanie, renderować EPS i zapisać
  plik PNG w kodzie Java.
og_image_alt: Guide showing Aspose.Page Java converting EPS to PNG with metered license
og_title: Aspose.Page konwertuje EPS na PNG w Javie (licencja rozliczana)
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  headline: Aspose.Page convert EPS to PNG in Java (metered license)
  type: TechArticle
- description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  name: Aspose.Page convert EPS to PNG in Java (metered license)
  steps:
  - name: initialize document and image format
    text: First, set the metered keys and define the output format (PNG). This establishes
      the foundation for the conversion. The `MeteredLicense` class stores your public
      and private keys, while `ImageSaveOptions` tells Aspose.Page to produce PNG
      output.
  - name: initialize PostScript input stream
    text: Open the EPS file you want to convert. The stream feeds the document into
      Aspose.Page. The `FileInputStream` reads the EPS file from disk, allowing the
      `Document` constructor to parse the PostScript data.
  - name: check document license
    text: Always verify that the metered license was applied correctly before processing.
      The `isLicensed()` method returns `true` only when the supplied keys are valid,
      preventing accidental usage of an unlicensed library.
  - name: initialize options and image device
    text: Create the options object that controls conversion settings and the device
      that will receive the rendered image. `ImageDevice` captures the rasterized
      output in memory, while `ImageSaveOptions` lets you tweak DPI, compression level,
      and color depth.
  - name: save EPS file as image
    text: This is the core **save EPS as PNG** call. The document is rendered into
      the image device using the options we configured. The `document.save(device,
      options)` method performs the rasterization in a single step.
  - name: get and save image bytes
    text: Extract the PNG bytes from the device and write them to a file on disk.
      This step demonstrates how to **write PNG file Java** safely. `Files.write(Paths.get("output.png"),
      device.getImagesBytes()[0])` persists the image without additional libraries.
  type: HowTo
- questions:
  - answer: Log into your Aspose account, navigate to the **Metered License** section,
      and copy the generated public and private keys.
    question: How do I obtain metered public and private keys?
  - answer: Aspose.Page offers a free trial with full functionality; production use
      requires a paid license. Download the trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is the Aspose.Page library free?
  - answer: Yes, a commercial license permits deployment in production environments.
      Purchase a license [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for commercial projects?
  - answer: The full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: Temporary licenses are provided through the Aspose portal [Aspose temporary
      license page](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image conversion
- metered licensing
title: Aspose.Page konwertuje EPS na PNG w Javie (licencja rozliczana)
url: /pl/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page konwertuje EPS na PNG w Javie (licencja metrowa)

## Wprowadzenie
Jeśli potrzebujesz **zapisać EPS jako PNG** w aplikacji Java, jednocześnie utrzymując prostą licencję, jesteś we właściwym miejscu. Ten samouczek przeprowadzi Cię przez konfigurację **licencji metrowej** dla Aspose.Page, wczytanie pliku EPS (Encapsulated PostScript) oraz konwersję go do obrazu PNG. Po zakończeniu zrozumiesz, jak **efektywnie renderować EPS do PNG** oraz jak **zapisać plik PNG w Javie** w sposób niezawodny w środowisku produkcyjnym.

## Szybkie odpowiedzi
- **Co oznacza „zapisać EPS jako PNG”?** Konwertuje wektorowy plik EPS na rastrowy obraz PNG, zachowując przezroczystość i bezstratną kompresję.  
- **Dlaczego używać licencji metrowej?** Płacisz tylko za przetworzone strony, co jest idealne przy zmiennym obciążeniu.  
- **Czy potrzebne jest połączenie internetowe?** Nie, klucze metrowe są weryfikowane lokalnie na JVM.  
- **Jaka wersja Javy jest wymagana?** Java 8 lub wyższa jest w pełni wspierana.  
- **Jak długo trwa konfiguracja?** Około 10 minut dla podstawowej implementacji.

## Co to jest „zapisz EPS jako PNG”?
Zapisanie EPS jako PNG konwertuje wektorowy dokument Encapsulated PostScript na rastrowy obraz PNG, zachowując przezroczystość i oferując bezstratną kompresję. Ta transformacja jest przydatna, gdy potrzebujesz grafik gotowych do sieci, miniatur lub podglądów do druku, które mogą być wyświetlane w dowolnej przeglądarce bez wymogu interpretera PostScript.

## Dlaczego renderować EPS do PNG przy użyciu Aspose.Page?
Aspose.Page udostępnia czyste API Java, które rasteryzuje pliki EPS z wysoką wiernością, obsługuje ponad 50 formatów wyjściowych i oferuje licencjonowanie metrowe, dzięki czemu płacisz tylko za to, co konwertujesz. Biblioteka może przetwarzać dokumenty wielostronicowe bez ładowania całego pliku do pamięci, zapewniając szybkie i dokładne renderowanie na każdej platformie obsługującej JVM.

## Wymagania wstępne
- Podstawowe doświadczenie w programowaniu w Javie.  
- Biblioteka Aspose.Page pobrana ze [Strona pobierania Aspose.Page Java](https://releases.aspose.com/page/java/).  
- Para metrowych kluczy publicznego i prywatnego z Twojego konta Aspose.  

## Importowanie pakietów
Instrukcje `import` wprowadzają wymagane klasy do zasięgu. Zachowaj ten blok dokładnie tak, jak pokazano, aby kod kompilował się bez zmian.

Klasy `java.io` obsługują strumienie plików, natomiast klasy Aspose.Page zarządzają licencjonowaniem, wczytywaniem dokumentu i renderowaniem obrazu.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Jak zapisać EPS jako PNG przy użyciu Aspose.Page Java
Poniżej znajduje się przewodnik krok po kroku, który łączy licencjonowanie, wczytywanie, renderowanie i zapisywanie końcowego pliku PNG.

### Bezpośrednia odpowiedź
Wczytaj plik EPS, zastosuj licencję metrową, skonfiguruj `ImageSaveOptions` dla PNG, wyrenderuj dokument do `ImageDevice`, a na końcu zapisz otrzymaną tablicę bajtów na dysk. Ta sekwencja kończy proces **zapisu EPS jako PNG** w zaledwie kilku linijkach kodu Java.

### Krok 1: inicjalizacja dokumentu i formatu obrazu
Najpierw ustaw klucze metrowe i określ format wyjściowy (PNG). To tworzy podstawę konwersji.

Klasa `MeteredLicense` przechowuje Twoje klucze publiczny i prywatny, natomiast `ImageSaveOptions` instruuje Aspose.Page, aby generował wyjście PNG.

```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```

### Krok 2: inicjalizacja strumienia wejściowego PostScript
Otwórz plik EPS, który chcesz przekonwertować. Strumień dostarcza dokument do Aspose.Page.

`FileInputStream` odczytuje plik EPS z dysku, umożliwiając konstruktorowi `Document` parsowanie danych PostScript.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### Krok 3: sprawdzenie licencji dokumentu
Zawsze weryfikuj, czy licencja metrowa została poprawnie zastosowana przed przetwarzaniem.

Metoda `isLicensed()` zwraca `true` tylko wtedy, gdy podane klucze są prawidłowe, zapobiegając przypadkowemu użyciu nielicencjonowanej biblioteki.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### Krok 4: inicjalizacja opcji i urządzenia obrazu
Utwórz obiekt opcji, który kontroluje ustawienia konwersji, oraz urządzenie, które otrzyma wyrenderowany obraz.

`ImageDevice` przechwytuje rasteryzowane wyjście w pamięci, natomiast `ImageSaveOptions` pozwala dostosować DPI, poziom kompresji i głębię kolorów.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### Krok 5: zapisanie pliku EPS jako obrazu
To jest podstawowe wywołanie **zapisz EPS jako PNG**. Dokument jest renderowany do urządzenia obrazu przy użyciu skonfigurowanych opcji.

Metoda `document.save(device, options)` wykonuje rasteryzację w jednym kroku.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### Krok 6: pobranie i zapisanie bajtów obrazu
Wyodrębnij bajty PNG z urządzenia i zapisz je do pliku na dysku. Ten krok pokazuje, jak **zapisać plik PNG w Javie** bezpiecznie.

`Files.write(Paths.get("output.png"), device.getImagesBytes()[0])` zapisuje obraz bez dodatkowych bibliotek.

```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```

## Typowe problemy i rozwiązania
| Issue | Why it happens | Fix |
|-------|----------------|-----|
| **Licencja nie rozpoznana** | Klucze są nieprawidłowe lub `setMeteredKey` jest wywoływany po przetworzeniu dokumentu. | Sprawdź ponownie ciągi kluczy publicznego/prywatnego i upewnij się, że `setMeteredKey` jest wywoływany przed jakimikolwiek wywołaniami Aspose.Page. |
| **Plik wyjściowy jest pusty** | `device.getImagesBytes()` zwróciło `null`, ponieważ plik EPS nie mógł zostać sparsowany. | Zweryfikuj, że plik EPS jest prawidłowy oraz że `ImageSaveOptions` określa niezerowy rozmiar płótna. |
| **OutOfMemoryError przy dużych EPS** | Renderowanie dużych plików wektorowych zużywa dużo pamięci sterty. | Przetwarzaj strony pojedynczo lub zwiększ pamięć sterty JVM (`-Xmx2g`). |

## Najczęściej zadawane pytania

**Q: Jak uzyskać metrowe klucze publiczny i prywatny?**  
A: Zaloguj się na swoje konto Aspose, przejdź do sekcji **Metered License** i skopiuj wygenerowane klucze publiczny i prywatny.

**Q: Czy biblioteka Aspose.Page jest darmowa?**  
A: Aspose.Page oferuje bezpłatną wersję próbną z pełną funkcjonalnością; użycie w produkcji wymaga płatnej licencji. Pobierz wersję próbną ze [Strona pobierania wersji próbnej Aspose](https://releases.aspose.com/).

**Q: Czy mogę używać Aspose.Page w projektach komercyjnych?**  
A: Tak, licencja komercyjna pozwala na wdrożenie w środowiskach produkcyjnych. Kup licencję na [Strona zakupu Aspose](https://purchase.aspose.com/buy).

**Q: Gdzie mogę znaleźć dodatkową dokumentację?**  
A: Pełna referencja API jest dostępna pod adresem [Referencja API Aspose.Page Java](https://reference.aspose.com/page/java/).

**Q: Jak mogę uzyskać tymczasową licencję do oceny?**  
A: Tymczasowe licencje są udostępniane przez portal Aspose na [Strona tymczasowej licencji Aspose](https://purchase.aspose.com/temporary-license/).

**Q: Co zrobić, jeśli muszę konwertować wielostronicowe pliki EPS?**  
A: Przejdź w pętli po każdej stronie używając `device.getImagesBytes()` i zapisz każdą tablicę bajtów do osobnego pliku PNG.

**Q: Czy mogę zmienić jakość PNG lub głębię kolorów?**  
A: Tak, skonfiguruj `ImageSaveOptions` (np. `options.setCompressionLevel(9)`) przed wywołaniem `document.save(...)`.

---

**Ostatnia aktualizacja:** 2026-09-24  
**Testowano z:** Aspose.Page 24.12 dla Java (najnowsza)  
**Autor:** Aspose

## Powiązane samouczki

- [Jak ustawić licencję dla Aspose.Page Java API – Zarządzanie licencją](/page/java/license-management/)
- [Konwersja PS do PNG przy użyciu Aspose.Page Java API](/page/java/postscript-conversion/to-image/)
- [Zmiana rozmiaru EPS przy użyciu Aspose.Page – Manipulacja EPS w Javie](/page/java/manipulation-eps/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}