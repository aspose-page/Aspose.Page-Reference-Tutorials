---
date: 2025-12-23
description: Dowiedz się, jak konwertować XPS na PDF w Javie przy użyciu Aspose.Page.
  Ten przewodnik pokazuje krok po kroku konwersję, jak renderować PDF z XPS oraz określić
  numery stron PDF.
linktitle: How to Convert XPS to PDF in Java
second_title: Aspose.Page Java API
title: Jak przekonwertować XPS na PDF w Javie
url: /pl/java/xps-conversion/to-pdf/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak przekonwertować XPS na PDF w Javie

## Jak przekonwertować XPS na PDF w Javie
W świecie programowania w Javie, **jak przekonwertować XPS na PDF** jest częstym pytaniem. Niezależnie od tego, czy tworzysz system zarządzania dokumentami, czy potrzebujesz generować raporty do druku, niezawodne konwertowanie plików XPS może być przełomowe. Na szczęście Aspose.Page for Java umożliwia łatwe **renderowanie PDF z XPS** przy użyciu kilku linijek kodu.

## Szybkie odpowiedzi
- **Jaką bibliotekę obsługuje konwersję?** Aspose.Page for Java.
- **Jak długo trwa implementacja?** Około 10‑15 minut dla podstawowej konfiguracji.
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa w ocenie; licencja jest wymagana w produkcji.
- **Czy mogę konwertować tylko wybrane strony?** Tak – użyj opcji *specify PDF page numbers*.
- **Czy konwersja jest bezstratna?** Biblioteka zachowuje wektorową grafikę i wierność tekstu.

## Czym jest konwersja XPS do PDF?
XPS (XML Paper Specification) to format dokumentu o stałym układzie firmy Microsoft. Konwersja go do PDF pozwala udostępniać, drukować lub archiwizować dokumenty przy użyciu powszechnie akceptowanego standardu PDF.

## Dlaczego warto używać Aspose.Page for Java do renderowania PDF z XPS?
- **Wysoka wierność** – zachowuje grafikę wektorową, czcionki i układ.
- **Precyzyjna kontrola** – możesz ustawić jakość obrazu, kompresję i nawet wybrać konkretne strony.
- **Brak zewnętrznych zależności** – czysta Java, działa na każdej platformie obsługującej JDK.

## Prerequisites
Zanim rozpoczniesz, upewnij się, że masz:

- **Java Development Kit (JDK)** – dowolną aktualną wersję (zalecane 8+).
- **Aspose.Page for Java** – pobierz bibliotekę z oficjalnej [dokumentacji](https://reference.aspose.com/page/java/).
- Plik XPS, który chcesz przekonwertować.

## Importowanie pakietów
W swoim projekcie Java zaimportuj wymagane pakiety do pracy z Aspose.Page for Java. Ten krok jest kluczowy dla uzyskania dostępu do funkcji potrzebnych do konwersji XPS na PDF.

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Przewodnik krok po kroku

### Krok 1: Ustaw katalog dokumentu
Zdefiniuj ścieżkę do folderu zawierającego źródłowy plik XPS.

```java
String dataDir = "Your Document Directory";
```

### Krok 2: Zainicjuj strumień wyjściowy PDF
Utwórz `FileOutputStream`, który otrzyma wygenerowany PDF.

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

### Krok 3: Załaduj dokument XPS
Załaduj plik XPS przy użyciu Aspose.Page.

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
Skonfiguruj urządzenie renderujące, które zapisze wyjście PDF.

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### Krok 6: Zapisz dokument  
Na koniec zapisz dokument XPS jako PDF, używając skonfigurowanych opcji i urządzenia.

```java
document.save(device, options);
```

Powtórz te kroki, dostosowując ścieżki plików i opcje do swojego konkretnego scenariusza.

## Jak określić numery stron PDF przy konwersji XPS
Jeśli potrzebujesz tylko podzbioru stron z oryginalnego XPS, wypełnij tablicę `setPageNumbers` żądanymi indeksami stron (licząc od 1). To pomaga zmniejszyć rozmiar pliku i czas przetwarzania.

## Typowe problemy i rozwiązywanie
- **FileNotFoundException** – Sprawdź, czy `dataDir` wskazuje prawidłowy folder i czy nazwa pliku XPS się zgadza.
- **LicenseException** – Wymagana jest ważna licencja Aspose.Page do użytku produkcyjnego; w przeciwnym razie biblioteka działa w trybie ewaluacyjnym z znakiem wodnym.
- **Niska jakość obrazu** – Zwiększ `setJpegQualityLevel` lub przełącz na kompresję bezstratną, jeśli to konieczne.

## Najczęściej zadawane pytania
### Czy mogę konwertować pliki XPS z wieloma stronami przy użyciu Aspose.Page for Java?
Tak, możesz **specify PDF page numbers** w `PdfSaveOptions` (zobacz Krok 4), aby uwzględnić dowolne potrzebne strony.

### Gdzie mogę znaleźć dodatkowe wsparcie lub dyskutować o zapytaniach związanych z Aspose.Page?
Odwiedź [forum Aspose.Page](https://forum.aspose.com/c/page/39) w celu uzyskania wsparcia społeczności i dyskusji.

### Czy dostępna jest darmowa wersja próbna Aspose.Page for Java?
Tak, możesz przetestować funkcje korzystając z [darmowej wersji próbnej](https://releases.aspose.com/).

### Jak mogę uzyskać tymczasową licencję dla Aspose.Page for Java?
Odwiedź [ten link](https://purchase.aspose.com/temporary-license/) po szczegóły dotyczące tymczasowej licencji.

### Gdzie mogę kupić licencję Aspose.Page for Java?
Licencję możesz kupić [tutaj](https://purchase.aspose.com/buy).

**Ostatnia aktualizacja:** 2025-12-23  
**Testowano z:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}