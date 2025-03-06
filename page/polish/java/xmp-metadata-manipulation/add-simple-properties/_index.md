---
title: Dodaj proste właściwości w XMP przy użyciu Java
linktitle: Dodaj proste właściwości w XMP przy użyciu Java
second_title: Aspose.Page API Java
description: Odblokuj potencjał Aspose.Page dla Javy dzięki naszemu przewodnikowi na temat dodawania właściwości do metadanych XMP w plikach EPS. Ulepsz przetwarzanie dokumentów bez wysiłku!
weight: 14
url: /pl/java/xmp-metadata-manipulation/add-simple-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj proste właściwości w XMP przy użyciu Java

## Wstęp
stale zmieniającym się środowisku przetwarzania dokumentów efektywne zarządzanie metadanymi ma kluczowe znaczenie. Aspose.Page dla Java umożliwia programistom płynne manipulowanie danymi Extensible Metadata Platform (XMP). W tym samouczku omówimy proces dodawania prostych właściwości do XMP przy użyciu języka Java, zapewniając kompleksowy przewodnik krok po kroku.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Podstawowa znajomość programowania w języku Java.
-  Zainstalowana biblioteka Aspose.Page dla Java. Możesz go pobrać[Tutaj](https://releases.aspose.com/page/java/).
- Przykładowy plik EPS zawierający metadane. Jeśli go nie masz, możesz skorzystać z dostarczonego pliku „xmp3.eps”.
## Importuj pakiety
Upewnij się, że zaimportowałeś niezbędne pakiety, aby rozpocząć projekt:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
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
## Krok 2: Dodaj właściwość daty
```java
// Dodaj wartość właściwości daty „xmp:Date1”.
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```
## Krok 3: Dodaj właściwość Integer
```java
// Dodaj wartość właściwości całkowitej „xmp:Intg1”.
xmp.put("xmp:Intg1", new XmpValue(111));
```
## Krok 4: Dodaj podwójną właściwość
```java
// Dodaj wartość podwójnej właściwości „xmp:Double1”.
xmp.put("xmp:Double1", new XmpValue(111.11D));
```
## Krok 5: Dodaj właściwość ciągu
```java
// Dodaj wartość właściwości ciągu „xmp:String1”.
xmp.put("xmp:String1", new XmpValue("ABC"));
```
## Krok 6: Zapisz dokument
```java
// Zainicjuj wyjściowy strumień pliku EPS
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
//Zapisz dokument ze zmienionymi metadanymi XMP
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Krok 7: Zamknij strumienie
```java
// Zamknij wejściowy strumień EPS
psStream.close();
```
## Wniosek
Aspose.Page dla Java upraszcza proces manipulowania metadanymi XMP w plikach EPS. Postępując zgodnie z tym przewodnikiem krok po kroku, możesz bez wysiłku dodawać proste właściwości, aby ulepszyć metadane swojego dokumentu.
## Często Zadawane Pytania
### Czy mogę używać Aspose.Page dla Java z innymi językami programowania?
Aspose.Page obsługuje przede wszystkim Javę, ale dostępne są wersje dla innych języków, takich jak .NET.
### Czy dostępna jest bezpłatna wersja próbna Aspose.Page dla Java?
 Tak, możesz poznać funkcje Aspose.Page, uzyskując bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć szczegółową dokumentację Aspose.Page dla Java?
 Dokumentacja jest dostępna[Tutaj](https://reference.aspose.com/page/java/).
### Jak mogę uzyskać tymczasową licencję na Aspose.Page dla Java?
 Można nabyć licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
### Gdzie mogę kupić Aspose.Page dla Java?
 Możesz kupić produkt[Tutaj](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
