---
date: 2026-02-18
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

# Samouczek Aspose.Page Java – ustaw niestandardowy rozmiar strony podczas dodawania stron w PostScript

## Wprowadzenie
W nowoczesnych aplikacjach Java **ustawianie niestandardowego rozmiaru strony** dla wyjścia PostScript jest często wymagane — niezależnie od tego, czy generujesz faktury, bilety, czy własne grafiki. W tym samouczku dowiesz się, jak **ustawić niestandardowy rozmiar strony** dla każdej strony, dodać wiele stron oraz ostatecznie **wygenerować plik PostScript**, który dokładnie odpowiada Twoim potrzebom układu. Przejdziemy krok po kroku przez kod, abyś mógł szybko zastosować tę technikę w własnych projektach.

## Szybkie odpowiedzi
- **Czy mogę ustawić różne rozmiary stron dla każdej strony?** Tak, możesz otwierać strony o własnych wymiarach używając `document.openPage(width, height)`.  
- **Czy potrzebna jest licencja do użytku produkcyjnego?** Wymagana jest ważna licencja Aspose.Page dla wdrożeń nie‑ewaluacyjnych.  
- **Jakie wersje Javy są obsługiwane?** Biblioteka działa z Java 8 i nowszymi.  
- **Czy API jest wątkowo‑bezpieczne?** Instancje dokumentów nie są wątkowo‑bezpieczne; utwórz osobny `PsDocument` dla każdego wątku.  
- **Jak duży może być plik PostScript?** Aspose.Page efektywnie obsługuje pliki wielo‑megabajtowe; zużycie pamięci skaluje się wraz z zawartością, a nie liczbą stron.  
- **Czy mogę użyć przeciążenia openPage width/height?** Oczywiście — `openPage(double width, double height)` pozwala określić dowolne wymiary w punktach.  

## Wymagania wstępne
Zanim przejdziesz dalej, upewnij się, że masz:

- Podstawową znajomość programowania w Javie.  
- Aspose.Page dla Javy dodany do projektu (Maven/Gradle lub ręcznie JAR).  
- Środowisko programistyczne Javy (IDE, JDK 8+).  

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
Po przygotowaniu dokumentu możesz dodać dowolną zawartość do pierwszej strony. Po zakończeniu zamknij stronę, aby zablokować jej treść.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## Jak ustawić niestandardowy rozmiar strony
Jeśli domyślny rozmiar strony nie spełnia Twoich wymagań, możesz **ustawić niestandardowy rozmiar strony** przy otwieraniu nowej strony. Jest to przydatne przy paragonach, etykietach lub dowolnym niestandardowym układzie.

## Krok 3: Dodaj drugą stronę o innym rozmiarze
Poniżej otwieramy drugą stronę i wyraźnie podajemy własną szerokość oraz wysokość (w punktach). To pokazuje, jak ustawić niestandardowy rozmiar strony dla poszczególnych stron, dając możliwość pracy z **różnymi rozmiarami stron** w tym samym dokumencie.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Krok 4: Zapisz dokument
Na koniec zapisz zmiany, zapisując dokument. Wszystkie strony — w tym te o niestandardowych rozmiarach — zostaną zapisane do pliku wyjściowego.

```java
// Save the document
document.save();
```

Postępując zgodnie z tymi krokami, możesz płynnie dodawać strony i **ustawiać niestandardowy rozmiar strony** w dokumencie PostScript w Javie przy użyciu Aspose.Page, uzyskując pełną kontrolę nad układem każdej strony.

## Dlaczego warto używać Aspose.Page do ustawiania niestandardowego rozmiaru strony?
- **Precyzja:** Wymiary definiowane są w punktach, co daje dokładną kontrolę nad szerokością i wysokością strony.  
- **Elastyczność:** Możesz mieszać **różne rozmiary stron** w jednym pliku PostScript.  
- **Wydajność:** Biblioteka strumieniuje zawartość bezpośrednio do pliku wyjściowego, co sprawia, że jest odpowiednia dla scenariuszy **generowania dużych plików PostScript**.  
- **Bogate API:** Obsługuje rysowanie grafiki, osadzanie obrazów i dodawanie tekstu — wszystko przy zachowaniu ustawionych wymiarów.  

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|---------|-------------|
| **Wymiary strony wydają się zamienione** | Pamiętaj, że `openPage(width, height)` oczekuje najpierw szerokość, a potem wysokość (obie w punktach). |
| **Zawartość wykracza poza stronę** | Skorzystaj z układu współrzędnych `PsGraphics`, aby pozycjonować elementy w obrębie niestandardowych granic lub skaluj rysunek. |
| **Błędy braku pamięci przy bardzo dużych dokumentach** | Włącz strumieniowanie, zapisując bezpośrednio do `FileOutputStream`, jak pokazano, i unikaj ładowania dużych obrazów do pamięci jednocześnie. |

## Najczęściej zadawane pytania
### Czy mogę dodać strony o różnych rozmiarach w jednym dokumencie PostScript?
Tak, jak pokazano w tym samouczku, możesz dodawać strony o różnych rozmiarach w wielostronicowym dokumencie PostScript.  

### Czy istnieją ograniczenia co do liczby stron, które mogę dodać?
Aspose.Page obsługuje praktycznie nieograniczoną liczbę stron w dokumencie.  

### Czy mogę dodać własną zawartość, taką jak obrazy lub grafiki, na stronach?
Oczywiście! Aspose.Page pozwala dodawać szeroki zakres treści, w tym tekst, obrazy i inne elementy graficzne.  

### Czy Aspose.Page nadaje się do obsługi dużych dokumentów?
Tak, Aspose.Page jest zaprojektowany tak, aby efektywnie radzić sobie zarówno z małymi, jak i dużymi dokumentami.  

### Gdzie mogę znaleźć dodatkowe zasoby i wsparcie dla Aspose.Page?
Odwiedź [dokumentację Aspose.Page](https://reference.aspose.com/page/java/), lub zajrzyj na [forum Aspose.Page](https://forum.aspose.com/c/page/39) w celu uzyskania pomocy od społeczności.  

**Dodatkowe pytania i odpowiedzi**

**P:** *Jakie formaty obrazów są obsługiwane przy rysowaniu na stronie PostScript?*  
**O:** Możesz osadzać obrazy PNG, JPEG, BMP i GIF bezpośrednio przy użyciu API rysowania.  

**P:** *Jak zmienić domyślną rozdzielczość DPI dokumentu?*  
**O:** Ustaw `PsSaveOptions.setResolution(int dpi)` przed utworzeniem `PsDocument`.  

**P:** *Czy mogę zaszyfrować plik PostScript hasłem?*  
**O:** Sam format PostScript nie obsługuje szyfrowania, ale możesz opakować wynik w PDF i zastosować zabezpieczenia, jeśli jest to potrzebne.  

---

**Ostatnia aktualizacja:** 2026-02-18  
**Testowano z:** Aspose.Page for Java 24.10  
**Autor:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}