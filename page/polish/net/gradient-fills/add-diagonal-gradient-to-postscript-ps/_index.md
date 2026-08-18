---
date: 2026-02-23
description: Dowiedz się, jak dodać gradient do plików PostScript, zapisać plik PostScript
  w formacie A4 oraz wypełnić prostokąt gradientem przy użyciu Aspose.Page dla .NET.
linktitle: Add Diagonal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Jak dodać gradient – gradient diagonalny w PostScript (PS) z Aspose.Page .NET
url: /pl/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dodać gradient: gradient diagonalny do PostScript (PS) z Aspose.Page .NET

## Wprowadzenie

Dodanie gradientu diagonalnego do dokumentu PostScript (PS) może znacząco poprawić atrakcyjność wizualną, szczególnie gdy potrzebujesz **how to add gradient** efektów w raportach technicznych, broszurach lub aplikacjach intensywnie wykorzystujących grafikę. W tym samouczku zobaczysz dokładnie, jak dodać gradient do pliku PostScript, ustawić rozmiar strony A4 i wypełnić prostokąt płynnym przejściem kolorów przy użyciu Aspose.Page dla .NET.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebujesz?** Aspose.Page for .NET  
- **Które wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6  
- **Czy mogę zmienić kierunek gradientu?** Tak – obróć transformację pędzla jak pokazano w kodzie  
- **Jak zapisać wynik?** Użyj `PsDocument.Save()`, które zapisuje plik PostScript na dysku  
- **Czy potrzebna jest licencja do produkcji?** Tak, licencja komercyjna odblokowuje pełną funkcjonalność  

## Czym jest gradient diagonalny w PostScript?

Gradient diagonalny to liniowe przejście kolorów, które przebiega pod kątem (zazwyczaj 45°) przez kształt. W PostScript osiąga się to, stosując `LinearGradientBrush` z niestandardową macierzą transformacji, która obraca, skaluje i przesuwa gradient, aby dopasować go do żądanego prostokąta.

## Dlaczego używać Aspose.Page do wypełnień gradientowych?

Aspose.Page abstrahuje niskopoziomowe polecenia PostScript, pozwalając pracować z znanymi obiektami graficznymi .NET. Możesz tworzyć złożone wypełnienia, ustawiać wymiary stron i eksportować bezpośrednio do **save PostScript file** bez konieczności ręcznego pisania składni PS.

## Wymagania wstępne

- **Aspose.Page for .NET Library** – pobierz ją [tutaj](https://releases.aspose.com/page/net/).  
- **Document Directory** – folder, w którym zostanie zapisany wygenerowany plik `*.ps`.

Teraz, gdy podstawy są już omówione, przejdźmy krok po kroku przez implementację.

## Importowanie przestrzeni nazw

Najpierw zaimportuj przestrzenie nazw, które dają dostęp do urządzenia EPS, narzędzi rysunkowych i klas I/O.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Krok 1: Utwórz strumień wyjściowy dla dokumentu PostScript (Utwórz dokument PostScript)

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## Krok 2: Ustaw rozmiar strony A4 (Opcje zapisu)

```csharp
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();
```

## Krok 3: Utwórz nowy dokument PS jednopaginowy

```csharp
	// Create new 1-paged PS Document
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
	//Create graphics path from the first rectangle
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## Krok 6: Utwórz pędzel Linear Gradient (Wypełnij gradientem prostokąt)

```csharp
	//Create linear gradient brush with rectangle as bounds, start, and end colors
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## Krok 7: Utwórz transformację dla pędzla

```csharp
	//Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
	//Translation components are offsets of the rectangle                
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## Krok 8: Zastosuj transformacje do pędzla (Obróć, Skaluj, Przesuń)

```csharp
	//Rotate gradient, then scale and translate to get visible color transition in required rectangle
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## Krok 9: Ustaw transformację dla pędzla

```csharp
	//Set transform
	brush.Transform = brushTransform;
```

## Krok 10: Ustaw farbę i wypełnij prostokąt

```csharp
	//Set paint
	document.SetPaint(brush);

	//Fill the rectangle
	document.Fill(path);
```

## Krok 11: Zamknij bieżącą stronę

```csharp
	//Close current page
	document.ClosePage();
```

## Krok 12: Zapisz dokument (Zapisz plik PostScript)

```csharp
	//Save the document
	document.Save();
}
// ExEnd:1
```

## Jak zapisać plik PostScript

Wywołanie `PsDocument.Save()` zapisuje w pełni sformowany content PostScript do strumienia otwartego w **Kroku 1**. Po zakończeniu bloku `using` plik `DiagonaGradient_outPS.ps` będzie dostępny w katalogu, który określiłeś.

## Typowe przypadki użycia

- **Dokumentacja techniczna** wymagająca subtelnego cieniowania tła.  
- **Broszury marketingowe**, w których gradient diagonalny dodaje nowoczesny wygląd.  
- **Automatyczne generatory raportów**, które na bieżąco tworzą drukowalne pliki PS.

## Rozwiązywanie problemów i wskazówki

- **Nieprawidłowe kolory** – sprawdź ponownie wartości ARGB przekazywane do `LinearGradientBrush`.  
- **Gradient niewidoczny** – upewnij się, że macierz transformacji prawidłowo obraca i skaluje; wywołanie `Rotate(-45)` ustawia kąt diagonalny.  
- **Plik nie został utworzony** – sprawdź, czy `dataDir` wskazuje istniejący folder i czy aplikacja ma uprawnienia do zapisu.

## Najczęściej zadawane pytania

**P: Czy Aspose.Page jest kompatybilny ze wszystkimi frameworkami .NET?**  
O: Aspose.Page obsługuje szeroki zakres wersji .NET, od .NET Framework 4.5+ po .NET 6+, zapewniając dużą kompatybilność.

**P: Czy mogę dostosować kolory gradientu w Aspose.Page?**  
O: Tak, możesz określić dowolne kolory ARGB przy tworzeniu `LinearGradientBrush`, co daje pełną kontrolę nad kolorami początkowymi i końcowymi.

**P: Czy dostępna jest wersja próbna Aspose.Page?**  
O: Tak, możesz zapoznać się z funkcjami Aspose.Page, pobierając wersję próbną [tutaj](https://releases.aspose.com/).

**P: Jak mogę uzyskać tymczasową licencję dla Aspose.Page?**  
O: Uzyskaj tymczasową licencję dla Aspose.Page [tutaj](https://purchase.aspose.com/temporary-license/), aby odblokować dodatkowe możliwości podczas oceny.

**P: Gdzie mogę znaleźć wsparcie społeczności dla Aspose.Page?**  
O: Dołącz do społeczności Aspose.Page na [forum](https://forum.aspose.com/c/page/39), aby uzyskać pomoc i dyskusje.

---

**Ostatnia aktualizacja:** 2026-02-23  
**Testowano z:** Aspose.Page for .NET (najnowsze stabilne wydanie)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}