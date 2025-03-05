---
title: Przycinanie PS za pomocą Aspose.Page dla .NET
linktitle: Wycinek PS
second_title: Aspose.Page API .NET
description: Poznaj możliwości Aspose.Page dla .NET w tym samouczku krok po kroku dotyczącym przycinania dokumentów PostScript. Dowiedz się, jak bez wysiłku zwiększyć możliwości przetwarzania dokumentów.
type: docs
weight: 10
url: /pl/net/canvas-manipulation/clippingps/
---
## Wstęp

Witamy w kompleksowym samouczku dotyczącym wykorzystania Aspose.Page dla .NET do implementowania obcinania w dokumentach PostScript (PS). Ten samouczek poprowadzi Cię przez proces przycinania dokumentów PS przy użyciu Aspose.Page, potężnej biblioteki do pracy z różnymi formatami dokumentów w aplikacjach .NET.

## Warunki wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

- Praktyczna znajomość języka programowania C#.
-  Zainstalowana biblioteka Aspose.Page dla .NET. Możesz go pobrać[Tutaj](https://releases.aspose.com/page/net/).
- Zintegrowane środowisko programistyczne (IDE), takie jak Visual Studio.

## Importuj przestrzenie nazw

Rozpocznij od zaimportowania niezbędnych przestrzeni nazw do kodu C#:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Podzielmy teraz przykład na kilka kroków:

## Krok 1: Ustaw katalog dokumentów

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";
```

## Krok 2: Utwórz strumień wyjściowy dla dokumentu PostScript

```csharp
// Utwórz strumień wyjściowy dla dokumentu PostScript
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

## Krok 3: Utwórz opcje zapisu

```csharp
// Utwórz opcje zapisu z wartościami domyślnymi
PsSaveOptions options = new PsSaveOptions();
```

## Krok 4: Utwórz nowy 1-stronicowy dokument PS

```csharp
// Utwórz nowy 1-stronicowy dokument PS
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Krok 5: Utwórz ścieżkę grafiki z prostokąta

```csharp
// Utwórz ścieżkę graficzną z prostokąta
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

## Krok 6: Przycinanie według kształtu

```csharp
// Zapisz stan grafiki, aby powrócić do tego stanu po przekształceniu
document.WriteGraphicsSave();

//Przesuń bieżący stan grafiki o 100 punktów w prawo i 100 punktów w dół.
document.Translate(100, 100);

// Utwórz ścieżkę graficzną z okręgu
GraphicsPath circlePath = new GraphicsPath();
circlePath.AddEllipse(new RectangleF(50, 0, 200, 200));

// Dodaj przycinanie okręgiem do bieżącego stanu grafiki
document.Clip(circlePath);

// Ustaw farbę na bieżący stan grafiki
document.SetPaint(new SolidBrush(Color.Blue));

// Wypełnij prostokąt w bieżącym stanie grafiki (z przycięciem)
document.Fill(rectanglePath);

// Przywróć stan grafiki do poprzedniego (górnego) poziomu
document.WriteGraphicsRestore();
```

## Krok 7: Przesuń stan grafiki wyższego poziomu

```csharp
// Przesuń stan grafiki wyższego poziomu o 100 punktów w prawo i 100 punktów w dół.
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// Narysuj prostokąt w bieżącym stanie graficznym (bez przycięcia) nad przyciętym prostokątem
document.Draw(rectanglePath);
```

## Krok 8: Zamknij i zapisz dokument

```csharp
// Zamknij bieżącą stronę
document.ClosePage();

// Zapisz dokument
document.Save();
```

Teraz pomyślnie zaimplementowałeś wycinanie w dokumencie PostScript przy użyciu Aspose.Page dla .NET.

## Wniosek

W tym samouczku nauczyłeś się, jak używać Aspose.Page dla .NET do implementowania obcinania w dokumentach PostScript. Ta potężna biblioteka zapewnia bezproblemową i wydajną obsługę różnych formatów dokumentów w aplikacjach .NET.

## Często zadawane pytania

### P1: Czy mogę używać Aspose.Page dla .NET z innymi językami programowania?

O1: Aspose.Page jest przeznaczony głównie dla aplikacji .NET. Jednak Aspose udostępnia podobne biblioteki dla innych języków programowania.

### P2: Gdzie mogę znaleźć dodatkowe przykłady i dokumentację Aspose.Page dla .NET?

 Odpowiedź 2: Więcej przykładów i szczegółowej dokumentacji można znaleźć na stronie[Dokumentacja Aspose.Page](https://reference.aspose.com/page/net/).

### P3: Czy dostępna jest bezpłatna wersja próbna Aspose.Page dla .NET?

 O3: Tak, możesz uzyskać dostęp do bezpłatnej wersji próbnej Aspose.Page dla .NET[Tutaj](https://releases.aspose.com/).

### P4: Jak mogę uzyskać tymczasową licencję na Aspose.Page dla .NET?

 A4: Możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).

### P5: Gdzie mogę uzyskać pomoc lub omówić zapytania związane z Aspose.Page?

 A5: Odwiedź[Fora Aspose.Page](https://forum.aspose.com/c/page/39) za wsparcie społeczności i dyskusje.