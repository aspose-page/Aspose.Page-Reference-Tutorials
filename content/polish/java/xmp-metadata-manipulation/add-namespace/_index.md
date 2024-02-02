---
title: Dodaj przestrzeń nazw w XMP przy użyciu Java
linktitle: Dodaj przestrzeń nazw w XMP przy użyciu Java
second_title: Aspose.Page API Java
description: Odblokuj moc manipulacji dokumentami za pomocą Aspose.Page dla Java. Z tego obszernego przewodnika dowiesz się, jak łatwo dodawać przestrzenie nazw XMP.
type: docs
weight: 13
url: /pl/java/xmp-metadata-manipulation/add-namespace/
---

## Wstęp

W obszarze manipulacji dokumentami Aspose.Page dla Java wyróżnia się jako solidne narzędzie oferujące szeroki wachlarz funkcjonalności. Jedną z zaawansowanych funkcji jest możliwość dodawania przestrzeni nazw w XMP (Extensible Metadata Platform) przy użyciu języka Java. Ten samouczek poprowadzi Cię przez cały proces, dzieląc go na łatwe do wykonania kroki.

## Warunki wstępne

Przed przystąpieniem do samouczka upewnij się, że spełnione są następujące wymagania wstępne:

-  Aspose.Page dla Java: Upewnij się, że masz zainstalowaną bibliotekę. Możesz go pobrać[Tutaj](https://releases.aspose.com/page/java/).

- Środowisko programistyczne Java: Skonfiguruj środowisko Java w swoim systemie.

- Plik dokumentu: Przygotuj plik EPS z metadanymi XMP. Jeśli nie zawiera metadanych XMP, biblioteka utworzy je na podstawie komentarzy do metadanych PS.

## Importuj pakiety

Aby rozpocząć, zaimportuj niezbędne pakiety do swojego projektu Java:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;

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
// Pobierz metadane XMP. Jeśli plik EPS nie zawiera metadanych XMP, utwórz nowy wypełniony wartościami z komentarzy do metadanych PS (%%Creator, %%CreateDate, %%Title itp.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Krok 2: Zarejestruj nową przestrzeń nazw

```java
// Dodaj nową przestrzeń nazw XML „http://www.some.org/schema/tmp#” z przedrostkiem „tmp”
xmp.registerNamespaceURI("tmp", "http://www.some.org/schema/tmp#");
```

## Krok 3: Dodaj nową właściwość

```java
// Dodaj nową właściwość „tmp:newKey” w nowej przestrzeni nazw XML
xmp.put("tmp:newKey", new XmpValue("NewValue"));
```

## Krok 4: Zapisz dokument

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

## Krok 5: Zamknij strumienie

```java
// Zamknij wejściowy strumień EPS
psStream.close();
```

Teraz pomyślnie dodałeś przestrzeń nazw w XMP przy użyciu Aspose.Page dla Java. Zachęcamy do odkrywania większej liczby funkcji i uwalniania pełnego potencjału tej biblioteki.

## Wniosek

Aspose.Page dla Java upraszcza złożone zadanie manipulowania metadanymi XMP w plikach EPS. Postępując zgodnie z tym przewodnikiem krok po kroku, zdobyłeś cenną umiejętność zwiększania możliwości przetwarzania dokumentów.

## Często zadawane pytania

### Czy mogę używać Aspose.Page dla Java z innymi językami programowania?
Aspose.Page obsługuje przede wszystkim Javę, ale dostępne są wersje dla innych języków, takich jak .NET.

### Czy dostępny jest bezpłatny okres próbny?
 Tak, możesz skorzystać z bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).

### Gdzie mogę znaleźć obszerną dokumentację?
 Zapoznaj się z dokumentacją[Tutaj](https://reference.aspose.com/page/java/).

### Jak mogę uzyskać licencję tymczasową?
 Możesz nabyć licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).

### Czy istnieją fora społeczności dla Aspose.Page?
 Tak, możesz nawiązać kontakt ze społecznością na stronie[Forum Aspose.Page](https://forum.aspose.com/c/page/39).