---
date: 2026-01-07
description: Dowiedz się, jak tworzyć dokumenty XPS w .NET przy użyciu Aspose.Page.
  Ten przewodnik pokazuje, jak dodawać glify wypełnione obrazami oraz obrazy zewnętrzne,
  aby uzyskać bogatszą wizualizację dokumentu.
linktitle: Add Image Filled Glyph & Foreign Image
second_title: Aspose.Page .NET API
title: Utwórz dokument XPS w .NET przy użyciu Aspose.Page – glif wypełniony obrazem
  i obcy obraz
url: /pl/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz dokument XPS .NET przy użyciu Aspose.Page – Glyph wypełniony obrazem i obcy obraz

## Wprowadzenie

Jeśli potrzebujesz **tworzyć dokument XPS .NET** w aplikacjach, które wyglądają elegancko i profesjonalnie, Aspose.Page dostarcza narzędzia do osadzania obrazów bezpośrednio w glyphach oraz ponownego użycia zasobów graficznych w różnych dokumentach. W tym samouczku pokażemy, jak zbudować dwa pliki XPS, wypełnić glyphy pędzlem obrazu, a następnie ponownie użyć tego pędzla w drugim dokumencie. Po zakończeniu zrozumiesz, dlaczego takie podejście oszczędza pamięć, upraszcza stylizację i otwiera kreatywne możliwości dla raportów, faktur czy dowolnych treści do druku.

## Szybkie odpowiedzi
- **Co obejmuje ten samouczek?** Dodawanie glyphów wypełnionych obrazem i ponowne ich użycie w dokumentach XPS przy pomocy Aspose.Page dla .NET.  
- **Jakie główne słowo kluczowe jest celem?** `create xps document .net`.  
- **Wymagania wstępne?** Środowisko programistyczne .NET, Aspose.Page dla .NET oraz folder na pliki XPS.  
- **Jak długo trwa implementacja?** Około 10‑15 minut, aby uzyskać działający prototyp.  
- **Czy mogę używać innych formatów obrazów?** Tak – każdy format obsługiwany przez `System.Drawing.Image` w .NET.

## Wymagania wstępne

Przed przystąpieniem do kodu upewnij się, że masz przygotowane:

- **Aspose.Page for .NET** – pobierz najnowszą bibliotekę z [here](https://releases.aspose.com/page/net/).  
- **Środowisko programistyczne** – Visual Studio 2022 (lub dowolne IDE obsługujące .NET 6+).  
- **Katalog dokumentów** – utwórz folder na swoim komputerze, w którym będą przechowywane obrazy wejściowe oraz generowane pliki XPS; będziemy odnosić się do niego jako **Your Document Directory** w fragmentach kodu.

## Importowanie przestrzeni nazw

Rozpocznij od zaimportowania przestrzeni nazw niezbędnych do pracy z obiektami XPS i narzędziami rysowania.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Przewodnik krok po kroku

### Krok 1: Utwórz pierwszy dokument XPS

Zaczynamy od utworzenia pustego dokumentu XPS, który będzie zawierał glyph wypełniony obrazem.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

### Krok 2: Dodaj glyphy do pierwszego dokumentu

Następnie dodaj glyph (znak tekstowy), który później wypełnimy pędzlem obrazu.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Krok 3: Wypełnij glyphy pędzlem obrazu

Tutaj tworzymy `ImageBrush` z pliku TIFF znajdującego się w naszym katalogu danych i stosujemy go do glyphu. Pędzel jest ustawiony w tryb kafelkowania, więc obraz powtarza się, jeśli obszar glyphu przekracza rozmiar obrazu.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

### Krok 4: Utwórz drugi dokument XPS

Teraz tworzymy drugi dokument XPS, który ponownie wykorzysta styl glyphu i pędzel obrazu z pierwszego.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

### Krok 5: Dodaj glyphy z czcionką z pierwszego dokumentu

Dodajemy glyph do drugiego dokumentu, ponownie używając dokładnego obiektu czcionki z pierwszego dokumentu. Zapewnia to spójność wizualną obu plików.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

### Krok 6: Utwórz pędzel obrazu z wypełnienia pierwszego dokumentu

Zamiast ponownie ładować obraz, klonujemy pędzel z `glyphs1` i przypisujemy go do `glyphs2`. To pokazuje, jak można **create XPS document .NET** przepływy pracy, które efektywnie współdzielą zasoby.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

### Krok 7: Zapisz dokumenty

Na koniec zapisujemy oba pliki XPS na dysku. Teraz możesz otworzyć je w dowolnym przeglądarce XPS, aby zobaczyć efekt glyphu wypełnionego obrazem.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Dlaczego używać glyphów wypełnionych obrazem przy tworzeniu dokumentu XPS .NET?

- **Efekt wizualny** – Przekształć zwykły tekst w elementy bogate w grafikę bez rasteryzacji całej strony.  
- **Ponowne użycie zasobów** – Udostępniaj pędzle i czcionki w wielu dokumentach, zmniejszając zużycie pamięci.  
- **Elastyczność** – Kafelkowanie, rozciąganie lub obracanie pędzla obrazu, aby uzyskać własne wzory lub branding.

## Typowe problemy i wskazówki

- **Błędy ścieżki pliku** – Upewnij się, że `dataDir` kończy się separatorem ścieżki (`\` lub `/`) odpowiednim dla Twojego systemu operacyjnego.  
- **Nieobsługiwane formaty obrazów** – Aspose.Page najlepiej współpracuje z TIFF, PNG i JPEG. Przed użyciem skonwertuj inne formaty.  
- **TileMode nie zastosowano** – Upewnij się, że rzutujesz do `XpsImageBrush` przed ustawieniem `TileMode`; w przeciwnym razie właściwość jest ignorowana.

## Najczęściej zadawane pytania

### Q1: Czy mogę używać różnych formatów obrazów do wypełniania glyphów?

**A:** Tak, Aspose.Page obsługuje TIFF, PNG, JPEG, BMP i GIF. Wystarczy podać odpowiednie rozszerzenie pliku w wywołaniu `CreateImageBrush`.

### Q2: Jak mogę dalej dostosować wygląd glyphów?

**A:** Przeglądaj dodatkowe właściwości `XpsGlyphs`, takie jak `Opacity`, `RenderTransform` i `Stroke`, aby precyzyjnie dopasować renderowanie.

### Q3: Czy Aspose.Page nadaje się do obsługi dużych zestawów dokumentów?

**A:** Absolutnie. Biblioteka jest zoptymalizowana pod kątem wysokiej wydajności i może przetwarzać tysiące plików XPS w zadaniach wsadowych.

### Q4: Czy mogę zastosować różne style do poszczególnych glyphów?

**A:** Tak. Każda instancja `XpsGlyphs` może mieć własne wypełnienie, obrys i transformację, co daje szczegółową kontrolę.

### Q5: Jakie są korzyści z używania Aspose.Page w porównaniu z innymi narzędziami do przetwarzania dokumentów?

**A:** Aspose.Page oferuje kompletny, wolny od licencji interfejs API do tworzenia, modyfikacji i konwersji XPS, z obszerną dokumentacją i całodobowym wsparciem.

---

**Last Updated:** 2026-01-07  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}