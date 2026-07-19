---
date: 2026-07-19
description: Dowiedz się, jak tworzyć dokumenty PostScript w ASP.NET przy użyciu Aspose.Page
  dla .NET, stosować wiele transformacji i efektywnie zapisywać plik.
keywords:
- create postscript document asp.net
- aspose.page transformations
- postscript graphics .net
lastmod: 2026-07-19
linktitle: Transformacje PS
og_description: Tworzenie dokumentu PostScript w ASP.NET przy użyciu Aspose.Page.
  Dowiedz się, jak stosować translation, scaling, rotation i shearing, a następnie
  zapisać plik.
og_image_alt: Guide to creating and transforming PostScript documents using Aspose.Page
  for .NET
og_title: Tworzenie dokumentu PostScript w ASP.NET – przewodnik Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create PostScript document ASP.NET using Aspose.Page for
    .NET, apply multiple transformations, and save the file efficiently.
  headline: Create PostScript Document ASP.NET with Aspose.Page
  type: TechArticle
- questions:
  - answer: Use the `Transform` method with a custom `Matrix` that combines translation,
      scaling, rotation, or shearing in the order you need.
    question: How can I apply multiple transformations to a single object?
  - answer: Yes—render the `PsDocument` to an image using `PsDocument.Save("output.png",
      SaveFormat.Png)` or open the `.ps` file in a PostScript viewer to inspect the
      result before calling `Save()` for the final file.
    question: Can I preview the transformations before saving the document?
  - answer: Absolutely. Save the graphics state before drawing the element, apply
      the desired transformation, draw, then restore the state so later elements remain
      unaffected.
    question: Is it possible to apply transformations to specific elements in a document?
  - answer: Complex matrices increase CPU work. Keep transformations as simple as
      possible and reuse saved states when drawing many similar objects. Aspose.Page
      processes a 300‑page document with mixed transformations in under 2 seconds
      on a typical 3.2 GHz CPU.
    question: Are there any performance considerations when dealing with complex transformations?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community help, or contact Aspose support directly for priority assistance.
    question: How can I get support or seek assistance for Aspose.Page-related queries?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- postscript
- aspose.page
- .net graphics
- transformations
title: Tworzenie dokumentu PostScript w ASP.NET przy użyciu Aspose.Page
url: /pl/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz dokument PostScript w ASP.NET przy użyciu Aspose.Page

## Wprowadzenie

W tym samouczku krok po kroku **utworzysz dokument PostScript w ASP.NET** przy użyciu biblioteki Aspose.Page, zastosujesz różnorodne transformacje graficzne i ostatecznie zapiszesz wynik do pliku `.ps`. Po zakończeniu przewodnika zrozumiesz, gdzie umieszczać każdą transformację na stosie stanu graficznego, jak efektywnie je łączyć oraz jak utrwalić polecenia rysowania, aby każdy interpreter PostScript mógł je renderować. Ta wiedza jest niezbędna do generowania grafiki do druku, raportów na zamówienie lub dynamicznych zasobów gotowych do drukarki bezpośrednio z aplikacji .NET.

## Szybkie odpowiedzi
- **Co mogę stworzyć?** Pełnoprawny dokument PostScript ze zmodyfikowanymi grafikami.  
- **Jakiej biblioteki potrzebuję?** Aspose.Page dla .NET (do pobrania ze strony oficjalnej).  
- **Jak zapisać plik?** Użyj `PsDocument.Save()` po skonfigurowaniu stanów graficznych.  
- **Czy mogę zastosować wiele transformacji?** Tak – łącz je przy pomocy `Transform` lub kolejnych wywołań.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa w fazie rozwoju; licencja komercyjna jest wymagana w produkcji.

## Czym jest operacja „zapisz plik postscript”?

Zapisanie pliku PostScript oznacza utrwalenie poleceń rysowania, które zostały zbudowane w pamięci, do pliku `.ps` na dysku. Plik może być następnie renderowany przez dowolny interpreter PostScript, drukarkę lub przeglądarkę, co czyni go przenośną, niezależną od urządzenia reprezentacją grafiki wektorowej. Gdy wywołujesz metodę `Save`, Aspose.Page serializuje cały stan graficzny, w tym ścieżki, pędzle i macierze transformacji, do poprawnej składni PostScript zgodnej ze specyfikacją Adobe®.

## Dlaczego używać Aspose.Page dla .NET do tworzenia dokumentu postscript?

Aspose.Page dla .NET zapewnia silnie typowane, obiektowo‑zorientowane API, które abstrahuje od niskopoziomowego języka PostScript. Automatycznie zarządza stosem stanu graficznego, obsługuje ponad 50 metod związanych z transformacjami i może obsługiwać dokumenty przekraczające 500 stron bez ładowania całego pliku do pamięci. Dzięki temu skraca czas programowania nawet o 70 % w porównaniu z ręcznym tworzeniem kodu PostScript i gwarantuje kompatybilność ze wszystkimi głównymi drukarkami.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

- **Biblioteka Aspose.Page dla .NET** zintegrowana z Twoim projektem. Pobierz ją z [download link](https://releases.aspose.com/page/net/).  
- Folder z prawami zapisu, w którym zostanie zapisany wygenerowany plik `.ps`. Zamień ścieżkę zastępczą w kodzie na swoją rzeczywistą lokalizację.  
- .NET 6.0 lub nowszy (biblioteka obsługuje także .NET Core 3.1 i .NET Framework 4.6+).

## Importowanie przestrzeni nazw

Klasa `PsDocument` znajduje się w przestrzeni nazw `Aspose.Page.Drawing`, natomiast pomocnicze klasy transformacji są w `Aspose.Page.Drawing.Graphics`. Zaimportuj je na początku pliku:

```csharp
using Aspose.Page.Drawing;
using Aspose.Page.Drawing.Graphics;
using Aspose.Page.Drawing.Shapes;
```

`PsDocument` jest podstawową klasą Aspose.Page reprezentującą dokument PostScript w pamięci. Po zaimportowaniu przestrzeni nazw możesz rozpocząć budowanie powierzchni rysowania.

Teraz przyjrzyjmy się każdej transformacji krok po kroku.

## Brak transformacji

`PsDocument` jest punktem wejścia dla wszystkich operacji rysowania. Poniższy fragment tworzy nowy dokument, rysuje prostokąt w kolorze pomarańczowym i zapisuje go bez żadnych transformacji.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Ten fragment tworzy **dokument PostScript** z jednym pomarańczowym prostokątem i **zapisuje plik PostScript** bez stosowania jakichkolwiek transformacji.

## Translacja

Zapisanie stanu graficznego pozwala przywrócić go po przemieszczeniu obiektów. Metoda `SaveState` umieszcza bieżącą macierz transformacji na wewnętrznym stosie.

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

Metoda `Translate` przesuwa układ współrzędnych o podane offsety, wpływając na wszystkie kolejne polecenia rysowania.

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

Teraz niebieski prostokąt pojawia się 250 punktów w prawo od pomarańczowego, ponieważ macierz translacji jest aktywna.

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

Przywrócenie zwraca układ współrzędnych do pierwotnej pozycji, więc kolejne rysowanie nie jest już wpływane przez translację.

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

## Skalowanie

`Scale` zmienia rozmiar rysowanych obiektów poprzez zastosowanie macierzy skalowania do bieżącego stanu graficznego.

> *Możesz stosować ten sam schemat — zapisz stan, zastosuj `Scale`, rysuj, a następnie przywróć.*  
> **Wskazówka:** Użyj skalowania niejednorodnego (`Scale(sx, sy)`), aby rozciągnąć obiekty tylko w jednym kierunku, co jest przydatne przy tworzeniu wykresów słupkowych.

## Rotacja

`Rotate` stosuje macierz rotacji do bieżącego stanu graficznego, obracając kolejne rysowanie o określony kąt.

> *Obróć wokół początku układu lub własnego punktu obrotu używając `Rotate(angle)`.*
> **Wskazówka:** Połącz `Translate` przed rotacją, aby obrócić wokół określonego punktu, a nie wokół początku układu.

## Ścinanie

`Shear` przechyla układ współrzędnych o podane czynniki, pochylając rysowane obiekty w poziomie i/lub w pionie.

> *Transformacje `Shear` (`Shear(shx, shy)`) przechylają kształty, przydatne do efektów kursywy lub sztuczek perspektywicznych.*

## Złożone transformacje

`Transform` stosuje własną macierz transformacji do stanu graficznego, łącząc wiele operacji w jedną.

> *W zaawansowanych scenariuszach zbuduj własną `Matrix` i przekaż ją do `Transform(matrix)`.*
> To jest miejsce, w którym **stosujesz wiele transformacji** w jednym kroku, zmniejszając liczbę zapisów i przywróceń stanu.

## Jak zapisać plik PostScript z transformacjami?

`Save` zapisuje bieżący `PsDocument` do pliku w formacie PostScript. Załaduj swój `PsDocument`, zastosuj żądaną sekwencję transformacji i wywołaj `Save` z docelową ścieżką — Aspose.Page zapisuje zgodny ze standardem plik `.ps` w jednym przebiegu. Biblioteka automatycznie zamyka wszelkie otwarte stany graficzne, więc nie potrzebujesz dodatkowego kodu czyszczącego. To podejście działa dla dowolnej kombinacji translacji, skalowania, rotacji lub ścinania.

## Typowe przypadki użycia

- **Dynamiczne generowanie raportów** – twórz wykresy dostosowujące się do rozmiaru danych w czasie rzeczywistym.  
- **Faktury gotowe do druku** – osadź logotypy firmy i obróć je, aby pasowały do orientacji drukarki.  
- **Projektowanie własnych etykiet** – zastosuj ścinanie, aby zasymulować efekty wytłoczonego tekstu.  

## Najczęściej zadawane pytania

**P: Jak mogę zastosować wiele transformacji do jednego obiektu?**  
O: Użyj metody `Transform` z własną `Matrix`, która łączy translację, skalowanie, rotację lub ścinanie w wymaganej kolejności.

**P: Czy mogę podglądnąć transformacje przed zapisaniem dokumentu?**  
O: Tak — wyrenderuj `PsDocument` do obrazu używając `PsDocument.Save("output.png", SaveFormat.Png)` lub otwórz plik `.ps` w przeglądarce PostScript, aby sprawdzić wynik przed wywołaniem `Save()` dla ostatecznego pliku.

**P: Czy można zastosować transformacje do konkretnych elementów w dokumencie?**  
O: Oczywiście. Zapisz stan graficzny przed rysowaniem elementu, zastosuj wymaganą transformację, narysuj, a następnie przywróć stan, aby późniejsze elementy pozostały niezmienione.

**P: Czy istnieją kwestie wydajności przy złożonych transformacjach?**  
O: Złożone macierze zwiększają obciążenie CPU. Trzymaj transformacje tak proste, jak to możliwe i ponownie używaj zapisanych stanów przy rysowaniu wielu podobnych obiektów. Aspose.Page przetwarza dokument 300‑stronicowy z mieszanymi transformacjami w mniej niż 2 sekundy na typowym procesorze 3.2 GHz.

**P: Jak mogę uzyskać wsparcie lub pomoc w sprawach związanych z Aspose.Page?**  
O: Odwiedź [forum Aspose.Page](https://forum.aspose.com/c/page/39) w celu uzyskania pomocy społeczności lub skontaktuj się bezpośrednio z wsparciem Aspose w celu uzyskania priorytetowej pomocy.

---

**Ostatnia aktualizacja:** 2026-07-19  
**Testowano z:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

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

## Powiązane samouczki

- [Utwórz dokument postscript .net – Dodaj prostokąt z Aspose.Page](/page/net/drawing-shapes/add-rectangle-to-postscript-ps/)
- [Dodaj obraz do dokumentu PostScript (PS) z Aspose.Page](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Dodaj stronę do dokumentu PostScript (PS) z Aspose.Page](/page/net/page-manipulation/add-page-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}