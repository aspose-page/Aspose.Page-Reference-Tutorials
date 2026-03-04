---
date: 2025-12-20
description: Dowiedz się, jak dodać metadane XMP do plików EPS za pomocą samouczka
  Aspose Page Java. Postępuj zgodnie z tym przewodnikiem krok po kroku, aby usprawnić
  zarządzanie dokumentami.
linktitle: Add Metadata in XMP using Java
second_title: Aspose.Page Java API
title: Samouczek Aspose Page Java – Dodaj metadane XMP do plików EPS
url: /pl/java/xmp-metadata-manipulation/add-metadata/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodawanie metadanych XMP przy użyciu Javy

## Wstęp
W tym **aspose page java tutorial**, nauczysz się, jak ulepszyć metadane swojego dziedzictwa, dodając informacje XMP przy użyciu Javy. Ten przewodnik krok po kroku prowadzi Cię przez odczytanie pliku EPS, wyodrębnienie jego metadanych XMP i zapisanie zmian na dysku przy użyciu biblioteki Aspose.Page for Java. Po usunięciu demontażu komputera solidny, utylizacja pracy z XMP w zasilaczu pracy EPS.

## Szybkie odpowiedzi
- **Jaka biblioteka jest wymagana?** Aspose.Page dla Java
- **Czy mogę dodać XMP do dowolnego pliku EPS?** Tak – API tworzy nowy blok XMP, jeśli nie istnieje.
- **Czy potrzebuję licencji na programowanie?** Wersja próbna działa do oceny; licencjat komercyjny jest wymagany w produkcji.
- **Która wersja Java jest obsługiwana?** Java8 i nowsze.
- **Jak długo trwa wdrożenie?** Rozwiązanie poniżej 10 minut dla podstawowej aktualizacji metadanych.

## Strona Aspose Przegląd samouczka Java
Dziesięć samouczków demonstruje podstawowe kroki potrzebne do manipulacji metadanymi XMP w plikach EPS. Zrozumienie tych rozwiązań umożliwia zintegrowanie obsługi metadanych z większymi potokami transmisji dokumentów, dostępu do możliwości wyszukiwania oraz usług kontrolnych w zakresie zarządzania funkcjami cyfrowymi.

## Warunki wstępne
Zanim przejdziesz do tutorialu, dokładnie się, że spełniasz szczegółowe wymagania:
- Podstawowa przyjemność programowania w Javie.
- Zainstalowana biblioteka Aspose.Page dla Java. Możesz ją zabrać [tutaj](https://releases.aspose.com/page/java/).
- Plik EPS, który powstaje.

## Importuj pakiety
Najpierw zaimportuj niezbędne pakiety do swojego programu w Javie:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```

## Krok 1: Uzyskaj metadane XMP
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created using values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

Zastąp `"Your Document Directory"` rzeczywistą ścieżką, w której przechowywane są Twoje dokumenty.

## Krok 2: Pobierz wartość CreatorTool
```java
// Get "CreatorTool" value
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Krok 3: Pobierz wartość CreateDate
```java
// Get "CreateDate" value
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Krok 4: Pobierz wartość Title
```java
// Get "Title" value
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```

## Krok 5: Pobierz wartość Format
```java
// Get "format" value
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Krok 6: Pobierz wartość Creator
```java
// Get "creator" value
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```

## Krok 7: Pobierz wartość MetadataDate
```java
// Get "MetadataDate" value
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```

## Krok 8: Zapisz dokument z nowymi metadanymi XMP
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Save document with new XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

Na koniec, nie zapomnij zamknąć strumienia wejściowego EPS:

```java
// Close input EPS stream
psStream.close();
```

Teraz pomyślnie dodałeś metadane do pliku EPS przy użyciu Aspose.Page for Java!

## Wniosek
W tym **aspose page java tutorial**, opisując, jak dodać metadane XMP do pliku EPS przy użyciu biblioteki Aspose.Page for Java. To API pozwala programować dostarczanie metadanych, pozostałości pozostałości w poleceniu i ich wyszukaniu.

## Często zadawane pytania

**P: Czy korzystanie z Aspose.Page dla Java jest bezpłatne?**
O: Aspose.Page dla Java jest produktem komercyjnym. Możesz poznać jego funkcje w ramach bezpłatnej wersji próbnej [tutaj](https://releases.aspose.com/).

**P: Gdzie mogę znaleźć dokumentację Aspose.Page dla Java?**
Odp.: Dokumentacja jest dostępna [tutaj] (https://reference.aspose.com/page/java/).

**P: Jak mogę uzyskać tymczasową licencję na Aspose.Page dla Javy?**
O: Licencję tymczasową można uzyskać [tutaj](https://purchase.aspose.com/temporary-license/).

**P: Jakie formaty plików obsługuje Aspose.Page dla Javy?**
O: Aspose.Page dla Javy obsługuje różne formaty, w tym EPS, PDF i XPS.

**P: Czy mogę kupić Aspose.Page dla Javy?**
O: Tak, Aspose.Page dla Javy można kupić [tutaj](https://purchase.aspose.com/buy).

**P: Jak obsługiwać duże pliki EPS podczas dodawania metadanych?**
O: Przetwarzaj plik strumieniowo (jak pokazano), aby utrzymać niskie zużycie pamięci i szybko zamykać strumienie.

**P: Czy mogę modyfikować istniejące pola XMP zamiast tylko je odczytywać?**
O: Oczywiście – możesz użyć polecenia `xmp.put(klucz, wartość)`, aby zaktualizować lub dodać nowe wpisy przed zapisaniem.

---

**Ostatnia aktualizacja:** 2025-12-20
**Testowano z:** Aspose.Page dla Java 24.12 (najnowsza wersja)
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}