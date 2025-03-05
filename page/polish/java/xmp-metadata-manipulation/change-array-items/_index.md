---
title: Zmień elementy tablicy w XMP przy użyciu Java
linktitle: Zmień elementy tablicy w XMP przy użyciu Java
second_title: Aspose.Page API Java
description: Dowiedz się, jak zmieniać elementy tablicy w XMP przy użyciu Aspose.Page dla Java. Zmieniaj metadane bez wysiłku, korzystając z naszego przewodnika krok po kroku. Ulepsz swoje dokumenty EPS już teraz!
type: docs
weight: 15
url: /pl/java/xmp-metadata-manipulation/change-array-items/
---
## Wstęp
Witamy w naszym obszernym przewodniku na temat zmiany elementów tablicy w XMP przy użyciu Aspose.Page dla Java! Aspose.Page to potężna biblioteka Java, która umożliwia płynną pracę z metadanymi XMP w plikach EPS. W tym samouczku przeprowadzimy Cię przez proces modyfikowania elementów tablicy w metadanych XMP, pomagając Ci ulepszać i dostosowywać dokumenty EPS.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Zestaw Java Development Kit (JDK) zainstalowany w systemie.
-  Biblioteka Aspose.Page dla Javy. Można go pobrać z[Tutaj](https://releases.aspose.com/page/java/).
## Importuj pakiety
Na początek zaimportujmy niezbędne pakiety do Twojego projektu Java. Upewnij się, że masz bibliotekę Aspose.Page w swoim projekcie.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;

```
## Krok 1: Uzyskaj metadane XMP
Najpierw pobierz metadane XMP z pliku EPS. Jeśli plik EPS nie zawiera jeszcze metadanych XMP, zostanie utworzony nowy z wartościami z komentarzy do metadanych PS, takimi jak %%Creator, %%CreateDate, %%Title itp.
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Zainicjuj wejściowy strumień pliku EPS
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Pobierz metadane XMP. Jeżeli plik EPS nie zawiera metadanych XMP, nowy zostanie wypełniony wartościami z komentarzy metadanych PS.
XmpMetadata xmp = document.getXmpMetadata();
```
## Krok 2: Ustaw element tablicy „dc:title”.
Teraz ustawmy element tablicy „dc:title” na indeks 0 z nową wartością.
```java
// Ustaw element tablicy „dc:title” według indeksu 0
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```
## Krok 3: Ustaw element tablicy „dc:creator”.
Podobnie ustaw element tablicy „dc:creator” na indeks 0 z nową wartością twórcy.
```java
// Ustaw element tablicy „dc:creator” według indeksu 0
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```
## Krok 4: Zainicjuj wyjściowy strumień pliku EPS
Przygotuj wyjściowy strumień pliku EPS, w którym zostanie zapisany zmodyfikowany dokument.
```java
// Zainicjuj wyjściowy strumień pliku EPS
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
## Krok 5: Zapisz dokument ze zmienionymi metadanymi XMP
Zapisz dokument ze zaktualizowanymi metadanymi XMP.
```java
//Zapisz dokument ze zmienionymi metadanymi XMP
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Wniosek
Gratulacje! Pomyślnie nauczyłeś się zmieniać elementy tablicy w XMP przy użyciu Aspose.Page dla Java. Ten samouczek zawiera wskazówki krok po kroku, dzięki którym możesz bez wysiłku wzbogacać dokumenty EPS o dostosowane metadane.

## Często zadawane pytania
### Czy mogę używać Aspose.Page dla Java z innymi językami programowania?
Aspose.Page jest przeznaczony głównie dla języka Java, ale Aspose udostępnia podobne biblioteki dla innych języków.
### Gdzie mogę znaleźć szczegółową dokumentację Aspose.Page dla Java?
 Dokumentacja jest dostępna[Tutaj](https://reference.aspose.com/page/java/).
### Czy dostępna jest bezpłatna wersja próbna Aspose.Page dla Java?
 Tak, możesz skorzystać z bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
### Jak mogę uzyskać tymczasową licencję na Aspose.Page dla Java?
 Możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
### Gdzie mogę kupić pełną wersję Aspose.Page dla Java?
 Można kupić pełną wersję[Tutaj](https://purchase.aspose.com/buy).