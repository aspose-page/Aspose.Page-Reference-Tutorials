---
title: Dodaj okrągłą elipsę do dokumentu XPS za pomocą Aspose.Page dla .NET
linktitle: Dodaj elipsę koła do dokumentu XPS
second_title: Aspose.Page API .NET
description: Ulepsz dokumenty XPS za pomocą żywych gradientów promieniowych za pomocą Aspose.Page dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby uzyskać oszałamiające efekty wizualne.
weight: 11
url: /pl/net/drawing-shapes/add-circle-ellipse-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj okrągłą elipsę do dokumentu XPS za pomocą Aspose.Page dla .NET

## Wstęp

Tworzenie atrakcyjnych wizualnie dokumentów XPS jest powszechnym wymogiem w różnych aplikacjach. Aspose.Page dla .NET zapewnia potężny zestaw funkcji do wydajnego manipulowania dokumentami XPS. W tym samouczku skupimy się na dodaniu elipsy koła do dokumentu XPS przy użyciu Aspose.Page dla .NET. Wykonaj poniższe czynności, aby wzbogacić swoje dokumenty XPS o żywe gradienty promieniowe.

## Warunki wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

-  Zainstalowano bibliotekę Aspose.Page dla .NET. Można go pobrać z[Tutaj](https://releases.aspose.com/page/net/).
- Środowisko programistyczne, najlepiej Visual Studio lub inne narzędzie programistyczne .NET.
- Podstawowa znajomość programowania w języku C#.

## Importuj przestrzenie nazw

Na początek uwzględnij niezbędne przestrzenie nazw w kodzie C#:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Podzielmy teraz przykład na kilka kroków:

## Krok 1: Skonfiguruj dokument

```csharp
// ExStart:1
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";
// Utwórz nowy dokument XPS
XpsDocument doc = new XpsDocument();
```

Tutaj inicjujemy nowy dokument XPS przy użyciu Aspose.Page dla .NET.

## Krok 2: Zdefiniuj promieniową elipsę gradientową

```csharp
// Promieniowy gradient obrysowanej elipsy w lewym dolnym rogu
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 0, 255), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), .25f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 255, 0), .5f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 255, 0), .75f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), 1f));

XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250"));
```

Ten krok polega na zdefiniowaniu promieniowej elipsy gradientu z różnymi przystankami kolorów.

## Krok 3: Ustaw promieniowy pędzel gradientowy

```csharp
path.Stroke = doc.CreateRadialGradientBrush(new PointF(575f, 125f), new PointF(575f, 100f), 75f, 50f);
((XpsGradientBrush)path.Stroke).SpreadMethod = XpsSpreadMethod.Reflect;
((XpsGradientBrush)path.Stroke).GradientStops.AddRange(stops);
stops.Clear();
```

Tutaj ustawiamy obrys elipsy na promieniowy pędzel gradientowy, nadając mu niezbędne parametry.

## Krok 4: Dostosuj grubość obrysu

```csharp
path.StrokeThickness = 12f;
```

Ten krok polega na dostosowaniu grubości kreski w celu lepszej wizualizacji.

## Krok 5: Zapisz wynikowy dokument XPS

```csharp
// Zapisz wynikowy dokument XPS
doc.Save(dataDir + "AddEllipse_outXPS.xps");
// RozwińKoniec:1
```

Na koniec zapisz zmodyfikowany dokument XPS w żądanej lokalizacji.

## Wniosek

Gratulacje! Pomyślnie dodałeś elipsę kołową z gradientami promieniowymi do dokumentu XPS przy użyciu Aspose.Page dla .NET. Eksperymentuj z różnymi parametrami i kolorami, aby uzyskać pożądane efekty wizualne w swoich dokumentach.

## Często zadawane pytania

### P1: Czy mogę używać Aspose.Page dla .NET z innymi formatami dokumentów?

O1: Aspose.Page dla .NET zajmuje się w szczególności manipulacją dokumentami XPS. W przypadku innych formatów rozważ użycie powiązanych bibliotek Aspose.

### P2: Czy dostępna jest licencja tymczasowa do celów testowych?

 Odpowiedź 2: Tak, możesz uzyskać tymczasową licencję na testowanie, odwiedzając[ten link](https://purchase.aspose.com/temporary-license/).

### P3: Gdzie mogę znaleźć dodatkową pomoc i dyskusje?

 A3: Odwiedź[Forum Aspose.Page](https://forum.aspose.com/c/page/39) za wsparcie społeczności i dyskusje.

### P4: Czy dostępne są jakieś przykładowe dokumenty w celach informacyjnych?

 A4: Poznaj[dokumentacja](https://reference.aspose.com/page/net/) aby uzyskać wyczerpujące przykłady i wytyczne.

### P5: Czy mogę kupić Aspose.Page dla .NET?

 Odpowiedź 5: Tak, możesz kupić bibliotekę[Tutaj](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
