---
date: 2026-01-12
description: Dowiedz się, jak zapisać plik PostScript i utworzyć dokument PostScript
  przy użyciu Aspose.Page dla .NET oraz zastosować wiele transformacji dla dynamicznej
  grafiki.
linktitle: Transformations PS
second_title: Aspose.Page .NET API
title: Zapisz plik PostScript przy użyciu transformacji Aspose.Page (.NET)
url: /pl/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zapisz plik PostScript przy użyciu transformacji Aspose.Page (.NET)

## Wprowadzenie

W tym samouczku odkryjesz, jak **zapisz plik PostScript** podczas pracy z Aspose.Page dla .NET. Przejdziemy przez tworzenie dokumentu PostScript, zastosowanie wielu transformacji, takich jak translacja, skalowanie, rotacja i ścinanie, a na końcu zapisanie wyniku. Po zakończeniu będziesz pewnie tworzyć dynamiczną grafikę programowo i dokładnie wiedzieć, gdzie umieścić każdą transformację w stanie graficznym.

## Szybkie odpowiedzi
- **Co mogę stworzyć?** W pełni funkcjonalny dokument PostScript z przekształconą grafiką.  
- **Jakiej biblioteki potrzebuję?** Aspose.Page for .NET (do pobrania ze strony oficjalnej).  
- **Jak zapisać plik?** Użyj `PsDocument.Save()` po skonfigurowaniu stanów graficznych.  
- **Czy mogę zastosować wiele transformacji?** Tak – łącz je przy pomocy `Transform` lub kolejnych wywołań.  
- **Czy potrzebna jest licencja?** Bezpłatna wersja próbna działa w fazie rozwoju; licencja komercyjna jest wymagana w produkcji.

## Czym jest operacja „zapisz plik postscript”?

Zapisanie pliku PostScript oznacza utrwalenie poleceń rysunkowych, które zbudowałeś w pamięci, w pliku `.ps` na dysku. Plik może być następnie renderowany przez dowolny interpreter PostScript, drukarkę lub przeglądarkę.

## Dlaczego używać Aspose.Page dla .NET do tworzenia dokumentu PostScript?

Aspose.Page zapewnia wysokopoziomowe, niezależne od urządzenia API, które abstrahuje od niskopoziomowej składni PostScript. Otrzymujesz:

- Silnie typowane obiekty C# dla ścieżek, pędzli i transformacji.  
- Automatyczne zarządzanie stosami stanu graficznego (save/restore).  
- Pełne wsparcie dla złożonych macierzy transformacji bez ręcznych obliczeń.  

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

- **Biblioteka Aspose.Page for .NET** zintegrowana z projektem. Pobierz ją z [linku do pobrania](https://releases.aspose.com/page/net/).  
- Folder, do którego można zapisywać, w którym zostanie zapisany wygenerowany plik `.ps`. Zastąp ścieżkę zastępczą w kodzie rzeczywistym katalogiem.

## Importowanie przestrzeni nazw

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Teraz przyjrzyjmy się każdemu krokowi transformacji.

## Brak transformacji

### Krok 1: Utwórz strumień wyjściowy

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Create save options with default values
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Create graphics path from the rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Set paint in graphics state on upper level
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Fill the first rectangle that is on the upper-level graphics state and without any transformations
    document.Fill(path);

    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Ten fragment tworzy **dokument PostScript** z pojedynczym pomarańczowym prostokątem i **zapisuje plik PostScript** bez stosowania jakichkolwiek transformacji.

## Translacja

### Krok 1: Zapisz stan graficzny

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

Zapisanie stanu graficznego pozwala przywrócić go po przemieszczeniu obiektów.

### Krok 2: Translacja stanu graficznego

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

Translacja przesuwa wszystko narysowane po tym wywołaniu o 250 jednostek w prawo.

### Krok 3: Wypełnij prostokąt transformacją translacji

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

Teraz niebieski prostokąt pojawia się 250 punktów w prawo od pomarańczowego.

### Krok 4: Przywróć stan graficzny

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

Przywrócenie przywraca układ współrzędnych do pierwotnej pozycji, więc kolejne rysowanie nie jest wpływane przez translację.

## Skalowanie

> *Możesz stosować ten sam schemat — zapisz stan, zastosuj `Scale`, rysuj, a następnie przywróć.*  
> **Wskazówka:** Użyj skalowania niejednorodnego (`Scale(sx, sy)`) aby rozciągnąć obiekty tylko w jednym kierunku.

## Rotacja

> *Obróć wokół początku układu lub własnego punktu obrotu używając `Rotate(angle)`. *  
> **Wskazówka:** Połącz `Translate` przed rotacją, aby obrócić wokół określonego punktu.

## Ścinanie

> *Transformacje ścinające (`Shear(shx, shy)`) przechylają kształty, przydatne do efektów kursywy.*  

## Złożone transformacje

> *W zaawansowanych scenariuszach zbuduj własną `Matrix` i przekaż ją do `Transform(matrix)`. *  
> Tutaj **stosujesz wiele transformacji** w jednym kroku.

## Podsumowanie

Nauczyłeś się, jak **zapisz plik PostScript**, **utworzyć dokument PostScript** i **zastosować wiele transformacji** przy użyciu Aspose.Page dla .NET. Eksperymentuj z różnymi kolejnościami transformacji, łącz je i obserwuj, jak grafika się rozwija.

## Najczęściej zadawane pytania

**Q: Jak mogę zastosować wiele transformacji do jednego obiektu?**  
A: Użyj metody `Transform` z własną `Matrix`, która łączy translację, skalowanie, rotację lub ścinanie w wymaganej kolejności.

**Q: Czy mogę podglądnąć transformacje przed zapisaniem dokumentu?**  
A: Tak — wyrenderuj `PsDocument` do obrazu lub użyj przeglądarki PostScript, aby sprawdzić wynik przed wywołaniem `Save()`.

**Q: Czy można zastosować transformacje do konkretnych elementów w dokumencie?**  
A: Oczywiście. Zapisz stan graficzny przed rysowaniem elementu, zastosuj wymaganą transformację, narysuj, a następnie przywróć stan.

**Q: Czy istnieją kwestie wydajności przy obsłudze złożonych transformacji?**  
A: Złożone macierze zwiększają obciążenie CPU. Trzymaj transformacje tak proste, jak to możliwe i ponownie używaj zapisanych stanów przy rysowaniu wielu podobnych obiektów.

**Q: Jak mogę uzyskać wsparcie lub pomoc w sprawach związanych z Aspose.Page?**  
A: Odwiedź [forum Aspose.Page](https://forum.aspose.com/c/page/39) aby uzyskać pomoc od społeczności lub skontaktuj się bezpośrednio z wsparciem Aspose.

---

**Ostatnia aktualizacja:** 2026-01-12  
**Testowano z:** Aspose.Page 24.11 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}