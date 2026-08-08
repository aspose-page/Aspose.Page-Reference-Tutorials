---
date: 2026-06-30
description: Dowiedz się, jak utworzyć dokument postscript .NET i dodać prostokąty
  przy użyciu Aspose.Page dla .NET. Przewodnik krok po kroku z przykładami kodu.
keywords:
- create postscript document .net
- how to generate postscript file
- Aspose.Page rectangle
linktitle: Dodaj prostokąt do PostScript (PS)
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create postscript document .net and add rectangles using
    Aspose.Page for .NET. Step‑by‑step guide with code samples.
  headline: Create PostScript Document .NET – Add Rectangle Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page for .NET.
    question: What library do I need?
  - answer: Yes – the API lets you build PS files programmatically.
    question: Can I create a PostScript document from scratch?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: Typically under 10 minutes for basic shapes.
    question: How long does the implementation take?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Utwórz dokument PostScript .NET – Dodaj prostokąt Aspose.Page
url: /pl/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj prostokąt do PostScript (PS) przy użyciu Aspose.Page dla .NET

## Wprowadzenie

Aspose.Page for .NET to biblioteka umożliwiająca programowe tworzenie i manipulację plikami PostScript, EPS i XPS. Jeśli chcesz **tworzenia dokumentu postscript .net**, ten samouczek przeprowadzi Cię przez dodawanie prostokątów do dokumentu PostScript przy użyciu Aspose.Page, dając solidne podstawy do generowania bardziej zaawansowanej grafiki.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebuję?** Aspose.Page for .NET.  
- **Czy mogę stworzyć dokument PostScript od podstaw?** Tak – API pozwala programowo tworzyć pliki PS.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna działa w testach; licencja jest wymagana w produkcji.  
- **Jak długo trwa implementacja?** Zazwyczaj poniżej 10 minut dla podstawowych kształtów.

## Co to jest tworzenie dokumentu postscript .net?

Tworzenie dokumentu PostScript w .NET oznacza programowe generowanie pliku `.ps`, który opisuje zawartość strony — tekst, grafikę lub kształty — przy użyciu API Aspose.Page. Takie podejście jest idealne do generowania grafiki po stronie serwera, automatycznego tworzenia raportów lub w każdym scenariuszu, w którym potrzebna jest precyzyjna kontrola nad formatem wyjściowym.

## Dlaczego warto używać Aspose.Page dla .NET?

Aspose.Page obsługuje **30+ prymitywów graficznych** i może generować pliki do **500 MB** bez ładowania całego dokumentu do pamięci, zapewniając wysokowydajne renderowanie na Windows, Linux i macOS. Daje pełną kontrolę nad kształtami, kolorami i obramowaniami, eliminując potrzebę pisania niskopoziomowego kodu PostScript.

- **Pełna kontrola nad grafiką** – rysuj kształty, ustawiaj kolory i stosuj obramowania bez konieczności zajmowania się niskopoziomową składnią PS.  
- **Wieloplatformowość** – działa w środowiskach Windows, Linux i macOS.  
- **Brak zewnętrznych zależności** – biblioteka obsługuje całe generowanie PS wewnętrznie.  
- **Bogata dokumentacja i przykłady** – szybko rozpocznij pracę.

## Wymagania wstępne

- **Biblioteka Aspose.Page dla .NET** – pobierz i zainstaluj z [tutaj](https://releases.aspose.com/page/net/).  
- **Środowisko programistyczne** – Visual Studio, VS Code lub dowolne IDE zgodne z .NET.

## Importowanie przestrzeni nazw

Przestrzeń nazw `Aspose.Page` udostępnia podstawowe klasy, których będziesz potrzebować, takie jak `Document`, `Page`, `SolidBrush` i `Pen`. Zaimportuj ją przed rozpoczęciem kodowania.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Teraz podzielmy przykład na jasne, numerowane kroki.

## Krok 1: Ustaw katalog dokumentu

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Zastąp `"Your Document Directory"` folderem, w którym chcesz zapisać wygenerowany plik PS.

## Krok 2: Utwórz strumień wyjściowy dla dokumentu PostScript

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Ten strumień wskazuje na **AddRectangle_outPS.ps**. Możesz dowolnie zmienić nazwę pliku lub lokalizację w razie potrzeby.

## Krok 3: Ustaw opcje zapisu i utwórz dokument PS

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Tutaj informujemy Aspose.Page, aby używał rozmiaru strony A4 i utworzył dokument jednopostaciowy.

## Krok 4: Dodaj wypełniony prostokąt

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

Definiujemy prostokąt w (250, 100) o szerokości 150 i wysokości 100, ustawiamy pomarańczowy pędzel i wypełniamy kształt.

## Krok 5: Dodaj prostokąt z obramowaniem

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

Drugi prostokąt jest tworzony niżej na stronie, tym razem z czerwonym obramowaniem o grubości 3 punktów.

## Krok 6: Zamknij stronę i zapisz dokument

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Zamknięcie strony finalizuje rysunek, a `Save()` zapisuje plik PS na dysku.

## Jak stworzyć dokument postscript .net?

`Document` jest główną klasą reprezentującą plik PostScript w Aspose.Page. `SaveOptions` określa ustawienia takie jak rozmiar strony i format wyjściowy dokumentu. Załaduj obiekt `Document`, skonfiguruj `SaveOptions` dla strony A4, rysuj kształty przy użyciu `SolidBrush` lub `Pen`, a następnie wywołaj `document.Save()` — cały przepływ wymaga tylko kilku linii kodu i działa na dowolnym obsługiwanym środowisku .NET. Ten wzorzec pozwala generować w pełni zgodne pliki PostScript bez konieczności ręcznego manipulowania surową składnią PS.

## Jak wygenerować plik postscript

Użyj klasy `SaveOptions` z Aspose.Page, aby określić format wyjściowy jako PostScript (`SaveFormat.PS`). Biblioteka przesyła zawartość bezpośrednio do pliku lub strumienia pamięci, umożliwiając efektywne generowanie dużych dokumentów bez nadmiernego zużycia pamięci.

## Typowe problemy i wskazówki

- **Nieprawidłowa ścieżka pliku** – Upewnij się, że `dataDir` kończy się separatorem ścieżki (`\\` lub `/`) lub użyj `Path.Combine`.  
- **Brak licencji** – W środowisku produkcyjnym zastosuj licencję Aspose przed tworzeniem dokumentu, aby uniknąć znaków wodnych wersji ewaluacyjnej.  
- **Widoczność koloru** – Jeśli prostokąt jest pusty, sprawdź, czy kolory pędzla lub pióra kontrastują z tłem strony.

## Najczęściej zadawane pytania

**Q:** Czy mogę dostosować kolory prostokątów?  
**A:** Oczywiście. Zmień wartości `Color.Orange` lub `Color.Red` w konstruktorach `SolidBrush` i `Pen` na dowolny `System.Drawing.Color`, który preferujesz.

**Q:** Czy Aspose.Page jest kompatybilny z innymi formatami dokumentów?  
**A:** Tak. Oprócz PostScript, Aspose.Page obsługuje także generowanie XPS i EPS.

**Q:** Jak mogę dodać tekst do tego samego dokumentu?  
**A:** Użyj klasy `TextFragment`, aby umieścić tekst w wybranych współrzędnych, a następnie wywołaj `document.Draw(textFragment)`.

**Q:** Gdzie mogę znaleźć dodatkowe przykłady i pełną referencję API?  
**A:** Przeglądaj dokumentację [tutaj](https://reference.aspose.com/page/net/) i dołącz do społeczności na [forum Aspose.Page](https://forum.aspose.com/c/page/39).

**Q:** Czy mogę wypróbować Aspose.Page przed zakupem?  
**A:** Tak, pobierz darmową wersję próbną [tutaj](https://releases.aspose.com/). Aby przedłużyć okres testowy, rozważ [tymczasową licencję](https://purchase.aspose.com/temporary-license/).

---

**Ostatnia aktualizacja:** 2026-06-30  
**Testowano z:** Aspose.Page 24.12 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Jak stworzyć dokument PostScript przy użyciu Aspose.Page dla .NET](/page/net/document-creation/create-postscript-document/)
- [Dodaj obraz do dokumentu PostScript (PS) przy użyciu Aspose.Page](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Dodaj tekst do dokumentu PostScript (PS) przy użyciu Aspose.Page](/page/net/text-manipulation/add-text-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}