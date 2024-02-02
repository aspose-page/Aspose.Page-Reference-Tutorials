---
title: Zmień rozmiar obrazów EPS za pomocą Aspose.Page dla .NET
linktitle: Zmień rozmiar obrazów EPS
second_title: Aspose.Page API .NET
description: Poznaj bezproblemowy proces zmiany rozmiaru obrazów EPS w .NET przy użyciu Aspose.Page. Osiągnij precyzję w punktach, calach, milimetrach i procentach bez wysiłku.
type: docs
weight: 11
url: /pl/net/image-manipulation/resize-eps-images/
---
## Wstęp

Czy chcesz płynnie zmieniać rozmiar obrazów EPS za pomocą Aspose.Page dla .NET? Ten samouczek to kompleksowy przewodnik umożliwiający łatwe manipulowanie rozmiarem obrazów EPS w różnych jednostkach, takich jak punkty, cale, milimetry i procenty. Aspose.Page dla .NET zapewnia potężny zestaw narzędzi, a w tym samouczku przeprowadzimy Cię krok po kroku przez proces.

## Warunki wstępne

Zanim zagłębisz się w magię zmiany rozmiaru, upewnij się, że spełnione są następujące wymagania wstępne:

-  Biblioteka Aspose.Page dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Page dla .NET. Można go pobrać z[Tutaj](https://releases.aspose.com/page/net/).

- Katalog dokumentów: Utwórz katalog, w którym będziesz przechowywać wejściowy plik EPS i pliki wyjściowe o zmienionym rozmiarze.

Teraz, gdy już wszystko skonfigurowałeś, przystąpmy do importowania niezbędnych przestrzeni nazw i zagłębiamy się w przewodnik krok po kroku.

## Importuj przestrzenie nazw

W projekcie .NET rozpocznij od zaimportowania niezbędnych przestrzeni nazw do pracy z Aspose.Page. Dodaj następujący kod na początku pliku:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

## Krok 1: Zmiana rozmiaru w punktach

Zacznijmy od zmiany rozmiaru obrazu EPS w punktach. Punkty są standardową jednostką miary w branży poligraficznej.

```csharp
public static void ResizeInPoints()
{
    // Twój katalog dokumentów
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_points.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(oldSize.Width * 2, oldSize.Height * 2), Units.Points);
        }
    }
}
```

## Krok 2: Zmiana rozmiaru w calach

Teraz zmieńmy rozmiar obrazu EPS w calach, popularnej jednostce używanej w projektowaniu graficznym.

```csharp
public static void ResizeInInches()
{
    // Twój katalog dokumentów
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_inches.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
        }
    }
}
```

## Krok 3: Zmiana rozmiaru w milimetrach

Zmieńmy teraz rozmiar obrazu EPS w milimetrach, kolejnej szeroko stosowanej jednostce w projektowaniu i drukowaniu.

```csharp
public static void ResizeInMillimeters()
{
    // Twój katalog dokumentów
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_mms.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
        }
    }
}
```

## Krok 4: Zmiana rozmiaru w procentach

Na koniec zmieńmy rozmiar obrazu EPS za pomocą wartości procentowych, zapewniając elastyczne podejście do dostosowywania rozmiaru obrazu.

```csharp
public static void ResizeInPercents()
{
    // Twój katalog dokumentów
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_percents.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
        }
    }
}
```

Możesz zintegrować te metody ze swoim projektem, a będziesz mógł łatwo zmieniać rozmiar obrazów EPS. Eksperymentuj z różnymi jednostkami, aby osiągnąć pożądane wymiary.

## Wniosek

Gratulacje! Opanowałeś sztukę zmiany rozmiaru obrazów EPS za pomocą Aspose.Page dla .NET. Ta potężna biblioteka otwiera świat możliwości manipulowania grafiką wektorową. Niezależnie od tego, czy projektujesz na potrzeby mediów drukowanych, czy cyfrowych, Aspose.Page umożliwia osiągnięcie precyzyjnych i dostosowanych do indywidualnych potrzeb wyników.

## Często zadawane pytania

### P1: Czy mogę jednocześnie zmieniać rozmiar wielu obrazów EPS?

Odpowiedź 1: Tak, możesz przeglądać kolekcję plików EPS, stosując odpowiednio metody zmiany rozmiaru.

### P2: Czy Aspose.Page jest kompatybilny z innymi formatami obrazów?

O2: Aspose.Page koncentruje się głównie na formatach PostScript i EPS. W przypadku innych formatów obrazów rozważ użycie Aspose.Imaging.

### P3: Czy istnieją jakieś kwestie licencyjne dotyczące projektów komercyjnych?

 Odpowiedź 3: Tak, upewnij się, że masz ważną licencję. Odwiedzać[Tutaj](https://purchase.aspose.com/buy) w celu uzyskania szczegółów licencji.

### P4: Czy mogę wypróbować Aspose.Page przed zakupem?

 A4: Absolutnie! Możesz skorzystać z bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).

### P5: Gdzie mogę szukać dodatkowej pomocy lub omówić problemy?

 A5: Odwiedź[Forum Aspose.Page](https://forum.aspose.com/c/page/39) aby nawiązać kontakt ze społecznością i uzyskać pomoc.