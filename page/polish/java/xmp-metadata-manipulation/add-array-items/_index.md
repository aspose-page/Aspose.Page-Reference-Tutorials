---
date: 2025-12-18
description: Dowiedz się, jak dodać metadane, wstawiając elementy tablicy do metadanych
  XMP plików EPS przy użyciu Aspose.Page dla Javy. Postępuj zgodnie z naszym przewodnikiem
  krok po kroku.
linktitle: Add Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Jak dodać metadane – dodawanie elementów tablicy w XMP (Java)
url: /pl/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodawanie elementów tablicy w metadanych XMP przy użyciu Javy

## Jak dodać metadane
Witamy w naszym przewodniku krok po kroku, jak **dodać metadane** do plików EPS przy użyciu Aspose.Page for Java. W tym tutorialu przeprowadzimy Cię przez dodawanie elementów tablicy do metadanych XMP — powszechne wymaganie, gdy trzeba wzbogacić informacje o dokumencie, takie jak tytuły czy twórcy. Po zakończeniu zrozumiesz, dlaczego XMP jest wartościowe, jak manipulować nim programowo oraz jak zapisać zaktualizowany plik EPS.

## Szybkie odpowiedzi
- **Jakiej biblioteki użyto?** Aspose.Page for Java  
- **Jaki format pliku jest celem?** EPS (Encapsulated PostScript)  
- **Czy mogę dodać wiele tytułów?** Tak, użyj wielokrotnie `xmp.addArrayItem("dc:title", ...)`  
- **Czy potrzebna jest licencja do produkcji?** Tak, wymagana jest ważna licencja Aspose.Page  
- **Czy kod jest kompatybilny z Java 8+?** Absolutnie, działa ze wszystkimi nowoczesnymi wersjami Javy  

## Wymagania wstępne
Zanim przejdziemy do tutorialu, upewnij się, że masz następujące wymagania:
- Zainstalowaną bibliotekę Aspose.Page for Java.
- Podstawową znajomość programowania w Javie.
- Ważny plik EPS z istniejącymi metadanymi XMP lub komentarzami metadanych PS.

## Importowanie pakietów
Aby rozpocząć, musisz zaimportować niezbędne pakiety do pracy z Aspose.Page. Dodaj następujące linie na początku swojego pliku Java:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Krok 1: Pobranie metadanych XMP
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
W tym kroku pobieramy istniejące metadane XMP z pliku EPS. Jeśli plik EPS nie zawiera jeszcze metadanych XMP, Aspose.Page generuje nowe i wypełnia je wartościami z komentarzy metadanych PS.

## Krok 2: Dodanie elementu tablicy "dc:title"
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Teraz dodajemy nowy element tablicy do właściwości **dc:title** w metadanych XMP. Zastąp `"NewTitle"` żądanym tytułem.

## Krok 3: Dodanie elementu tablicy "dc:creator"
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
Podobnie, dodajemy nowy element tablicy do właściwości **dc:creator** w metadanych XMP. Zastąp `"NewCreator"` odpowiednimi informacjami o twórcy.

## Krok 4: Inicjalizacja strumienia wyjściowego pliku EPS
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Przygotuj strumień wyjściowy pliku EPS, w którym zostanie zapisany zmodyfikowany dokument z zaktualizowanymi metadanymi XMP.

## Krok 5: Zapis dokumentu z zmienionymi metadanymi XMP
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Zapisz dokument z zaktualizowanymi metadanymi XMP do wyjściowego pliku EPS.

## Podsumowanie
Gratulacje! Pomyślnie nauczyłeś się **jak dodać metadane** poprzez wstawianie elementów tablicy w metadanych XMP przy użyciu Aspose.Page for Java. Ta potężna biblioteka upraszcza proces manipulacji plikami EPS i oferuje rozbudowaną funkcjonalność przetwarzania dokumentów.

## Najczęściej zadawane pytania

### Czy mogę używać Aspose.Page for Java z innymi formatami dokumentów?
Tak, Aspose.Page obsługuje różne formaty dokumentów, w tym EPS, PDF i XPS.

### Czy dostępna jest darmowa wersja próbna Aspose.Page for Java?
Tak, darmową wersję próbną znajdziesz [tutaj](https://releases.aspose.com/).

### Gdzie mogę znaleźć dokumentację Aspose.Page for Java?
Dokumentację znajdziesz [tutaj](https://reference.aspose.com/page/java/).

### Jak mogę zakupić Aspose.Page for Java?
Produkt możesz kupić [tutaj](https://purchase.aspose.com/buy).

### Czy dostępne są tymczasowe licencje dla Aspose.Page for Java?
Tak, tymczasową licencję można uzyskać [tutaj](https://purchase.aspose.com/temporary-license/).

## Dodatkowe często zadawane pytania

**P: Czy mogę dodać więcej niż jeden element tablicy do tej samej właściwości?**  
O: Oczywiście. Wywołaj `xmp.addArrayItem` wielokrotnie dla tej samej właściwości, aby zbudować listę wartości.

**P: Czy to podejście działa z istniejącymi schematami XMP innymi niż Dublin Core?**  
O: Tak, możesz dodawać elementy tablicy do dowolnej właściwości XMP, o ile przestrzeń nazw jest poprawnie określona.

**P: Jak mogę zweryfikować, że metadane zostały dodane prawidłowo?**  
O: Otwórz wynikowy plik EPS w przeglądarce obsługującej XMP (np. Adobe Bridge) lub wyodrębnij metadane programowo przy użyciu metod `XmpMetadata`.

---

**Ostatnia aktualizacja:** 2025-12-18  
**Testowano z:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}