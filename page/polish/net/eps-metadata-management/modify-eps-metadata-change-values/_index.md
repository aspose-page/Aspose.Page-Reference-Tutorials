---
title: Zmień wartości za pomocą Aspose.Page dla .NET
linktitle: Zmiana wartości
second_title: Aspose.Page API .NET
description: Opanuj manipulację plikami EPS za pomocą Aspose.Page dla .NET. Zmieniaj wartości metadanych XMP bez wysiłku.
type: docs
weight: 17
url: /pl/net/eps-metadata-management/modify-eps-metadata-change-values/
---
## Wstęp

W dynamicznym świecie przetwarzania dokumentów Aspose.Page dla .NET wyróżnia się jako potężne narzędzie, oferując programistom możliwość łatwego manipulowania plikami EPS. W tym samouczku zagłębimy się w proces zmiany wartości w plikach EPS przy użyciu Aspose.Page dla .NET. Niezależnie od tego, czy jesteś doświadczonym programistą, czy ciekawskim początkującym, ten przewodnik krok po kroku wyposaży Cię w umiejętności potrzebne do wydajnego modyfikowania metadanych XMP w plikach EPS.

## Warunki wstępne

Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

### 1. Aspose.Page dla biblioteki .NET

Upewnij się, że masz zainstalowaną bibliotekę Aspose.Page dla .NET w swoim środowisku programistycznym. Jeśli nie, możesz go pobrać[Tutaj](https://releases.aspose.com/page/net/).

### 2. Katalog dokumentów

Skonfiguruj katalog dla swoich dokumentów. Będzie to lokalizacja, w której przechowywane są pliki EPS.

Teraz, gdy mamy już ustalone wymagania wstępne, przejdźmy do kolejnych kluczowych kroków.

## Importuj przestrzenie nazw

W każdym projekcie .NET konieczne jest zaimportowanie niezbędnych przestrzeni nazw, aby móc korzystać z funkcjonalności Aspose.Page. Oto jak możesz to zrobić:

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

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";
// Zainicjuj strumień wejściowy pliku EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

## Krok 2: Utwórz instancję PsDocument ze strumienia

```csharp
//Utwórz instancję PsDocument ze strumienia
PsDocument document = new PsDocument(psStream);
```

Teraz, gdy jesteśmy już gotowi, przejdźmy do sedna naszego samouczka – zmiany wartości metadanych XMP w pliku EPS.

## Krok 3: Uzyskaj metadane XMP

```csharp
// Pobierz metadane XMP. Jeśli plik EPS nie zawiera metadanych XMP, otrzymamy nowy wypełniony wartościami z komentarzy do metadanych PS (%%Creator, %%CreateDate, %%Title itp.)
XmpMetadata xmp = document.GetXmpMetadata();
```

## Krok 4: Zmodyfikuj wartości metadanych XMP

Zmieńmy teraz niektóre kluczowe wartości w metadanych XMP:

### Krok 4.1: Zmień wartość ModifyDate

```csharp
// Zmień wartość ModifyDate
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

### Krok 4.2: Zmień wartość Twórcy

```csharp
// Zmień wartość Twórcy
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### Krok 4.3: Zmień wartość tytułu

```csharp
// Zmień wartość tytułu
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

Po dokonaniu tych zmian przejdźmy do ostatniego kroku - zapisania zmodyfikowanego pliku EPS.

## Krok 5: Zapisz plik EPS ze zmienionymi metadanymi XMP

### Krok 5.1: Utwórz strumień wyjściowy

```csharp
// Utwórz strumień wyjściowy
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

### Krok 5.2: Zapisz plik EPS

```csharp
// Zapisz plik EPS
document.Save(outPsStream);
```

Na koniec zamknij strumień wejściowy:

```csharp
finally
{
    psStream.Close();
}
```

Gratulacje! Pomyślnie zmodyfikowałeś wartości metadanych XMP w pliku EPS przy użyciu Aspose.Page dla .NET.

## Wniosek

W tym samouczku omówiliśmy płynny proces zmiany wartości w plikach EPS przy użyciu Aspose.Page dla .NET. Jako programista masz teraz do dyspozycji potężne narzędzie do wydajnej manipulacji dokumentami.

## Często zadawane pytania

### P1: Czy mogę używać Aspose.Page dla .NET z innymi formatami plików?

O1: Aspose.Page skupia się przede wszystkim na manipulacji plikami EPS. W przypadku innych formatów przejrzyj różnorodną gamę produktów Aspose.

### P2: Czy dostępna jest wersja próbna?

 Odpowiedź 2: Tak, możesz wypróbować Aspose.Page dla .NET w ramach bezpłatnej wersji próbnej[Tutaj](https://releases.aspose.com/).

### P3: Gdzie mogę znaleźć szczegółową dokumentację?

 Odpowiedź 3: Można znaleźć obszerną dokumentację[Tutaj](https://reference.aspose.com/page/net/).

### P4: Jak uzyskać licencję tymczasową?

 A4: Możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).

### P5: Czy mogę kupić Aspose.Page dla .NET?

 A5: Absolutnie! Odwiedź stronę zakupu[Tutaj](https://purchase.aspose.com/buy) dla opcji licencjonowania.