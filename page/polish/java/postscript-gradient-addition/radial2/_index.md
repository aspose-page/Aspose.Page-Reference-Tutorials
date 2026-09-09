---
date: 2026-09-09
description: Dowiedz się, jak stworzyć gradient w Java PostScript i dodać gradient
  do kształtu przy użyciu Aspose.Page. Przejdź przez ten przewodnik krok po kroku
  z kodem i wskazówkami.
keywords:
- how to create gradient
- add gradient to shape
- radial gradient Java
lastmod: 2026-09-09
linktitle: Java PostScript Radial Gradient z Aspose.Page
og_description: Dowiedz się, jak stworzyć gradient w Java PostScript i dodać gradient
  do kształtu przy użyciu Aspose.Page. Przejdź przez ten przewodnik krok po kroku
  z kodem i wskazówkami.
og_image_alt: 'Developer guide: create gradient in Java PostScript with radial fill
  using Aspose.Page'
og_title: Jak stworzyć gradient w Java PostScript z radial fill
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create gradient in Java PostScript and add gradient to
    shape using Aspose.Page. Follow this step‑by‑step guide with code and tips.
  headline: How to create gradient in Java PostScript with radial fill
  type: TechArticle
- questions:
  - answer: The full API reference is available in the [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).
    question: Where can I find the documentation for Aspose.Page for Java?
  - answer: Grab the latest JAR from the [releases page](https://releases.aspose.com/page/java/).
    question: How can I download Aspose.Page for Java?
  - answer: Yes—download a trial version from the [Aspose free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Absolutely, request one from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for testing?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- radial gradient
- fill shape
title: Jak stworzyć gradient w Java PostScript z radial fill
url: /pl/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak stworzyć gradient w Java PostScript z wypełnieniem radialnym

## Wstęp
W tym samouczku nauczysz się **tworzyć gradient** w dokumencie PostScript przy użyciu Javy i Aspose.Page. Przejdziemy przez każdy krok — od konfiguracji projektu po renderowanie koła wypełnionego płynnym gradientem radialnym — abyś mógł **dodać gradient do obiektów kształtu** natychmiast i podnieść jakość wizualną swoich aplikacji Java.

## Szybkie odpowiedzi
- **Co tworzy ten samouczek?** Plik PostScript (`.ps`) zawierający koło wypełnione gradientem radialnym.  
- **Jakiej biblioteki potrzebujesz?** Aspose.Page for Java (najnowsza wersja).  
- **Jak długo trwa implementacja?** Około 10‑15 minut dla działającego przykładu.  
- **Czy potrzebna jest licencja?** Do użytku produkcyjnego wymagana jest tymczasowa lub pełna licencja; darmowa wersja próbna działa w fazie rozwoju.  
- **Czy mogę ponownie użyć kodu dla PDF lub SVG?** Tak — Aspose.Page obsługuje wiele formatów wyjściowych przy minimalnych zmianach.

## Jak wypełnić kształt gradientem w PostScript
Możesz wypełnić kształt gradientem radialnym w PostScript, tworząc `PsDocument`, definiując `RadialGradientPaint`, stosując go do docelowego kształtu i na końcu zapisując dokument. Ten zwięzły przepływ pracy pozwala tworzyć profesjonalnie wyglądające grafiki wektorowe bez obrazów rastrowych, a ten sam kod może być ponownie użyty dla wyjścia PDF lub SVG. Proces jest prosty i działa konsekwentnie we wszystkich obsługiwanych formatach.

## Czym jest gradient radialny?
Gradient radialny przechodzi kolory od centralnego punktu na zewnątrz, tworząc płynne, okrągłe przejście. Jest idealny do podświetleń, tła przycisków lub każdego elementu wizualnego, który wymaga naturalnego efektu „poświaty”. Poprzez zmianę punktów kolorów i promienia możesz symulować oświetlenie, głębię i właściwości materiału w czystej formie wektorowej.

## Dlaczego używać Aspose.Page do gradientów radialnych?
Aspose.Page pozwala generować niezależne od urządzenia grafiki wektorowe przy użyciu jednej API w Javie. Obsługuje ponad 50 formatów wejścia i wyjścia — w tym PostScript, PDF i SVG — zachowując dokładność kolorów i antyaliasing dla wyjścia wysokiej rozdzielczości. Biblioteka udostępnia także łatwe w użyciu klasy gradientów, co sprawia, że skomplikowane efekty wizualne są proste do wdrożenia.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz:

- Podstawową znajomość programowania w Javie.  
- Zainstalowane JDK 8 lub nowsze.  
- Bibliotekę Aspose.Page for Java (pobierz z [dokumentacji Aspose.Page Java](https://reference.aspose.com/page/java/)).  

## Importowanie pakietów
Najpierw zaimportuj klasy, które będą potrzebne. Obejmują one standardowe typy grafiki AWT oraz API Aspose.Page.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Krok 1: ustaw katalog dokumentu
Zdefiniuj folder, w którym zostanie zapisany wygenerowany plik PostScript. Zastąp symboliczny placeholder rzeczywistą ścieżką w swoim systemie.

```java
String dataDir = "Your Document Directory";
```

## Krok 2: utwórz strumień wyjściowy
`FileOutputStream` zapisuje surowe bajty do pliku, umożliwiając zapis danych binarnych. Otworzenie takiego strumienia skierowanego do pliku `.ps` pozwala Aspose.Page przesłać wygenerowane dane PostScript bezpośrednio na dysk.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Krok 3: utwórz opcje zapisu
`PsSaveOptions` konfiguruje sposób zapisu pliku PostScript, w tym rozmiar strony i kompresję. Możesz dostosować te ustawienia, ale domyślne wartości są wystarczające dla tego przykładu.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Krok 4: utwórz dokument ps
`PsDocument` reprezentuje dokument PostScript w pamięci i udostępnia metody dodawania stron oraz grafiki.

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Krok 5: utwórz koło
`Ellipse2D.Float` opisuje kształt elipsy; gdy szerokość = wysokość, staje się idealnym kołem. Ten obiekt posłuży jako płótno dla naszego gradientu.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Jak narysować koło z gradientem
Aby narysować koło z gradientem radialnym, wczytujesz `RadialGradientPaint` do kontekstu graficznego, a następnie wypełniasz wcześniej zdefiniowaną elipsę. Ta pojedyncza operacja maluje kształt płynnym przejściem kolorów od środka na zewnątrz, tworząc atrakcyjny wizualnie efekt.

## Krok 6: zdefiniuj kolory gradientu
Przygotuj dwie tablice: jedną dla kolorów, które pojawią się w gradiencie, oraz drugą dla odpowiadających im pozycji ułamkowych (0 = środek, 1 = krawędź).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Krok 7: utwórz AffineTransform
`AffineTransform` to macierz, która może przesuwać, obracać, skalować lub ścinać obiekty graficzne. Tutaj skaluje i przesuwa gradient, aby idealnie pasował do koła.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Krok 8: utwórz radialny gradient
`RadialGradientPaint` tworzy radialny gradient kolorów na podstawie punktu centralnego, promienia i punktów kolorów.

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## Krok 9: ustaw farbę i wypełnij koło
Zastosuj farbę gradientu do dokumentu i wypełnij wcześniej zdefiniowane koło. To jest sedno naszego **przykładu gradientu radialnego** i pokazuje, jak **wypełnić kształt gradientem**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Krok 10: zamknij stronę i zapisz dokument
Zakończ stronę, zapisz zawartość na dysk i zamknij strumień. Twój plik PostScript jest gotowy do otwarcia w dowolnym przeglądarce PS.

```java
document.closePage();
document.save();
```

Gratulacje! Pomyślnie stworzyłeś przykład gradientu radialnego w Java PostScript przy użyciu Aspose.Page. Masz teraz wzorzec do **wypełniania kształtu gradientem**, który można dostosować do innych kształtów i formatów wyjściowych.

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|---------|-------------|
| **FileNotFoundException** przy otwieraniu strumienia wyjściowego | Sprawdź, czy `dataDir` wskazuje istniejący folder i masz uprawnienia do zapisu. |
| Gradient wygląda płasko lub brakuje go | Upewnij się, że tablica `fractions` ma taką samą długość jak tablica `colors` i że `AffineTransform` skaluje poprawnie. |
| Kolory są odwrócone | Zamień kolejność kolorów w tablicy `colors` lub dostosuj współrzędne punktu `focus`. |

## Najczęściej zadawane pytania

**P: Gdzie mogę znaleźć dokumentację Aspose.Page dla Javy?**  
O: Pełna referencja API jest dostępna w [dokumentacji Aspose.Page Java API](https://reference.aspose.com/page/java/).

**P: Jak mogę pobrać Aspose.Page dla Javy?**  
O: Pobierz najnowszy JAR z [strony wydań](https://releases.aspose.com/page/java/).

**P: Czy dostępna jest darmowa wersja próbna?**  
O: Tak — pobierz wersję próbną ze [strony pobierania darmowej wersji próbnej Aspose](https://releases.aspose.com/).

**P: Czy mogę uzyskać tymczasową licencję do testów?**  
O: Oczywiście, zamów ją na [stronie licencji tymczasowej](https://purchase.aspose.com/temporary-license/).

**P: Gdzie mogę uzyskać wsparcie społeczności?**  
O: Dołącz do dyskusji na [forum Aspose.Page](https://forum.aspose.com/c/page/39).

## Podsumowanie
W tym przewodniku zbudowaliśmy kompletny **przykład gradientu radialnego** dla dokumentu PostScript przy użyciu Aspose.Page for Java. Postępując zgodnie z krokami, masz teraz wzorzec do **wypełniania kształtu gradientem**, który możesz dostosować do PDF, SVG lub dowolnego innego formatu obsługiwanego przez Aspose.Page. Eksperymentuj z różnymi kolorami, promieniami i kształtami, aby wzbogacić swoje projekty graficzne w Javie.

---

**Ostatnia aktualizacja:** 2026-09-09  
**Testowano z:** Aspose.Page for Java 24.11 (najnowsza w momencie pisania)  
**Autor:** Aspose

## Powiązane samouczki

- [Create PostScript Gradient in Java – Add Vertical Gradient](/page/java/postscript-gradient-addition/vertical/)
- [Create Texture Pattern in PostScript with Aspose.Page for Java](/page/java/postscript-texture-patterns/)
- [Aspose.Page Transparency Tutorial – Add Transparency in Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}