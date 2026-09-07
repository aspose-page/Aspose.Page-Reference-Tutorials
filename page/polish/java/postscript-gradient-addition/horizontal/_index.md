---
date: 2026-09-04
description: Dowiedz się, jak stworzyć poziomy gradient Java w pliku PostScript przy
  użyciu Linear Gradient Paint Java z Aspose.Page dla Javy. Kod krok po kroku, typowe
  pułapki i najczęściej zadawane pytania.
keywords:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page Java
- PostScript gradient Java
lastmod: 2026-09-04
linktitle: Tworzenie poziomego gradientu Java w PostScript przy użyciu Aspose
og_description: Stwórz poziomy gradient Java w PostScript przy użyciu Linear Gradient
  Paint Java. Ten samouczek Aspose.Page pokazuje dokładne kroki, wymagania wstępne
  oraz wskazówki rozwiązywania problemów w mniej niż 15 minut.
og_image_alt: Screenshot of a Java PostScript file rendered with a horizontal gradient
  using Aspose.Page
og_title: Tworzenie poziomego gradientu Java w PostScript przy użyciu Aspose
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to create horizontal gradient java in a PostScript file using
    Linear Gradient Paint Java with Aspose.Page for Java. Step‑by‑step code, common
    pitfalls, and FAQs.
  headline: Create horizontal gradient java in PostScript using Aspose
  type: TechArticle
- questions:
  - answer: Aspose.Page for Java (includes Linear Gradient Paint Java).
    question: What library is required?
  - answer: About 10‑15 minutes for a basic horizontal gradient.
    question: How long does implementation take?
  - answer: A temporary or full license is required for production use.
    question: Do I need a license?
  - answer: Java 8 or newer.
    question: Which JDK version works?
  - answer: Yes – the same `LinearGradientPaint` instance can fill shapes and be applied
      to text strokes or fills.
    question: Can I use the gradient on both shapes and text?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page
- Java PostScript
title: Tworzenie poziomego gradientu Java w PostScript przy użyciu Aspose
url: /pl/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dodać poziomy gradient w Java PostScript przy użyciu Linear Gradient Paint

## Wprowadzenie
W tym obszernej samouczku nauczysz się **jak tworzyć poziomy gradient w Java** w dokumencie PostScript przy użyciu klasy **Linear Gradient Paint Java**, która jest dostarczana z Aspose.Page for Java. Przejdziemy przez każdy krok — od skonfigurowania projektu po renderowanie gradientu na kształtach i tekście — abyś mógł w kilka minut uzyskać dopracowaną grafikę gotową do druku. Niezależnie od tego, czy tworzysz silnik raportowy, narzędzie do automatyzacji projektowania, czy własny sterownik drukarki, ten przewodnik dostarcza dokładny kod, którego potrzebujesz.

## Szybkie odpowiedzi
- **Jakiej biblioteki wymaga?** Aspose.Page for Java (zawiera Linear Gradient Paint Java).  
- **Jak długo trwa implementacja?** Około 10‑15 minut dla podstawowego poziomego gradientu.  
- **Czy potrzebna jest licencja?** Wymagana jest tymczasowa lub pełna licencja do użytku produkcyjnego.  
- **Która wersja JDK działa?** Java 8 lub nowsza.  
- **Czy mogę używać gradientu zarówno na kształtach, jak i tekście?** Tak — ta sama instancja `LinearGradientPaint` może wypełniać kształty oraz być stosowana do obrysów lub wypełnień tekstu.

## Czym jest poziomy gradient i dlaczego go używać?
Poziomy gradient miesza kolory od lewej krawędzi obiektu do jego prawej krawędzi, tworząc płynne przejście, które dodaje głębi i atrakcyjności wizualnej. Jest idealny dla nowoczesnych komponentów UI, wyróżnionych nagłówków lub subtelnych cieniowań tła w raportach PDF lub PostScript. Korzystanie z **Linear Gradient Paint Java** pozwala precyzyjnie kontrolować kolory początkowe i końcowe, przezroczystość oraz skalowanie, zapewniając ostry wygląd na każdym urządzeniu lub drukarce.

## Wymagania wstępne
Zanim zagłębisz się w kod, upewnij się, że masz następujące elementy:

- Zainstalowany Java Development Kit (JDK) na komputerze.  
- Biblioteka Aspose.Page for Java. Możesz ją pobrać z [dokumentacji Aspose.Page Java](https://reference.aspose.com/page/java/).

## Importowanie pakietów
Rozpocznij od zaimportowania niezbędnych pakietów w swoim projekcie Java. Te importy zapewniają dostęp do prymitywów graficznych, obsługi gradientów oraz API Aspose.Page.

Klasa `PsDocument` reprezentuje dokument PostScript, na którym możesz rysować grafikę.  

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

## Krok 1: utwórz prostokąt
Najpierw skonfiguruj strumień wyjściowy, dokument oraz prostokąt, który będzie zawierał gradient.

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

## Krok 2: utwórz poziomy gradient liniowy
`LinearGradientPaint` jest podstawową klasą definiującą liniowe przejście kolorów.  
Klasa `LinearGradientPaint` reprezentuje obiekt malujący, który renderuje gradient wzdłuż prostej linii; określasz punkty początkowy i końcowy, przystanki kolorów oraz opcjonalny `AffineTransform`, aby skalować go do swojego kształtu.

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

## Krok 3: wypełnij prostokąt
Teraz wypełnij prostokąt gradientem, który właśnie zdefiniowaliśmy.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Krok 4: wypełnij tekst gradientem
Możesz także zastosować ten sam gradient do tekstu, tworząc efektowne wrażenie wizualne.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Krok 5: obrysuj tekst gradientem
Na koniec obrysuj tekst, używając gradientu jako koloru obrysu.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Typowe problemy i rozwiązania
| Problem | Dlaczego się pojawia | Rozwiązanie |
|---------|----------------------|-------------|
| Gradient jest rozciągnięty | Nieprawidłowe skalowanie `AffineTransform` | Upewnij się, że szerokość i wysokość transformacji odpowiadają wymiarom prostokąta (200 × 100 w przykładzie). |
| Kolory wyglądają na wyblakłe | Wartości alfa ustawione zbyt nisko | Zwiększ komponent alfa (czwartą wartość w `new Color(r,g,b,alpha)`). |
| Tekst jest niewidoczny | Nie ustawiono farby przed rysowaniem tekstu | Wywołaj `document.setPaint(paint)` **przed** jakimikolwiek wywołaniami `fillAndStrokeText` lub `outlineText`. |

## Najczęściej zadawane pytania
**Q:** Czy mogę używać Aspose.Page for Java w projektach komercyjnych?  
**A:** Tak, Aspose.Page for Java może być używany w projektach komercyjnych. Szczegóły licencjonowania znajdziesz na stronie [Aspose.Purchase](https://purchase.aspose.com/buy).

**Q:** Czy dostępna jest darmowa wersja próbna?  
**A:** Tak, możesz uzyskać dostęp do darmowej wersji próbnej Aspose.Page for Java na stronie [Aspose.Page for Java free trial](https://releases.aspose.com/).

**Q:** Gdzie mogę znaleźć dodatkową dokumentację i wsparcie?  
**A:** Odwiedź [dokumentację Aspose.Page Java](https://reference.aspose.com/page/java/) po kompleksowe zasoby. Po pomoc społeczności, sprawdź [forum Aspose.Page](https://forum.aspose.com/c/page/39).

**Q:** Jak mogę uzyskać tymczasową licencję?  
**A:** Możesz uzyskać tymczasową licencję na stronie [Aspose.Purchase temporary license page](https://purchase.aspose.com/temporary-license/).

**Q:** Jakie są wymagania systemowe dla Aspose.Page for Java?  
**A:** Zapoznaj się z [dokumentacją Aspose.Page Java](https://reference.aspose.com/page/java/) po szczegółowe wymagania systemowe.

---

**Ostatnia aktualizacja:** 2026-09-04  
**Testowano z:** Aspose.Page for Java 24.11  
**Autor:** Aspose

## Powiązane samouczki

- [Utwórz gradient PostScript w Java — Dodaj pionowy gradient](/page/java/postscript-gradient-addition/vertical/)
- [Jak dodać gradient: Diagonalny gradient w Java PostScript przy użyciu Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Utwórz gradient PostScript — Gradient radialny w Java](/page/java/postscript-gradient-addition/radial1/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}