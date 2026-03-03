---
date: 2026-03-03
description: Dowiedz się, jak używać Aspose.Page dla .NET do układania obrazów w dokumentach
  XPS. Ten przewodnik krok po kroku pokazuje, jak efektywnie układać obrazy i zwiększyć
  ich atrakcyjność wizualną.
linktitle: Add Tiled Image to XPS Document
second_title: Aspose.Page .NET API
title: Jak używać Aspose.Page do dodawania obrazka w kafelkach do dokumentu XPS
url: /pl/net/image-management/add-tiled-image-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak używać Aspose.Page do dodania obrazka kafelkowego do dokumentu XPS

## Wprowadzenie

Jeśli zastanawiasz się **jak używać Aspose**, aby nadać swoim plikom XPS bogatszy styl wizualny, trafiłeś we właściwe miejsce. W tym samouczku przeprowadzimy Cię przez dokładne kroki potrzebne do **kafelkowania obrazu** wewnątrz dokumentu XPS przy użyciu Aspose.Page dla .NET. Po zakończeniu będziesz mieć wielokrotnego użytku fragment kodu, który możesz wstawić do dowolnego projektu .NET, aby w locie tworzyć grafiki z obrazem kafelkowanym.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebujesz?** Aspose.Page for .NET  
- **Która metoda tworzy pędzel kafelkowy?** `CreateImageBrush` z `TileMode = XpsTileMode.Tile`  
- **Czy mogę kontrolować krycie?** Tak – ustaw `path.Fill.Opacity` (np. 0.5f)  
- **Czy potrzebna jest licencja do testów?** Tymczasowa licencja działa w ocenie; pełna licencja jest wymagana w produkcji.  
- **Jakie wersje .NET są wspierane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6!

## Czym jest Aspose.Page i dlaczego kafelkować obrazy?

Aspose.Page to potężne API, które pozwala programistom generować, edytować i renderować XPS, PDF oraz inne formaty oparte na stronach, bez polegania na Microsoft Office. Kafelkowanie obrazu — powtarzanie bitmapy na kształcie — pomaga wypełnić duże obszary wzorami, znakami wodnymi lub teksturami tła, jednocześnie utrzymując niewielki rozmiar pliku.

## Jak używać Aspose.Page do kafelkowania obrazów w dokumentach XPS

Poniżej znajdziesz kompletny, gotowy do uruchomienia przykład. Każdy krok jest wyjaśniony prostym językiem przed odpowiadającym mu blokiem kodu, abyś mógł zobaczyć **dlaczego** każda linia ma znaczenie.

### Wymagania wstępne

- **Aspose.Page for .NET** – pobierz i odwołaj się do biblioteki ze strony oficjalnej [here](https://reference.aspose.com/page/net/).  
- **Środowisko programistyczne** – Visual Studio (dowolna edycja) lub inne ulubione IDE .NET.

### Importowanie przestrzeni nazw

Najpierw wprowadź wymagane przestrzenie nazw, aby kompilator wiedział, gdzie znaleźć klasy XPS.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

### Krok 1: Zdefiniuj katalog dokumentu

Określ, gdzie będą przechowywane wygenerowany plik XPS i obraz źródłowy. Zastąp symbol zastępczy rzeczywistym folderem na swoim komputerze.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Krok 2: Utwórz nowy dokument XPS

Zainicjuj pusty dokument XPS, który będzie zawierał grafikę kafelkową.

```csharp
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Krok 3: Dodaj obraz kafelkowy

Tutaj tworzymy prostokątną ścieżkę, wypełniamy ją `ImageBrush` i ustawiamy pędzel w tryb kafelkowy. Właściwość `TileMode` instruuje silnik, aby powtarzał obraz zarówno w poziomie, jak i w pionie. Dostosuj współrzędne prostokąta lub obraz źródłowy w zależności od potrzeb.

```csharp
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

### Krok 4: Zapisz wynikowy dokument XPS

Na koniec zapisz dokument na dysku. Plik wyjściowy może być otwarty dowolnym przeglądarką XPS lub dalej przetwarzany przy użyciu Aspose.Page.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

## Typowe problemy i wskazówki

- **Błędy ścieżki** – Upewnij się, że `dataDir` kończy się ukośnikiem lub użyj `Path.Combine`, aby uniknąć problemów z brakującym separatorem.  
- **Niezgodności rozmiaru obrazu** – Obraz źródłowy powinien być wystarczająco duży dla obszaru kafelkowania; w przeciwnym razie wzór może wyglądać na rozciągnięty.  
- **Krycie niewidoczne** – Niektóre przeglądarki ignorują krycie w XPS; przetestuj z przeglądarką, która w pełni obsługuje renderowanie XPS (np. XPS Viewer w systemie Windows).

## Najczęściej zadawane pytania

### Q1: Czy Aspose.Page jest kompatybilny ze wszystkimi środowiskami programistycznymi .NET?

A: Tak, Aspose.Page działa z Visual Studio, Rider, VS Code i każdym IDE obsługującym .NET.

### Q2: Czy mogę dostosować krycie kafelkowego obrazu?

A: Oczywiście. Przykład ustawia `path.Fill.Opacity = 0.5f;` — możesz zmienić wartość zmiennoprzecinkową pomiędzy 0 (przezroczyste) a 1 (nieprzezroczyste).

### Q3: Czy dostępne są inne tryby kafelkowania w Aspose.Page dla .NET?

A: Tak. Oprócz `XpsTileMode.Tile` możesz używać `FlipX`, `FlipY` i `FlipXY`, aby tworzyć odbite wzory.

### Q4: Jak obsługiwać tymczasowe licencje dla Aspose.Page?

A: Odwołaj się do strony [temporary license](https://purchase.aspose.com/temporary-license/) na witrynie Aspose, aby uzyskać szczegóły dotyczące uzyskania i zastosowania licencji próbnej.

### Q5: Gdzie mogę uzyskać pomoc lub połączyć się ze społecznością Aspose.Page?

A: Odwiedź [forum Aspose.Page](https://forum.aspose.com/c/page/39), aby zadawać pytania, udostępniać fragmenty kodu i uczyć się od innych programistów.

### Q6: Czy mogę użyć tego podejścia do stworzenia efektu znaku wodnego?

A: Tak. Obniżając krycie i wybierając półprzezroczysty obraz, pędzel kafelkowy doskonale sprawdza się jako powtarzający się znak wodny.

## Podsumowanie

Teraz wiesz **jak używać Aspose**, aby dodać obraz kafelkowy do dokumentu XPS, kontrolować jego krycie i zapisać wynik do dalszego użycia. Ta technika jest idealna dla wzorów tła, znaków wodnych lub każdej sytuacji, w której powtarzająca się grafika dodaje atrakcyjności wizualnej bez zwiększania rozmiaru pliku. Śmiało eksperymentuj z różnymi kształtami, obrazami i trybami kafelkowania, aby dopasować je do potrzeb swojego projektu.

---

**Ostatnia aktualizacja:** 2026-03-03  
**Testowano z:** Aspose.Page for .NET (latest release)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}