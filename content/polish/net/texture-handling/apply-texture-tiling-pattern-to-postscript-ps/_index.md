---
title: Zastosuj wzór kafelkowania tekstury do PostScript (PS) za pomocą Aspose.Page
linktitle: Zastosuj wzór kafelkowania tekstury do PostScriptu (PS)
second_title: Aspose.Page API .NET
description: Ulepsz swoje dokumenty PostScript (PS) za pomocą wzorów kafelków tekstur za pomocą Aspose.Page dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby uzyskać kreatywny akcent.
type: docs
weight: 10
url: /pl/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
---
## Wstęp

Witamy w tym samouczku krok po kroku dotyczącym stosowania wzoru kafelków tekstury do dokumentu PostScript (PS) za pomocą Aspose.Page dla .NET. Aspose.Page to potężna biblioteka, która pozwala pracować z różnymi formatami dokumentów. W tym samouczku przyjrzymy się, jak ulepszyć dokumenty PS, dodając wzory kafelków tekstur.

## Warunki wstępne

Zanim przejdziemy do samouczka, upewnij się, że posiadasz następujące elementy:

- [Studio wizualne](https://visualstudio.microsoft.com/) zainstalowany na Twojej maszynie.
- Podstawowa znajomość programowania w języku C#.
-  Pobierz i zainstaluj[Aspose.Page dla biblioteki .NET](https://releases.aspose.com/page/net/).
- Plik obrazu wzoru tekstury (np. „TestTexture.bmp”).

## Importuj przestrzenie nazw

Upewnij się, że w kodzie C# zaimportowałeś niezbędne przestrzenie nazw:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Podzielmy podany przykład na wiele kroków, aby poprowadzić Cię przez proces.

## Krok 1: Skonfiguruj katalog dokumentów

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";
```

Pamiętaj, aby zastąpić „Katalog Twoich dokumentów” ścieżką, w której chcesz zapisać dokument PS.

## Krok 2: Utwórz strumień wyjściowy dla dokumentu PS

```csharp
// Utwórz strumień wyjściowy dla dokumentu PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Twórz opcje zapisywania w formacie A4
    PsSaveOptions options = new PsSaveOptions();

    // Utwórz nowy 1-stronicowy dokument PS
    PsDocument document = new PsDocument(outPsStream, options, false);
```

W tym kroku konfigurowany jest strumień wyjściowy dokumentu PS, łącznie z definiowaniem rozmiaru dokumentu.

## Krok 3: Zastosuj wzór kafelków tekstury

```csharp
// Utwórz obiekt Bitmap z pliku obrazu
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Utwórz pędzel tekstury z obrazu
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    //Dodaj skalowanie w kierunku X do wzoru
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Ustaw ten pędzel tekstury jako bieżącą farbę
    document.SetPaint(brush);
}
```

Ten krok polega na utworzeniu pędzla tekstury z obrazu i ustawieniu go jako bieżącej farby dla dokumentu.

## Krok 4: Utwórz ścieżkę prostokątną i wypełnij

```csharp
// Utwórz ścieżkę prostokątną
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Wypełnij prostokąt
document.Fill(path);
```

Tutaj definiujemy prostokątną ścieżkę i wypełniamy ją wcześniej ustawionym pędzlem teksturowym.

## Krok 5: Ustaw obrys i rysuj

```csharp
// Kup aktualną farbę
Brush paint = document.GetPaint();

// Ustaw czerwony obrys
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Obrysuj prostokąt
document.Draw(path);
```

Ten krok polega na ustawieniu właściwości obrysu i narysowaniu zarysowanego prostokąta.

## Krok 6: Wypełnij i obrysuj tekst wzorem tekstury

```csharp
// Wypełnij tekst wzorem tekstury
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Zarys tekstu ze wzorem tekstury
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

Na koniec wypełniamy i obrysowujemy tekst wzorem tekstury, zwiększając atrakcyjność wizualną dokumentu.

## Krok 7: Zapisz i zamknij dokument

```csharp
// Zamknij bieżącą stronę
document.ClosePage();

// Zapisz dokument
document.Save();
```

Pamiętaj o zamknięciu bieżącej strony i zapisaniu dokumentu, aby zastosować zmiany.

## Wniosek

Gratulacje! Pomyślnie nauczyłeś się, jak zastosować wzór kafelkowania tekstury do dokumentu PostScript za pomocą Aspose.Page dla .NET. Eksperymentuj z różnymi obrazami i wzorami, aby jeszcze bardziej dostosować dokumenty PS.

## Często zadawane pytania

### P1: Czy mogę użyć innych formatów obrazu dla wzoru tekstury?

O1: Tak, Aspose.Page obsługuje różne formaty obrazów. Zapewnij zgodność z dokumentacją biblioteki.

### P2: Czy Aspose.Page jest kompatybilny z .NET Core?

O2: Tak, Aspose.Page jest kompatybilny zarówno z .NET Framework, jak i .NET Core.

### P3: Jak mogę dostosować rozmiar prostokąta z teksturą?

 A3: Zmień wymiary w pliku`RectangleF` parametry podczas tworzenia ścieżki.

### P4: Czy mogę dodać wiele wzorów tekstur do jednego dokumentu?

Odpowiedź 4: Tak, możesz powtórzyć proces z różnymi obrazami i ścieżkami.

### P5: Gdzie mogę znaleźć dodatkowe zasoby i wsparcie?

 A5: Odwiedź[Forum Aspose.Page](https://forum.aspose.com/c/page/39) o wsparcie społeczności i poznaj[dokumentacja](https://reference.aspose.com/page/net/).
