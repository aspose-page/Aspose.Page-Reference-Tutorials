---
date: 2025-12-07
description: Dowiedz się, jak skalować prostokąt, przesuwać kształt i stosować przekształcenie
  afiniczne w Javie przy użyciu Aspose.Page do tworzenia dokumentów PostScript.
language: pl
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Jak skalować prostokąt i stosować transformacje w Aspose.Page
url: /java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak skalować prostokąt i stosować transformacje przy użyciu Aspose.Page

## Wprowadzenie
Witamy w kompleksowym przewodniku po wykorzystaniu potężnych funkcji **Aspose.Page for Java** do wykonywania różnorodnych transformacji stron. W tym tutorialu dowiesz się, **jak skalować prostokąt**, przesuwać kształty, obracać obiekty oraz **stosować transformacje afiniczne** podczas tworzenia **dokumentu PostScript**. Te możliwości pozwalają budować bogate, graficznie intensywne aplikacje Java bez konieczności zajmowania się kodem renderującym niskiego poziomu.

## Szybkie odpowiedzi
- **Jak skalować prostokąt w Javie przy użyciu Aspose.Page?** Użyj metody `document.scale()` przed narysowaniem kształtu.  
- **Czy mogę przesunąć (przetłumaczyć) kształt bez wpływu na inne grafiki?** Tak — zapisz stan grafiki, wywołaj `document.translate(x, y)`, narysuj, a następnie przywróć stan.  
- **Która klasa tworzy plik PostScript?** `PsDocument` wraz z `PsSaveOptions`.  
- **Czy potrzebna jest licencja do użytku produkcyjnego?** Tak, wymagana jest ważna licencja Aspose.Page dla wdrożeń komercyjnych.  
- **Jaką wersję Javy obsługuje?** Aspose.Page działa z Java 8 i nowszymi.

## Wymagania wstępne
Zanim przejdziemy do szczegółowego przewodnika, upewnij się, że spełniasz następujące wymagania:

- Podstawowa znajomość programowania w Javie.  
- Biblioteka Aspose.Page for Java zainstalowana. Możesz ją pobrać z [dokumentacji Aspose.Page for Java](https://reference.aspose.com/page/java/).  
- Zintegrowane środowisko programistyczne (IDE) Javy skonfigurowane na Twoim komputerze.

## Importowanie pakietów
W swoim projekcie Java zaimportuj niezbędne pakiety, aby korzystać z Aspose.Page for Java:

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

## Jak przesunąć kształt przy użyciu Aspose.Page
Przesunięcie (translacja) przenosi kształt w nowe miejsce bez zmiany jego wymiarów. To istota **jak przesunąć kształt**. Poprzez zapisanie stanu grafiki, zastosowanie `translate(dx, dy)`, narysowanie i przywrócenie stanu, inne obiekty pozostają niezmienione.

## Przykład 1: Brak transformacji
Pierwszy przykład rysuje prosty prostokąt bez zastosowanej transformacji. Służy jako punkt odniesienia do późniejszych przykładów.

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
Tutaj demonstrujemy **jak przesunąć kształt**, przesuwając kontekst graficzny o 250 jednostek w prawo przed narysowaniem drugiego prostokąta.

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
Ten przykład odpowiada na podstawowe pytanie **jak skalować prostokąt**. Zmniejszamy prostokąt do 50 % jego pierwotnej szerokości i 75 % wysokości.

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
Obrót to kolejna powszechna operacja afiniczna. Choć fragmenty kodu dotyczące obrotu zostały pominięte dla zwięzłości, schemat jest identyczny: zapisz stan grafiki, wywołaj `document.rotate(angle)`, narysuj kształt, a następnie przywróć. To demonstruje **rotate shape java** oraz **jak obrócić prostokąt** w praktyce.

## Dlaczego warto używać Aspose.Page do tych transformacji?
- **Niezależność od urządzenia**: Napisz raz, generuj PostScript lub XPS bez kodu specyficznego dla platformy.  
- **Precyzyjna kontrola**: Bezpośredni dostęp do stanu grafiki pozwala łączyć translację, skalowanie, pochylenie i obrót.  
- **Wydajność**: API o niskim narzucie, odpowiednie do przetwarzania wsadowego dużych dokumentów.  

## Typowe scenariusze użycia
- Generowanie drukowanych faktur z dynamicznymi kodami kreskowymi i logo.  
- Tworzenie diagramów technicznych, gdzie wymagana jest precyzyjna skalacja i pozycjonowanie.  
- Automatyzacja produkcji wielostronicowych raportów w formacie Post.

## Zakończenie
W tym tutorialu poznaliśmy różne transformacje w manipulacji stronami w Javie przy użyciu Aspose.Page for Java, koncentrując się na **jak skalować prostokąt**, **jak przesunąć kształt** oraz innych operacjach afinicznych. Postępując zgodnie z przedstawionymi przykładami, możesz wzbogacić swoje aplikacje Java o zaawansowane możliwości manipulacji stronami i **tworzyć dokumenty PostScript**, które spełniają profesjonalne standardy publikacji.

## FAQ's
### Czy mogę używać Aspose.Page for Java do innych formatów dokumentów?
Aspose.Page koncentruje się głównie na manipulacji stronami dla formatów PostScript i XPS.

### Gdzie znajdę więcej przykładów i dokumentacji dla Aspose.Page for Java?
Odwiedź [dokumentację Aspose.Page for Java](https://reference.aspose.com/page/java/) po kompleksowe informacje.

### Czy dostępna jest darmowa wersja próbna Aspose.Page for Java?
Tak, darmową wersję próbną znajdziesz [tutaj](https://releases.aspose.com/).

### Jak mogę uzyskać tymczasową licencję dla Aspose.Page for Java?
Uzyskaj tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/).

### Gdzie mogę szukać wsparcia społeczności lub zadawać pytania o Aspose.Page for Java?
Odwiedź [forum Aspose.Page for Java](https://forum.aspose.com/c/page/39) w celu dyskusji społecznościowych.

## Frequently Asked Questions

**Q: Jaka jest różnica między `translate` a `scale`?**  
A: `translate` przesuwa początek układu współrzędnych, natomiast `scale` zmienia rozmiar rysowanych obiektów wzdłuż osi X i/lub Y.

**Q: Czy mogę łączyć wiele transformacji w jednym stanie grafiki?**  
A: Tak — wywołując kolejno `translate`, `scale`, `rotate` lub `shear` przed rysowaniem, tworzysz połączoną transformację afiniczną.

**Q: Jak zresetować transformacje po narysowaniu kształtu?**  
A: Użyj `document.writeGraphicsRestore()`, aby przywrócić wcześniej zapisany stan grafiki.

**Q: Czy można obrócić prostokąt wokół jego środka?**  
A: Oczywiście. Przesuń prostokąt do początku układu, zastosuj `rotate(angle)`, a następnie przywróć pozycję przed rysowaniem.

**Q: Czy Aspose.Page obsługuje anti‑aliasing dla płynniejszych grafik?**  
A: Tak — ustaw odpowiednie opcje renderowania w `PsSaveOptions`, aby włączyć anti‑aliasing.

---

**Ostatnia aktualizacja:** 2025-12-07  
**Testowano z:** Aspose.Page for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}