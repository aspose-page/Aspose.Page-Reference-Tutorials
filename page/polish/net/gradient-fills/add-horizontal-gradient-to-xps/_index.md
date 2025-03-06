---
title: Dodaj gradient poziomy do XPS za pomocą Aspose.Page dla .NET
linktitle: Dodaj gradient poziomy do XPS
second_title: Aspose.Page API .NET
description: Dowiedz się, jak dodawać wspaniałe poziome gradienty do dokumentów XPS za pomocą Aspose.Page dla .NET. Bez wysiłku podnieś atrakcyjność wizualną.
weight: 13
url: /pl/net/gradient-fills/add-horizontal-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj gradient poziomy do XPS za pomocą Aspose.Page dla .NET

## Wstęp

W tym samouczku przyjrzymy się, jak ulepszyć dokumenty XPS, dodając poziomy gradient za pomocą Aspose.Page dla .NET. Aspose.Page dla .NET to potężna biblioteka, która zapewnia bezproblemową obsługę dokumentów XPS (Specyfikacja papieru XML) w aplikacjach .NET. Dodanie gradientów może nadać dokumentom atrakcyjność wizualną, a ten przewodnik przeprowadzi Cię przez ten proces krok po kroku.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

1.  Biblioteka Aspose.Page dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Page dla .NET w swoim środowisku programistycznym. Można go pobrać z[Aspose.Page dla dokumentacji .NET](https://reference.aspose.com/page/net/).

2. Środowisko programistyczne: Skonfiguruj odpowiednie środowisko programistyczne, w tym edytor kodu, taki jak Visual Studio.

## Importuj przestrzenie nazw

Zacznij od zaimportowania niezbędnych przestrzeni nazw do swojego projektu. Te przestrzenie nazw są niezbędne do pracy z Aspose.Page dla .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Podzielmy teraz podany przykład na wiele kroków.

## Krok 1: Ustaw ścieżkę katalogu dokumentów

```csharp
// ExStart:3
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";
// RozwińKoniec:3
```

## Krok 2: Utwórz nowy dokument XPS

```csharp
// ExStart:4
// Utwórz nowy dokument XPS
XpsDocument doc = new XpsDocument();
// RozwińKoniec:4
```

## Krok 3: Zainicjuj punkty gradientu

```csharp
// ExStart:5
// Zainicjuj listę XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// RozwińKoniec:5
```

## Krok 4: Utwórz nową ścieżkę

```csharp
// ExStart:6
//Utwórz nową ścieżkę, definiując geometrię w formie skrótu
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// RozwińKoniec:6
```

## Krok 5: Zapisz wynikowy dokument XPS

```csharp
// ExStart:7
// Zapisz wynikowy dokument XPS
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// RozwińKoniec:7
```

Teraz pomyślnie dodałeś poziomy gradient do swojego dokumentu XPS za pomocą Aspose.Page dla .NET.

## Wniosek

Ulepszanie dokumentów XPS za pomocą gradientów nie tylko poprawia ich atrakcyjność wizualną, ale także zapewnia bardziej wciągające doświadczenie użytkownika. Aspose.Page dla .NET upraszcza ten proces, umożliwiając bezproblemowe osiągnięcie profesjonalnych wyników.

## Często zadawane pytania

### P1: Gdzie mogę znaleźć dokumentację Aspose.Page dla .NET?

 Odpowiedź 1: Możesz znaleźć dokumentację[Tutaj](https://reference.aspose.com/page/net/).

### P2: Jak pobrać Aspose.Page dla .NET?

 O2: Możesz pobrać bibliotekę z[Aspose.Page dla strony pobierania .NET](https://releases.aspose.com/page/net/).

### P3: Gdzie mogę kupić Aspose.Page dla .NET?

 O3: Możesz kupić Aspose.Page dla .NET w sklepie[strona zakupu](https://purchase.aspose.com/buy).

### P4: Czy dostępny jest bezpłatny okres próbny?

 A4: Tak, możesz uzyskać bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/).

### P5: Jak uzyskać tymczasową licencję na Aspose.Page dla .NET?

 Odpowiedź 5: Możesz uzyskać licencję tymczasową od[ten link](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
