---
title: Dodaj nazwaną wartość za pomocą Aspose.Page
linktitle: Dodaj nazwaną wartość
second_title: Aspose.Page API .NET
description: Dowiedz się, jak dodawać nazwane wartości do plików EPS w .NET przy użyciu Aspose.Page. Ten kompleksowy samouczek przeprowadzi Cię przez proces krok po kroku.
type: docs
weight: 12
url: /pl/net/eps-metadata-management/modify-eps-metadata-add-named-value/
---
## Wstęp

W obszarze przetwarzania dokumentów w .NET Aspose.Page wyróżnia się jako potężne narzędzie do obsługi plików EPS. Aspose.Page umożliwia programistom manipulowanie metadanymi XMP, ułatwiając zadania takie jak dodawanie nazwanych wartości. Ten samouczek poprowadzi Cię krok po kroku przez proces dodawania nazwanych wartości do pliku EPS przy użyciu Aspose.Page.

## Warunki wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

- Podstawowa znajomość języka programowania C#.
- Zainstalowane zintegrowane środowisko programistyczne (IDE), takie jak Visual Studio.
-  Aspose.Page dla biblioteki .NET. Jeśli nie jest zainstalowany, możesz go pobrać z[Tutaj](https://releases.aspose.com/page/net/).

## Importuj przestrzenie nazw

Najpierw zaimportujmy niezbędne przestrzenie nazw do kodu C#. Te przestrzenie nazw są niezbędne do uzyskania dostępu do funkcjonalności zapewnianych przez Aspose.Page:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Krok 1: Zainicjuj strumień wejściowy pliku EPS

 Początkowy krok polega na zainicjowaniu strumienia wejściowego dla pliku EPS. Zastępować`"Your Document Directory"` ze ścieżką do katalogu dokumentów:

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Krok 2: Uzyskaj metadane XMP

Pobierz metadane XMP z pliku EPS. Jeżeli w pliku EPS brakuje metadanych XMP, zostanie utworzony nowy, wypełniony wartościami z komentarzy do metadanych PS:

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## Krok 3: Zmień wartości metadanych XMP

Teraz wprowadźmy zmiany w metadanych XMP. W tym przykładzie dodamy nazwaną wartość do struktury „xmpTPg:MaxPageSize”:

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## Krok 4: Zapisz plik EPS ze zmienionymi metadanymi XMP

Zapisz plik EPS ze zaktualizowanymi metadanymi XMP. Utwórz strumień wyjściowy i zapisz zmodyfikowany plik EPS:

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## Wniosek

Gratulacje! Pomyślnie dodałeś nazwaną wartość do pliku EPS przy użyciu Aspose.Page w .NET. Ten samouczek przeprowadził Cię przez najważniejsze kroki, pokazując prostotę i skuteczność Aspose.Page w manipulowaniu dokumentami.

## Często zadawane pytania

### P1: Czy Aspose.Page jest kompatybilny z różnymi wersjami plików EPS?

Odpowiedź 1: Aspose.Page obsługuje różne wersje plików EPS, zapewniając kompatybilność z szeroką gamą dokumentów.

### P2: Czy mogę używać Aspose.Page do projektów komercyjnych?

 Odpowiedź 2: Tak, Aspose.Page jest dostarczany z licencją komercyjną i możesz ją kupić[Tutaj](https://purchase.aspose.com/buy).

### P3: Czy dostępna jest bezpłatna wersja próbna Aspose.Page?

 Odpowiedź 3: Tak, możesz przeglądać Aspose.Page w ramach bezpłatnej wersji próbnej[Tutaj](https://releases.aspose.com/).

### P4: Jak mogę uzyskać wsparcie lub połączyć się ze społecznością Aspose?

 A4: Odwiedź[Forum Aspose.Page](https://forum.aspose.com/c/page/39) aby uzyskać wsparcie i nawiązać kontakt ze społecznością.

### P5: Co to jest licencja tymczasowa i jak mogę ją uzyskać?

 Odpowiedź 5: Jeśli potrzebujesz tymczasowej licencji do celów testowania lub oceny, możesz ją nabyć[Tutaj](https://purchase.aspose.com/temporary-license/).