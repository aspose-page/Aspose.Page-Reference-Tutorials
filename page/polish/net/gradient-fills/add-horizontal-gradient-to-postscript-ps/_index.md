---
date: 2026-02-25
description: Ulepsz dokumenty PostScript, dodając prostokąt z gradientem liniowym
  przy użyciu Aspose.Page dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po
  kroku, aby poznać wypełnianie tekstu gradientem oraz konturowanie tekstu gradientem.
linktitle: Add Horizontal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Dodaj prostokąt z gradientem liniowym do PostScript (PS) przy użyciu Aspose.Page
url: /pl/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj prostokąt z gradientem liniowym do PostScript (PS) przy użyciu Aspose.Page

## Wprowadzenie

Witamy w tym kompleksowym samouczku dotyczącym dodawania **linear gradient rectangle** do dokumentów PostScript (PS) przy użyciu Aspose.Page dla .NET. Aspose.Page to potężna biblioteka, która umożliwia tworzenie, modyfikowanie i renderowanie dokumentów w różnych formatach, a dzisiaj skupimy się na tym, jak wprowadzić przyciągające wzrok gradienty do plików PS.

### Szybkie odpowiedzi
- **Co robi linear gradient rectangle?** Wypełnia prostokątny obszar płynną przejściową zmianą koloru od jednej krawędzi do drugiej.  
- **Które API obsługuje wypełnianie gradientem tekstu?** `LinearGradientBrush` w połączeniu z `SetPaint` i `FillAndStrokeText`.  
- **Czy mogę obrysować tekst gradientem?** Tak — użyj `SetStroke` z pędzlem gradientowym i wywołaj `OutlineText`.  
- **Czy potrzebna jest licencja do produkcji?** Wymagana jest komercyjna licencja Aspose.Page do użytku nie‑ewaluacyjnego.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Wymagania wstępne

- Biblioteka Aspose.Page dla .NET: Upewnij się, że biblioteka jest odwołana w Twoim projekcie. Możesz ją pobrać z [dokumentacji Aspose.Page dla .NET](https://reference.aspose.com/page/net/).
- Katalog dokumentów: Utwórz folder na dysku, w którym zostanie zapisany wygenerowany plik PS i zamień **„Your Document Directory”** w kodzie na tę ścieżkę.

## Importowanie przestrzeni nazw

Aby rozpocząć, zaimportuj przestrzenie nazw, które dają dostęp do klas rysowania i specyficznych dla PS:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Czym jest linear gradient rectangle?

**linear gradient rectangle** to po prostu prostokątny kształt, którego wnętrze jest pomalowane gradientem liniowym — kolory przechodzą płynnie wzdłuż prostej linii, zazwyczaj od lewej do prawej (poziomo) lub od góry do dołu (pionowo). W Aspose.Page osiąga się to, łącząc `GraphicsPath` definiujący prostokąt z `LinearGradientBrush` opisującym przejście kolorów.

## Dlaczego używać wypełniania gradientem tekstu i gradientu obrysu tekstu?

- **Atrakcyjny wygląd:** Tekst wypełniony gradientem dodaje głębi i nowoczesnego stylu raportom, fakturom lub materiałom promocyjnym.  
- **Spójność marki:** Dopasuj kolory firmowe przy użyciu precyzyjnych wartości ARGB.  
- **Wszechstronność:** Ten sam pędzel może być ponownie użyty do wypełniania kształtów, wypełniania tekstu i gradientów obrysu, co zmniejsza duplikację kodu.

## Krok 1: Konfiguracja dokumentu

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## Krok 2: Definiowanie prostokąta gradientowego i kolorów

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // Create graphics path from the first rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    // Create linear gradient brush with rectangle as bounds, start, and end colors
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## Krok 3: Ustawienie transformacji dla pędzla

```csharp
    // Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    // Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Set transform
    brush.Transform = brushTransform;
```

## Krok 4: Ustawienie farby i wypełnienie prostokąta

```csharp
    // Set paint
    document.SetPaint(brush);

    // Fill the rectangle
    document.Fill(path);
```

## Jak zastosować wypełnianie gradientem tekstu

```csharp
    // Fill text with gradient
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## Używanie gradientu obrysu tekstu

```csharp
    // Set current stroke
    document.SetStroke(new Pen(brush, 5));
    // Outline text with gradient
    document.OutlineText("ABC", font, 200, 400);
```

## Krok 7: Zamknięcie bieżącej strony i zapisanie dokumentu

```csharp
    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Gratulacje! Pomyślnie dodałeś **linear gradient rectangle** do dokumentu PostScript i użyłeś tego samego pędzla do **gradientowego wypełnienia tekstu** oraz **gradientowego obrysu tekstu**.

## Typowe przypadki użycia i wskazówki

- **Nagłówki raportów:** Wypełnij duże bloki tekstu gradientami, aby podkreślić tytuły sekcji.  
- **Logotypy marki:** Odtwórz kształty logo przy użyciu gradientowych wypełnień dla spójnej identyfikacji wizualnej.  
- **Wskazówka:** Ponownie używaj tej samej instancji `LinearGradientBrush` w wielu wywołaniach rysowania, aby kolory były idealnie wyrównane pomiędzy kształtami i tekstem.

## Najczęściej zadawane pytania

### Q1: Czy mogę zastosować gradienty do innych kształtów niż prostokąty?

**A:** Tak, możesz zastosować gradienty do dowolnego kształtu zdefiniowanego przez `GraphicsPath`. Po prostu dodaj koła, wielokąty lub własne ścieżki przed wywołaniem `document.Fill(path)`.

### Q2: Jak mogę zmienić kolory gradientu?

**A:** Zmodyfikuj wartości `Color.FromArgb` przy tworzeniu `LinearGradientBrush`. Pierwszy kolor to początek, drugi to koniec gradientu.

### Q3: Czy Aspose.Page jest kompatybilny z różnymi formatami dokumentów?

**A:** Zdecydowanie. Aspose.Page obsługuje XPS, PS, PDF oraz kilka innych formatów wektorowych. Sprawdź oficjalną dokumentację, aby zobaczyć pełną listę.

### Q4: Czy mogę używać Aspose.Page w projektach komercyjnych?

**A:** Tak, dostępna jest licencja komercyjna. Zobacz stronę zakupu po szczegóły: [here](https://purchase.aspose.com/buy).

### Q5: Gdzie mogę znaleźć wsparcie społeczności?

**A:** Dołącz do forum społeczności Aspose.Page: [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

---

**Ostatnia aktualizacja:** 2026-02-25  
**Testowano z:** Aspose.Page 24.10 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}