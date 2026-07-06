---
date: 2026-02-13
description: Dowiedz się, jak wypełnić kształt gradientem i narysować okrąg z gradientem
  w Java PostScript przy użyciu Aspose.Page. Przewodnik krok po kroku z kodem i wskazówkami.
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 'Wypełnij kształt gradientem: przykład radialny w Java PostScript'
url: /pl/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wypełnij kształt gradientem: Przykład radialny Java PostScript

## Wstęp
W tym samouczku nauczysz się, jak **wypełnić kształt gradientem**, budując przykład radialnego gradientu dla dokumentu PostScript przy użyciu Aspose.Page dla Javy. Przejdziemy przez każdy krok — od konfiguracji projektu po renderowanie koła wypełnionego płynnym gradientem radialnym — abyś mógł od razu dodać przyciągające uwagę grafiki do swoich aplikacji Java.

## Szybkie odpowiedzi
- **Co tworzy ten samouczek?** Plik PostScript (`.ps`) zawierający koło wypełnione gradientem radialnym.  
- **Jakiej biblioteki potrzebujesz?** Aspose.Page dla Javy (najnowsza wersja).  
- **Jak długo trwa implementacja?** Około 10‑15 minut dla działającego przykładu.  
- **Czy potrzebna jest licencja?** Wymagana jest tymczasowa lub pełna licencja do użytku produkcyjnego; wersja próbna działa w środowisku deweloperskim.  
- **Czy mogę ponownie użyć kodu dla PDF lub SVG?** Tak — Aspose.Page obsługuje wiele formatów wyjściowych przy minimalnych zmianach.

## Jak wypełnić kształt gradientem w PostScript
Zanim przejdziemy do kodu, wyjaśnijmy, dlaczego „wypełnienie kształtu gradientem” ma znaczenie. Gradienty nadają grafikom profesjonalny, trójwymiarowy wygląd bez konieczności używania obrazów rastrowych. Dzięki Aspose.Page możesz zastosować tę samą logikę gradientu do dowolnego kształtu wektorowego — kół, prostokątów lub własnych ścieżek — we wszystkich obsługiwanych formatach wyjściowych (PostScript, PDF, SVG).

## Co to jest gradient radialny?
Gradient radialny przechodzi kolory od punktu centralnego na zewnątrz, tworząc płynne, okrągłe przejście. Jest idealny do podświetleń, tła przycisków lub wszelkich elementów wymagających naturalnego efektu „poświaty”.

## Dlaczego warto używać Aspose.Page do gradientów radialnych?
- **Renderowanie niezależne od urządzenia** – działa tak samo w PostScript, PDF, SVG i innych.  
- **Pełna integracja z Javą** – bez kodu natywnego, tylko czyste API Javy.  
- **Wysokiej jakości wynik** – obsługa antyaliasingu i kontroli przestrzeni kolorów.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz:

- Podstawową znajomość programowania w Javie.  
- Zainstalowane JDK 8 lub nowsze na swoim komputerze.  
- Bibliotekę Aspose.Page dla Javy (pobierz z [dokumentacji Aspose.Page Java](https://reference.aspose.com/page/java/)).  

## Importowanie pakietów
Najpierw zaimportuj klasy, których będziemy potrzebować. Obejmują one standardowe typy grafiki AWT oraz API Aspose.Page.

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

## Krok 1: Ustawienie katalogu dokumentu
Zdefiniuj folder, w którym zostanie zapisany wygenerowany plik PostScript. Zamień symboliczny placeholder na rzeczywistą ścieżkę w swoim systemie.

```java
String dataDir = "Your Document Directory";
```

## Krok 2: Utworzenie strumienia wyjściowego
Otwórz `FileOutputStream`, który wskazuje na docelowy plik `.ps`. Ten strumień dostarcza binarne dane generowane przez Aspose.Page.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Krok 3: Utworzenie opcji zapisu
Zainicjuj `PsSaveOptions`. Możesz dostosować rozmiar strony, kompresję itp., ale domyślne ustawienia są wystarczające dla tego przykładu.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Krok 4: Utworzenie dokumentu PS
Utwórz obiekt `PsDocument`, przekazując strumień wyjściowy i opcje zapisu. Flaga `false` informuje Aspose.Page, aby nie otwierał automatycznie strony (zrobimy to ręcznie).

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Krok 5: Utworzenie koła
Narysujemy koło przy użyciu `Ellipse2D.Float`. Parametry to `(x, y, width, height)`. Ustawienie `width = height` tworzy idealne koło.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Jak narysować koło z gradientem
Teraz, gdy mamy kształt, następnym krokiem jest **narysowanie koła z gradientem**. Poprzez zastosowanie `RadialGradientPaint` do koła, operacja wypełniania automatycznie użyje zdefiniowanego gradientu.

## Krok 6: Definicja kolorów gradientu
Przygotuj dwie tablice: jedną dla kolorów, które pojawią się w gradiencie, oraz drugą dla odpowiadających im pozycji ułamkowych (0 = środek, 1 = krawędź).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Krok 7: Utworzenie AffineTransform
`AffineTransform` skaluje i przesuwa gradient, aby pasował do naszego koła. Macierz `(scaleX, 0, 0, scaleY, translateX, translateY)` wykonuje to zadanie.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Krok 8: Utworzenie RadialGradientPaint
Teraz budujemy obiekt `RadialGradientPaint`. Przyjmuje on punkt środkowy, promień, punkt ogniskowy, ułamki kolorów, tablicę kolorów, metodę cyklu, przestrzeń kolorów oraz transformację, którą właśnie zdefiniowaliśmy.

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

## Krok 9: Ustawienie farby i wypełnienie koła
Zastosuj farbę gradientu do dokumentu i wypełnij wcześniej zdefiniowane koło. To jest sedno naszego **przykładu gradientu radialnego** i pokazuje, jak **wypełnić kształt gradientem**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Krok 10: Zamknięcie strony i zapis dokumentu
Zakończ stronę, zapisz zawartość na dysk i zamknij strumień. Twój plik PostScript jest teraz gotowy do otwarcia w dowolnym przeglądarce PS.

```java
document.closePage();
document.save();
```

Gratulacje! Pomyślnie stworzyłeś przykład gradientu radialnego w Java PostScript przy użyciu Aspose.Page. Masz teraz wielokrotnego użytku wzorzec dla **wypełniania kształtu gradientem**, który można dostosować do innych kształtów i formatów wyjściowych.

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|---------|-------------|
| **FileNotFoundException** przy otwieraniu strumienia wyjściowego | Sprawdź, czy `dataDir` wskazuje na istniejący folder i masz uprawnienia do zapisu. |
| Gradient wygląda płasko lub nie jest widoczny | Upewnij się, że tablica `fractions` ma taką samą długość jak tablica `colors` oraz że `AffineTransform` skaluje poprawnie. |
| Kolory są odwrócone | Zamień kolejność kolorów w tablicy `colors` lub dostosuj współrzędne punktu `focus`. |

## Najczęściej zadawane pytania

**P: Gdzie mogę znaleźć dokumentację Aspose.Page dla Javy?**  
O: Pełna referencja API jest dostępna [tutaj](https://reference.aspose.com/page/java/).

**P: Jak mogę pobrać Aspose.Page dla Javy?**  
O: Pobierz najnowszy plik JAR ze [strony wydań](https://releases.aspose.com/page/java/).

**P: Czy dostępna jest darmowa wersja próbna?**  
O: Tak — wersję próbną pobierzesz [tutaj](https://releases.aspose.com/).

**P: Czy mogę uzyskać tymczasową licencję do testów?**  
O: Oczywiście, zamów ją na [stronie tymczasowej licencji](https://purchase.aspose.com/temporary-license/).

**P: Gdzie mogę uzyskać wsparcie społeczności?**  
O: Dołącz do dyskusji na [forum Aspose.Page](https://forum.aspose.com/c/page/39).

## Zakończenie
W tym przewodniku zbudowaliśmy kompletny **przykład gradientu radialnego** dla dokumentu PostScript przy użyciu Aspose.Page dla Javy. Postępując zgodnie z krokami, masz teraz wielokrotnego użytku wzorzec dla **wypełniania kształtu gradientem**, który możesz dostosować do PDF, SVG lub dowolnego innego formatu obsługiwanego przez Aspose.Page. Eksperymentuj z różnymi kolorami, promieniami i kształtami, aby wzbogacić swoje projekty graficzne w Javie.

---

**Ostatnia aktualizacja:** 2026-02-13  
**Testowano z:** Aspose.Page dla Javy 24.11 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}