---
title: Dodaj gradient ukośny do PostScriptu (PS) za pomocą Aspose.Page .NET
linktitle: Dodaj gradient ukośny do PostScriptu (PS)
second_title: Aspose.Page API .NET
description: Odkryj prostotę dodawania ukośnych gradientów do dokumentów PostScript w .NET za pomocą Aspose.Page. Podnieś poziom swoich projektów dzięki dynamicznym elementom wizualnym.
type: docs
weight: 10
url: /pl/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
---
## Wstęp

Dodanie ukośnego gradientu do dokumentu PostScript (PS) może zwiększyć atrakcyjność wizualną i kreatywność Twoich projektów. Aspose.Page dla .NET zapewnia płynne rozwiązanie do integracji tej funkcji z aplikacjami. W tym samouczku poprowadzimy Cię krok po kroku przez proces dodawania gradientu ukośnego do dokumentu PS za pomocą Aspose.Page.

## Warunki wstępne

Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

-  Biblioteka Aspose.Page dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Page dla .NET. Możesz go pobrać[Tutaj](https://releases.aspose.com/page/net/).

- Katalog dokumentów: skonfiguruj katalog dla swoich dokumentów, w którym zostanie zapisany wyjściowy plik PS.

Przejdźmy teraz do przewodnika krok po kroku.

## Importuj przestrzenie nazw

Po pierwsze, pamiętaj o zaimportowaniu niezbędnych przestrzeni nazw do swojego projektu. Te przestrzenie nazw są kluczowe dla pracy z funkcjonalnościami Aspose.Page.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Krok 1: Utwórz strumień wyjściowy dla dokumentu PostScript

```csharp
// ExStart:1
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";
//Utwórz strumień wyjściowy dla dokumentu PostScript
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## Krok 2: Utwórz opcje zapisu w formacie A4

```csharp
	//Twórz opcje zapisywania w formacie A4
	PsSaveOptions options = new PsSaveOptions();
```

## Krok 3: Utwórz nowy 1-stronicowy dokument PS

```csharp
	// Utwórz nowy 1-stronicowy dokument PS
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Krok 4: Zdefiniuj parametry prostokąta

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## Krok 5: Utwórz ścieżkę graficzną

```csharp
	//Utwórz ścieżkę graficzną z pierwszego prostokąta
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## Krok 6: Utwórz liniowy pędzel gradientowy

```csharp
	//Utwórz pędzel gradientu liniowego z prostokątem jako kolorami granic, początkowymi i końcowymi
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## Krok 7: Utwórz transformację dla pędzla

```csharp
	//Utwórz transformację dla pędzla. Składowa skali X i Y musi być równa odpowiednio szerokości i wysokości prostokąta.
	// Składniki translacji są przesunięciami prostokąta
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## Krok 8: Zastosuj transformacje do pędzla

```csharp
	//Obróć gradient, następnie przeskaluj i przesuń, aby uzyskać widoczne przejście kolorów w wymaganym prostokącie
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## Krok 9: Ustaw opcję Przekształć na Pędzel

```csharp
	//Ustaw transformację
	brush.Transform = brushTransform;
```

## Krok 10: Ustaw farbę i wypełnij prostokąt

```csharp
	//Ustaw farbę
	document.SetPaint(brush);

	//Wypełnij prostokąt
	document.Fill(path);
```

## Krok 11: Zamknij bieżącą stronę

```csharp
	//Zamknij bieżącą stronę
	document.ClosePage();
```

## Krok 12: Zapisz dokument

```csharp
	//Zapisz dokument
	document.Save();
}
// RozwińKoniec:1
```

Wykonując poniższe kroki, z powodzeniem dodasz ukośny gradient do dokumentu PostScript przy użyciu Aspose.Page dla .NET.

## Wniosek

Ulepszanie dokumentów PS za pomocą ukośnych gradientów może sprawić, że Twoje projekty będą atrakcyjne wizualnie i dynamiczne. Aspose.Page dla .NET upraszcza ten proces, umożliwiając programistom bezproblemową integrację tej funkcji ze swoimi aplikacjami.

## Często zadawane pytania

### P1: Czy Aspose.Page jest kompatybilny ze wszystkimi frameworkami .NET?

O1: Aspose.Page obsługuje różne platformy .NET, zapewniając kompatybilność z szeroką gamą środowisk programistycznych.

### P2: Czy mogę dostosować kolory gradientu w Aspose.Page?

Odpowiedź 2: Tak, Aspose.Page zapewnia elastyczność w wyborze i dostosowywaniu kolorów gradientu zgodnie z wymaganiami projektu.

### P3: Czy dostępna jest wersja próbna Aspose.Page?

 Odpowiedź 3: Tak, możesz poznać funkcje Aspose.Page, pobierając wersję próbną[Tutaj](https://releases.aspose.com/).

### P4: Jak mogę uzyskać tymczasową licencję na Aspose.Page?

 A4: Uzyskaj tymczasową licencję na Aspose.Page[Tutaj](https://purchase.aspose.com/temporary-license/) aby odblokować dodatkowe funkcje.

### P5: Gdzie mogę znaleźć wsparcie społeczności dla Aspose.Page?

 A5: Nawiąż kontakt ze społecznością Aspose.Page na stronie[forum](https://forum.aspose.com/c/page/39) za pomoc i dyskusję.