---
date: 2026-03-29
description: Dowiedz się, jak używać pędzla liniowego gradientu w C# do tworzenia
  pseudo‑przezroczystości w PostScript przy użyciu Aspose.Page dla .NET.
linktitle: Show Pseudo-Transparency in PostScript (PS)
second_title: Aspose.Page .NET API
title: Pędzel liniowego gradientu C# do pseudo‑przezroczystości w PS
url: /pl/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pędzel gradientu liniowego C# dla pseudo‑przezroczystości w PostScript (PS)

## Wprowadzenie

Jeśli potrzebujesz dodać subtelną efekt przezroczystości do swoich plików PostScript (PS), **linear gradient brush C#** jest idealnym narzędziem. Aspose.Page for .NET ułatwia malowanie prostokątów zarówno z nieprzezroczystymi, jak i przezroczystymi wypełnieniami gradientowymi, nadając dokumentom nowoczesny, warstwowy wygląd. W tym samouczku przeprowadzimy Cię krok po kroku przez proces tworzenia pseudo‑przezroczystości przy użyciu pędzla gradientu liniowego w C#.

## Szybkie odpowiedzi
- **Jaką bibliotekę zapewnia pędzel gradientu liniowego?** Aspose.Page for .NET
- **Która klasa graficzna tworzy gradient?** `LinearGradientBrush`
- **Czy mogę kontrolować krycie dla każdego koloru?** Tak, używając `Color.FromArgb(alpha, …)`
- **Czy potrzebna jest licencja do produkcji?** Wymagana jest ważna licencja Aspose.Page
- **Obsługiwane wersje .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## Czym jest pędzel gradientu liniowego C#?

`LinearGradientBrush` to obiekt GDI+, który rysuje płynne przejście między dwoma kolorami wzdłuż prostej linii. Gdy określisz kanał alfa (0‑255) dla każdego koloru, możesz tworzyć przezroczyste gradienty — dokładnie tego potrzebujemy do pseudo‑przezroczystości w PostScript.

## Dlaczego używać pędzla gradientu liniowego C# do pseudo‑przezroczystości?

- **Precyzyjna kontrola krycia:** Dostosuj wartość alfa każdego koloru, aby uzyskać pożądany poziom przezroczystości.  
- **Renderowanie niezależne od urządzenia:** Pędzel działa tak samo na ekranie, w PDF, EPS i wyjściach PS.  
- **Proste API:** Kilka linii kodu C# generuje efekty wizualne klasy profesjonalnej jakości.

## Wymagania wstępne

Zanim zanurzysz się w kod, upewnij się, że masz:

- Aspose.Page for .NET zainstalowane. Możesz je pobrać z [Aspose.Page documentation](https://reference.aspose.com/page/net/).
- Folder, do którego można zapisywać, w którym zostanie zapisany wygenerowany dokument PostScript.

Teraz, gdy masz niezbędne narzędzia, rozpocznijmy budowanie pseudo‑przezroczystych prostokątów.

## Importowanie przestrzeni nazw

Zanim zaczniemy, zaimportuj przestrzenie nazw, które zawierają klasy, których będziemy używać:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Krok 1: Utwórz strumień wyjściowy dla dokumentu PostScript

Zaczynamy od utworzenia strumienia pliku, który będzie przechowywał wynikowy plik PS, a następnie inicjalizujemy `PsDocument`.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();

	// Create new 1‑paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Krok 2: Utwórz prostokąt z **nieprzezroczystym** wypełnieniem gradientowym

Tutaj budujemy `LinearGradientBrush`, którego kolory są w pełni nieprzezroczyste (alpha = 255). Ten prostokąt posłuży jako warstwa tła.

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

## Krok 3: Utwórz prostokąt z **przezroczystym** wypełnieniem gradientowym

Teraz używamy **linear gradient brush C#**, w którym wartości alfa są mniejsze niż 255 (np. 150 i 50). Dzięki temu prostokąt jest częściowo przezroczysty, co osiąga efekt pseudo‑przezroczystości.

```csharp
	offsetX = 350;

	//Create graphics path from the first rectangle
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Create linear gradient brush colors which transparency are not 255, but 150 and 50. So it are translucent.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Krok 4: Zamknij stronę i zapisz dokument

Na koniec kończymy stronę i zapisujemy plik PS na dysku.

```csharp
	document.ClosePage();
	document.Save();
}
// ExEnd:1
```

Postępując zgodnie z tymi czterema krokami, możesz płynnie łączyć nieprzezroczyste i przezroczyste prostokąty, tworząc przekonujący efekt pseudo‑przezroczystości w dowolnym wyjściu PostScript.

## Typowe problemy i rozwiązania

| Problem | Dlaczego się pojawia | Rozwiązanie |
|-------|----------------|-----|
| Kolory wydają się w pełni nieprzezroczyste | Wartość alfa ustawiona na 255 przez pomyłkę | Use `Color.FromArgb(alpha, …)` with `alpha` < 255 |
| Gradient jest rozciągnięty nieprawidłowo | Nieprawidłowa macierz przekształcenia | Verify the matrix parameters match the rectangle dimensions |
| Plik wyjściowy jest pusty | Strumień nie został zamknięty lub nie wywołano `Save()` | Ensure `document.ClosePage()` and `document.Save()` are executed inside the `using` block |

## Najczęściej zadawane pytania

**Q: Czy Aspose.Page jest kompatybilny ze wszystkimi wersjami .NET?**  
A: Aspose.Page for .NET jest kompatybilny z różnymi wersjami platformy .NET, zapewniając elastyczność i łatwość integracji.

**Q: Czy mogę zastosować pseudo‑przezroczystość do innych kształtów poza prostokątami?**  
A: Tak, te same zasady można zastosować do dowolnego kształtu, dostosowując odpowiednio `GraphicsPath`.

**Q: Gdzie mogę znaleźć dodatkowe przykłady i dokumentację?**  
A: Zapoznaj się z [Aspose.Page documentation](https://reference.aspose.com/page/net/) dla kompleksowych przykładów i szczegółowych odniesień API.

**Q: Czy dostępna jest darmowa wersja próbna Aspose.Page?**  
A: Tak, możesz uzyskać darmową wersję próbną Aspose.Page z [this link](https://releases.aspose.com/).

**Q: Jak mogę uzyskać tymczasową licencję na Aspose.Page?**  
A: Odwiedź [this link](https://purchase.aspose.com/temporary-license/) aby uzyskać tymczasową licencję dla Aspose.Page.

---

**Ostatnia aktualizacja:** 2026-03-29  
**Testowano z:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}