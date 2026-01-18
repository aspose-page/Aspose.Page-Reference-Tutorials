---
date: 2026-01-18
description: Dowiedz się, jak tworzyć dokumenty PostScript w .NET i dodawać prostokąty
  przy użyciu Aspose.Page dla .NET. Przewodnik krok po kroku z przykładami kodu.
linktitle: Add Rectangle to PostScript (PS)
second_title: Aspose.Page .NET API
title: Utwórz dokument PostScript w .NET – Dodaj prostokąt przy użyciu Aspose.Page
url: /pl/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj prostokąt do PostScript (PS) z Aspose.Page dla .NET

## Wprowadzenie

Jeśli chcesz **tworzyć dokument postscript w .net**, Aspose.Page zapewnia potężne rozwiązanie do obsługi plików PostScript. W tym samouczku pokażemy, jak dodać prostokąty do dokumentu PostScript przy użyciu Aspose.Page dla .NET, dając solidne podstawy do generowania bardziej zaawansowanej grafiki.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebuję?** Aspose.Page dla .NET.  
- **Czy mogę utworzyć dokument PostScript od podstaw?** Tak – API pozwala programowo budować pliki PS.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna wystarczy do testów; licencja jest wymagana w produkcji.  
- **Jak długo trwa implementacja?** Zazwyczaj mniej niż 10 minut dla podstawowych kształtów.

## Co to jest tworzenie dokumentu postscript w .net?
Tworzenie dokumentu PostScript w .NET oznacza programowe generowanie pliku .ps, który opisuje zawartość strony — tekst, grafikę lub kształty — przy użyciu API Aspose.Page. Takie podejście jest idealne do generowania grafiki po stronie serwera, automatycznego tworzenia raportów lub wszelkich scenariuszy, w których potrzebna jest precyzyjna kontrola nad formatem wyjściowym.

## Dlaczego warto używać Aspose.Page dla .NET?
- **Pełna kontrola nad grafiką** – rysuj kształty, ustawiaj kolory i stosuj obrysy bez konieczności pracy z niskopoziomową składnią PS.  
- **Cross‑platform** – działa w środowiskach Windows, Linux i macOS.  
- **Brak zewnętrznych zależności** – biblioteka samodzielnie generuje PS.  
- **Bogata dokumentacja i przykłady** – szybki start.

## Wymagania wstępne

- **Aspose.Page dla .NET** – pobierz i zainstaluj z [tutaj](https://releases.aspose.com/page/net/).  
- **Środowisko programistyczne** – Visual Studio, VS Code lub dowolne IDE zgodne z .NET.

## Importowanie przestrzeni nazw

Przed rozpoczęciem kodowania zaimportuj przestrzenie nazw, które udostępniają potrzebne klasy:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Teraz podzielmy przykład na przejrzyste, numerowane kroki.

## Krok 1: Ustaw katalog dokumentu

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Zastąp `"Your Document Directory"` folderem, w którym ma zostać zapisany wynikowy plik PS.

## Krok 2: Utwórz strumień wyjściowy dla dokumentu PostScript

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Ten strumień wskazuje na **AddRectangle_outPS.ps**. Możesz zmienić nazwę pliku lub lokalizację wedle potrzeb.

## Krok 3: Ustaw opcje zapisu i utwórz dokument PS

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Tutaj informujemy Aspose.Page, aby użył rozmiaru strony A4 i stworzył dokument jednopostaciowy.

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

Definiujemy prostokąt w punkcie (250, 100) o szerokości 150 i wysokości 100, ustawiamy pomarańczowy pędzel i wypełniamy kształt.

## Krok 5: Dodaj prostokąt z obrysem

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

Drugi prostokąt tworzony jest niżej na stronie, tym razem z czerwonym obrysem o grubości 3 punktów.

## Krok 6: Zamknij stronę i zapisz dokument

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Zamknięcie strony finalizuje rysowanie, a metoda `Save()` zapisuje plik PS na dysku.

## Typowe problemy i wskazówki

- **Nieprawidłowa ścieżka pliku** – Upewnij się, że `dataDir` kończy się separatorem ścieżki (`\\` lub `/`) lub użyj `Path.Combine`.  
- **Brak licencji** – W środowisku produkcyjnym zastosuj licencję Aspose przed utworzeniem dokumentu, aby uniknąć znaków wodnych wersji ewaluacyjnej.  
- **Widoczność koloru** – Jeśli prostokąt wydaje się pusty, sprawdź, czy kolory pędzla lub pióra kontrastują z tłem strony.

## Najczęściej zadawane pytania

**P:** Czy mogę dostosować kolory prostokątów?  
**O:** Oczywiście. Zmień wartości `Color.Orange` lub `Color.Red` w konstruktorach `SolidBrush` i `Pen` na dowolny `System.Drawing.Color`, który Ci odpowiada.

**P:** Czy Aspose.Page jest kompatybilny z innymi formatami dokumentów?  
**O:** Tak. Oprócz PostScript, Aspose.Page obsługuje także generowanie XPS i EPS.

**P:** Jak dodać tekst do tego samego dokumentu?  
**O:** Użyj klasy `TextFragment`, aby umieścić tekst w wybranych współrzędnych, a następnie wywołaj `document.Draw(textFragment)`.

**P:** Gdzie mogę znaleźć dodatkowe przykłady i pełną dokumentację API?  
**O:** Zapoznaj się z dokumentacją [tutaj](https://reference.aspose.com/page/net/) oraz dołącz do społeczności na [forum Aspose.Page](https://forum.aspose.com/c/page/39).

**P:** Czy mogę wypróbować Aspose.Page przed zakupem?  
**O:** Tak, pobierz darmową wersję próbną [tutaj](https://releases.aspose.com/). Do dłuższej oceny rozważ [tymczasową licencję](https://purchase.aspose.com/temporary-license/).

---

**Ostatnia aktualizacja:** 2026-01-18  
**Testowano z:** Aspose.Page 24.12 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}