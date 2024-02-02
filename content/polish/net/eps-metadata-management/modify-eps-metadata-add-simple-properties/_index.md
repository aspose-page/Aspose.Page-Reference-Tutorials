---
title: Dodaj proste właściwości za pomocą Aspose.Page dla .NET
linktitle: Dodaj proste właściwości
second_title: Aspose.Page API .NET
description: Ulepsz pliki EPS za pomocą Aspose.Page dla .NET. Bez wysiłku dodawaj proste właściwości, aby uzyskać dostosowane metadane dokumentu.
type: docs
weight: 14
url: /pl/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/
---
## Wstęp

W dziedzinie manipulacji i ulepszania dokumentów Aspose.Page dla .NET okazuje się potężnym narzędziem, zapewniającym programistom możliwość płynnego dodawania i modyfikowania metadanych XMP w plikach EPS. Ten samouczek poprowadzi Cię przez proces dodawania prostych właściwości do pliku EPS przy użyciu Aspose.Page dla .NET.

## Warunki wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

1.  Aspose.Page dla .NET: Upewnij się, że masz zainstalowany Aspose.Page dla .NET w swoim środowisku programistycznym. Jeśli nie, możesz go pobrać[Tutaj](https://releases.aspose.com/page/net/).

2.  Katalog dokumentów: skonfiguruj katalog do przechowywania plików EPS. Zaktualizuj`dataDir` zmienną w podanym fragmencie kodu ze ścieżką do katalogu dokumentów.

## Importuj przestrzenie nazw

Aby rozpocząć, zaimportuj niezbędne przestrzenie nazw, aby umożliwić komunikację z Aspose.Page dla .NET. Dodaj następujące wiersze na początku pliku kodu:

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
// ExStart:1
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";
// Zainicjuj strumień wejściowy pliku EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//Utwórz instancję PsDocument ze strumienia
PsDocument document = new PsDocument(psStream);
```

## Krok 2: Uzyskaj metadane XMP

```csharp
// Pobierz metadane XMP. Jeśli plik EPS nie zawiera metadanych XMP, otrzymamy nowy wypełniony wartościami z komentarzy do metadanych PS (%%Creator, %%CreateDate, %%Title itp.)
XmpMetadata xmp = document.GetXmpMetadata();
```

## Krok 3: Zmień wartości metadanych XMP

```csharp
// Zmień wartości metadanych XMP
DateTime now = DateTime.UtcNow;

// Dodaj właściwość Integer
xmp.Add("xmp:Intg1", new XmpValue(111));

// Dodaj właściwość DateTime
xmp.Add("xmp:Date1", new XmpValue(now));

// Dodaj właściwość Double
xmp.Add("xmp:Double1", new XmpValue(111.11D));

//Dodaj właściwość String
xmp.Add("xmp:String1", new XmpValue("ABC"));
```

## Krok 4: Zapisz plik EPS ze zmienionymi metadanymi XMP

```csharp
// Zapisz plik EPS ze zmienionymi metadanymi XMP

// Utwórz strumień wyjściowy
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_simple_props_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Zapisz plik EPS
    document.Save(outPsStream);
}
```

## Krok 5: Zamknij FileStream

```csharp
finally
{
    psStream.Close();
}
```

Wykonując poniższe kroki, możesz bez wysiłku włączyć proste właściwości do plików EPS za pomocą Aspose.Page dla .NET.

## Wniosek

Podsumowując, Aspose.Page dla .NET okazuje się nieocenionym nabytkiem dla programistów pragnących ulepszyć pliki EPS za pomocą niestandardowych metadanych XMP. Dodając proste właściwości, możesz dostosowywać i wzbogacać swoje dokumenty, aby spełniały określone wymagania, otwierając świat możliwości manipulacji dokumentami.

## Często zadawane pytania

### P1: Czy Aspose.Page dla .NET jest kompatybilny ze wszystkimi plikami EPS?

O1: Aspose.Page dla .NET obsługuje szeroką gamę plików EPS. Jednakże zgodność może się różnić w zależności od złożoności i struktury poszczególnych plików.

### P2: Czy mogę modyfikować istniejące metadane XMP za pomocą Aspose.Page dla .NET?

A2: Absolutnie! Jak pokazano w tym samouczku, możesz łatwo zmienić istniejące wartości metadanych XMP lub dodać nowe w zależności od potrzeb.

### P3: Czy istnieją jakieś ograniczenia dotyczące typów właściwości, które mogę dodać?

O3: Aspose.Page dla .NET obsługuje różne typy danych dla właściwości, w tym liczby całkowite, daty, liczby podwójne i ciągi znaków. Masz elastyczność w wyborze odpowiedniego typu metadanych.

### P4: Jak mogę uzyskać pomoc techniczną dla Aspose.Page dla .NET?

 A4: Aby uzyskać pomoc techniczną, odwiedź stronę[Forum Aspose.Page](https://forum.aspose.com/c/page/39) lub eksploruj[dokumentacja](https://reference.aspose.com/page/net/) w celu uzyskania kompleksowych wskazówek.

### P5: Czy dostępna jest bezpłatna wersja próbna Aspose.Page dla .NET?

 Odpowiedź 5: Tak, możesz uzyskać dostęp do bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).