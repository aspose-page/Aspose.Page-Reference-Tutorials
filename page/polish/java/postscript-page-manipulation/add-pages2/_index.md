---
date: 2025-12-11
description: Dowiedz się, jak ustawić niestandardowy rozmiar strony i dodawać strony
  do dokumentów PostScript w Javie przy użyciu Aspose.Page. Skorzystaj z naszego przewodnika
  krok po kroku, aby płynnie manipulować dokumentami.
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: Samouczek Aspose.Page Java – ustaw niestandardowy rozmiar strony podczas dodawania
  stron w PostScript
url: /pl/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Poradnik Aspose.Page Java – ustaw niestandardowy rozmiar strony podczas dodawania stron w PostScript

## Wprowadzenie
W nowoczesnych aplikacjach Java często wymaga się **ustawiania niestandardowego rozmiaru strony** dla wyjścia PostScript — niezależnie od tego, czy generujesz faktury, bilety, czy własne grafiki. Aspose.Page for Java ułatwia to zadanie. W tym poradniku nauczysz się, jak dodawać strony i ustawiać niestandardowe rozmiary stron w dokumencie PostScript, krok po kroku, abyś za każdym razem uzyskał idealny układ.

## Szybkie odpowiedzi
- **Czy mogę ustawić różne rozmiary stron dla każdej strony?** Tak, możesz otwierać strony z niestandardowymi wymiarami używając `document.openPage(width, height)`.  
- **Czy potrzebna jest licencja do użytku produkcyjnego?** Wymagana jest ważna licencja Aspose.Page dla wdrożeń nie‑ewaluacyjnych.  
- **Jakie wersje Java są wspierane?** Biblioteka działa z Java 8 i nowszymi.  
- **Czy API jest bezpieczne wątkowo?** Instancje dokumentu nie są bezpieczne wątkowo; utwórz osobny `PsDocument` dla każdego wątku.  
- **Jak duży może być plik PostScript?** Aspose.Page obsługuje pliki wielokrotnych megabajtów efektywnie; zużycie pamięci skaluje się z zawartością, a nie z liczbą stron.

## Wymagania wstępne
- Podstawowa znajomość programowania w języku Java.  
- Dodany do projektu Aspose.Page for Java (Maven/Gradle lub ręczny JAR).  
- Środowisko programistyczne Java (IDE, JDK 8+).  

## Importowanie pakietów
Aby rozpocząć, zaimportuj niezbędne klasy z biblioteki Aspose.Page.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Krok 1: Utwórz wielostronicowy dokument PostScript
Najpierw utwórz nowy `PsDocument` skonfigurowany do obsługi wielu stron. To ustawia strumień wyjściowy i informuje bibliotekę, że będziemy pracować z plikiem wielostronicowym.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddPages2_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Set variable that indicates if resulting PostScript document will be multipaged
boolean multiPaged = true;
// Create new multipaged PS Document with one page opened
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Krok 2: Dodaj zawartość do pierwszej strony
Gdy dokument jest gotowy, możesz dodać dowolną zawartość do pierwszej strony. Po zakończeniu zamknij stronę, aby zablokować jej zawartość.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## Jak ustawić niestandardowy rozmiar strony
Jeśli domyślny rozmiar strony nie spełnia Twoich wymagań, możesz **ustawić niestandardowy rozmiar strony** przy otwieraniu nowej strony. Jest to przydatne przy paragonach, etykietach lub dowolnym niestandardowym układzie.

## Krok 3: Dodaj drugą stronę o innym rozmiarze
Poniżej otwieramy drugą stronę i jawnie podajemy niestandardową szerokość i wysokość (w punktach). To pokazuje, jak ustawić niestandardowy rozmiar strony dla poszczególnych stron.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Krok 4: Zapisz dokument
Na koniec zachowaj zmiany, zapisując dokument. Wszystkie strony — w tym te o niestandardowych rozmiarach — zostaną zapisane do pliku wyjściowego.

```java
// Save the document
document.save();
```

Postępując zgodnie z tymi krokami, możesz płynnie dodawać strony i **ustawiać niestandardowe rozmiary stron** w dokumencie PostScript Java przy użyciu Aspose.Page, co daje pełną kontrolę nad układem każdej strony.

## Zakończenie
Aspose.Page for Java oferuje solidne, przyjazne dla programistów API do obsługi dokumentów PostScript. Teraz wiesz, jak dodać wiele stron, zastosować niestandardowe wymiary i zapisać wynik — co umożliwia generowanie precyzyjnie sformatowanego wyjścia dla dowolnego rozwiązania opartego na Javie.

## Najczęściej zadawane pytania
### Czy mogę dodać strony o różnych rozmiarach w jednym dokumencie PostScript?
Tak, jak pokazano w tym poradniku, możesz dodawać strony o różnych rozmiarach w wielostronicowym dokumencie PostScript.  
### Czy istnieją ograniczenia co do liczby stron, które mogę dodać?
Aspose.Page umożliwia dodawanie praktycznie nieograniczonej liczby stron do dokumentu.  
### Czy mogę dodać własną zawartość, taką jak obrazy lub grafiki, na strony?
Oczywiście! Aspose.Page pozwala dodawać szeroką gamę treści, w tym tekst, obrazy i inne elementy graficzne.  
### Czy Aspose.Page nadaje się do obsługi dużych dokumentów?
Tak, Aspose.Page jest zaprojektowany tak, aby efektywnie obsługiwać zarówno małe, jak i duże dokumenty.  
### Gdzie mogę znaleźć dodatkowe zasoby i wsparcie dla Aspose.Page?
Explore the [Aspose.Page documentation](https://reference.aspose.com/page/java/), or visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community support.  

**Additional Q&A**

**Q:** *Jakie formaty obrazów są obsługiwane przy rysowaniu na stronie PostScript?*  
**A:** Możesz osadzać obrazy PNG, JPEG, BMP i GIF bezpośrednio przy użyciu API rysowania.  

**Q:** *Jak zmienić domyślną rozdzielczość DPI dokumentu?*  
**A:** Ustaw `PsSaveOptions.setResolution(int dpi)` przed utworzeniem `PsDocument`.  

**Q:** *Czy mogę zaszyfrować plik PostScript hasłem?*  
**A:** Sam format PostScript nie obsługuje szyfrowania, ale możesz opakować wyjście w PDF i zastosować ustawienia zabezpieczeń w razie potrzeby.  

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.Page for Java 24.10  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
