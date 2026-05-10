---
date: 2026-02-07
description: Dowiedz się, jak skalować prostokąt za pomocą Aspose.Page dla Javy, jak
  przesuwać kształt oraz stosować przekształcenie afiniczne w celu tworzenia dokumentów
  PostScript.
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Jak skalować prostokąt przy użyciu Aspose.Page dla Javy
url: /pl/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak skalować prostokąt przy użyciu Aspose.Page dla Javy

## Wprowadzenie
Witamy w kompleksowym przewodniku po wykorzystaniu potężnych funkcji **Aspose.Page dla Javy** do wykonywania różnorodnych transformacji stron. W tym tutorialu dowiesz się, **jak skalować prostokąt**, przesuwać kształty, obracać obiekty oraz **zastosować transformację afiniczną** podczas tworzenia **dokumentu PostScript**. Te możliwości pozwalają budować bogate, graficznie intensywne aplikacje Java bez konieczności zajmowania się kodem renderującym niskiego poziomu.

## Szybkie odpowiedzi
- **Jak skalować prostokąt w Javie przy użyciu Aspose.Page?** Użyj metody `document.scale()` przed rysowaniem kształtu.  
- **Czy mogę przesunąć (przetłumaczyć) kształt bez wpływu na inne grafiki?** Tak — zapisz stan grafiki, wywołaj `document.translate(x, y)`, narysuj, a następnie przywróć stan.  
- **Która klasa tworzy plik PostScript?** `PsDocument` wraz z `PsSaveOptions`.  
- **Czy potrzebna jest licencja do użytku produkcyjnego?** Wymagana jest ważna licencja Aspose.Page dla wdrożeń komercyjnych.  
- **Jaką wersję Javy obsługuje?** Aspose.Page działa z Java 8 i nowszymi.

## Wymagania wstępne
Zanim przejdziemy do szczegółowego przewodnika, upewnij się, że spełniasz następujące wymagania:

- Podstawowa znajomość programowania w Javie.  
- Biblioteka Aspose.Page dla Javy zainstalowana. Możesz ją pobrać z [dokumentacji Aspose.Page dla Javy](https://reference.aspose.com/page/java/).  
- Zintegrowane środowisko programistyczne (IDE) dla Javy skonfigurowane na Twoim komputerze.

## Importowanie pakietów
W swoim projekcie Java zaimportuj niezbędne pakiety, aby korzystać z Aspose.Page dla Javy:

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
Skalowanie prostokąta zmienia jego rozmiar wzdłuż osi X i Y, zachowując jednocześnie kształt. Aspose.Page udostępnia metodę `scale(float sx, float sy)`, która stosuje **transformację afiniczną** do bieżącego stanu grafiki. To podstawowa technika stojąca za słowem kluczowym **jak skalować prostokąt**.

## Jak przetłumaczyć kształt przy użyciu Aspose.Page
Przesunięcie (translacja) przenosi kształt w nowe miejsce bez zmiany jego wymiarów. To istota **jak przetłumaczyć kształt**. Poprzez zapisanie stanu grafiki, zastosowanie `translate(dx, dy)`, narysowanie i przywrócenie stanu, inne obiekty pozostają niezmienione.

## Przykład 1: Brak transformacji
Pierwszy przykład rysuje prosty prostokąt bez zastosowanej transformacji. Służy jako punkt odniesienia do porównań z późniejszymi przykładami.

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

## Przykład 2: Translacja
Tutaj demonstrujemy **jak przetłumaczyć kształt**, przesuwając kontekst graficzny o 250 jednostek w prawo przed narysowaniem drugiego prostokąta.

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

## Przykład 3: Skalowanie
Ten przykład odpowiada na podstawowe pytanie **jak skalować prostokąt**. Zmniejszamy prostokąt do 50 % pierwotnej szerokości i 75 % pierwotnej wysokości.

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
Obrót jest kolejną powszechną operacją afiniczną. Chociaż fragmenty kodu dotyczące obrotu zostały pominięte dla zwięzłości, schemat jest identyczny: zapisz stan grafiki, wywołaj `document.rotate(angle)`, narysuj kształt, a następnie przywróć. To demonstruje **rotate shape java** oraz **jak obrócić prostokąt** w praktyce.

## Dlaczego to ma znaczenie – korzyści w rzeczywistych zastosowaniach
- **Wyjście niezależne od urządzenia** – Napisz raz i generuj PostScript lub XPS bez specyficznych poprawek platformowych.  
- **Precyzyjna kontrola** – Łącz translację, skalowanie, pochylenie i obrót, aby spełnić dokładne wymagania układu.  
- **Skoncentrowane na wydajności** – Niskokosztowe API idealne do przetwarzania wsadowego dużych dokumentów.  

## Typowe scenariusze użycia
- Generowanie faktur do druku – na przykład rozwiązanie **printable invoice java**, które precyzyjnie rozmieszcza loga i kody kreskowe.  
- Tworzenie diagramów technicznych, gdzie wymagana jest dokładna skala i pozycjonowanie.  
- Automatyzacja produkcji wielostronicowych raportów w formacie PostScript.

## Typowe problemy i rozwiązania
- **Transformacja nie resetuje się** – Zawsze paruj `document.writeGraphicsSave()` z `document.writeGraphicsRestore()`, aby uniknąć niepożądanych efektów przenoszenia.  
- **Nieoczekiwane kolory** – Upewnij się, że ustawiasz farbę po każdej transformacji; stan grafiki nie zachowuje poprzednich ustawień koloru po przywróceniu.  
- **Rozmiar pliku zbyt duży** – Użyj `PsSaveOptions`, aby włączyć kompresję lub zmniejszyć rozdzielczość obrazu przy osadzaniu grafiki rastrowej.

## FAQ
### Czy mogę używać Aspose.Page dla Javy do innych formatów dokumentów?
Aspose.Page koncentruje się głównie na manipulacji stronami w formatach PostScript i XPS.

### Gdzie mogę znaleźć więcej przykładów i dokumentacji dla Aspose.Page dla Javy?
Odwiedź [dokumentację Aspose.Page dla Javy](https://reference.aspose.com/page/java/) po kompleksowe informacje.

### Czy dostępna jest bezpłatna wersja próbna Aspose.Page dla Javy?
Tak, bezpłatną wersję próbną znajdziesz [tutaj](https://releases.aspose.com/).

### Jak mogę uzyskać tymczasową licencję dla Aspose.Page dla Javy?
Uzyskaj tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/).

### Gdzie mogę uzyskać wsparcie społeczności lub zadać pytania dotyczące Aspose.Page dla Javy?
Odwiedź [forum Aspose.Page dla Javy](https://forum.aspose.com/c/page/39) w celu dyskusji ze społecznością.

## Najczęściej zadawane pytania

**P: Jaka jest różnica między `translate` a `scale`?**  
O: `translate` przesuwa początek układu współrzędnych, natomiast `scale` zmienia rozmiar rysowanych obiektów wzdłuż osi X i/lub Y.

**P: Czy mogę łączyć wiele transformacji w jednym stanie grafiki?**  
O: Tak — wywołując kolejno `translate`, `scale`, `rotate` lub `shear` przed rysowaniem, tworzysz połączoną transformację afiniczną.

**P: Jak zresetować transformacje po narysowaniu kształtu?**  
O: Użyj `document.writeGraphicsRestore()`, aby powrócić do wcześniej zapisanego stanu grafiki.

**P: Czy można obrócić prostokąt wokół jego środka?**  
O: Oczywiście. Przesuń prostokąt do początku układu, zastosuj `rotate(angle)`, a następnie przywróć pozycję przed rysowaniem.

**P: Czy Aspose.Page obsługuje anti‑aliasing dla wygładzania grafiki?**  
O: Tak — ustaw odpowiednie opcje renderowania w `PsSaveOptions`, aby włączyć anti‑aliasing.

---

**Ostatnia aktualizacja:** 2026-02-07  
**Testowano z:** Aspose.Page dla Javy 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}