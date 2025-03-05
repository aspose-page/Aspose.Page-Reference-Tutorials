---
title: Dodaj elementy tablicy w metadanych XMP przy użyciu języka Java
linktitle: Dodaj elementy tablicy w metadanych XMP przy użyciu języka Java
second_title: Aspose.Page API Java
description: Ulepsz pliki EPS za pomocą Aspose.Page dla Java. Dowiedz się, jak bez wysiłku dodawać elementy tablicy do metadanych XMP. Skorzystaj już teraz z naszego przewodnika krok po kroku!
type: docs
weight: 10
url: /pl/java/xmp-metadata-manipulation/add-array-items/
---
## Wstęp
Witamy w naszym przewodniku krok po kroku dotyczącym używania Aspose.Page dla Java w celu dodawania elementów tablicy w metadanych XMP. Aspose.Page to potężna biblioteka Java, która umożliwia manipulowanie i pracę z różnymi formatami dokumentów, w tym plikami EPS. W tym samouczku skupimy się na konkretnym zadaniu dodawania elementów tablicy w metadanych XMP przy użyciu języka Java.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Zainstalowana biblioteka Aspose.Page dla Java.
- Podstawowa znajomość programowania w języku Java.
- Prawidłowy plik EPS z istniejącymi metadanymi XMP lub komentarzami do metadanych PS.
## Importuj pakiety
Aby rozpocząć, musisz zaimportować pakiety niezbędne do pracy z Aspose.Page. Umieść następujące wiersze na początku pliku Java:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## Krok 1: Uzyskaj metadane XMP
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Zainicjuj wejściowy strumień pliku EPS
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Pobierz metadane XMP. Jeśli plik EPS nie zawiera metadanych XMP, otrzymamy nowy wypełniony wartościami z komentarzy do metadanych PS (%%Creator, %%CreateDate, %%Title itp.)
XmpMetadata xmp = document.getXmpMetadata();
```
Na tym etapie pobieramy istniejące metadane XMP z pliku EPS. Jeśli plik EPS nie zawiera jeszcze metadanych XMP, Aspose.Page generuje nowy i wypełnia go wartościami z komentarzy metadanych PS.
## Krok 2: Dodaj element tablicy „dc:title”.
```java
// Dodaj jeszcze jeden element tablicy „dc:title”.
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Teraz dodajemy nowy element tablicy do właściwości „dc:title” w metadanych XMP. Zastąp „NewTitle” żądanym tytułem.
## Krok 3: Dodaj element tablicy „dc:creator”.
```java
// Dodaj jeszcze jeden element tablicy „dc:creator”.
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
Podobnie dodajemy nowy element tablicy do właściwości „dc:creator” w metadanych XMP. Zastąp „NewCreator” żądanymi informacjami o twórcy.
## Krok 4: Zainicjuj wyjściowy strumień pliku EPS
```java
// Zainicjuj wyjściowy strumień pliku EPS
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Przygotuj wyjściowy strumień pliku EPS, w którym zostanie zapisany zmodyfikowany dokument ze zaktualizowanymi metadanymi XMP.
## Krok 5: Zapisz dokument ze zmienionymi metadanymi XMP
```java
//Zapisz dokument ze zmienionymi metadanymi XMP
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Zapisz dokument ze zaktualizowanymi metadanymi XMP w wyjściowym pliku EPS.
## Wniosek
Gratulacje! Pomyślnie nauczyłeś się dodawać elementy tablicy w metadanych XMP przy użyciu Aspose.Page dla Java. Ta potężna biblioteka upraszcza proces manipulowania plikami EPS i zapewnia rozbudowaną funkcjonalność przetwarzania dokumentów.
## Często Zadawane Pytania

### Czy mogę używać Aspose.Page dla Java z innymi formatami dokumentów?
Tak, Aspose.Page obsługuje różne formaty dokumentów, w tym EPS, PDF i XPS.
### Czy dostępna jest bezpłatna wersja próbna Aspose.Page dla Java?
 Tak, możesz uzyskać dostęp do bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć dokumentację Aspose.Page dla Java?
 Dokumentacja jest dostępna[Tutaj](https://reference.aspose.com/page/java/).
### Jak mogę kupić Aspose.Page dla Java?
 Możesz kupić produkt[Tutaj](https://purchase.aspose.com/buy).
### Czy dostępne są tymczasowe licencje dla Aspose.Page dla Java?
 Tak, możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).