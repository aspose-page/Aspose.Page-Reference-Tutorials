---
title: Bezproblemowa integracja licencji licznikowych z Aspose.Page Java
linktitle: Ustaw licencję licznikową w Javie
second_title: Aspose.Page API Java
description: Poznaj bezproblemową integrację Aspose.Page z Javą. Bez wysiłku konfiguruj licencje licznikowe i zwiększaj możliwości przetwarzania dokumentów.
weight: 10
url: /pl/java/license-management/set-metered-license/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bezproblemowa integracja licencji licznikowych z Aspose.Page Java

## Wstęp
Witamy w naszym obszernym przewodniku na temat konfigurowania licencji licznikowej w Javie przy użyciu Aspose.Page. Jeśli chcesz zwiększyć możliwości przetwarzania dokumentów i zapewnić bezproblemową integrację z Aspose.Page, jesteś we właściwym miejscu. W tym samouczku przeprowadzimy Cię przez cały proces, dzieląc każdy krok na łatwo przyswajalne fragmenty.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Podstawowa znajomość programowania w języku Java.
-  Zainstalowana biblioteka Aspose.Page. Można go pobrać z[Tutaj](https://releases.aspose.com/page/java/).
- Mierzone klucze publiczne i prywatne, które można uzyskać za pośrednictwem konta Aspose.
## Importuj pakiety
Zacznijmy od zaimportowania niezbędnych pakietów dla naszego programu Java. Upewnij się, że masz zintegrowaną bibliotekę Aspose.Page ze swoim projektem.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;

```
## Krok 1: Zainicjuj format dokumentu i obrazu
Pierwszym krokiem jest skonfigurowanie dokumentu i zdefiniowanie pożądanego formatu obrazu.
```java
// ustaw mierzone klucze publiczne i prywatne
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Uzyskaj dostęp do właściwości setMeteredKey i przekaż klucze publiczne i prywatne jako parametry
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```
## Krok 2: Zainicjuj strumień wejściowy PostScript
Na tym etapie inicjujemy strumień wejściowy PostScript do przetwarzania.
```java
// Zainicjuj strumień wejściowy PostScript
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```
## Krok 3: Sprawdź licencję dokumentu
Przed kontynuowaniem należy sprawdzić, czy dokument posiada odpowiednią licencję.
```java
// Sprawdź, czy dokument jest licencjonowany
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```
## Krok 4: Zainicjuj opcje i urządzenie obrazu
Teraz zainicjujmy opcje i urządzenie obrazu z parametrami domyślnymi.
```java
// Zainicjuj obiekt opcji z parametrami domyślnymi.
ImageSaveOptions options = new ImageSaveOptions();
// Zainicjuj obiekt ImageDevice z parametrami domyślnymi.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```
## Krok 5: Zapisz plik EPS jako obraz
Zapisz plik EPS jako obraz, korzystając ze zdefiniowanych opcji i urządzenia.
```java
// Zapisz plik EPS jako obraz
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```
## Krok 6: Pobierz i zapisz bajty obrazu
Pobierz bajty obrazu i zapisz je w pliku.
```java
// Pobierz bajty obrazów. Tablica jednobajtowa dla jednej strony. W naszym przypadku mamy jedną stronę.
byte[][] imagesBytes = device.getImagesBytes();
// Zapisz bajty obrazu do pliku
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```
## Wniosek
Gratulacje! Pomyślnie skonfigurowałeś licencję taryfową w Javie przy użyciu Aspose.Page. W tym samouczku przedstawiono przewodnik krok po kroku zapewniający płynny proces integracji.
## Często zadawane pytania
### P: Jak uzyskać mierzone klucze publiczne i prywatne?
Możesz uzyskać te klucze za pośrednictwem swojego konta Aspose.
### P: Czy biblioteka Aspose.Page jest bezpłatna?
 Aspose.Page oferuje zarówno bezpłatną wersję próbną, jak i wersję płatną. Odwiedzać[Tutaj](https://releases.aspose.com/) na bezpłatny okres próbny.
### P: Czy mogę używać Aspose.Page do projektów komercyjnych?
 Tak, Aspose.Page oferuje licencje komercyjne. Możesz je kupić[Tutaj](https://purchase.aspose.com/buy).
### P: Gdzie mogę znaleźć dodatkową dokumentację?
 Zapoznaj się z dokumentacją[Tutaj](https://reference.aspose.com/page/java/).
### P: Jak mogę uzyskać licencje tymczasowe?
 Można uzyskać licencje tymczasowe[Tutaj](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
