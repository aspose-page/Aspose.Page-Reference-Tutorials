---
date: 2025-12-03
description: Dowiedz się, jak zapisać EPS jako PNG przy użyciu Aspose.Page dla Javy,
  konfigurując licencję licznikową. Przewodnik krok po kroku z pełnym przykładem kodu.
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: Zapisz EPS jako PNG przy użyciu Aspose.Page Java (licencja metrowa)
url: /pl/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zapisz EPS jako PNG przy użyciu Aspose.Page Java (licencja metrowana)

## Wprowadzenie
Jeśli potrzebujesz **zapisać EPS jako PNG** w aplikacji Java i chcesz prosty sposób zarządzania licencjonowaniem, trafiłeś we właściwe miejsce. Ten samouczek przeprowadzi Cię przez konfigurację licencji metrowanej dla Aspose.Page, wczytanie pliku PostScript (EPS) oraz konwersję go do obrazu PNG — wszystko w przejrzystych, małych krokach, które możesz od razu zastosować.

## Szybkie odpowiedzi
- **Co oznacza „zapisz EPS jako PNG”?** Konwertuje plik wektorowy EPS na rastrowy obraz PNG.  
- **Dlaczego używać licencji metrowanej?** Pozwala płacić tylko za przetworzone strony, idealne przy zmiennym obciążeniu.  
- **Czy potrzebne jest połączenie z internetem?** Nie, klucze metrowane są weryfikowane lokalnie.  
- **Jakiej wersji Javy wymaga?** Java 8 lub nowsza.  
- **Jak długo trwa konfiguracja?** Około 10 minut dla podstawowej implementacji.

## Co to jest „zapisz EPS jako PNG”?
Zapisanie EPS jako PNG przekształca skalowalny dokument Encapsulated PostScript w powszechnie obsługiwany format bitmapowy. PNG zachowuje przezroczystość i oferuje bezstratną kompresję, co czyni go idealnym do grafiki internetowej, miniatur oraz podglądów wydruków.

## Dlaczego warto używać Aspose.Page do tego zadania?
- **Czyste API Java** – bez zależności natywnych.  
- **Wysoka wierność** – grafika wektorowa jest renderowana dokładnie.  
- **Licencjonowanie metrowane** – płacisz tylko za to, co konwertujesz.  
- **Obsługa wielu formatów wyjściowych** – PNG, JPEG, TIFF itp.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

- Podstawową znajomość programowania w Javie.  
- Bibliotekę Aspose.Page zainstalowaną – pobierz ją [tutaj](https://releases.aspose.com/page/java/).  
- Publiczny i prywatny klucz metrowany, które możesz uzyskać w swoim koncie Aspose.

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

## Krok 1: Inicjalizacja dokumentu i formatu obrazu
Tutaj ustawiamy klucze metrowane i definiujemy format wyjściowy (PNG). To podstawa operacji **zapisz EPS jako PNG**.

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

## Krok 2: Inicjalizacja strumienia wejściowego PostScript
Otwórz plik EPS, który chcesz przekonwertować. Strumień dostarcza dokument do Aspose.Page.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

## Krok 3: Sprawdzenie licencji dokumentu
Zawsze weryfikuj, czy licencja metrowana została poprawnie zastosowana przed przetwarzaniem.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

## Krok 4: Inicjalizacja opcji i urządzenia obrazu
Utwórz obiekt opcji, który kontroluje ustawienia konwersji, oraz urządzenie, które otrzyma wyrenderowany obraz.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

## Krok 5: Zapisz plik EPS jako obraz
To jest sedno wywołania **zapisz EPS jako PNG**. Dokument jest renderowany do urządzenia obrazu przy użyciu skonfigurowanych opcji.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

## Krok 6: Pobranie i zapisanie bajtów obrazu
Wyodrębnij bajty PNG z urządzenia i zapisz je do pliku na dysku.

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
|-------|----------------|-----|
| **Licencja nie rozpoznana** | Klucze są niepoprawne lub w złej kolejności. | Sprawdź dokładnie ciągi kluczy publicznego i prywatnego oraz upewnij się, że `setMeteredKey` jest wywoływane przed jakimkolwiek przetwarzaniem dokumentu. |
| **Plik wyjściowy jest pusty** | `device.getImagesBytes()` zwróciło `null`. | Zweryfikuj, czy plik EPS jest prawidłowy oraz czy `ImageSaveOptions` nie ustawia pustego (zero‑rozmiarowego) płótna. |
| **OutOfMemoryError przy dużym EPS** | Renderowanie dużych plików wektorowych zużywa dużo pamięci. | Przetwarzaj strony pojedynczo lub zwiększ przydział pamięci JVM (`-Xmx2g`). |

## Najczęściej zadawane pytania

**P: Jak uzyskać publiczny i pryny klucz metrowany?**  
O: Klucze te możesz pobrać ze swojego konta Aspose.

**P: Czy biblioteka Aspose.Page jest darmowa?**  
O: Aspose.Page oferuje zarówno wersję próbną, jak i płatną. Odwiedź [tutaj](https://releases.aspose.com/) aby pobrać wersję próbną.

**P: Czy mogę używać Aspose.Page w projektach komercyjnych?**  
O: Tak, Aspose.Page posiada licencje komercyjne. Możesz je zakupić [tutaj](https://purchase.aspose.com/buy).

**P: Gdzie znajdę dodatkową dokumentację?**  
O: Dokumentację znajdziesz [tutaj](https://reference.aspose.com/page/java/).

**P: Jak mogę uzyskać licencje tymczasowe?**  
O: Licencje tymczasowe są dostępne [tutaj](https://purchase.aspose.com/temporary-license/).

---

**Ostatnia aktualizacja:** 2025-12-03  
**Testowano z:** Aspose.Page 24.12 dla Javy  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}