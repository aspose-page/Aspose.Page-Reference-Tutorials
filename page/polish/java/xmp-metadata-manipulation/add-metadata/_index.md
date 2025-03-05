---
title: Dodaj metadane w XMP przy użyciu Java
linktitle: Dodaj metadane w XMP przy użyciu Java
second_title: Aspose.Page API Java
description: Poznaj bezproblemową integrację Aspose.Page dla Java i dowiedz się, jak bez wysiłku dodawać metadane XMP do plików EPS. Podnieś poziom swojej gry w zarządzanie dokumentami już dziś!
type: docs
weight: 11
url: /pl/java/xmp-metadata-manipulation/add-metadata/
---
## Wstęp
Czy chcesz ulepszyć metadane swojego dokumentu, dodając informacje XMP przy użyciu języka Java? Nie szukaj dalej! Ten przewodnik krok po kroku przeprowadzi Cię przez proces dodawania metadanych do pliku EPS przy użyciu biblioteki Aspose.Page for Java. Aspose.Page to potężne narzędzie, które upraszcza zadania manipulacji dokumentami w aplikacjach Java.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Podstawowa znajomość programowania w języku Java.
-  Zainstalowana biblioteka Aspose.Page dla Java. Możesz go pobrać[Tutaj](https://releases.aspose.com/page/java/).
- Plik EPS, który chcesz zmodyfikować.
## Importuj pakiety
Najpierw zaimportuj niezbędne pakiety do swojego programu Java:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```
## Krok 1: Uzyskaj metadane XMP
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Zainicjuj wejściowy strumień pliku EPS
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Pobierz metadane XMP. Jeśli plik EPS nie zawiera metadanych XMP, tworzony jest nowy przy użyciu wartości z komentarzy do metadanych PS (%%Creator, %%CreateDate, %%Title itp.)
XmpMetadata xmp = document.getXmpMetadata();
```
Pamiętaj, aby zastąpić „Twój katalog dokumentów” rzeczywistą ścieżką, w której przechowywane są Twoje dokumenty.

## Krok 2: Pobierz wartość CreatorTool
```java
// Uzyskaj wartość „CreatorTool”.
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## Krok 3: Pobierz wartość CreateDate
```java
// Uzyskaj wartość „CreateDate”.
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Krok 4: Pobierz wartość tytułu
```java
// Uzyskaj wartość „Tytuł”.
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```
## Krok 5: Pobierz wartość formatu
```java
//Uzyskaj wartość „formatu”.
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## Krok 6: Odzyskaj wartość twórcy
```java
// Uzyskaj wartość „twórcy”.
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```
## Krok 7: Pobierz wartość MetadataDate
```java
// Uzyskaj wartość „MetadataDate”.
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```
## Krok 8: Zapisz dokument z nowymi metadanymi XMP
```java
// Zainicjuj wyjściowy strumień pliku EPS
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Zapisz dokument z nowymi metadanymi XMP
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Na koniec nie zapomnij zamknąć wejściowego strumienia EPS:
```java
// Zamknij wejściowy strumień EPS
psStream.close();
```
Teraz pomyślnie dodałeś metadane do swojego pliku EPS za pomocą Aspose.Page dla Java!
## Wniosek
W tym samouczku omówiliśmy proces dodawania metadanych XMP do pliku EPS przy użyciu biblioteki Aspose.Page dla Java. To potężne narzędzie umożliwia płynną manipulację dokumentami, poprawiając ogólne wrażenia z zarządzania dokumentami.
## Często zadawane pytania
### P: Czy korzystanie z Aspose.Page dla Java jest darmowe?
 O: Aspose.Page dla Java jest produktem komercyjnym. Możesz poznać jego funkcje w ramach bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
### P: Gdzie mogę znaleźć dokumentację Aspose.Page dla Java?
 Odp.: Dokumentacja jest dostępna[Tutaj](https://reference.aspose.com/page/java/).
### P: Jak mogę uzyskać tymczasową licencję na Aspose.Page dla Java?
 Odp.: Możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
### P: Jakie formaty plików obsługuje Aspose.Page dla Java?
Odp.: Aspose.Page dla Java obsługuje różne formaty, w tym EPS, PDF i XPS.
### P: Czy mogę kupić Aspose.Page dla Java?
 O: Tak, możesz kupić Aspose.Page dla Java[Tutaj](https://purchase.aspose.com/buy).