---
date: 2026-05-25
description: Dowiedz się, jak odczytywać XMP przy użyciu Aspose.Page w Javie. Ten
  szczegółowy przewodnik pokazuje, jak wyodrębniać metadane XMP, informacje o twórcy,
  znaczniki czasu, miniatury i wiele innych.
keywords:
- read xmp using aspose.page
- xmp metadata java
- aspose.page java
linktitle: Jak odczytać metadane XMP w Javie
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to read xmp using aspose.page with Java. This step‑by‑step
    guide shows extracting XMP metadata, creator info, timestamps, thumbnails, and
    more.
  headline: Read XMP using Aspose.Page – Java Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page can read XMP from PDF, EPS, and several image formats.
    question: Does this approach work with PDF files that contain XMP?
  - answer: Absolutely. The `XmpMetadata` object is mutable; you can add, update,
      or remove keys and then save the document.
    question: Can I modify XMP metadata after reading it?
  - answer: You can retrieve the binary data from the `xmpGImg:data` property of each
      thumbnail entry and write it to a file.
    question: Is there a way to extract all thumbnail images, not just dimensions?
  type: FAQPage
second_title: Aspose.Page Java API
title: Odczyt XMP przy użyciu Aspose.Page – przewodnik Java
url: /pl/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pobieranie metadanych z XMP przy użyciu Javy

## Jak odczytać XMP przy użyciu Aspose.Page (Java)?

Załaduj plik EPS za pomocą `new Document("file.eps")` — klasa `Document` reprezentuje załadowany plik. Wywołaj `getXmpMetadata()`, które wyodrębnia pakiet XMP, a następnie zapytaj zwrócony obiekt `XmpMetadata` — interfejs podobny do mapy dla właściwości XMP — aby pobrać potrzebne klucze. To wszystko jest wymagane do odczytania XMP przy użyciu Aspose.Page. API ukrywa niskopoziomowe parsowanie, więc otrzymujesz gotową do użycia mapę właściwości w zaledwie dwóch linijkach kodu.

Witamy w naszym samouczku krok po kroku, który pokazuje **jak odczytać XMP** metadane przy użyciu Javy i biblioteki Aspose.Page. XMP (Extensible Metadata Platform) jest powszechnie przyjętym standardem umożliwiającym osadzanie bogatych metadanych w dokumentach. Po zakończeniu tego przewodnika będziesz w stanie odczytać XMP formatu dokumentu, wyodrębnić informacje o twórcy, znaczniki czasu, miniatury i wiele więcej — co pozwoli Ci tworzyć inteligentniejsze rozwiązania do analizy dokumentów.

## Szybkie odpowiedzi
- **Co oznacza „odczytać XMP”?** Oznacza to programowe wyodrębnianie pakietu XMP, który przechowuje metadane wewnątrz pliku.  
- **Jakiej biblioteki wymaga się?** Aspose.Page for Java (pobierz z oficjalnej strony [here](https://releases.aspose.com/page/java/)).  
- **Czy potrzebna jest licencja?** Wymagana jest tymczasowa lub pełna licencja do produkcji; darmowa wersja próbna działa w celach oceny.  
- **Jaką wersję Javy obsługuje?** Java 8 lub wyższą.  
- **Czy mogę odczytać XMP z innych formatów?** Tak — Aspose.Page wyodrębnia XMP z EPS, PDF, JPEG, PNG i ponad 20 innych formatów.

## Wymagania wstępne
Zanim zagłębisz się w kod, upewnij się, że masz:

- **Java Development Kit (JDK)** – Java 8+ zainstalowaną i skonfigurowaną na Twoim komputerze.  
- **Aspose.Page for Java** – Pobierz bibliotekę z oficjalnej strony [here](https://releases.aspose.com/page/java/).  
- Plik EPS zawierający metadane XMP (np. `xmp1.eps`).  

## Importowanie pakietów
Klasa `XmpMetadata` znajduje się w przestrzeni nazw `com.aspose.page.xmp`, natomiast klasa `Document` jest w `com.aspose.page`. Zaimportuj obie, aby móc pracować z plikiem EPS i jego metadanymi.  
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Krok 1: Zainicjalizuj strumień wejściowy pliku EPS
Rozpocznij od ustawienia ścieżki do katalogu dokumentów i zainicjalizowania strumienia wejściowego pliku EPS.  
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## Krok 2: Pobierz metadane XMP
`XmpMetadata` jest obiektem Aspose.Page, który przechowuje pakiet XMP wyodrębniony z dokumentu. Pobierz go za pomocą `document.getXmpMetadata()`. Jeśli plik nie zawiera XMP, API tworzy minimalny pakiet na podstawie istniejących komentarzy PostScript.  
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Krok 3: Wyodrębnij informację CreatorTool
Klucz `CreatorTool` znajduje się w przestrzeni nazw `xmp` i zapisuje aplikację, która wygenerowała plik. Sprawdź jego obecność i wypisz wartość.  
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Krok 4: Wyodrębnij informację CreateDate
`CreateDate` przechowuje znacznik czasu, kiedy dokument został pierwotnie utworzony. Użyj tego samego wzorca `containsKey`/`get`, aby go odczytać.  
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Krok 5: Pobierz szerokość miniatury
Jeśli miniatury istnieją, tablica `xmp:Thumbnails` zawiera jeden lub więcej wpisów. Każdy wpis zawiera `width`, `height` oraz dane binarne. Przykład wyodrębnia szerokość pierwszej miniatury.  
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Krok 6: Wyodrębnij informację o formacie
Klucz `format` informuje o oryginalnym formacie pliku (np. „application/postscript”). Jest to przydatne, gdy musisz rejestrować lub weryfikować typy źródłowe.  
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Krok 7: Pobierz DocumentID
`DocumentID` jest unikalnym identyfikatorem nadanym przez aplikację twórczą. Może być używany do deduplikacji w dużych bibliotekach zasobów.  
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Dlaczego to jest ważne
Aspose.Page może odczytywać XMP z **ponad 20** formatów plików i przetwarza dokumenty do **500 MB** bez wczytywania całego pliku do pamięci, zapewniając szybki, niskokosztowy dostęp do kluczowych metadanych. Ta możliwość jest kluczowa dla potoków przetwarzania wsadowego, systemów zarządzania zasobami cyfrowymi oraz wszelkich rozwiązań opierających się na przeszukiwalnych, maszynowo czytelnych atrybutach dokumentów.

## Częste pułapki i wskazówki
- **Brak XMP:** Niektóre pliki EPS mogą nie zawierać XMP. Wywołanie `getXmpMetadata()` wygeneruje minimalny zestaw na podstawie istniejących komentarzy PS, ale nie uzyskasz pełnych metadanych, jeśli nie są one osadzone.  
- **Tablice miniatur:** Klucz `xmp:Thumbnails` może zawierać wiele wpisów. Przykład wyodrębnia tylko pierwszy; iteruj tablicę, jeśli potrzebujesz wszystkich miniatur.  
- **Świadomość przestrzeni nazw:** Klucze XMP używają przestrzeni nazw (np. `xmp:`, `dc:`). Upewnij się, że odwołujesz się do dokładnej nazwy klucza; w przeciwnym razie `containsKey` zwróci false.  

## Często zadawane pytania
### Czy mogę używać Aspose.Page dla Javy z innymi językami programowania?
Tak, Aspose.Page obsługuje Javę, .NET i kilka innych języków. Zobacz pełną listę w [dokumentacji](https://reference.aspose.com/page/java/).

### Czy dostępna jest darmowa wersja próbna Aspose.Page dla Javy?
Tak, możesz uzyskać dostęp do darmowej wersji próbnej [tutaj](https://releases.aspose.com/).

### Gdzie mogę znaleźć wsparcie dla Aspose.Page dla Javy?
Odwiedź [forum Aspose.Page](https://forum.aspose.com/c/page/39), aby uzyskać pomoc społeczności i oficjalne wsparcie.

### Jak uzyskać tymczasową licencję dla Aspose.Page dla Javy?
Możesz uzyskać tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/).

### Czy są dodatkowe zasoby dla Aspose.Page dla Javy?
Przeglądaj pełną [dokumentację](https://reference.aspose.com/page/java/) i pobierz bibliotekę [tutaj](https://releases.aspose.com/page/java/).

## Dodatkowe FAQ
**Q: Czy to podejście działa z plikami PDF zawierającymi XMP?**  
A: Tak, Aspose.Page może odczytywać XMP z PDF, EPS i kilku formatów obrazów.

**Q: Czy mogę modyfikować metadane XMP po ich odczytaniu?**  
A: Oczywiście. Obiekt `XmpMetadata` jest mutowalny; możesz dodawać, aktualizować lub usuwać klucze, a następnie zapisać dokument.

**Q: Czy istnieje sposób na wyodrębnienie wszystkich obrazów miniatur, a nie tylko wymiarów?**  
A: Możesz pobrać dane binarne z właściwości `xmpGImg:data` każdego wpisu miniatury i zapisać je do pliku.

## Podsumowanie
Teraz opanowałeś **jak odczytać XMP** metadane przy użyciu Javy i Aspose.Page. Postępując zgodnie z tymi krokami, możesz wyodrębnić narzędzia twórcy, znaczniki czasu, miniatury, informacje o formacie i identyfikatory dokumentów — co daje pełny wgląd w osadzone metadane Twoich plików EPS. Śmiało eksperymentuj z dodatkowymi przestrzeniami nazw XMP, aby uzyskać jeszcze bogatsze dane dla swoich aplikacji.

---

**Ostatnia aktualizacja:** 2026-05-25  
**Testowano z:** Aspose.Page for Java 24.12 (latest)  
**Autor:** Aspose

## Powiązane samouczki

- [Samouczek Aspose Page Java – Dodaj metadane XMP do plików EPS](/page/java/xmp-metadata-manipulation/add-metadata/)
- [samouczek aspose.page xmp – Dodaj przestrzeń nazw w XMP przy użyciu Javy](/page/java/xmp-metadata-manipulation/add-namespace/)
- [samouczek aspose page xmp – Zmień nazwany wartość w XMP przy użyciu Javy](/page/java/xmp-metadata-manipulation/change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}