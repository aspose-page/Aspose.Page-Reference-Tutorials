---
date: 2026-02-05
description: Dowiedz się, jak zapisać plik EPS jako PNG przy użyciu Aspose.Page dla
  Javy, konfigurując licencję licznikową. Przewodnik krok po kroku z pełnym przykładem
  kodu.
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: Zapisz EPS jako PNG przy użyciu Aspose.Page Java (licencja metrowa)
url: /pl/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zapisz EPS jako PNG przy użyciu Aspose.Page Java (licencja metrowa)

## Wprowadzenie
Jeśli potrzebujesz **zapisać EPS jako PNG** w aplikacji Java i szukasz prostego sposobu zarządzania licencjonowaniem, jesteś we właściwym miejscu. Ten samouczek przeprowadzi Cię przez konfigurowanie licencji metrowej dla Aspose.Page, wczytywanie pliku PostScript (EPS) oraz konwersję go do obrazu PNG — wszystko w przejrzystych, małych krokach, które możesz od razu zastosować. Po zakończeniu zrozumiesz także, jak **renderować EPS do PNG** efektywnie oraz jak napisać kod **write PNG file Java**, który sprawdzi się w środowiskach produkcyjnych.

## Szybkie odpowiedzi
- **Co oznacza „save EPS as PNG”?** Konwertuje wektorowy plik EPS na rastrowy obraz PNG.  
- **Dlaczego używać licencji metrowej?** Pozwala płacić tylko za przetworzone strony, idealne przy zmiennym obciążeniu.  
- **Czy potrzebne jest połączenie z internetem?** Nie, klucze metrowe są weryfikowane lokalnie.  
- **Jakiej wersji Javy wymaga?** Java 8 lub nowsza.  
- **Jak długo trwa konfiguracja?** Około 10 minut dla podstawowej implementacji.  

## Co to jest „save EPS as PNG”?
Zapisanie EPS jako PNG przekształca skalowalny dokument Encapsulated PostScript w powszechnie obsługiwany format bitmapowy. PNG zachowuje przezroczystość i oferuje bezstratną kompresję, co czyni go idealnym do grafiki internetowej, miniatur i podglądów wydruków.

## Dlaczego renderować EPS do PNG przy użyciu Aspose.Page?
- **Czyste API Java** – bez zależności natywnych, więc możesz uruchomić je wszędzie tam, gdzie obsługiwana jest JVM.  
- **Wysoka wierność renderowania** – grafika wektorowa jest rasteryzowana dokładnie, zachowując jakość linii.  
- **Licencjonowanie metrowe** – płacisz tylko za to, co konwertujesz, co utrzymuje koszty przewidywalnymi.  
- **Wiele opcji wyjściowych** – oprócz PNG możesz generować także JPEG, TIFF i inne, dając elastyczność w różnych projektach.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

- Podstawową znajomość programowania w Javie.  
- Bibliotekę Aspose.Page zainstalowaną – pobierz ją [tutaj](https://releases.aspose.com/page/java/).  
- Publiczny i prywatny klucz metrowy, które możesz uzyskać w swoim koncie Aspose.

## Importowanie pakietów
Najpierw zaimportuj klasy, które będą potrzebne. Zachowaj blok importu dokładnie tak, jak pokazano, aby kod kompilował się bez zmian.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Jak zapisać EPS jako PNG przy użyciu Aspose.Page Java
Poniżej znajduje się przewodnik krok po kroku, łączący licencjonowanie, wczytywanie, renderowanie i zapisywanie końcowego pliku PNG.

### Krok 1: Inicjalizacja dokumentu i formatu obrazu
Tutaj ustawiamy klucze metrowe i definiujemy format wyjściowy (PNG). To podstawa operacji **save EPS as PNG**.

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

### Krok 2: Inicjalizacja strumienia wejściowego PostScript
Otwórz plik EPS, który chcesz skonwertować. Strumień dostarcza dokument do Aspose.Page.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### Krok 3: Sprawdzenie licencji dokumentu
Zawsze weryfikuj, czy licencja metrowa została poprawnie zastosowana przed przetwarzaniem.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### Krok 4: Inicjalizacja opcji i urządzenia obrazu
Utwórz obiekt opcji kontrolujący ustawienia konwersji oraz urządzenie, które otrzyma wyrenderowany obraz.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### Krok 5: Zapisz plik EPS jako obraz
To jest kluczowe wywołanie **save EPS as PNG**. Dokument jest renderowany do urządzenia obrazu przy użyciu skonfigurowanych opcji.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### Krok 6: Pobierz i zapisz bajty obrazu
Wyodrębnij bajty PNG z urządzenia i zapisz je do pliku na dysku. Ten krok pokazuje, jak bezpiecznie **write PNG file Java**.

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
| Problem | Dlaczego się pojawia | Rozwiązanie |
|---------|----------------------|-------------|
| **Licencja nie rozpoznana** | Klucze są niepoprawne lub umieszczone w niewłaściwej kolejności. | Sprawdź dokładnie ciągi kluczy publicznego/prywatnego i upewnij się, że `setMeteredKey` jest wywoływane przed jakimkolwiek przetwarzaniem dokumentu. |
| **Plik wyjściowy jest pusty** | `device.getImagesBytes()` zwróciło `null`. | Zweryfikuj, czy plik EPS jest prawidłowy oraz czy `ImageSaveOptions` nie ustawiono na płótno o zerowym rozmiarze. |
| **OutOfMemoryError przy dużym EPS** | Renderowanie dużych plików wektorowych zużywa dużo pamięci. | Przetwarzaj strony pojedynczo lub zwiększ pamięć sterty JVM (`-Xmx2g`). |

## Najczęściej zadawane pytania

**Q: Jak uzyskać publiczny i prywatny klucz metrowy?**  
A: Możesz uzyskać te klucze w swoim koncie Aspose.

**Q: Czy biblioteka Aspose.Page jest darmowa?**  
A: Aspose.Page oferuje zarówno wersję próbną, jak i płatną. Odwiedź [tutaj](https://releases.aspose.com/) aby pobrać wersję próbną.

**Q: Czy mogę używać Aspose.Page w projektach komercyjnych?**  
A: Tak, Aspose.Page oferuje licencje komercyjne. Możesz je zakupić [tutaj](https://purchase.aspose.com/buy).

**Q: Gdzie mogę znaleźć dodatkową dokumentację?**  
A: Zapoznaj się z dokumentacją [tutaj](https://reference.aspose.com/page/java/).

**Q: Jak mogę uzyskać licencje tymczasowe?**  
A: Licencje tymczasowe są dostępne [tutaj](https://purchase.aspose.com/temporary-license/).

**Q: Co zrobić, jeśli muszę konwertować wielostronicowe pliki EPS?**  
A: Przejdź pętlą po każdej stronie, używając `device.getImagesBytes()` i zapisz każdy bajtowy zestaw do osobnego pliku PNG.

**Q: Czy mogę zmienić jakość PNG lub głębię kolorów?**  
A: Tak, skonfiguruj `ImageSaveOptions` (np. `options.setCompressionLevel(...)`) przed wywołaniem `document.save(...)`.

---

**Ostatnia aktualizacja:** 2025-12-03  
**Testowano z:** Aspose.Page 24.12 for Java  
**Autor:** Aspose  

**Ostatnia aktualizacja:** 2026-02-05  
**Testowano z:** Aspose.Page 24.12 for Java (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}