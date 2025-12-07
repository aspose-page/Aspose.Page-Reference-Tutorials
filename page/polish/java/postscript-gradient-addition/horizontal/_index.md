---
date: 2025-12-07
description: Dowiedz się, jak dodać poziomy gradient w Java PostScript przy użyciu
  Linear Gradient Paint Java z Aspose.Page dla Javy.
language: pl
linktitle: Add Gradient in Java PostScript using Linear Gradient Paint Java
second_title: Aspose.Page Java API
title: Dodaj gradient w Java PostScript przy użyciu Linear Gradient Paint.
url: /java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj gradient w Java PostScript przy użyciu Linear Gradient Paint Java

## Wprowadzenie
W tym kompleksowym samouczku dowiesz się, jak stworzyć piękny poziomy gradient w dokumencie PostScript, wykorzystując **Linear Gradient Paint Java**. Aspose.Page for Java ułatwia pracę z formatami PostScript, PDF i innymi wektorowymi, a klasa `LinearGradientPaint` daje precyzyjną kontrolę nad przejściami kolorów. Po zakończeniu tego przewodnika będziesz w stanie renderować gradienty na kształtach **oraz** tekście, nadając swoim dokumentom profesjonalny, przyciągający uwagę wygląd.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebujesz?** Aspose.Page for Java (obsługuje Linear Gradient Paint Java).  
- **Jak długo trwa implementacja?** Około 10‑15 minut dla podstawowego gradientu.  
- **Czy potrzebna jest licencja?** Wymagana jest tymczasowa lub pełna licencja do użytku produkcyjnego.  
- **Która wersja JDK działa?** Java 8 lub nowsza.  
- **Czy mogę używać gradientu zarówno na kształtach, jak i tekście?** Tak – możesz wypełniać kształty oraz wypełniać lub obrysowywać tekst tym samym gradientem.

## Wymagania wstępne
Zanim przejdziesz do kodu, upewnij się, że masz następujące elementy:

- Zainstalowany Java Development Kit (JDK).  
- Bibliotekę Aspose.Page for Java. Możesz ją pobrać z [dokumentacji Aspose.Page Java](https://reference.aspose.com/page/java/).

## Importowanie pakietów
Rozpocznij od zaimportowania niezbędnych pakietów w swoim projekcie Java. Te importy dają dostęp do prymitywów graficznych, obsługi gradientów oraz API Aspose.Page.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Krok 1: Utwórz prostokąt
Najpierw skonfiguruj strumień wyjściowy, dokument i prostokąt, który będzie hostował gradient.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Krok 2: Utwórz poziomy Linear Gradient Paint
Tutaj budujemy obiekt **Linear Gradient Paint Java**, który definiuje poziome przejście kolorów. `AffineTransform` skaluję gradient, aby pasował do szerokości i wysokości prostokąta.

```java
// Create horizontal linear gradient paint. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Set paint
document.setPaint(paint);
```

## Krok 3: Wypełnij prostokąt
Teraz wypełnij prostokąt gradientem, który właśnie zdefiniowaliśmy.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Krok 4: Wypełnij tekst gradientem
Możesz również zastosować ten sam gradient do tekstu, tworząc efektowny wizualnie rezultat.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Krok 5: Obrysuj tekst gradientem
Na koniec obrysuj tekst, używając gradientu jako koloru obrysu.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Typowe problemy i rozwiązania
| Problem | Dlaczego się pojawia | Rozwiązanie |
|---------|----------------------|-------------|
| Gradient wygląda na rozciągnięty | Nieprawidłowe skalowanie w `AffineTransform` | Upewnij się, że szerokość i wysokość transformacji odpowiadają wymiarom prostokąta (200 × 100 w przykładzie). |
| Kolory wydają się wyblakłe | Zbyt niskie wartości alfa | Zwiększ komponent alfa (czwartą wartość w `new Color(r,g,b,alpha)`). |
| Tekst nie jest widoczny | Nie ustawiono farby przed rysowaniem tekstu | Wywołaj `document.setPaint(paint)` **przed** jakimikolwiek wywołaniami `fillAndStrokeText` lub `outlineText`. |

## Najczęściej zadawane pytania
### Czy mogę używać Aspose.Page for Java w projektach komercyjnych?
Tak, Aspose.Page for Java może być używany w projektach komercyjnych. Szczegóły licencjonowania znajdziesz na [Aspose.Purchase](https://purchase.aspose.com/buy).

### Czy dostępna jest darmowa wersja próbna?
Tak, darmową wersję próbną Aspose.Page for Java możesz uzyskać [tutaj](https://releases.aspose.com/).

### Gdzie mogę znaleźć dodatkową dokumentację i wsparcie?
Odwiedź [dokumentację Aspose.Page Java](https://reference.aspose.com/page/java/) po kompleksowe zasoby. Wsparcie społeczności znajdziesz na [forum Aspose.Page](https://forum.aspose.com/c/page/39).

### Jak mogę uzyskać tymczasową licencję?
Tymczasową licencję możesz uzyskać na [Aspose.Purchase](https://purchase.aspose.com/temporary-license/).

### Jakie są wymagania systemowe dla Aspose.Page for Java?
Szczegółowe wymagania systemowe znajdziesz w [dokumentacji](https://reference.aspose.com/page/java/).

---

**Ostatnia aktualizacja:** 2025-12-07  
**Testowano z:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}