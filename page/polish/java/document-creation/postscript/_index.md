---
date: 2026-06-20
description: Dowiedz się, jak ustawić rozmiar strony A4, tworzyć pliki PostScript
  w Javie oraz dodawać własne czcionki przy użyciu Aspose.Page. Wypróbuj darmową wersję
  próbną już dziś!
keywords:
- set a4 page size
- add custom fonts java
- java create postscript
linktitle: Tworzenie dokumentu w Javie z PostScript
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to set A4 page size and create PostScript in Java with Aspose.Page
  type: TechArticle
- description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to set A4 page size and create PostScript in Java with Aspose.Page
  steps:
  - name: Set Document Directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define Fonts Folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create Output Stream for PostScript Document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create Save Options with A4 Size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set Page Margins and Add Custom Fonts Folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a Multipaged or Single‑Paged PS Document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close Current Page and Save Document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [here](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [here](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page forum [forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
title: Jak ustawić rozmiar strony A4 i tworzyć PostScript w Javie z Aspose.Page
url: /pl/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ustawić rozmiar strony A4 i utworzyć PostScript w Javie z Aspose.Page

## Wprowadzenie
Jeśli potrzebujesz **ustawić rozmiar strony a4** podczas generowania plików PostScript w Javie, Aspose.Page oferuje szybkie, niezawodne API, które ukrywa szczegóły niskiego poziomu. W tym samouczku przeprowadzimy Cię przez cały proces — tworzenie dokumentu PostScript, konfigurowanie wymiarów strony A4 oraz **dodawanie własnych czcionek**, gdy jest to wymagane. Po zakończeniu będziesz mieć gotowy fragment kodu, który możesz wstawić do dowolnego projektu Java.

## Szybkie odpowiedzi
- **Jaka biblioteka tworzy PostScript w Javie?** Aspose.Page for Java.  
- **Jaki rozmiar strony jest celem tego przewodnika?** A4 (210 mm × 297 mm).  
- **Czy mogę osadzić własne czcionki?** Tak – ustaw dodatkowy folder czcionek w opcjach zapisu.  
- **Czy potrzebuję licencji do produkcji?** Wymagana jest licencja komercyjna; dostępna jest darmowa wersja próbna.  
- **Jakie wersje Javy są obsługiwane?** Java 8 i nowsze.

## Jak ustawić rozmiar strony a4 i utworzyć postscript w Javie
Załaduj bibliotekę Aspose.Page, skonfiguruj `PsSaveOptions` przy użyciu stałych A4 i zapisz dokument do pliku — wszystko w mniej niż dziesięciu linijkach kodu. Takie bezpośrednie podejście zapewnia prawidłowe wymiary strony i pozwala dodać własne czcionki bez dodatkowej konfiguracji.

## Co to jest rozmiar postscript a4?
Rozmiar PostScript A4 to standard ISO 216 (210 mm × 297 mm) wyrażony w języku opisu stron PostScript. Definiuje on obszar drukowalny, który interpretują drukarki i przeglądarki, zapewniając spójny układ na różnych platformach. Ponieważ PostScript opisuje zawartość strony w sposób niezależny od urządzenia, użycie rozmiaru A4 gwarantuje, że dokument będzie wyglądał tak samo na każdej drukarce lub przeglądarce obsługującej A4 na całym świecie.

## Dlaczego używać Aspose.Page do ustawiania rozmiaru strony postscript?
Aspose.Page obsługuje **ponad 30 operatorów PostScript** i może generować pliki do **500 MB** bez ładowania całego dokumentu do pamięci. Daje to precyzyjną kontrolę nad wymiarami strony przy jednoczesnym efektywnym przetwarzaniu dużych obciążeń. Biblioteka dodatkowo abstrahuje złożoną składnię PostScript, automatycznie zarządza zasobami i zapewnia wysokowydajne strumieniowanie, co czyni ją idealną zarówno dla prostych jednostronicowych ulotek, jak i złożonych raportów wielostronicowych.

## Jak dodać własne czcionki w Javie
Osadzenie własnych krojów pisma zapewnia, że wygenerowany dokument wygląda dokładnie tak, jak zaprojektowano, na każdej drukarce lub przeglądarce, a Aspose.Page automatycznie wykrywa czcionki umieszczone w określonym folderze. Rejestrując dodatkowy folder czcionek, możesz używać dowolnej czcionki TrueType lub OpenType, unikać zastępowania awaryjnego i utrzymywać spójność marki na wszystkich urządzeniach wyjściowych.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

- Praktyczną znajomość programowania w Javie.  
- Zainstalowany Aspose.Page for Java. Możesz go pobrać [tutaj](https://releases.aspose.com/page/java/).  
- Folder o nazwie `necessary_fonts` (lub dowolną inną nazwę), który zawiera wszystkie własne czcionki, które chcesz osadzić.

## Importowanie pakietów
W swoim projekcie Java zaimportuj wymagane klasy Aspose.Page:

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Teraz podzielmy przykład na przejrzyste, numerowane kroki.

### Krok 1: Ustaw katalog dokumentu
Stała `OUTPUT_DIR` informuje bibliotekę, gdzie zapisać wygenerowany plik.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Krok 2: Zdefiniuj folder czcionek
`FONTS_FOLDER` wskazuje katalog, w którym znajdują się Twoje własne czcionki TrueType lub OpenType.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Krok 3: Utwórz strumień wyjściowy dla dokumentu PostScript
`FileOutputStream` otwiera strumień, który odbierze ostateczny wynik PostScript A4.

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### Krok 4: Utwórz opcje zapisu z rozmiarem A4
`PsSaveOptions` pozwala określić docelowy rozmiar strony.  
**Definicja:** `PsPageSize` to wyliczenie zawierające standardowe stałe rozmiarów stron, takie jak A4, Letter i Legal.  
Ustawienie `options.setPageSize(PsPageSize.A4)` konfiguruje dokument do standardowych wymiarów A4.

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### Krok 5: Ustaw marginesy strony i dodaj folder własnych czcionek
`options.setMargins(0, 0, 0, 0)` usuwa wszystkie marginesy, tworząc stronę bez obramowania, a `options.setAdditionalFontsFolder(FONTS_FOLDER)` rejestruje Twoje własne czcionki.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### Krok 6: Utwórz wielostronicowy lub jednostronicowy dokument PS
`PsDocument document = new PsDocument(outputStream, options)` tworzy dokument. `PsDocument` reprezentuje dokument PostScript, który może zawierać jedną lub wiele stron. Ustaw `multiPaged` na `true`, aby uzyskać wyjście wielostronicowe.

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### Krok 7: Zamknij bieżącą stronę i zapisz dokument
Wywołanie `document.close()` finalizuje plik i zapisuje wynik **PostScript A4 size** na dysku.

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Typowe problemy i wskazówki
- **Czcionka nie wyświetla się?** Sprawdź, czy plik czcionki jest w obsługiwanym formacie TrueType lub OpenType oraz czy `FONTS_FOLDER` kończy się ukośnikiem (`/`).  
- **Marginesy nadal się wyświetlają?** Wywołaj `options.setMargins(...)` **przed** utworzeniem `PsDocument`.  
- **Wynik wielostronicowy jest pusty?** Pamiętaj, aby wywołać `document.newPage()` dla każdej dodatkowej strony, której potrzebujesz.

## Najczęściej zadawane pytania

**P: Czy mogę używać własnych czcionek w moim dokumencie PostScript?**  
O: Tak, ustaw dodatkowy folder czcionek w opcjach zapisu (zobacz Krok 5), a Aspose.Page automatycznie osadzi czcionki.

**P: Czy dostępna jest wersja próbna Aspose.Page for Java?**  
O: Tak, możesz uzyskać darmową wersję próbną [tutaj](https://releases.aspose.com/).

**P: Jak mogę uzyskać dostęp do pełnej dokumentacji API?**  
O: Odwołaj się do dokumentacji [tutaj](https://reference.aspose.com/page/java/).

**P: Gdzie mogę kupić licencję na Aspose.Page for Java?**  
O: Licencję możesz kupić [tutaj](https://purchase.aspose.com/buy).

**P: Gdzie mogę poprosić społeczność o pomoc?**  
O: Odwiedź forum Aspose.Page [forum](https://forum.aspose.com/c/page/39).

**P: Czy mogę generować wielostronicowe pliki PostScript?**  
O: Oczywiście — ustaw `multiPaged` na `true` w Kroku 6 i wywołaj `document.newPage()` dla każdej dodatkowej strony.

## Podsumowanie
Postępując zgodnie z tymi krokami, teraz wiesz **jak ustawić rozmiar strony a4** i tworzyć pliki **PostScript** w Javie z Aspose.Page, a także **dodawać własne czcionki w Javie** i kontrolować opcje rozmiaru strony. Aspose.Page zajmuje się trudnym zadaniem, dzięki czemu możesz skoncentrować się na treści swoich dokumentów.

---

**Ostatnia aktualizacja:** 2026-06-20  
**Testowano z:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Samouczek Aspose.Page Java – ustaw niestandardowy rozmiar strony podczas dodawania stron w PostScript](/page/java/postscript-page-manipulation/add-pages2/)
- [Jak dodać tekst w PostScript przy użyciu Aspose.Page for Java](/page/java/postscript-text-manipulation/)
- [Samouczek Aspose Page Java – konwersja PostScript do PDF](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
document.closePage();
document.save();
```