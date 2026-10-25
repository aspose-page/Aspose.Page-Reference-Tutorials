---
date: 2026-10-25
description: Dowiedz się, jak ustawić niestandardowy rozmiar strony i dodać strony
  do dokumentów Java PostScript przy użyciu Aspose.Page. Postępuj zgodnie z naszym
  przewodnikiem krok po kroku, aby płynnie manipulować dokumentami.
keywords:
- set custom page size
- Aspose.Page Java
- PostScript page manipulation
- add pages PostScript
lastmod: 2026-10-25
linktitle: Dodawanie stron w PostScript
og_description: Dowiedz się, jak ustawić niestandardowy rozmiar strony w PostScript
  przy użyciu Aspose.Page dla Javy. Postępuj zgodnie z instrukcjami krok po kroku,
  aby dodać strony, ustawić wymiary i efektywnie zapisać dokument.
og_image_alt: Aspose.Page Java tutorial showing how to set custom page size in a PostScript
  document
og_title: Ustaw niestandardowy rozmiar strony w PostScript przy użyciu Aspose.Page
  Java
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to set custom page size and add pages to Java PostScript
    documents using Aspose.Page. Follow our step‑by‑step guide for seamless document
    manipulation.
  headline: Aspose.Page Java Tutorial – set custom page size while Adding Pages in
    PostScript
  type: TechArticle
- questions:
  - answer: Yes—you can open pages with custom dimensions using `document.openPage(width,
      height)`.
    question: Can I set different page sizes for each page?
  - answer: A valid Aspose.Page license is required for non‑evaluation deployments.
    question: Do I need a license for production use?
  - answer: The library works with Java 8 and newer.
    question: Which Java versions are supported?
  - answer: Document instances are not thread‑safe; create a separate `PsDocument`
      per thread.
    question: Is the API thread‑safe?
  - answer: Aspose.Page handles multi‑megabyte files efficiently; memory usage scales
      with content, not page count.
    question: How large can a PostScript file be?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java PostScript
- custom page size
- add pages
- document generation
title: Samouczek Aspose.Page Java – ustaw niestandardowy rozmiar strony podczas dodawania
  stron w formacie PostScript
url: /pl/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Samouczek Aspose.Page Java – ustaw niestandardowy rozmiar strony podczas dodawania stron w PostScript

## Wprowadzenie
We współczesnych aplikacjach Java często wymaga się **ustawienia niestandardowego rozmiaru strony** dla wyjścia PostScript — niezależnie od tego, czy generujesz faktury, bilety, czy własne grafiki. Ten samouczek pokaże, jak ustawić niestandardowy rozmiar strony dla każdej strony, dodać wiele stron i wygenerować plik PostScript, który dokładnie odpowiada Twoim potrzebom układu. Otrzymasz kompletny, gotowy do uruchomienia przykład, który możesz wkleić do dowolnego projektu Java 8+.

## Szybkie odpowiedzi
- **Czy mogę ustawić różne rozmiary stron dla każdej strony?** Tak — możesz otwierać strony o niestandardowych wymiarach używając `document.openPage(width, height)`.  
- **Czy potrzebuję licencji do użytku produkcyjnego?** Wymagana jest ważna licencja Aspose.Page dla wdrożeń nie‑ewaluacyjnych.  
- **Jakie wersje Java są obsługiwane?** Biblioteka działa z Java 8 i nowszymi.  
- **Czy API jest wątkowo‑bezpieczne?** Instancje Document nie są wątkowo‑bezpieczne; utwórz osobny `PsDocument` dla każdego wątku.  
- **Jak duży może być plik PostScript?** Aspose.Page obsługuje pliki wielomegabajtowe efektywnie; zużycie pamięci skaluje się z zawartością, a nie liczbą stron.  
- **Czy mogę użyć przeciążenia open page width/height?** Oczywiście — `openPage(double width, double height)` pozwala określić dowolne wymiary w punktach.  

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz:

- Podstawową znajomość programowania w Javie.  
- Aspose.Page for Java dodany do projektu (Maven/Gradle lub ręczny JAR).  
- Środowisko programistyczne Java (IDE, JDK 8+).  

## Importowanie pakietów
Do działania potrzebne są następujące klasy: `FileOutputStream` do zapisu plików, `PsDocument` do tworzenia dokumentów PostScript oraz `PsSaveOptions` do konfigurowania opcji wyjściowych.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Krok 1: utwórz wielostronicowy dokument postscript
`PsDocument` jest klasą podstawową reprezentującą dokument PostScript, który może zawierać wiele stron.

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

## Krok 2: dodaj zawartość do pierwszej strony
Po przygotowaniu dokumentu możesz dodać dowolną zawartość do pierwszej strony. Po zakończeniu zamknij stronę, aby zablokować jej treść.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## Jak ustawić niestandardowy rozmiar strony
Ustawiasz niestandardowy rozmiar strony, wywołując `document.openPage(width, height)` z żądanymi wymiarami w punktach przed rysowaniem czegokolwiek. `openPage(width, height)` otwiera nową stronę o określonej szerokości i wysokości, dając pełną kontrolę nad płótnem strony. Jeśli domyślny rozmiar nie spełnia Twoich wymagań, możesz **ustawić niestandardowy rozmiar strony** przy otwieraniu nowej strony. Jest to przydatne przy paragonach, etykietach lub dowolnym niestandardowym układzie.

## Krok 3: dodaj drugą stronę o innym rozmiarze
Poniżej otwieramy drugą stronę i wyraźnie podajemy niestandardową szerokość oraz wysokość (w punktach). Demonstracja pokazuje, jak ustawić niestandardowy rozmiar strony dla poszczególnych stron, dając możliwość pracy z **różnymi rozmiarami stron** w tym samym dokumencie.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Krok 4: zapisz dokument
Na koniec utrwal zmiany, zapisując dokument. Wszystkie strony — w tym te o niestandardowych rozmiarach — zostaną zapisane do pliku wyjściowego.

```java
// Save the document
document.save();
```

Postępując zgodnie z tymi krokami, możesz płynnie dodawać strony i **ustawiać niestandardowy rozmiar strony** w dokumencie Java PostScript przy użyciu Aspose.Page, uzyskując pełną kontrolę nad układem każdej strony.

## Dlaczego używać Aspose.Page do ustawiania niestandardowego rozmiaru strony?
Aspose.Page zapewnia precyzyjną kontrolę nad wymiarami stron, umożliwiając definiowanie dowolnej szerokości i wysokości w punktach, mieszanie wielu rozmiarów stron w jednym dokumencie oraz efektywne strumieniowanie zawartości dla wysokowydajnej generacji PostScript. Dzięki temu jest idealny do faktur, biletów i przetwarzania wsadowego na dużą skalę, gdzie zużycie pamięci musi pozostać niskie.

Aspose.Page pozwala definiować dokładne wymiary strony w punktach, mieszać różne rozmiary w jednym pliku i strumieniowo przetwarzać zawartość, co daje precyzyjną kontrolę i wysoką wydajność przy generowaniu PostScript.  
- **Precyzja:** Wymiary są definiowane w punktach, więc masz dokładną kontrolę nad szerokością i wysokością strony.  
- **Elastyczność:** Mieszaj i dopasowuj **różne rozmiary stron** w jednym pliku PostScript.  
- **Wydajność:** Biblioteka strumieniuje zawartość bezpośrednio do pliku wyjściowego, obsługując pliki do 500 MB przy zużyciu pamięci sterty poniżej 100 MB, co czyni ją odpowiednią dla scenariuszy **generowania dużych plików PostScript**.  
- **Bogate API:** Obsługuje ponad 30 prymitywów graficznych, 10 formatów obrazów i nieograniczoną liczbę obiektów tekstowych na stronę — wszystko przy zachowaniu ustawionych niestandardowych wymiarów.

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|----------|
| **Wymiary strony wydają się zamienione** | Pamiętaj, że `openPage(width, height)` oczekuje najpierw szerokość, potem wysokość (obie w punktach). |
| **Zawartość wykracza poza stronę** | Użyj układu współrzędnych `PsGraphics`, aby pozycjonować elementy w obrębie niestandardowych granic lub skaluj rysunek. |
| **Błędy Out‑of‑memory przy dużych dokumentach** | Włącz strumieniowanie, zapisując bezpośrednio do `FileOutputStream` jak pokazano, i unikaj ładowania dużych obrazów do pamięci jednocześnie. |

## Najczęściej zadawane pytania
### Czy mogę dodać strony o różnych rozmiarach w jednym dokumencie PostScript?
Tak, jak pokazano w tym samouczku, możesz dodawać strony o różnych rozmiarach w wielostronicowym dokumencie PostScript.  

### Czy istnieją ograniczenia liczby stron, które mogę dodać?
Aspose.Page obsługuje dodawanie praktycznie nieograniczonej liczby stron do dokumentu.  

### Czy mogę dodać niestandardową zawartość, taką jak obrazy lub grafiki, na strony?
Oczywiście! Aspose.Page pozwala dodawać szeroką gamę treści, w tym tekst, obrazy i inne elementy graficzne.  

### Czy Aspose.Page nadaje się do obsługi dużych dokumentów?
Tak, Aspose.Page jest zaprojektowany tak, aby efektywnie radzić sobie zarówno z małymi, jak i dużymi dokumentami.  

### Gdzie mogę znaleźć dodatkowe zasoby i wsparcie dla Aspose.Page?
Zapoznaj się z [Aspose.Page documentation](https://reference.aspose.com/page/java/), lub odwiedź [Aspose.Page forum](https://forum.aspose.com/c/page/39) w celu uzyskania wsparcia społeczności.  

**Dodatkowe Pytania i Odpowiedzi**

**Q:** *Jakie formaty obrazu są obsługiwane przy rysowaniu na stronie PostScript?*  
**A:** Możesz osadzać obrazy PNG, JPEG, BMP i GIF bezpośrednio przy użyciu API rysowania.  

**Q:** *Jak zmienić domyślną DPI dokumentu?*  
**A:** Ustaw `PsSaveOptions.setResolution(int dpi)` przed utworzeniem `PsDocument`.  

**Q:** *Czy mogę zaszyfrować plik PostScript hasłem?*  
**A:** PostScript sam w sobie nie obsługuje szyfrowania, ale możesz opakować wynik w PDF i zastosować ustawienia zabezpieczeń, jeśli to potrzebne.

---

**Ostatnia aktualizacja:** 2026-10-25  
**Testowano z:** Aspose.Page for Java 24.10  
**Autor:** Aspose  

---

## Powiązane samouczki

- [Jak ustawić rozmiar strony A4 i utworzyć PostScript w Javie przy użyciu Aspose.Page](/page/java/document-creation/postscript/)
- [Jak przekonwertować PostScript na PDF przy użyciu Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [Jak narysować prostokąt w Java PostScript przy użyciu Aspose.Page](/page/java/postscript-shapes/add-rectangle/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}