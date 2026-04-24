---
date: 2026-01-05
description: Dowiedz się, jak dodać ścieżkę przycinania w PostScript przy użyciu Aspose.Page
  dla .NET – krok po kroku przewodnik z technikami ustawiania pędzla i rysowania przerywanego
  prostokąta.
linktitle: Clipping PS
second_title: Aspose.Page .NET API
title: Dodaj ścieżkę przycinania do PS przy użyciu Aspose.Page dla .NET
url: /pl/net/canvas-manipulation/clippingps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj ścieżkę przycinania do PS przy użyciu Aspose.Page dla .NET

## Wprowadzenie

W tym obszernej tutorialu dowiesz się, jak **dodać ścieżkę przycinania** do dokumentu PostScript (PS) przy użyciu Aspose.Page dla .NET. Przejdziemy krok po kroku, pokażemy, jak **ustawić pędzel malujący**, oraz zademonstrujemy, jak **narysować przerywany prostokąt** wokół przyciętej zawartości. Po zakończeniu będziesz mieć w pełni funkcjonalny plik PS, który ilustruje przycinanie za pomocą kształtu, czyniąc Twoje grafiki bardziej dynamicznymi i profesjonalnymi.

## Szybkie odpowiedzi
- **Co robi „add clipping path”?** Ogranicza operacje rysowania do określonego kształtu, ukrywając wszystko poza tym kształtem.  
- **Która biblioteka obsługuje przycinanie w .NET?** Aspose.Page dla .NET udostępnia bogate API do manipulacji PS/EPS.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa w trakcie rozwoju; licencja komercyjna jest wymagana w produkcji.  
- **Czy mogę zmienić kolor pędzla?** Tak, użyj `SetPaint` z dowolnym `SolidBrush` lub gradientem, który preferujesz.  
- **Czy rysowanie przerywanego prostokąta jest możliwe?** Oczywiście – utwórz `Pen` z `DashStyle.Dash` i użyj `Draw`.  

## Czym jest ścieżka przycinania w PostScript?
Ścieżka przycinania definiuje widoczny obszar kolejnych poleceń rysowania. Wszystko narysowane poza ścieżką jest ignorowane, co pozwala tworzyć złożone grafiki maskowane bez modyfikowania oryginalnej zawartości.

## Dlaczego używać Aspose.Page do przycinania?
- **Brak zewnętrznych zależności** – czysta biblioteka .NET.  
- **Pełna kontrola** nad stanem grafiki (save/restore, translate, rotate).  
- **Bogate prymitywy rysowania** takie jak `SetPaint`, `Clip` i `Draw` z konfigurowalnymi piórami i pędzlami.  

## Wymagania wstępne

- Podstawowa znajomość programowania w C#.  
- Biblioteka Aspose.Page dla .NET zainstalowana – możesz ją pobrać [tutaj](https://releases.aspose.com/page/net/).  
- Visual Studio lub dowolne preferowane środowisko IDE .NET.  

## Importowanie przestrzeni nazw

Najpierw zaimportuj przestrzenie nazw wymagane do manipulacji grafiką:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Teraz rozbijmy przykład na jasne, numerowane kroki.

### Krok 1: Ustaw katalog dokumentu

Zdefiniuj folder, w którym będą przechowywane Twoje pliki źródłowe i wyjściowe.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Krok 2: Utwórz strumień wyjściowy dla dokumentu PostScript

Utwórz zapisywalny strumień, który będzie przechowywał wygenerowany plik PS.

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

### Krok 3: Utwórz opcje zapisu

Zainicjuj `PsSaveOptions` z ustawieniami domyślnymi. W razie potrzeby możesz je później dostosować.

```csharp
// Create save options with default values
PsSaveOptions options = new PsSaveOptions();
```

### Krok 4: Utwórz nowy jednopostowy dokument PS

Zainicjuj obiekt `PsDocument`, który reprezentuje Twój plik PS.

```csharp
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Krok 5: Utwórz ścieżkę graficzną z prostokąta

Użyjemy prostokąta jako podstawowego kształtu, który później zostanie przycięty.

```csharp
// Create graphics path from the rectangle
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

### Krok 6: Przycinanie za pomocą kształtu

Tutaj **dodajemy ścieżkę przycinania** przy użyciu koła, **ustawiamy pędzel malujący** na niebieski i wypełniamy prostokąt w obrębie przyciętego regionu.

```csharp
// Save graphics state in order to return back to this state after transformation
document.WriteGraphicsSave();

// Displace current graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

// Create graphics path from the circle
GraphicsPath circlePath = new GraphicsPath();
circlePath.AddEllipse(new RectangleF(50, 0, 200, 200));

// Add clipping by circle to the current graphics state
document.Clip(circlePath);

// Set paint in the current graphics state
document.SetPaint(new SolidBrush(Color.Blue));

// Fill the rectangle in the current graphics state (with clipping)
document.Fill(rectanglePath);

// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

### Krok 7: Przemieszczenie wyższego poziomu stanu graficznego i narysowanie przerywanego prostokąta

Po przywróceniu poprzedniego stanu, ponownie przesuwamy kursor graficzny, **rysujemy przerywany prostokąt** i stosujemy niebieski obrys.

```csharp
// Displace upper-level graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// Draw the rectangle in the current graphics state (has no clipping) above the clipped rectangle
document.Draw(rectanglePath);
```

### Krok 8: Zamknij i zapisz dokument

Zakończ stronę i zapisz plik PS na dysku.

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Udało Ci się teraz pomyślnie **dodać ścieżkę przycinania**, ustawić własny pędzel malujący i narysować przerywany prostokąt wokół Twojej grafiki przy użyciu Aspose.Page dla .NET.

## Typowe problemy i rozwiązania

- **Przycinanie niewidoczne:** Upewnij się, że wywołujesz `WriteGraphicsSave()` przed translacją i `WriteGraphicsRestore()` po wypełnieniu.  
- **Nieprawidłowe kolory:** Sprawdź, czy `SetPaint` jest wywoływany po `Clip` i przed `Fill`.  
- **Linie przerywane wyglądają na ciągłe:** Upewnij się, że `DashStyle` pióra (`Pen`) jest ustawiony na `DashStyle.Dash` przed `SetStroke`.  

## Najczęściej zadawane pytania

### Q1: Czy mogę używać Aspose.Page dla .NET z innymi językami programowania?
A: Aspose.Page jest przede wszystkim przeznaczony dla aplikacji .NET. Jednak Aspose udostępnia podobne biblioteki dla innych języków programowania.

### Q2: Gdzie mogę znaleźć dodatkowe przykłady i dokumentację dla Aspose.Page dla .NET?
A: Więcej przykładów i szczegółową dokumentację możesz znaleźć w [dokumentacji Aspose.Page](https://reference.aspose.com/page/net/).

### Q3: Czy dostępna jest darmowa wersja próbna Aspose.Page dla .NET?
A: Tak, darmową wersję próbną Aspose.Page dla .NET możesz uzyskać [tutaj](https://releases.aspose.com/).

### Q4: Jak mogę uzyskać tymczasową licencję dla Aspose.Page dla .NET?
A: Tymczasową licencję możesz uzyskać [tutaj](https://purchase.aspose.com/temporary-license/).

### Q5: Gdzie mogę uzyskać wsparcie lub dyskutować o zapytaniach związanych z Aspose.Page?
A: Odwiedź [forum Aspose.Page](https://forum.aspose.com/c/page/39) w celu uzyskania wsparcia społeczności i dyskusji.

---

**Ostatnia aktualizacja:** 2026-01-05  
**Testowano z:** Aspose.Page 24.11 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}