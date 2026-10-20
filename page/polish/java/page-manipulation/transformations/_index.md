---
date: 2026-10-20
description: Dowiedz się, jak skalować prostokąt przy użyciu Aspose.Page for Java,
  jak przesuwać kształt oraz stosować przekształcenie afiniczne w celu tworzenia dokumentów
  PostScript.
keywords:
- how to scale rectangle
- how to translate shape
- save postscript file
- apply affine transform
- java graphics scaling
lastmod: 2026-10-20
linktitle: Transformacje w manipulacji stronami w języku Java
og_description: Dowiedz się, jak skalować prostokąt, przesuwać kształt i stosować
  przekształcenie afiniczne przy użyciu Aspose.Page for Java, aby efektywnie generować
  pliki PostScript.
og_image_alt: Screenshot of Java code scaling a rectangle with Aspose.Page
og_title: Jak skalować prostokąt przy użyciu Aspise.Page for Java – przewodnik krok
  po kroku
schemas:
- author: Aspose
  dateModified: '2026-10-20'
  description: Learn how to scale rectangle with Aspose.Page for Java, how to translate
    shape, and apply affine transform to create PostScript documents.
  headline: How to Scale Rectangle with Aspose.Page for Java
  type: TechArticle
- questions:
  - answer: '`translate` moves the origin of the coordinate system, while `scale`
      changes the size of drawn objects along the X and/or Y axes.'
    question: What is the difference between `translate` and `scale`?
  - answer: Yes—by calling `translate`, `scale`, `rotate`, or `shear` sequentially
      before drawing, you create a combined affine transformation.
    question: Can I combine multiple transformations in a single graphics state?
  - answer: Use `writeGraphicsRestore()` to revert to the previously saved graphics
      state.
    question: How do I reset transformations after drawing a shape?
  - answer: Absolutely. Translate the rectangle to the origin, apply `rotate(angle)`,
      then translate it back before drawing.
    question: Is it possible to rotate a rectangle around its center?
  - answer: Yes—set the appropriate rendering options in `PsSaveOptions` to enable
      anti‑aliasing.
    question: Does Aspose.Page support anti‑aliasing for smoother graphics?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript generation
- affine transformation
- rectangle scaling
title: Jak skalować prostokąt przy użyciu Aspose.Page for Java
url: /pl/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak skalować prostokąt przy użyciu Aspose.Page dla Javy

## Wprowadzenie
W tym przewodniku odkryjesz **jak skalować prostokąt** przy użyciu Aspose.Page dla Javy, a także nauczysz się przesuwać pozycje kształtów, obracać grafikę i stosować operacje przekształceń afinicznych, aby uzyskać wysokiej jakości wyjście PostScript. Te techniki pozwalają tworzyć zaawansowaną, niezależną od urządzenia grafikę bez pisania kodu renderującego niskiego poziomu, co czyni Twoje aplikacje Java bardziej potężnymi i łatwiejszymi w utrzymaniu.

## Szybkie odpowiedzi
`scale(sx, sy)` skaluje kontekst graficzny o podane czynniki poziomy i pionowy.  

- **Jak skalować prostokąt w Javie przy użyciu Aspose.Page?** Wywołaj metodę `scale(sx, sy)` na kontekście graficznym przed narysowaniem prostokąta.  
- **Czy mogę przesunąć (przetłumaczyć) kształt bez wpływu na inne grafiki?** Tak — otocz translację wywołaniami `writeGraphicsSave()` i `writeGraphicsRestore()`.  
- **Jaka klasa tworzy plik PostScript?** Użyj `PsDocument` wraz z `PsSaveOptions`.  
- **Czy potrzebna jest licencja do użytku produkcyjnego?** Wymagana jest ważna licencja Aspose.Page dla wdrożeń komercyjnych.  
- **Która wersja Javy jest wspierana?** Aspose.Page działa z Java 8 i nowszymi.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

- Solidną znajomość podstawowej składni Javy i koncepcji programowania obiektowego.  
- Zainstalowaną bibliotekę Aspose.Page dla Javy. Możesz ją pobrać z [dokumentacji Aspose.Page dla Javy](https://reference.aspose.com/page/java/).  
- IDE Javy (IntelliJ IDEA, Eclipse lub VS Code) skonfigurowane z plikami JAR biblioteki na ścieżce klas.

## Importowanie pakietów
`PsDocument` jest główną klasą używaną do tworzenia dokumentu PostScript, a `PsSaveOptions` konfiguruje sposób zapisu dokumentu.  

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Co oznacza „jak skalować prostokąt” w Aspose.Page?
`scale(float sx, float sy)` stosuje afiniczne przekształcenie skalowania do bieżącego stanu graficznego, zmieniając rozmiar kolejnych rysunków o czynniki `sx` (poziomy) i `sy` (pionowy). To podstawowa operacja stojąca za słowem kluczowym **jak skalować prostokąt**. Stosując to przekształcenie przed rysowaniem, wszystkie kolejne kształty, takie jak prostokąty, będą renderowane z nowymi wymiarami przy zachowaniu proporcji.

## Jak przetłumaczyć kształt przy użyciu Aspose.Page
`writeGraphicsSave()` zapisuje bieżący stan graficzny, a `writeGraphicsRestore()` go przywraca, zapewniając, że przekształcenia wpływają tylko na wybrany kształt. Translacja przemieszcza początek układu współrzędnych bez zmiany wymiarów obiektu. Otaczając `translate(dx, dy)` wywołaniami `writeGraphicsSave()` / `writeGraphicsRestore()`, zapewniasz, że tylko wybrany kształt się przemieszcza, podczas gdy inne grafiki pozostają niezmienione, co daje precyzyjną kontrolę nad poszczególnymi elementami.

## Przykład 1: brak przekształceń
Pierwszy przykład rysuje prostokąt bez żadnych przekształceń, ustanawiając punkt odniesienia do wizualnego porównania z późniejszymi przykładami.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## Przykład 2: translacja
W tym przykładzie przesuwamy kontekst graficzny o 250 jednostek w prawo przed narysowaniem drugiego prostokąta, ilustrując **jak przetłumaczyć kształt**.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Przykład 3: skalowanie
Tutaj odpowiadamy na podstawowe pytanie **jak skalować prostokąt**. Prostokąt jest zmniejszany do 50 % pierwotnej szerokości i 75 % pierwotnej wysokości przy użyciu wywołania `scale(0.5f, 0.75f)`.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Jak obrócić kształt w Javie (rotate shape java)
`rotate(angle)` obraca układ współrzędnych o podany kąt w stopniach. Załaduj swój `PsDocument`, wywołaj `rotate(angle)` na stanie graficznym, narysuj kształt, a następnie przywróć poprzedni stan. Ten wzorzec realizuje **rotate shape java** i **how to rotate rectangle** w jednym, wielokrotnie używanym bloku, umożliwiając obracanie grafiki wokół dowolnego wybranego punktu.

## Dlaczego to ma znaczenie – korzyści w praktyce
- **Niezależny od urządzenia output** – Aspose.Page może generować pliki PostScript i XPS, które renderują się identycznie na każdej drukarce lub przeglądarce, eliminując specyficzne dla platformy poprawki.  
- **Precyzyjna kontrola** – Łącz translację, skalowanie, ścinanie i rotację, aby spełnić dokładne specyfikacje układu; API obsługuje ponad 20 kombinacji przekształceń na stronę.  
- **Przetwarzanie nastawione na wydajność** – Biblioteka przetwarza dokumenty przy zużyciu pamięci poniżej 10 MB dla typowych raportów 100‑stronicowych, co sprawia, że zadania wsadowe są szybkie i skalowalne.

## Typowe przypadki użycia
- **Drukowalne faktury** – Precyzyjnie umieszczaj loga, kody kreskowe i tabele, używając skalowania i translacji, aby dopasować się do wytycznych marki korporacyjnej.  
- **Diagramy techniczne** – Generuj schematy, w których każdy element musi być proporcjonalnie przeskalowany i rozmieszczony.  
- **Automatyczne raporty wielostronicowe** – Twórz raporty PostScript wymagające spójnego skalowania na wszystkich stronach, np. specyfikacje inżynieryjne.

## Typowe problemy i rozwiązania
- **Przekształcenie nie resetuje się** – Zawsze paruj `writeGraphicsSave()` z `writeGraphicsRestore()`; w przeciwnym razie kolejne rysunki dziedziczą niepożądane przekształcenia.  
- **Nieoczekiwane kolory** – Ustaw farbę (kolor) po każdym przekształceniu, ponieważ stan graficzny nie zachowuje informacji o kolorze po przywróceniu.  
- **Zbyt duży rozmiar pliku** – Włącz kompresję w `PsSaveOptions` i ogranicz rozdzielczość osadzonych obrazów rastrowych, aby utrzymać ostateczny plik poniżej 5 MB dla typowych dokumentów 50‑stronicowych.

## FAQ
### Czy mogę używać Aspose.Page dla Javy do innych formatów dokumentów?
Aspose.Page koncentruje się głównie na manipulacji stronami w formatach PostScript i XPS, ale oferuje również ograniczone możliwości eksportu do PDF.

### Gdzie mogę znaleźć więcej przykładów i dokumentacji dla Aspose.Page dla Javy?
Odwiedź [dokumentację Aspose.Page dla Javy](https://reference.aspose.com/page/java/) po kompleksowe przewodniki, referencje API i przykładowe projekty.

### Czy dostępna jest bezpłatna wersja próbna Aspose.Page dla Javy?
Tak, możesz uzyskać bezpłatną wersję próbną na stronie **Aspose free trial download**: [Aspose free trial download](https://releases.aspose.com/).

### Jak mogę uzyskać tymczasową licencję dla Aspose.Page dla Javy?
Uzyskaj tymczasową licencję poprzez **temporary license request page**: [temporary license request page](https://purchase.aspose.com/temporary-license/).

### Gdzie mogę szukać wsparcia społeczności lub zadawać pytania o Aspose.Page dla Javy?
Odwiedź [forum Aspose.Page dla Javy](https://forum.aspose.com/c/page/39) w celu dyskusji społeczności, fragmentów kodu i wskazówek rozwiązywania problemów.

## Najczęściej zadawane pytania

**Q: Jaka jest różnica między `translate` a `scale`?**  
A: `translate` przesuwa początek układu współrzędnych, podczas gdy `scale` zmienia rozmiar rysowanych obiektów wzdłuż osi X i/lub Y.

**Q: Czy mogę połączyć wiele przekształceń w jednym stanie graficznym?**  
A: Tak — wywołując kolejno `translate`, `scale`, `rotate` lub `shear` przed rysowaniem, tworzysz połączone przekształcenie afiniczne.

**Q: Jak zresetować przekształcenia po narysowaniu kształtu?**  
A: Użyj `writeGraphicsRestore()` aby przywrócić wcześniej zapisany stan graficzny.

**Q: Czy można obrócić prostokąt wokół jego środka?**  
A: Oczywiście. Przesuń prostokąt do początku układu, zastosuj `rotate(angle)`, a następnie przesuń go z powrotem przed rysowaniem.

**Q: Czy Aspose.Page obsługuje anti‑aliasing dla wygładzania grafiki?**  
A: Tak — ustaw odpowiednie opcje renderowania w `PsSaveOptions`, aby włączyć anti‑aliasing.

---

**Ostatnia aktualizacja:** 2026-10-20  
**Testowano z:** Aspose.Page for Java 24.12  
**Autor:** Aspose

## Powiązane samouczki

- [Jak narysować prostokąt w Java PostScript przy użyciu Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [Utwórz gradient promienisty w PostScript przy użyciu Aspose.Page dla Javy](/page/java/postscript-gradient-addition/)
- [Manipulacja stroną PostScript](/page/java/postscript-page-manipulation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}