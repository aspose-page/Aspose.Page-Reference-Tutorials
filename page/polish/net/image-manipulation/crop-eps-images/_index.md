---
date: 2026-03-16
description: Naucz się przycinać obrazy EPS i zmieniać rozmiar plików EPS w .NET przy
  użyciu Aspose.Page. Skorzystaj z tego przewodnika krok po kroku, aby łatwo przycinać
  i zmieniać rozmiar obrazów EPS.
linktitle: Crop EPS Images
second_title: Aspose.Page .NET API
title: Jak przyciąć obrazy EPS za pomocą Aspose.Page dla .NET
url: /pl/net/image-manipulation/crop-eps-images/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak przyciąć obrazy EPS za pomocą Aspose.Page dla .NET

## Wprowadzenie

Jeśli potrzebujesz dowiedzieć się, **jak przyciąć obrazy EPS** w aplikacji .NET, trafiłeś we właściwe miejsce. W tym samouczku przeprowadzimy Cię krok po kroku przez przycinanie i zmianę rozmiaru plików EPS przy użyciu potężnej biblioteki Aspose.Page dla .NET. Niezależnie od tego, czy udoskonalasz narzędzie raportujące, czy przygotowujesz grafikę dla usługi internetowej, opanowanie tej techniki zaoszczędzi Twój czas i zapewni wyniki o perfekcyjnej jakości pikseli.

## Szybkie odpowiedzi
- **Jaką bibliotekę używać do przycinania EPS?** Aspose.Page dla .NET  
- **Główna metoda?** `doc.CropEps(outputStream, newBoundingBox)`  
- **Czy mogę także zmienić rozmiar EPS?** Tak – użyj `ResizeEps` z calami, milimetrami lub procentami.  
- **Wymagania wstępne?** .NET (Framework 4.5+ / .NET Core 3.1+), zainstalowany Aspose.Page, plik EPS.  
- **Typowy czas implementacji?** Około 10 minut dla podstawowego przepływu przycinania‑i‑zmiany‑rozmiaru.

## Wymagania wstępne

Zanim przejdziesz do kodu, upewnij się, że masz:

- Praktyczną znajomość programowania w .NET.  
- Bibliotekę Aspose.Page dla .NET zainstalowaną. Jeśli jej nie masz, możesz pobrać ją [tutaj](https://releases.aspose.com/page/net/).  
- Przykładowy obraz EPS (w kodzie zamień `"input.eps"` na swoją rzeczywistą nazwę pliku).

## Importowanie przestrzeni nazw

Zacznijmy od zaimportowania przestrzeni nazw, które dają dostęp do klas obsługujących EPS.

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

## Jak przyciąć obrazy EPS – przewodnik krok po kroku

### Krok 1: Inicjalizacja `PsDocument`

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

Tworzymy instancję `PsDocument` z wejściowego strumienia EPS. Obiekt ten reprezentuje plik EPS w pamięci i udostępnia metody przycinania oraz zmiany rozmiaru.

### Krok 2: Pobranie oryginalnego Bounding Box

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

Bounding box określa bieżące wymiary płótna EPS. Znajomość tych wartości pomaga zdefiniować bezpieczny prostokąt przycięcia.

### Krok 3: Utworzenie strumienia wyjściowego

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

Otwieramy zapisywalny strumień, w którym zostanie zapisany przycięty EPS. Użycie bloku `using` zapewnia prawidłowe zamknięcie strumienia.

### Krok 4: Definicja nowego Bounding Box

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

Zastąp liczby współrzędnymi, które chcesz zachować. Upewnij się, że nowe wartości mieszczą się w oryginalnym bounding box; w przeciwnym razie operacja się nie powiedzie.

### Krok 5: Przycięcie i zapis EPS

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

Ten jedyny wiersz wykonuje przycięcie i zapisuje wynik do `output_crop.eps`. Metoda modyfikuje dokument w pamięci, więc w razie potrzeby możesz łańcuchowo wywoływać kolejne operacje.

## Zmiana rozmiaru obrazu EPS

Po przycięciu często zachodzi potrzeba zmiany rozmiaru EPS w celu wyświetlenia lub druku. Aspose.Page obsługuje trzy jednostki miary.

### Zmiana rozmiaru w calach

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

### Zmiana rozmiaru w milimetrach

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

### Zmiana rozmiaru w procentach

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

Każde wywołanie nadpisuje poprzedni wynik, więc jeśli potrzebujesz osobnych plików dla każdego rozmiaru, utwórz nowy strumień wyjściowy.

## Typowe problemy i rozwiązywanie

| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|-------|--------------------------|-------------|
| **Wartości bounding box poza zakresem** | Nowy prostokąt przekracza oryginalne wymiary | Sprawdź wartości `initialBoundingBox` i wybierz współrzędne mieszczące się w tym zakresie. |
| **Plik wyjściowy jest pusty** | Strumień wyjściowy nie został opróżniony lub zamknięty | Upewnij się, że blok `using` zakończył się przed dostępem do pliku, lub wywołaj `outputEpsStream.Flush()`. |
| **Nieoczekiwane skalowanie** | Mieszanie jednostek (np. cale vs. milimetry) | Zawsze podawaj właściwą wartość enum `Units`, która odpowiada używanym jednostkom. |

## FAQ

### P1: Czy mogę używać Aspose.Page dla .NET z innymi formatami obrazów?

Odp1: Aspose.Page koncentruje się głównie na obrazach EPS, ale Aspose oferuje różne biblioteki do obsługi innych formatów. Sprawdź ich dokumentację, aby dowiedzieć się o konkretnych formatach.

### P2: Jak mogę uzyskać tymczasową licencję dla Aspose.Page dla .NET?

Odp2: Odwiedź [ten link](https://purchase.aspose.com/temporary-license/), aby uzyskać tymczasową licencję do testów.

### P3: Czy istnieją ograniczenia co do rozmiaru obrazu, który mogę przetworzyć przy pomocy Aspose.Page dla .NET?

Odp3: Aspose.Page jest zaprojektowany do obsługi obrazów o różnych rozmiarach. Jednak wydajność może się różnić w zależności od złożoności obrazu.

### P4: Czy istnieje forum społecznościowe poświęcone dyskusjom o Aspose.Page?

Odp5: Tak, możesz uczestniczyć w społeczności Aspose.Page [tutaj](https://forum.aspose.com/c/page/39).

### P5: Gdzie znajdę szczegółową dokumentację Aspose.Page dla .NET?

Odp5: Zapoznaj się z dokumentacją [tutaj](https://reference.aspose.com/page/net/).

---

**Ostatnia aktualizacja:** 2026-03-16  
**Testowano z:** Aspose.Page 24.11 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}