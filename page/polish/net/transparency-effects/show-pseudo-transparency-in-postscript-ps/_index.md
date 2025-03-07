---
title: Pokaż pseudoprzezroczystość w PostScript (PS) za pomocą Aspose.Page
linktitle: Pokaż pseudoprzezroczystość w PostScript (PS)
second_title: Aspose.Page API .NET
description: Odkryj moc pseudoprzezroczystości w PostScript dzięki Aspose.Page dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby uzyskać oszałamiające wizualnie dokumenty.
weight: 13
url: /pl/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pokaż pseudoprzezroczystość w PostScript (PS) za pomocą Aspose.Page

## Wstęp

Czy chcesz poprawić atrakcyjność wizualną dokumentów PostScript (PS) poprzez dodanie pseudoprzezroczystości? Aspose.Page dla .NET zapewnia potężne rozwiązanie umożliwiające osiągnięcie tego efektu bez wysiłku. W tym samouczku krok po kroku przeprowadzimy Cię przez proces pokazywania pseudoprzezroczystości w PostScript za pomocą Aspose.Page.

## Warunki wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

- Aspose.Page dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Page dla .NET. Można go pobrać z[Dokumentacja Aspose.Page](https://reference.aspose.com/page/net/).

- Katalog dokumentów: skonfiguruj katalog do przechowywania dokumentów PostScript.

Teraz, gdy masz już niezbędne narzędzia w swoim arsenale, przyjrzyjmy się, jak zaprezentować pseudoprzezroczystość w PostScript za pomocą Aspose.Page.

## Importuj przestrzenie nazw

Zanim zagłębisz się w przykład, upewnij się, że zaimportowałeś wymagane przestrzenie nazw:

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
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//Twórz opcje zapisywania w formacie A4
	PsSaveOptions options = new PsSaveOptions();

	// Utwórz nowy 1-stronicowy dokument PS
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Krok 2: Utwórz prostokąt z nieprzezroczystym wypełnieniem gradientowym

```csharp
	float offsetX = 50;
	float offsetY = 100;
	float width = 200;
	float height = 100;

	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	LinearGradientBrush opaqueBrush = new LinearGradientBrush(new RectangleF(0, 0, 200, 100), Color.FromArgb(0, 0, 0),
		Color.FromArgb(40, 128, 70), 0f);
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	opaqueBrush.Transform = brushTransform;
	Aspose.Page.EPS.GradientBrush gradientBrush = new GradientBrush(opaqueBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Krok 3: Utwórz prostokąt z przezroczystym wypełnieniem gradientowym

```csharp
	offsetX = 350;

	//Utwórz ścieżkę graficzną z pierwszego prostokąta
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Twórz kolory pędzli z gradientem liniowym, których przezroczystość nie wynosi 255, ale 150 i 50. Są więc półprzezroczyste.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Krok 4: Zamknij bieżącą stronę i zapisz dokument

```csharp
	document.ClosePage();
	document.Save();
}
// RozwińKoniec:1
```

Wykonując poniższe kroki, możesz bezproblemowo zintegrować pseudoprzezroczystość z dokumentami PostScript za pomocą Aspose.Page dla .NET.

## Wniosek

Podsumowując, Aspose.Page dla .NET oferuje prosty i skuteczny sposób na ulepszenie elementów wizualnych dokumentów PostScript. Kroki opisane powyżej zapewniają jasną ścieżkę do zastosowania pseudoprzezroczystości, umożliwiając tworzenie oszałamiających wizualnie wyników.

## Często zadawane pytania

### P1: Czy Aspose.Page jest kompatybilny ze wszystkimi wersjami .NET?

O1: Aspose.Page dla .NET jest kompatybilny z różnymi wersjami frameworku .NET, zapewniając elastyczność i łatwość integracji.

### P2: Czy mogę zastosować pseudoprzezroczystość do innych kształtów oprócz prostokątów?

Odpowiedź 2: Tak, te same zasady można zastosować do innych kształtów, odpowiednio dostosowując GraphicsPath.

### P3: Gdzie mogę znaleźć dodatkowe przykłady i dokumentację?

 A3: Poznaj[Dokumentacja Aspose.Page](https://reference.aspose.com/page/net/) obszerne przykłady i szczegółową dokumentację.

### P4: Czy dostępna jest bezpłatna wersja próbna Aspose.Page?

 A4: Tak, możesz uzyskać dostęp do bezpłatnej wersji próbnej Aspose.Page z[ten link](https://releases.aspose.com/).

### P5: Jak mogę uzyskać tymczasową licencję na Aspose.Page?

 A5: Odwiedź[ten link](https://purchase.aspose.com/temporary-license/) aby uzyskać tymczasową licencję na Aspose.Page.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
