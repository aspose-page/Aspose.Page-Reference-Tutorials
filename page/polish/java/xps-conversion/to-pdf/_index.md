---
date: 2026-03-13
description: Dowiedz się, jak wykonać konwersję Aspose Page z XPS do PDF w Javie.
  Ten przewodnik krok po kroku pokazuje, jak renderować PDF z XPS, ustawiać numery
  stron w PDF oraz optymalizować wynik.
linktitle: How to Convert XPS to PDF in Java
second_title: Aspose.Page Java API
title: Konwersja stron Aspose – Jak przekonwertować XPS na PDF w Javie
url: /pl/java/xps-conversion/to-pdf/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Page Conversion – Jak przekonwertować XPS do PDF w Javie

Konwersja plików XPS do PDF jest powszechnym wymogiem, gdy potrzebny jest uniwersalny format dokumentu. W tym samouczku poznasz **aspose page conversion** w praktyce, używając Aspose.Page dla Javy do **renderowania PDF z XPS** w kilku linijkach kodu. Niezależnie od tego, czy tworzysz system zarządzania dokumentami, generujesz raporty do druku, czy archiwizujesz pliki, ten przewodnik poprowadzi Cię przez cały proces – od wymagań wstępnych po rozwiązywanie problemów.

## Szybkie odpowiedzi
- **Jaką bibliotekę obsługuje konwersję?** Aspose.Page dla Javy.  
- **Jak długo trwa implementacja?** Około 10‑15 minut dla podstawowej konfiguracji.  
- **Czy potrzebna jest licencja?** Bezpłatna wersja próbna działa w trybie ewaluacyjnym; licencja jest wymagana w środowisku produkcyjnym.  
- **Czy mogę konwertować tylko wybrane strony?** Tak – użyj opcji *specify PDF page numbers*.  
- **Czy konwersja jest bezstratna?** Biblioteka zachowuje wektorową grafikę i wierność tekstu.  

## Co to jest Aspose Page Conversion z XPS do PDF?
Aspose Page conversion przekształca dokumenty XPS (XML Paper Specification) – format stałego układu Microsoftu – w PDF, de‑facto standard do udostępniania i drukowania. Konwersja zachowuje układ, czcionki oraz grafikę wektorową, zapewniając, że powstały PDF wygląda dokładnie tak jak oryginalny XPS.

## Dlaczego warto używać Aspose.Page dla Javy do renderowania PDF z XPS?
- **Wysoka wierność** – zachowuje grafikę wektorową, czcionki i układ.  
- **Precyzyjna kontrola** – możesz ustawić jakość obrazu, kompresję i wybrać konkretne strony.  
- **Brak zewnętrznych zależności** – czysta Java, działa na każdej platformie obsługującej JDK.  
- **Wbudowany wybór stron** – łatwo **specify PDF page numbers**, aby zmniejszyć rozmiar pliku.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

- **Java Development Kit (JDK)** – dowolna aktualna wersja (zalecane 8+).  
- **Aspose.Page dla Javy** – pobierz bibliotekę z oficjalnej [documentation](https://reference.aspose.com/page/java/).  
- Plik XPS, który chcesz przekonwertować.

## Importowanie pakietów
W swoim projekcie Java zaimportuj niezbędne pakiety do pracy z Aspose.Page dla Javy. Ten krok jest kluczowy, aby uzyskać dostęp do funkcji potrzebnych do konwersji XPS do PDF.

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Przewodnik krok po kroku

### Krok 1: Ustaw katalog dokumentu
Zdefiniuj ścieżkę do folderu zawierającego plik źródłowy XPS.

```java
String dataDir = "Your Document Directory";
```

### Krok 2: Zainicjuj strumień wyjściowy PDF
Utwórz `FileOutputStream`, który będzie odbierał wygenerowany PDF.

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

### Krok 3: Załaduj dokument XPS
Wczytaj plik XPS przy użyciu Aspose.Page.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Krok 4: Zainicjuj opcje zapisu PDF  
Utwórz opcje konwersji. Tutaj możesz **specify PDF page numbers**, dostosować jakość obrazu i ustawić kompresję.

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);
options.setImageCompression(PdfImageCompression.Jpeg);
options.setTextCompression(PdfTextCompression.Flate);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### Krok 5: Utwórz urządzenie renderujące PDF  
Skonfiguruj urządzenie renderujące, które zapisze wynikowy PDF.

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### Krok 6: Zapisz dokument  
Na koniec zapisz dokument XPS jako PDF, używając skonfigurowanych opcji i urządzenia.

```java
document.save(device, options);
```

Powtarzaj te kroki, dostosowując ścieżki plików i opcje do swojego konkretnego scenariusza.

## Jak określić numery stron PDF przy konwersji XPS
Jeśli potrzebujesz tylko podzbioru stron z oryginalnego XPS, wypełnij tablicę `setPageNumbers` żądanymi indeksami stron (licząc od 1). Dzięki temu zmniejszysz rozmiar pliku i czas przetwarzania.

## Typowe problemy i rozwiązywanie ich
- **FileNotFoundException** – Sprawdź, czy `dataDir` wskazuje na właściwy folder i czy nazwa pliku XPS jest poprawna.  
- **LicenseException** – Do użytku produkcyjnego wymagana jest ważna licencja Aspose.Page; w przeciwnym razie biblioteka działa w trybie ewaluacyjnym z znakami wodnymi.  
- **Niska jakość obrazu** – Zwiększ `setJpegQualityLevel` lub przełącz się na bezstratną kompresję, jeśli to konieczne.

## Najczęściej zadawane pytania
### Czy mogę konwertować pliki XPS z wieloma stronami przy użyciu Aspose.Page dla Javy?
Tak, możesz **specify PDF page numbers** w `PdfSaveOptions` (zobacz Krok 4), aby uwzględnić dowolne potrzebne strony.

### Gdzie mogę znaleźć dodatkowe wsparcie lub dyskutować o zagadnieniach związanych z Aspose.Page?
Odwiedź [forum Aspose.Page](https://forum.aspose.com/c/page/39) w celu uzyskania pomocy społeczności i dyskusji.

### Czy dostępna jest bezpłatna wersja próbna Aspose.Page dla Javy?
Tak, możesz wypróbować funkcje korzystając z [free trial](https://releases.aspose.com/).

### Jak uzyskać tymczasową licencję dla Aspose.Page dla Javy?
Wejdź pod [ten link](https://purchase.aspose.com/temporary-license/) po szczegóły dotyczące licencji tymczasowej.

### Gdzie mogę kupić licencję Aspose.Page dla Javy?
Licencję możesz nabyć [tutaj](https://purchase.aspose.com/buy).

---

**Ostatnia aktualizacja:** 2026-03-13  
**Testowano z:** Aspose.Page dla Javy 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}