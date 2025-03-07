---
title: Zastosuj pędzel wizualny siatki za pomocą Aspose.Page dla .NET
linktitle: Zastosuj pędzel wizualny siatki
second_title: Aspose.Page API .NET
description: Poznaj dynamiczny świat przetwarzania dokumentów w .NET z Aspose.Page. Dowiedz się, jak zastosować pędzel wizualny siatki, aby uzyskać oszałamiające wizualnie dokumenty.
weight: 10
url: /pl/net/visual-brushes/apply-grid-visual-brush/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zastosuj pędzel wizualny siatki za pomocą Aspose.Page dla .NET

## Wstęp

W świecie programowania .NET Aspose.Page wyróżnia się jako potężne narzędzie do obsługi zadań związanych z przetwarzaniem dokumentów. Jedną z fascynujących funkcji, jakie oferuje, jest możliwość zastosowania pędzla wizualnego siatki, nadającego dokumentom nowy wymiar. Ten samouczek poprowadzi Cię krok po kroku przez proces wdrażania pędzla wizualnego Magenta Grid przy użyciu Aspose.Page dla .NET.

## Warunki wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

-  Aspose.Page dla .NET: Upewnij się, że masz zainstalowaną i skonfigurowaną bibliotekę w środowisku .NET. Możesz go pobrać[Tutaj](https://releases.aspose.com/page/net/).

- Środowisko programistyczne: Przygotuj działające środowisko programistyczne .NET i podstawową wiedzę na temat programowania w języku C#.

- Katalog dokumentów: Utwórz katalog dla swoich dokumentów, w którym będą zapisywane przetworzone pliki.

## Importuj przestrzenie nazw

Aby efektywnie wykorzystać funkcje Aspose.Page, w kodzie C# musisz zaimportować niezbędne przestrzenie nazw:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Podzielmy teraz przykład na wiele kroków.

## Krok 1: Zainicjuj dokument Xps

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// RozwińKoniec:3
```

 Tutaj tworzymy instancję`XpsDocument` do pracy z dokumentami XPS.

## Krok 2: Utwórz geometrię siatki w kolorze magenta

```csharp
// ExStart:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// RozwińKoniec:4
```

Ten krok obejmuje utworzenie geometrii ścieżki dla siatki w kolorze magenta.

## Krok 3: Zaprojektuj pędzel VisualBrush z siatką w kolorze magenta

```csharp
// ExStart:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// RozwińKoniec:5
```

Tutaj projektujemy wizualną stronę siatki w kolorze magenta za pomocą grafiki wektorowej.

## Krok 4: Zastosuj VisualBrush do siatki

```csharp
// ExStart:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// RozwińKoniec:6
```

Zastosuj pędzel wizualny do ścieżki siatki, upewniając się, że jest ona odpowiednio ułożona.

## Krok 5: Dodaj siatkę do płótna

```csharp
// ExStart:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// RozwińKoniec:7
```

Dodaj siatkę do płótna, określając wszelkie potrzebne przekształcenia.

## Krok 6: Wzmocnij czerwonym prostokątem

```csharp
// ExStart:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f;
// RozwińKoniec:8
```

Zwiększ atrakcyjność wizualną, dodając czerwony przezroczysty prostokąt.

## Krok 7: Zapisz dokument

```csharp
// ExStart: 9
doc.Save(dataDir + "AddGrid_out.xps");
// RozwińKoniec:9
```

Zapisz powstały dokument XPS w określonym katalogu.

## Wniosek

Gratulacje! Pomyślnie zastosowałeś pędzel wizualny siatki do swojego dokumentu przy użyciu Aspose.Page dla .NET. Technika ta może znacznie poprawić elementy wizualne dokumentów, zapewniając dynamiczne i angażujące doświadczenie użytkownika.

## Często zadawane pytania

### P1: Czy mogę używać Aspose.Page dla .NET zarówno w aplikacjach internetowych, jak i stacjonarnych?

O1: Tak, Aspose.Page dla .NET jest wszechstronny i może być używany w różnych typach aplikacji.

### P2: Czy przed zakupem dostępna jest wersja próbna?

 Odpowiedź 2: Oczywiście, możesz uzyskać dostęp do bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).

### P3: Gdzie mogę znaleźć dodatkowe wsparcie lub dyskusje społeczności?

 A3: Odwiedź[Forum Aspose.Page](https://forum.aspose.com/c/page/39) za dyskusję i wsparcie.

### P4: Jak mogę uzyskać tymczasową licencję na Aspose.Page dla .NET?

 Odpowiedź 4: Możesz nabyć licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).

### P5: Jaka inna dokumentacja jest dostępna dla Aspose.Page dla .NET?

 Odpowiedź 5: Zapoznaj się z obszerną dokumentacją[Tutaj](https://reference.aspose.com/page/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
