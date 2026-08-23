---
date: 2026-03-26
description: Dowiedz się, jak tworzyć dokumenty PostScript w .NET z wzorami tekstur
  kafelkowych przy użyciu Aspose.Page. Skorzystaj z naszego przewodnika krok po kroku,
  aby dodać bogate tekstury do swoich plików PS.
linktitle: Create PostScript .NET document with texture tiling
second_title: Aspose.Page .NET API
title: Utwórz dokument PostScript .NET z kafelkowaniem tekstury
url: /pl/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz dokument PostScript .NET z wzorem tekstury

## Jak utworzyć dokument PostScript .NET z wzorem tekstury

W tym samouczku dowiesz się, jak **utworzyć dokument PostScript .NET** i wzbogacić go o wzór tekstury przy użyciu biblioteki Aspose.Page. Przejdziemy krok po kroku, od konfiguracji projektu po wypełnianie i obrysowywanie tekstu pędzlem tekstury, abyś mógł w kilka minut wygenerować atrakcyjne wizualnie pliki PS.

## Szybkie odpowiedzi
- **Jakiej biblioteki używać?** Aspose.Page for .NET  
- **Czy mogę używać .NET Core?** Tak, biblioteka obsługuje .NET Core oraz .NET 5/6  
- **Jakie formaty obrazów działają jako tekstura?** Każdy format obsługiwany przez System.Drawing (BMP, PNG, JPEG itp.)  
- **Jak długo trwa implementacja?** Około 10‑15 minut dla podstawowego przykładu  
- **Czy potrzebna jest licencja?** Bezpłatna wersja próbna wystarczy do testów; licencja jest wymagana w produkcji  

## Wymagania wstępne

- [Visual Studio](https://visualstudio.microsoft.com/) zainstalowane na komputerze.  
- Podstawowa znajomość programowania w C#.  
- Pobierz i zainstaluj [bibliotekę Aspose.Page for .NET](https://releases.aspose.com/page/net/).  
- Plik obrazu będący wzorem tekstury (np. **TestTexture.bmp**).

## Importowanie przestrzeni nazw

W swoim pliku C# zaimportuj wymagane przestrzenie nazw, aby kompilator wiedział, gdzie znaleźć używane typy:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Krok 1: Ustawienie katalogu dokumentu

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Zastąp **Your Document Directory** folderem, w którym ma zostać zapisany wygenerowany plik PS.

## Krok 2: Utworzenie strumienia wyjściowego dla dokumentu PS

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

Ten fragment otwiera strumień pliku, konfiguruje rozmiar strony (domyślnie A4) i tworzy nową instancję **PsDocument**, na której będziemy rysować.

## Krok 3: Zastosowanie wzoru tekstury

```csharp
// Create a Bitmap object from the image file
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Create texture brush from the image
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    // Add scaling in X direction to the pattern
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Set this texture brush as the current paint
    document.SetPaint(brush);
}
```

Tutaj wczytujemy bitmapę, opakowujemy ją w **TextureBrush**, opcjonalnie rozciągamy w poziomie i przekazujemy **PsDocument**, aby używał tego pędzla w kolejnych operacjach rysowania.

## Krok 4: Utworzenie ścieżki prostokąta i wypełnienie

```csharp
// Create rectangle path
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Fill rectangle
document.Fill(path);
```

Definiujemy prosty prostokąt i wypełniamy go wcześniej ustawionym pędzlem tekstury.

## Krok 5: Ustawienie obrysu i rysowanie

```csharp
// Get current paint
Brush paint = document.GetPaint();

// Set red stroke
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Stroke the rectangle
document.Draw(path);
```

Pobieramy bieżący pędzel (tekstura), tworzymy czerwony pióro dla obrysu i rysujemy krawędź prostokąta.

## Krok 6: Wypełnienie i obrysowanie tekstu wzorem tekstury

```csharp
// Fill text with texture pattern                
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Outline text with texture pattern
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

Ten krok demonstruje możliwość **wypełniania i obrysowywania tekstu**: znaki „ABC” są wypełnione pędzlem tekstury, a następnie obrysowane, co daje efektowny wygląd.

## Krok 7: Zapis i zamknięcie dokumentu

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Zamknięcie strony finalizuje polecenia rysowania, a `Save()` zapisuje plik PostScript na dysku.

## Typowe problemy i rozwiązania

- **Tekstura jest nieprawidłowo rozciągnięta** – Dostosuj wartości `Matrix`, aby kontrolować skalowanie w kierunkach X/Y.  
- **Nie znaleziono obrazu** – Upewnij się, że `dataDir` wskazuje na właściwy folder i że nazwa pliku jest dokładnie taka sama, łącznie z wielkością liter.  
- **Kolory wyglądają inaczej** – Pamiętaj, że PostScript używa przestrzeni kolorów niezależnej od urządzenia; zapewnij, że używasz obiektów `Color`, które są prawidłowo mapowane.

## Najczęściej zadawane pytania

**P:** Czy mogę używać innych formatów obrazów jako wzoru tekstury?  
**O:** Tak, każdy format obsługiwany przez `System.Drawing.Bitmap` (BMP, PNG, JPEG, GIF itp.) działa.

**P:** Czy Aspose.Page jest kompatybilny z .NET Core?  
**O:** Oczywiście. Biblioteka działa na .NET Framework, .NET Core oraz .NET 5/6.

**P:** Jak zmienić rozmiar prostokąta z teksturą?  
**O:** Zmodyfikuj wartości `RectangleF` w kroku tworzenia prostokąta (np. `new RectangleF(0, 0, 300, 150)`).

**P:** Czy mogę zastosować wiele wzorów tekstury w jednym dokumencie?  
**O:** Tak. Po prostu utwórz nowy `TextureBrush` z innym obrazem i wywołaj ponownie `SetPaint` przed rysowaniem kolejnego kształtu lub tekstu.

**P:** Gdzie mogę znaleźć więcej przykładów i dokumentację API?  
**O:** Odwiedź [Aspose.Page Forum](https://forum.aspose.com/c/page/39) po pomoc społeczności oraz oficjalną [dokumentację](https://reference.aspose.com/page/net/) po szczegółowy opis API.

## Podsumowanie

Teraz wiesz, jak **utworzyć dokument PostScript .NET** i zastosować w nim wzór tekstury, w tym jak **wypełniać i obrysowywać tekst** tą teksturą. Eksperymentuj z różnymi obrazami, macierzami skalowania i prymitywami rysowania, aby tworzyć własne, stylizowane pliki PS do raportów, ulotek lub innych graficznych wyjść.

---

**Ostatnia aktualizacja:** 2026-03-26  
**Testowane z:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}