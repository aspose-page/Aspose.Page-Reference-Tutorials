---
title: Transformacje XPS z Aspose.Page dla .NET
linktitle: Transformacje XPS
second_title: Aspose.Page API .NET
description: Przekształcaj dokumenty XPS bez wysiłku dzięki Aspose.Page dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby uzyskać płynne transformacje.
type: docs
weight: 13
url: /pl/net/canvas-manipulation/transformationsxps/
---
## Wstęp

Witamy w świecie Aspose.Page dla .NET, potężnej biblioteki, która umożliwia bezproblemowe wykonywanie różnych transformacji dokumentów XPS. W tym samouczku zagłębimy się w proces przekształcania dokumentów XPS przy użyciu Aspose.Page dla .NET. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten przewodnik przeprowadzi Cię przez każdy krok, zapewniając łatwe zrozumienie koncepcji.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz przygotowane następujące elementy:

-  Aspose.Page dla biblioteki .NET: Pobierz i zainstaluj bibliotekę z[Aspose.Page dla dokumentacji .NET](https://reference.aspose.com/page/net/).

- Środowisko programistyczne: skonfiguruj kompatybilne środowisko programistyczne, takie jak Visual Studio lub dowolne inne narzędzie programistyczne .NET.

- Twój katalog dokumentów: Zastąp symbol zastępczy w kodzie rzeczywistą ścieżką do katalogu dokumentów.

Przejdźmy teraz do samouczka!

## Importuj przestrzenie nazw

Po pierwsze, upewnij się, że zaimportowałeś niezbędne przestrzenie nazw, aby udostępnić funkcje Aspose.Page dla .NET w swoim kodzie. Dodaj następujące przestrzenie nazw na początku skryptu:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Krok 1: Utwórz nowy dokument XPS

```csharp
// ExStart:1
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";

// Utwórz nowy dokument XPS
XpsDocument doc = new XpsDocument();
```

## Krok 2: Utwórz główne płótno

```csharp
// Utwórz główne płótno, wspólne dla wszystkich elementów strony
XpsCanvas canvas1 = doc.AddCanvas();

// Wykonaj przesunięcia w lewo i w górę na głównym płótnie
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Krok 3: Utwórz geometrię ścieżki prostokątnej

```csharp
// Utwórz prostokątną geometrię ścieżki
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

## Krok 4: Dodaj wypełnienie prostokątów

```csharp
// Utwórz wypełnienie prostokątów
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Krok 5: Dodaj nowe płótno bez przekształceń

```csharp
// Dodaj nowe płótno bez żadnych przekształceń do głównego płótna
XpsCanvas canvas2 = canvas1.AddCanvas();

// Utwórz prostokąt na tym płótnie i wypełnij go
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Krok 6: Dodaj nowe płótno za pomocą transformacji tłumaczenia

```csharp
// Dodaj nowe płótno z transformacją tłumaczenia do głównego płótna
XpsCanvas canvas3 = canvas1.AddCanvas();

// Przetłumacz to płótno, aby umieścić nowy prostokąt poniżej poprzedniego prostokąta
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Przetłumacz to płótno na prawą stronę strony
canvas3.RenderTransform.Translate(500, 0);

// Utwórz prostokąt na tym płótnie i wypełnij go
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

## Krok 7: Dodaj nowe płótno z transformacją o podwójnej skali

```csharp
//Dodaj nowe płótno z transformacją podwójnej skali do głównego płótna
XpsCanvas canvas4 = canvas1.AddCanvas();

// Przetłumacz to płótno, aby umieścić nowy prostokąt poniżej poprzedniego prostokąta
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Skaluj to płótno
canvas4.RenderTransform.Scale(2, 2);

// Utwórz prostokąt na tym płótnie i wypełnij go
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

## Krok 8: Dodaj nowe płótno z obrotem wokół transformacji punktu

```csharp
// Dodaj nowe płótno z obrotem wokół transformacji punktowej do głównego płótna
XpsCanvas canvas5 = canvas1.AddCanvas();

// Przetłumacz to płótno, aby umieścić nowy prostokąt poniżej poprzedniego prostokąta
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Obróć to płótno wokół punktu o 45 stopni
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Utwórz prostokąt na tym płótnie i wypełnij go
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

## Krok 9: Zapisz wynikowy dokument XPS

```csharp
// Zapisz wynikowy dokument XPS
doc.Save(dataDir + "output1.xps");
// RozwińKoniec:1
```

## Wniosek

Gratulacje! Pomyślnie przekształciłeś dokument XPS przy użyciu Aspose.Page dla .NET. W tym przewodniku omówiono podstawowe kroki, od skonfigurowania wymagań wstępnych po wykonanie różnych transformacji. Eksperymentuj z tymi technikami i odblokuj pełny potencjał Aspose.Page dla .NET w swoich projektach.

## Często zadawane pytania

### P1: Czy Aspose.Page dla .NET jest kompatybilny ze wszystkimi środowiskami programistycznymi .NET?

O1: Tak, Aspose.Page dla .NET został zaprojektowany do bezproblemowej współpracy z różnymi środowiskami programistycznymi .NET, w tym Visual Studio.

### P2: Gdzie mogę znaleźć dodatkowe przykłady i dokumentację Aspose.Page dla .NET?

 A2: Odwiedź[Aspose.Page dla dokumentacji .NET](https://reference.aspose.com/page/net/) obszerną dokumentację i przykłady.

### P3: Czy przed zakupem mogę wypróbować Aspose.Page dla .NET?

 Odpowiedź 3: Tak, możesz skorzystać z bezpłatnej wersji próbnej, odwiedzając ją[Bezpłatna wersja próbna Aspose.Page](https://releases.aspose.com/).

### P4: Jak mogę uzyskać tymczasową licencję na Aspose.Page dla .NET?

 A4: Zdobądź tymczasową licencję, odwiedzając[Licencja tymczasowa](https://purchase.aspose.com/temporary-license/).

### P5: Gdzie mogę kupić Aspose.Page dla .NET?

 A5: Kup Aspose.Page dla .NET pod adresem[Aspose.Strona Kup](https://purchase.aspose.com/buy).