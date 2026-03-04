---
date: 2025-12-20
description: Dowiedz się, jak tworzyć metadane XMP EPS w plikach EPS przy użyciu Aspose.Page
  dla Javy. Przewodnik krok po kroku, jak programowo dodać proste właściwości XMP.
linktitle: Add Simple Properties in XMP using Java
second_title: Aspose.Page Java API
title: Jak utworzyć metadane XMP EPS w Javie
url: /pl/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj proste właściwości w XMP przy użyciu Javy

## Wprowadzenie
W nowoczesnych przepływach pracy z dokumentami możliwość **tworzenia plików XMP metadata EPS** programowo daje pełną kontrolę nad tym, jak Twoje grafiki są opisywane, wyszukiwane i archiwizowane. Dzięki Aspose.Page for Java możesz odczytywać, modyfikować i zapisywać pakiety XMP wewnątrz dokumentów EPS, nie opuszczając ekosystemu Javy. W tym samouczku przeprowadzimy Cię krok po kroku przez proces dodawania prostych właściwości XMP do pliku EPS, abyś mógł szybko i niezawodnie wzbogacić swoje grafiki o niestandardowe metadane.

## Szybkie odpowiedzi
- **Co oznacza „create xmp metadata eps”?** Dodanie pakietu XMP (metadane oparte na XML) do pliku EPS.  
- **Jakiej biblioteki potrzebujesz?** Aspose.Page for Java (do pobrania ze strony Aspose).  
- **Czy potrzebna jest licencja do testów?** Darmowa wersja próbna wystarcza do rozwoju; licencja komercyjna jest wymagana w produkcji.  
- **Ile linii kodu?** Mniej niż 30 linii Javy plus kilka instrukcji importu.  
- **Czy mogę dodać inne typy danych?** Tak – obsługiwane są daty, liczby całkowite, liczby zmiennoprzecinkowe, ciągi znaków oraz tablice.

## Co to jest create xmp metadata eps?
XMP (Extensible Metadata Platform) to standard umożliwiający osadzanie bogatych metadanych w plikach. Gdy **tworzysz XMP metadata EPS**, osadzasz pakiet XML wewnątrz dokumentu EPS (Encapsulated PostScript), co pozwala aplikacjom downstream odczytywać autora, datę utworzenia, niestandardowe tagi i wiele innych informacji.

## Dlaczego dodawać metadane XMP do plików EPS?
- **Wyszukiwalność:** Umożliwia automatyczne indeksowanie przez systemy DAM.  
- **Zgodność:** Przechowuje informacje prawne lub licencyjne bezpośrednio w pliku.  
- **Automatyzacja:** Pozwala pipeline'om downstream podejmować decyzje na podstawie osadzonych danych.  
- **Przenośność:** Metadane podróżują wraz z EPS, zapewniając spójność na różnych platformach.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

- Podstawową znajomość programowania w Javie.  
- Zainstalowaną bibliotekę Aspose.Page for Java. Możesz ją pobrać **[tutaj](https://releases.aspose.com/page/java/)**.  
- Przykładowy plik EPS zawierający metadane. Jeśli go nie masz, możesz użyć dostarczonego pliku **`xmp3.eps`**.

## Importowanie pakietów
Najpierw zaimportuj klasy, które będą potrzebne. Importy pozostają dokładnie takie same jak w oryginalnym przykładzie:

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

## Krok 1: Załaduj dokument EPS i pobierz metadane XMP
Otwieramy plik EPS, tworzymy instancję `PsDocument` i pobieramy (lub tworzymy) pakiet XMP.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Krok 2: Dodaj właściwość Date
Dodanie daty jest tak proste, jak utworzenie obiektu `Date` i wstawienie go do mapy XMP.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Krok 3: Dodaj właściwość Integer
Możesz przechowywać identyfikatory numeryczne lub numery wersji przy użyciu wartości całkowitej.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Krok 4: Dodaj właściwość Double
Liczby zmiennoprzecinkowe są przydatne do pomiarów lub ocen.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Krok 5: Dodaj właściwość String
Niestandardowe tagi tekstowe (np. kody projektów) są przechowywane jako ciągi znaków.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Krok 6: Zapisz zaktualizowany plik EPS
Po dodaniu wszystkich właściwości zapisujemy dokument z powrotem na dysk.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Krok 7: Oczyść zasoby
Zawsze zamykaj strumień wejściowy, aby uniknąć wycieków uchwytów plików.

```java
// Close input EPS stream
psStream.close();
```

## Typowe problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| **Null XMP metadata** | Plik EPS nie zawierał pakietu XMP, a biblioteka nie mogła wywnioskować komentarzy PS. | Upewnij się, że źródłowy EPS zawiera przynajmniej jeden komentarz PS (np. `%%Creator`). Biblioteka automatycznie wygeneruje minimalny pakiet XMP. |
| **Time zone mismatch** | Daty są przesunięte po otwarciu w innej aplikacji. | Ustaw `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` przed utworzeniem obiektu `Date`, jak pokazano w Kroku 2. |
| **License exception** | W czasie wykonywania wyrzuca `LicenseException`. | Zastosuj ważną licencję Aspose.Page przed użyciem API lub uruchom w trybie próbnym w celu oceny. |

## Zakończenie
Postępując zgodnie z tymi krokami, teraz wiesz, jak **tworzyć pliki XMP metadata EPS** przy użyciu Aspose.Page for Java. Dodawanie prostych właściwości, takich jak daty, liczby całkowite, liczby zmiennoprzecinkowe i ciągi znaków, jest proste, a uzyskane pliki EPS zawierają bogate, wyszukiwalne metadane, które przynoszą korzyści w każdym downstreamowym przepływie pracy.

## Najczęściej zadawane pytania
### Czy mogę używać Aspose.Page for Java z innymi językami programowania?
Aspose.Page głównie obsługuje Javę, ale dostępne są wersje dla innych języków, takich jak .NET.

### Czy dostępna jest darmowa wersja próbna Aspose.Page for Java?
Tak, możesz wypróbować funkcje Aspose.Page, pobierając darmową wersję próbną [tutaj](https://releases.aspose.com/).

### Gdzie znajdę szczegółową dokumentację Aspose.Page for Java?
Dokumentacja jest dostępna [tutaj](https://reference.aspose.com/page/java/).

### Jak mogę uzyskać tymczasową licencję na Aspose.Page for Java?
Tymczasową licencję można uzyskać [tutaj](https://purchase.aspose.com/temporary-license/).

### Gdzie mogę kupić Aspose.Page for Java?
Produkt można zakupić [tutaj](https://purchase.aspose.com/buy).

---

**Ostatnia aktualizacja:** 2025-12-20  
**Testowano z:** Aspose.Page for Java 24.11 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}