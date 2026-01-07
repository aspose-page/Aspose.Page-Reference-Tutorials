---
date: 2026-01-07
description: Dowiedz się, jak tworzyć dokument XPS, dodawać klony glifów, używać pędzla
  jednolitego koloru i zapisywać plik XPS przy użyciu Aspose.Page dla .NET.
linktitle: Add Glyph Clone and Change Color
second_title: Aspose.Page .NET API
title: Utwórz dokument XPS – dodaj klon glifu i zmień kolor przy użyciu Aspose.Page
  dla .NET
url: /pl/net/cross-document-editing/add-glyph-clone-and-change-color/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz dokument XPS – Dodaj klon glifu i zmień kolor przy użyciu Aspose.Page dla .NET

## Wprowadzenie

Witamy w tym przewodniku krok po kroku, który pokazuje **jak tworzyć pliki dokumentów XPS**, klonować glify i zmieniać ich kolory przy użyciu Aspose.Page dla .NET. Niezależnie od tego, czy tworzysz dynamiczne raporty, faktury, czy własne grafiki, opanowanie tych technik pozwala na generowanie wizualnie bogatych dokumentów XPS bez opuszczania ekosystemu .NET.

## Szybkie odpowiedzi
- **Jaki jest główny cel?** Utworzyć dokument XPS, dodać klony glifów i zmienić ich kolory.  
- **Która biblioteka jest używana?** Aspose.Page for .NET.  
- **Czy potrzebna jest licencja?** Dostępna jest tymczasowa licencja do oceny; pełna licencja jest wymagana w środowisku produkcyjnym.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Jak zapisać wynik?** Użyj metody `Save`, aby zapisać plik XPS na dysku.

## Wymagania wstępne

- Podstawowa znajomość języka programowania C#.  
- Zainstalowane Visual Studio lub inne preferowane środowisko programistyczne C#.  
- Biblioteka Aspose.Page for .NET. Możesz ją pobrać [tutaj](https://releases.aspose.com/page/net/).  
- Znajomość formatu dokumentu XPS.

## Importowanie przestrzeni nazw

Aby rozpocząć, dołącz niezbędne przestrzenie nazw w swoim projekcie C#:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Jak utworzyć dokument XPS i dodać klony glifów

### Krok 1: Skonfiguruj katalog dokumentów

Rozpocznij od skonfigurowania katalogu, w którym będą przechowywane Twoje dokumenty:

```csharp
string dataDir = "Your Document Directory";
```

### Krok 2: Utwórz pierwszy dokument XPS

Teraz utwórzmy pierwszy dokument XPS:

```csharp
XpsDocument doc1 = new XpsDocument();
```

### Krok 3: Dodaj glify do pierwszego dokumentu

Dodaj glify do pierwszego dokumentu, używając określonych parametrów:

```csharp
XpsGlyphs glyphs = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Krok 4: Wypełnij glify stałą szczotką koloru

Wypełnij glify w pierwszym dokumencie **stałą szczotką koloru**, na przykład zielonym:

```csharp
glyphs.Fill = doc1.CreateSolidColorBrush(Color.Green);
```

### Krok 5: Utwórz drugi dokument XPS

Teraz utwórz drugi dokument XPS:

```csharp
XpsDocument doc2 = new XpsDocument();
```

### Krok 6: Jak dodać klon glifu do innego dokumentu

Sklonuj glify z pierwszego dokumentu i dodaj je do drugiego dokumentu:

```csharp
glyphs = doc2.Add(glyphs.Clone());
```

### Krok 7: Jak zmienić kolor sklonowanego glifu

Zmień kolor sklonowanych glifów w drugim dokumencie, na przykład na czerwony. To pokazuje **jak zmienić kolor** glifu po sklonowaniu:

```csharp
((XpsSolidColorBrush)glyphs.Fill).Color = doc2.CreateColor(Color.Red);
```

### Krok 8: Zapisz plik XPS – pierwszy dokument

Zapisz pierwszy dokument XPS w folderze zdefiniowanym wcześniej:

```csharp
doc1.Save(dataDir + "out1.xps");
```

### Krok 9: Zapisz plik XPS – drugi dokument

Zapisz drugi dokument XPS:

```csharp
doc2.Save(dataDir + "out2.xps");
```

Gratulacje! Pomyślnie **utworzyłeś pliki dokumentów XPS**, dodałeś klony glifów i zmieniłeś ich kolory przy użyciu Aspose.Page dla .NET.

## Dlaczego warto używać klonowania glifów i zmiany kolorów?

- **Ponowne użycie:** Klonuj istniejące glify, aby ponownie wykorzystać złożone kształty wektorowe bez ponownego definiowania ich.  
- **Wydajność:** Skraca czas przetwarzania w porównaniu do odtworzenia glifów od podstaw.  
- **Elastyczność projektowa:** Zastosuj różne instancje `SolidColorBrush` do tego samego glifu, aby uzyskać różnorodne motywy wizualne.  
- **Edycja między dokumentami:** Klonuj glify w wielu plikach XPS, umożliwiając spójną identyfikację wizualną w raportach.

## Typowe problemy i rozwiązywanie

| Problem | Rozwiązanie |
|---------|-------------|
| **Klon zwraca null** | Upewnij się, że źródłowy glif (`glyphs`) został dodany do pierwszego dokumentu przed klonowaniem. |
| **Kolor się nie zmienia** | Rzutuj `glyphs.Fill` na `XpsSolidColorBrush` przed ustawieniem właściwości `Color` (jak pokazano w Kroku 7). |
| **Plik nie został zapisany** | Sprawdź, czy `dataDir` wskazuje na prawidłowy, zapisywalny folder oraz czy masz odpowiednie uprawnienia systemu plików. |
| **Nieoczekiwany rozmiar glifu** | Dostosuj parametr rozmiaru czcionki (drugi argument w `AddGlyphs`), aby odpowiednio skalować glif. |

## Najczęściej zadawane pytania

**P1: Czy mogę używać Aspose.Page for .NET z innymi formatami dokumentów?**  
A1: Aspose.Page for .NET jest specjalnie zaprojektowany do pracy z dokumentami XPS. Jeśli potrzebujesz manipulować innymi formatami, możesz rozważyć inne biblioteki Aspose przeznaczone do tych formatów.

**P2: Czy dostępna jest tymczasowa licencja dla Aspose.Page for .NET?**  
A2: Tak, możesz uzyskać tymczasową licencję do celów testowych. Odwiedź [tutaj](https://purchase.aspose.com/temporary-license/) po więcej informacji.

**P3: Jak mogę uzyskać wsparcie lub pomoc w razie problemów?**  
A3: Zapraszamy do odwiedzenia [forum Aspose.Page](https://forum.aspose.com/c/page/39), aby połączyć się ze społecznością i uzyskać pomoc.

**P4: Czy darmowa wersja próbna ma jakieś ograniczenia?**  
A4: Wersja próbna ma pewne ograniczenia; zaleca się zapoznanie z dokumentacją w celu uzyskania szczegółów przed użyciem.

**P5: Gdzie mogę znaleźć pełną dokumentację Aspose.Page for .NET?**  
A5: Dokumentację znajdziesz [tutaj](https://reference.aspose.com/page/net/), zawierającą szczegółowe informacje i przykłady.

**P6: Jak zmienić kolor obrysu glifu zamiast wypełnienia?**  
A6: Użyj `glyphs.Stroke = doc.CreateSolidColorBrush(Color.Blue);`, aby ustawić szczotkę obrysu.

**P7: Czy mogę dodać wiele klonów glifów do tego samego dokumentu?**  
A7: Tak, wywołuj `doc2.Add(glyphs.Clone());` wielokrotnie, dostosowując pozycje w razie potrzeby.

---

**Ostatnia aktualizacja:** 2026-01-07  
**Testowano z:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}