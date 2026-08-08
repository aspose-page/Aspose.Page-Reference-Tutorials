---
date: 2026-06-30
description: Dowiedz się, jak tworzyć dokument XPS .NET i dodawać glify wypełnione
  obrazami lub obce obrazy przy użyciu Aspose.Page dla .NET w kilku prostych krokach.
keywords:
- create xps document .net
- image filled glyph
- foreign image
linktitle: Dodaj glif wypełniony obrazem i obcy obraz
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create XPS document .NET and add image‑filled glyphs or
    foreign images using Aspose.Page for .NET in a few easy steps.
  headline: Create XPS Document .NET – Add Image Filled Glyph & Foreign Image with
    Aspose.Page
  type: TechArticle
- questions:
  - answer: Over 25 image formats and the ability to process XPS files up to 500 MB
      without full memory loading.
    question: What does Aspose.Page support?
  - answer: 'Just two lines: create an `ImageBrush` and assign it to a `Glyph`.'
    question: How many lines of code to add an image‑filled glyph?
  - answer: Yes, a commercial license removes evaluation watermarks.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are compatible?
  - answer: Absolutely – you can import the font collection from the first document
      into the second.
    question: Can I reuse fonts from another XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Tworzenie dokumentu XPS .NET – Dodaj glif wypełniony obrazem i obcy obraz przy
  użyciu Aspose.Page
url: /pl/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz dokument XPS .NET – Dodaj glif wypełniony obrazem i obcy obraz przy użyciu Aspose.Page

## Wprowadzenie

W programowaniu .NET zadania **create XPS document .NET** są powszechne, gdy potrzebujesz grafik wysokiej jakości, niezależnych od rozdzielczości. Aspose.Page dla .NET ułatwia to i pozwala wzbogacić pliki XPS o glify wypełnione obrazami lub pobrać obrazy z innego dokumentu XPS. Po zakończeniu tego samouczka będziesz wiedział, jak utworzyć dwa dokumenty XPS, wypełnić glify obrazami i ponownie używać tych obrazów w różnych dokumentach — idealne do generowania faktur, certyfikatów lub wszelkich wizualnie bogatych wyjść.

## Szybkie odpowiedzi
- **Co obsługuje Aspose.Page?** Ponad 25 formatów obrazów oraz możliwość przetwarzania plików XPS do 500 MB bez pełnego ładowania do pamięci.  
- **Ile linii kodu potrzebnych jest do dodania glifu wypełnionego obrazem?** Tylko dwie linie: utwórz `ImageBrush` i przypisz go do `Glyph`.  
- **Czy potrzebna jest licencja do produkcji?** Tak, licencja komercyjna usuwa znaki wodne wersji ewaluacyjnej.  
- **Jakie wersje .NET są kompatybilne?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Czy mogę ponownie używać czcionek z innego XPS?** Oczywiście – możesz zaimportować kolekcję czcionek z pierwszego dokumentu do drugiego.

## Jak utworzyć dokument XPS przy użyciu Aspose.Page .NET?

Załaduj bibliotekę Aspose.Page, utwórz instancję `XpsDocument`, dodaj stronę i wywołaj `Save` – to pełny przepływ pracy w trzech zwięzłych instrukcjach. API automatycznie obsługuje rozmiar strony, DPI i zarządzanie zasobami, więc nie musisz samodzielnie zarządzać niskopoziomowymi strukturami XPS. To podejście skaluje się od jednostronicowych ulotek po katalogi liczące setki stron.

## Prerequisites

- **Aspose.Page for .NET** – pobierz go z [here](https://releases.aspose.com/page/net/).  
- **IDE .NET** – Visual Studio, Rider lub VS Code z rozszerzeniem C#.  
- **Folder na dokumenty** – będziemy odnosić się do niego jako **Your Document Directory** w fragmentach kodu.

## Importuj przestrzenie nazw

Przestrzeń nazw `Aspose.Page.XPS` dostarcza podstawowe klasy dokumentu XPS, natomiast `Aspose.Page.XPS.XpsModel` zawiera elementy modelu, takie jak glify i pędzle. Zaimportuj je na początku pliku:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Czym jest glif wypełniony obrazem?

Glif to wektorowy kształt, który może być renderowany przy użyciu jednolitego koloru, gradientu lub pędzla obrazu. Gdy zastosujesz `ImageBrush`, wnętrze glifu jest malowane dostarczonym obrazem, co umożliwia tworzenie złożonych efektów wizualnych bez rasteryzacji całej strony.

## Krok 1: Utwórz pierwszy dokument XPS

`XpsDocument` reprezentuje pakiet XPS i jest punktem wejścia do tworzenia i zapisywania plików XPS. Zacznij od utworzenia pierwszego dokumentu XPS, który będzie zawierał glify wypełnione obrazami.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

## Krok 2: Dodaj glify do pierwszego dokumentu

`XpsGlyphs` definiuje kolekcję glifów (znaków tekstowych), które można umieścić na stronie. Dodaj glify do pierwszego dokumentu, określając czcionkę, rozmiar, styl i pozycję.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## Krok 3: Wypełnij glify pędzlem obrazu

`ImageBrush` maluje obszar obrazem, umożliwiając wypełnianie kształtów wzorami lub zdjęciami. Wypełnij glify pędzlem obrazu, używając obrazu z katalogu danych.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## Krok 4: Utwórz drugi dokument XPS

`XpsDocument` służy do tworzenia nowego pliku XPS, który może zawierać strony, zasoby i treść. Teraz utwórz drugi dokument XPS, który będzie zawierał glify z pierwszego dokumentu.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

## Krok 5: Dodaj glify z czcionką z pierwszego dokumentu

`Font` reprezentuje krój pisma używany do renderowania tekstu w dokumencie XPS. Dodaj glify do drugiego dokumentu, używając czcionki wyodrębnionej z pierwszego dokumentu. Dzięki współdzieleniu kolekcji czcionek utrzymujesz mały rozmiar pliku i zapewniasz spójność wizualną.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## Krok 6: Utwórz pędzel obrazu z wypełnienia pierwszego dokumentu

`ImageBrush` może być utworzony z istniejącego wypełnienia, aby ponownie używać tego samego obrazu w różnych dokumentach. Utwórz pędzel obrazu z wypełnienia pierwszego dokumentu i użyj go do wypełnienia glifów w drugim dokumencie. Ta technika „obcego obrazu” pozwala ponownie wykorzystać grafikę bez duplikowania pliku źródłowego.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## Krok 7: Zapisz dokumenty

`Save` zapisuje pakiet XPS do pliku, osadzając wszystkie zasoby. Zapisz zarówno pierwszy, jak i drugi dokument XPS do folderu wyjściowego. Metoda `Save` zapisuje pakiet XPS, osadzając wszystkie zasoby i zachowując glify wypełnione obrazami.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Częste problemy i rozwiązania

| Problem | Dlaczego się pojawia | Rozwiązanie |
|---------|----------------------|-------------|
| **Obraz nie pojawia się wewnątrz glifu** | `ImageBrush` został utworzony z nieprawidłowym URI lub rozmiar obrazu przekracza granice glifu. | Zweryfikuj ścieżkę obrazu i opcjonalnie ustaw `ImageBrush.Stretch = Stretch.Uniform`. |
| **Brak czcionek w drugim dokumencie** | Zasoby czcionek nie zostały wyeksportowane z pierwszego XPS. | Użyj `firstDoc.Fonts.SaveTo(secondDoc.Fonts)` przed dodaniem glifów. |
| **Spowolnienie wydajności przy dużych plikach** | Ładowanie dużych obrazów do pamięci dla każdego glifu. | Ponownie użyj jednej instancji `ImageBrush` dla wszystkich glifów lub zmniejsz rozdzielczość obrazu przed użyciem. |

## Najczęściej zadawane pytania

### Q1: Czy mogę używać różnych formatów obrazów do wypełniania glifów?
A1: Tak, Aspose.Page obsługuje PNG, JPEG, BMP, GIF, TIFF i inne — ponad 25 formatów łącznie.

### Q2: Jak mogę dalej dostosować wygląd glifów?
A2: Zbadaj właściwości takie jak `Glyph.Stroke`, `Glyph.FillOpacity` i `Glyph.Transform`, aby dostosować kontury, przezroczystość i obrót.

### Q3: Czy Aspose.Page nadaje się do obsługi dużych zestawów dokumentów?
A3: Zdecydowanie. Biblioteka przetwarza wielostronicowe pliki XPS przy użyciu strumieniowania, utrzymując zużycie pamięci poniżej 100 MB nawet przy dokumentach liczących 500 stron.

### Q4: Czy mogę zastosować różne style do poszczególnych glifów?
A4: Tak, każda instancja `Glyph` ma własne właściwości `Fill`, `Stroke` i `Transform`, co umożliwia stylizację poszczególnych glifów.

### Q5: Jakie są korzyści z używania Aspose.Page w porównaniu z innymi narzędziami XPS?
A5: Aspose.Page obsługuje ponad 25 formatów obrazów, przetwarza pliki do 500 MB bez pełnego ładowania do pamięci i oferuje w 100 % natywny dla .NET interfejs API — eliminując potrzebę interfejsu COM lub zewnętrznych narzędzi.

---

**Ostatnia aktualizacja:** 2026-06-30  
**Testowano z:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Utwórz dokument XPS – Aspose.Page dla .NET](/page/net/document-creation/)
- [Dodaj obraz do dokumentu XPS przy użyciu Aspose.Page dla .NET](/page/net/image-management/add-image-to-xps-document/)
- [Dodaj klon glifu i zmień kolor przy użyciu Aspose.Page dla .NET](/page/net/cross-document-editing/add-glyph-clone-and-change-color/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}