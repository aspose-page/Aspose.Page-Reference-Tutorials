---
title: Dodaj pionowy gradient do XPS za pomocą Aspose.Page dla .NET
linktitle: Dodaj gradient pionowy do XPS
second_title: Aspose.Page API .NET
description: Dowiedz się, jak ulepszyć dokumenty XPS za pomocą gradientów pionowych za pomocą Aspose.Page dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby zapewnić bezproblemową integrację.
weight: 15
url: /pl/net/gradient-fills/add-vertical-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj pionowy gradient do XPS za pomocą Aspose.Page dla .NET

## Wstęp

Witamy w tym samouczku krok po kroku dotyczącym dodawania gradientu pionowego do dokumentu XPS przy użyciu Aspose.Page dla .NET. Aspose.Page to potężny interfejs API, który umożliwia pracę z plikami XPS (Specyfikacja papieru XML) w aplikacjach .NET. W tym samouczku przeprowadzimy Cię przez proces tworzenia nowego dokumentu XPS, dodawania pionowego gradientu do ścieżki i zapisywania wyniku.

## Warunki wstępne

Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

-  Biblioteka Aspose.Page dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Page dla .NET w swoim środowisku programistycznym. Możesz go pobrać[Tutaj](https://releases.aspose.com/page/net/).

- Środowisko programistyczne: skonfiguruj środowisko programistyczne .NET z preferowanym IDE, takim jak Visual Studio.

Teraz zacznijmy od dodania pionowego gradientu do dokumentu XPS przy użyciu Aspose.Page dla .NET.

## Importuj przestrzenie nazw

W swojej aplikacji .NET uwzględnij niezbędne przestrzenie nazw, aby uzyskać dostęp do klas i metod Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Krok 1: Skonfiguruj katalog dokumentów

Zanim zaczniesz, ustaw ścieżkę do katalogu dokumentów, w którym chcesz zapisać wynikowy dokument XPS.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// RozwińKoniec:3
```

## Krok 2: Utwórz nowy dokument XPS

Zainicjuj nowy dokument XPS, używając następującego kodu:

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// RozwińKoniec:4
```

## Krok 3: Zdefiniuj punkty gradientu

Utwórz listę przystanków gradientu, określając kolor i położenie każdego przystanku. W tym przykładzie definiujemy gradient pionowy z pięcioma przystankami.

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// RozwińKoniec:5
```

## Krok 4: Utwórz ścieżkę z gradientem

Zdefiniuj ścieżkę, określając jej geometrię i zastosuj do niej pędzel z gradientem liniowym.

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// RozwińKoniec:6
```

## Krok 5: Zapisz wynikowy dokument XPS

Zapisz zmodyfikowany dokument XPS w określonym katalogu.

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// RozwińKoniec:7
```

Gratulacje! Pomyślnie dodałeś gradient pionowy do dokumentu XPS przy użyciu Aspose.Page dla .NET.

## Wniosek

W tym samouczku omówiliśmy, jak wykorzystać Aspose.Page dla .NET do ulepszenia dokumentów XPS za pomocą gradientów pionowych. Aspose.Page upraszcza złożone zadania, zapewniając programistom płynny sposób manipulowania plikami XPS w aplikacjach .NET.

## Często zadawane pytania

### P1: Czy Aspose.Page jest kompatybilny z Visual Studio 2019?

O1: Tak, Aspose.Page jest kompatybilny z Visual Studio 2019. Upewnij się, że masz zainstalowaną odpowiednią wersję biblioteki.

### P2: Czy mogę używać Aspose.Page do projektów komercyjnych?

 Odpowiedź 2: Tak, Aspose.Page można używać w projektach komercyjnych. Odwiedzać[Tutaj](https://purchase.aspose.com/buy) aby poznać opcje licencjonowania.

### P3: Czy dostępny jest bezpłatny okres próbny?

 Odpowiedź 3: Tak, możesz uzyskać bezpłatną wersję próbną Aspose.Page[Tutaj](https://releases.aspose.com/).

### P4: Gdzie mogę znaleźć dokumentację Aspose.Page?

 A4: Dokumentacja jest dostępna[Tutaj](https://reference.aspose.com/page/net/).

### P5: Jak mogę uzyskać wsparcie lub zadać pytania?

 A5: Odwiedź[Forum Aspose.Page](https://forum.aspose.com/c/page/39) za wsparcie społeczności.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
