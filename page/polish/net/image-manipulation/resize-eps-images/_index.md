---
date: 2026-03-03
description: Dowiedz się, jak zmienić rozmiar obrazów EPS w .NET przy użyciu Aspose.Page
  – krok po kroku przewodnik, jak zmieniać rozmiar EPS przy użyciu punktów, cali,
  milimetrów lub procentów.
linktitle: Resize EPS Images
second_title: Aspose.Page .NET API
title: Jak zmienić rozmiar obrazów EPS przy użyciu Aspose.Page dla .NET
url: /pl/net/image-manipulation/resize-eps-images/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak zmienić rozmiar obrazów EPS przy użyciu Aspose.Page dla .NET

## Wprowadzenie

Szukasz **jak zmienić rozmiar EPS** obrazów płynnie przy użyciu Aspose.Page dla .NET? Ten samouczek jest Twoim kompleksowym przewodnikiem, który pozwoli Ci bez wysiłku manipulować rozmiarem obrazów EPS w różnych jednostkach, takich jak punkty, cale, milimetry i procenty. Aspose.Page dla .NET oferuje potężny zestaw narzędzi, a w tym samouczku przeprowadzimy Cię krok po kroku przez cały proces.

## Szybkie odpowiedzi
- **Jaką bibliotekę obsługuje zmiana rozmiaru EPS?** Aspose.Page for .NET  
- **Jakie jednostki są obsługiwane?** Points, Inches, Millimeters, and Percents  
- **Czy potrzebuję licencji do produkcji?** Yes – a commercial license is required  
- **Czy mogę zmienić rozmiar wielu plików jednocześnie?** Absolutely – just loop through the files  
- **Czy .NET Core jest obsługiwany?** Yes, the API works with .NET Framework and .NET Core  

## Co to jest zmiana rozmiaru EPS?
Encapsulated PostScript (EPS) jest formatem grafiki wektorowej powszechnie używanym w procesach drukowania i projektowania. Zmiana rozmiaru pliku EPS modyfikuje jego ramkę ograniczającą bez rasteryzacji grafiki, zachowując ostrość przy dowolnej skali.

## Dlaczego zmieniać rozmiar obrazów EPS?
- **Utrzymaj jakość druku:** Skalowanie wektorowe zachowuje ostre krawędzie.  
- **Dopasuj wymagania układu:** Dostosuj wymiary do rozmiarów strony lub płótna.  
- **Automatyzuj zadania wsadowe:** Programowo zmieniaj rozmiar dziesiątek plików w ciągu kilku sekund.  

## Wymagania wstępne

Zanim zanurzysz się w magię zmiany rozmiaru, upewnij się, że masz spełnione następujące wymagania:

- Aspose.Page for .NET Library: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Page for .NET. Możesz ją pobrać [tutaj](https://releases.aspose.com/page/net/).

- Document Directory: Utwórz katalog, w którym będziesz przechowywać plik wejściowy EPS oraz wyjściowe pliki o zmienionym rozmiarze.

Teraz, gdy wszystko jest gotowe, przejdźmy do importowania niezbędnych przestrzeni nazw i zagłębmy się w przewodnik krok po kroku.

## Importowanie przestrzeni nazw

W swoim projekcie .NET rozpocznij od zaimportowania niezbędnych przestrzeni nazw, aby pracować z Aspose.Page. Dodaj poniższy kod na początku swojego pliku:

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

## Jak zmienić rozmiar EPS w punktach

Punkty są standardową jednostką miary w branży drukarskiej. Poniższy przykład podwaja oryginalną szerokość i wysokość.

```csharp
public static void ResizeInPoints()
{
    // Your Document Directory
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

## Jak zmienić rozmiar EPS w calach

Cale są często używane przez grafików przy przygotowywaniu materiałów do druku.

```csharp
public static void ResizeInInches()
{
    // Your Document Directory
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

## Jak zmienić rozmiar EPS w milimetrach

Milimetry są powszechne w regionach korzystających z systemu metrycznego.

```csharp
public static void ResizeInMillimeters()
{
    // Your Document Directory
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

## Jak zmienić rozmiar EPS przy użyciu procentów

Skalowanie oparte na procentach pozwala zmienić rozmiar obrazu w stosunku do jego pierwotnego rozmiaru.

```csharp
public static void ResizeInPercents()
{
    // Your Document Directory
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

Śmiało integruj te metody w swoim projekcie, a zmiana rozmiaru obrazów EPS stanie się dziecinnie prosta. Eksperymentuj z różnymi jednostkami, aby uzyskać pożądane wymiary.

## Częste problemy i rozwiązania
- **Plik nie znaleziony:** Zweryfikuj, że `dataDir` wskazuje na właściwy folder i że `input.eps` istnieje.  
- **Nieoczekiwany rozmiar:** Pamiętaj, że `Units.Percents` oczekuje wartości takich jak 150 dla 150 % pierwotnego rozmiaru.  
- **Wyjątek licencyjny:** Jeśli pojawi się błąd licencji, upewnij się, że prawidłowy plik licencji Aspose.Page został załadowany przed utworzeniem `PsDocument`.

## Zakończenie

Gratulacje! Opanowałeś **jak zmienić rozmiar EPS** przy użyciu Aspose.Page dla .NET. Ta potężna biblioteka otwiera świat możliwości manipulacji grafiką wektorową. Niezależnie od tego, czy projektujesz dla druku, czy mediów cyfrowych, Aspose.Page umożliwia osiągnięcie precyzyjnych i spersonalizowanych rezultatów.

## FAQ

### P1: Czy mogę zmienić rozmiar wielu obrazów EPS jednocześnie?

A1: Tak, możesz przejść pętlą przez kolekcję plików EPS, stosując odpowiednio metody zmiany rozmiaru.

### P2: Czy Aspose.Page jest kompatybilny z innymi formatami obrazów?

A2: Aspose.Page koncentruje się głównie na formatach PostScript i EPS. Dla innych formatów obrazów rozważ użycie Aspose.Imaging.

### P3: Czy istnieją kwestie licencyjne dla projektów komercyjnych?

A3: Tak, upewnij się, że posiadasz ważną licencję. Szczegóły licencjonowania znajdziesz [tutaj](https://purchase.aspose.com/buy).

### P4: Czy mogę wypróbować Aspose.Page przed zakupem?

A4: Oczywiście! Bezpłatną wersję próbną możesz pobrać [tutaj](https://releases.aspose.com/).

### P5: Gdzie mogę uzyskać dodatkową pomoc lub dyskutować o problemach?

A5: Odwiedź [forum Aspose.Page](https://forum.aspose.com/c/page/39), aby połączyć się ze społecznością i uzyskać wsparcie.

## Najczęściej zadawane pytania

**P: Czy ten kod działa z .NET Core 6?**  
A: Tak. API jest kompatybilne z .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ oraz .NET 6+.

**P: Jak mogę zachować oryginalny profil kolorów?**  
A: Metoda `ResizeEps` nie zmienia danych kolorystycznych; zmienia jedynie ramkę ograniczającą.

**P: Czy możliwe jest zmienienie rozmiaru EPS bez ładowania całego pliku do pamięci?**  
A: Użycie strumienia, jak pokazano, utrzymuje niskie zużycie pamięci; dokument jest przetwarzany w locie.

**P: Czy mogę łączyć wiele operacji zmiany rozmiaru?**  
A: Oczywiście. Wywołuj `ResizeEps` kolejno na tej samej instancji `PsDocument`.

**P: Co się dzieje z osadzonymi obrazami wewnątrz EPS?**  
A: Są one skalowane proporcjonalnie wraz z zawartością wektorową, zachowując jakość.

---

**Ostatnia aktualizacja:** 2026-03-03  
**Testowano z:** Aspose.Page 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}