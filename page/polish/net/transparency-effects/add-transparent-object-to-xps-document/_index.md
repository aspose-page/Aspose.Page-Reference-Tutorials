---
title: Dodaj przezroczysty obiekt do dokumentu XPS za pomocą Aspose.Page
linktitle: Dodaj przezroczysty obiekt do dokumentu XPS
second_title: Aspose.Page API .NET
description: Dowiedz się, jak dodawać przezroczyste obiekty do dokumentów XPS w .NET przy użyciu Aspose.Page. Zwiększ atrakcyjność wizualną dzięki wskazówkom krok po kroku.
type: docs
weight: 11
url: /pl/net/transparency-effects/add-transparent-object-to-xps-document/
---
## Wstęp

tym samouczku omówimy, jak dodać przezroczyste obiekty do dokumentu XPS za pomocą Aspose.Page dla .NET. Przejrzystość dokumentów XPS może zwiększyć atrakcyjność wizualną i skutecznie przekazywać informacje. Podzielimy proces na łatwe do wykonania etapy, zapewniając przejrzystość i łatwość zrozumienia.

## Warunki wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

-  Aspose.Page dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Page dla .NET. Można go pobrać z[Aspose.Page dla dokumentacji .NET](https://reference.aspose.com/page/net/).

## Importuj przestrzenie nazw

Aby rozpocząć, uwzględnij w swoim projekcie niezbędne przestrzenie nazw:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Przejdźmy teraz do przewodnika krok po kroku.

## Krok 1: Utwórz nowy dokument XPS

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";
// Utwórz nowy dokument XPS
XpsDocument doc = new XpsDocument();
```

Ten kod inicjuje nowy dokument XPS przy użyciu Aspose.Page dla .NET.

## Krok 2: Wykaż przejrzystość

```csharp
// Tylko po to, żeby wykazać przejrzystość
doc.AddPath(doc.CreatePathGeometry("M120,0 H400 v1000 H120")).Fill = doc.CreateSolidColorBrush(Color.Gray);
doc.AddPath(doc.CreatePathGeometry("M300,120 h600 V420 h-600")).Fill = doc.CreateSolidColorBrush(Color.Gray);
```

Linie te tworzą przezroczyste ścieżki, aby pokazać efekt przezroczystości w dokumencie.

## Krok 3: Utwórz ścieżkę z geometrią zamkniętego prostokąta

```csharp
XpsPath path1 = doc.CreatePath(doc.CreatePathGeometry("M20,20 h200 v200 h-200 z"));
path1.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

Tutaj tworzymy ścieżkę o geometrii zamkniętego prostokąta, ustawiamy niebieski pełny pędzel do jej wypełnienia i dodajemy do bieżącej strony.

## Krok 4: Manipuluj ścieżkami i kolorami

```csharp
XpsPath path2 = doc.Add(path1);
path2.Fill = doc.CreateSolidColorBrush(Color.Green);
```

tym kroku pokazano, jak można manipulować ścieżkami i zmieniać kolory.

## Krok 5: Klonuj i przekształcaj ścieżki

```csharp
XpsPath path3 = doc.Add(path2);
path3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 300);
path3.Fill = doc.CreateSolidColorBrush(Color.Red);
```

Klonuj i przekształcaj ścieżki, przesuwając i zmieniając kolor sklonowanej ścieżki.

## Krok 6: Powtarzaj i modyfikuj ścieżki

```csharp
XpsPath path4 = doc.AddPath(path2.Data);
path4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 300, 0);
path4.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

Powtórz proces, tworząc nową ścieżkę na podstawie poprzedniej, z modyfikacjami.

## Krok 7: Zarządzaj przezroczystością

```csharp
XpsPath path5 = doc.Add(path4);
path5.RenderTransform = path5.RenderTransform.Clone();
path5.RenderTransform.Translate(0, 300);
path5.Fill.Opacity = 0.8f;
```

Zademonstruj, jak można niezależnie zarządzać nieprzezroczystością dla różnych ścieżek.

## Krok 8: Zapisz dokument XPS

```csharp
doc.Save(dataDir + "WorkingWithTransparency_out.xps");
```

Na koniec zapisz powstały dokument XPS z zastosowaną przezroczystością.

## Wniosek

Dodawanie przezroczystych obiektów do dokumentów XPS za pomocą Aspose.Page dla .NET zapewnia wszechstronny sposób ulepszania prezentacji wizualnych. Eksperymentuj z różnymi geometriami, kolorami i przezroczystością, aby osiągnąć pożądany efekt.

## Często zadawane pytania

### P1: Czy mogę zastosować przezroczystość do dowolnego obiektu w dokumencie XPS?

Odpowiedź 1: Tak, przezroczystość można zastosować do różnych obiektów, takich jak ścieżki, kształty i obrazy w dokumencie XPS.

### P2: Jak mogę dostosować krycie określonego elementu?

Odpowiedź 2: Możesz ustawić właściwość krycia wypełnienia lub obrysu, aby dostosować przezroczystość określonego elementu.

### P3: Czy Aspose.Page jest kompatybilny z .NET Core?

O3: Tak, Aspose.Page obsługuje .NET Core, umożliwiając rozwój na wielu platformach.

### P4: Czy mogę eksportować dokumenty XPS do innych formatów za pomocą Aspose.Page?

O4: Aspose.Page zapewnia funkcjonalność eksportowania dokumentów XPS do różnych formatów, w tym PDF i obrazów.

### P5: Gdzie mogę znaleźć dodatkowe wsparcie i dyskusje społeczności?

 Odpowiedź 5: Aby uzyskać dodatkowe wsparcie i dyskusje w społeczności, odwiedź stronę[Forum Aspose.Page](https://forum.aspose.com/c/page/39).