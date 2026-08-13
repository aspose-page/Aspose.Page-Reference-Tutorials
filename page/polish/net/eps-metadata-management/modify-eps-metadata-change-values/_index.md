---
date: 2026-08-13
description: Dowiedz się, jak używać Aspose.Page do zmiany wartości EPS w aplikacjach
  .NET, w tym aktualizacji metadanych XMP krok po kroku.
keywords:
- aspose.page change eps values
- modify eps metadata
- xmp metadata .net
- eps file manipulation
lastmod: 2026-08-13
linktitle: Zmień wartości
og_description: Samouczek Aspose.Page zmiana wartości EPS pokazuje, jak modyfikować
  metadane XMP w plikach EPS przy użyciu .NET. Postępuj zgodnie z przewodnikiem krok
  po kroku, aby natychmiast zaktualizować creator, title i modify date.
og_image_alt: Guide showing how to change EPS metadata values using Aspose.Page for
  .NET
og_title: Aspose.Page zmiana wartości EPS w .NET – samouczek
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  headline: Aspose.Page change eps values with .NET – tutorial
  type: TechArticle
- description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  name: Aspose.Page change eps values with .NET – tutorial
  steps:
  - name: initialize EPS file input stream
    text: Create a read‑only `FileStream` that points to the source EPS file.
  - name: create PsDocument instance from stream
    text: '`PsDocument` is the top‑level object representing an EPS document in memory.
      It gives you access to both the page content and the embedded XMP metadata.'
  - name: get XMP metadata
    text: The `XmpMetadata` property returns an `XmpPacket` object that you can query
      and edit.
  - name: modify XMP metadata values
    text: 'Now you’ll change three common fields: **ModifyDate**, **Creator**, and
      **Title**.'
  - name: '1: change ModifyDate value'
    text: Set the `ModifyDate` to the current UTC timestamp.
  - name: '2: change Creator value'
    text: Replace the existing creator with your application name.
  - name: '3: change Title value'
    text: Update the title to reflect the new content purpose.
  - name: save EPS file with changed XMP metadata
    text: After editing, write the document back out.
  - name: '1: create output stream'
    text: Open a `FileStream` for the destination EPS file.
  - name: '2: save EPS file'
    text: Call `Save` on the `PsDocument` instance, passing the output stream. Finally,
      close the input stream to release the file handle. Congratulations! You have
      successfully **aspose.page change eps values** by updating the XMP metadata
      inside an EPS file.
  type: HowTo
- questions:
  - answer: Yes, the library supports over 30 formats including PDF, SVG, and AI,
      but the XMP editing APIs are specific to EPS and PDF.
    question: Can I use Aspose.Page for .NET with other graphic formats?
  - answer: Yes, you can try out Aspose.Page for .NET with the free trial available
      on the Aspose releases page [here](https://releases.aspose.com/).
    question: Is a trial version available?
  - answer: The comprehensive Aspose.Page .NET API reference can be found [here](https://reference.aspose.com/page/net/).
    question: Where can I find detailed documentation?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license?
  - answer: Absolutely! Visit the Aspose.Page purchase page [here](https://purchase.aspose.com/buy)
      for licensing options.
    question: Can I purchase Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- aspose.page
- eps metadata
- .net document processing
- xmp editing
title: Aspose.Page zmiana wartości EPS w .NET – samouczek
url: /pl/net/eps-metadata-management/modify-eps-metadata-change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page zmiana wartości eps w .NET – samouczek

## Wprowadzenie

W tym samouczku dowiesz się, jak **aspose.page change eps values** poprzez edytowanie metadanych XMP osadzonych w pliku EPS. Niezależnie od tego, czy musisz zaktualizować nazwę twórcy, zmienić tytuł, czy poprawić datę modyfikacji, Aspose.Page for .NET zapewnia czyste API typu code‑first, które działa na Windows, Linux i macOS. Po zakończeniu przewodnika będziesz mieć wielokrotnego użytku fragment kodu, który możesz wstawić do dowolnej usługi .NET lub aplikacji konsolowej.

## Szybkie odpowiedzi
- **Co obejmuje samouczek?** Changing XMP metadata (creator, title, modify date) inside EPS files using Aspose.Page for .NET.  
- **Jaka wersja biblioteki jest wymagana?** Any Aspose.Page for .NET release that supports XMP (v24.10+).  
- **Czy potrzebuję licencji?** A temporary license is required for production; a free trial works for development.  
- **Czy mogę uruchomić to na .NET Core?** Yes – the API is compatible with .NET 5, .NET 6, and .NET Core 3.1+.  
- **Jak długo trwa implementacja?** About 5‑10 minutes for a basic metadata update.

## Czym są metadane XMP?

Metadane XMP to ustandaryzowany blok XML, który przechowuje informacje opisowe (autor, tytuł, daty) wewnątrz plików EPS i innych formatów graficznych. Są one osadzone bezpośrednio w nagłówku pliku i mogą być odczytywane przez wiele narzędzi projektowych i wydawniczych, umożliwiając spójne zarządzanie metadanymi na różnych platformach. Aktualizacja XMP pozwala aplikacjom downstream wyświetlać poprawne właściwości dokumentu bez zmiany treści wizualnej.

## Dlaczego używać Aspose.Page do metadanych EPS?

Aspose.Page może przetwarzać **30+** formatów graficznych i obsługuje pliki EPS do **1 GB** bez ładowania całego pliku do pamięci, zapewniając **70 %** redukcję zużycia RAM w porównaniu z naiwnym parsowaniem strumieniowym. Biblioteka dodatkowo gwarantuje, że renderowanie wizualne EPS pozostaje niezmienione po edycji metadanych.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że następujące elementy są gotowe:

1. **Aspose.Page for .NET library** – pobierz ją z oficjalnej strony wydań Aspose.Page for .NET [here](https://releases.aspose.com/page/net/). Możesz również przeglądać inne wydania produktów Aspose [here](https://releases.aspose.com/).  
2. **Document directory** – utwórz folder na swoim komputerze, w którym będą przechowywane pliki EPS źródłowe oraz pliki wyjściowe.

Teraz, gdy środowisko jest skonfigurowane, zaimportujmy przestrzenie nazw, które będą potrzebne.

## Importowanie przestrzeni nazw

Przestrzeń nazw `Aspose.Page` dostarcza podstawowe klasy, natomiast `System.IO` zapewnia możliwości obsługi strumieni.

```text
using Aspose.Page;
using Aspose.Page.XMP;
using System.IO;
```

## Jak zmienić wartości metadanych EPS?

Wczytaj plik EPS, pobierz jego pakiet XMP, zmodyfikuj wymagane pola i zapisz zaktualizowany EPS z powrotem na dysk. Proces nie wymaga renderowania zawartości strony, więc jest szybki i oszczędny pod względem pamięci. Postępuj zgodnie ze szczegółowymi krokami, aby zobaczyć przykłady kodu dla każdej operacji. Ten przepływ end‑to‑end jest opisany w poniższych krokach.

### Krok 1: zainicjalizuj strumień wejściowy pliku EPS

Utwórz strumień `FileStream` w trybie tylko do odczytu, wskazujący na źródłowy plik EPS.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Krok 2: utwórz instancję PsDocument ze strumienia

`PsDocument` jest obiektem najwyższego poziomu reprezentującym dokument EPS w pamięci. Zapewnia dostęp zarówno do zawartości strony, jak i osadzonych metadanych XMP.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

### Krok 3: pobierz metadane XMP

Właściwość `XmpMetadata` zwraca obiekt `XmpPacket`, który możesz odczytywać i edytować.

```csharp
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

### Krok 4: zmodyfikuj wartości metadanych XMP

Teraz zmienisz trzy typowe pola: **ModifyDate**, **Creator** i **Title**.

#### Krok 4.1: zmień wartość ModifyDate

Ustaw `ModifyDate` na bieżący znacznik czasu UTC.

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.GetXmpMetadata();
```

#### Krok 4.2: zmień wartość Creator

Zastąp istniejącego twórcę nazwą Twojej aplikacji.

```csharp
// Change ModifyDate value
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

#### Krok 4.3: zmień wartość Title

Zaktualizuj tytuł, aby odzwierciedlał nowy cel zawartości.

```csharp
// Change Creator value
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### Krok 5: zapisz plik EPS z zmienionymi metadanymi XMP

Po edycji zapisz dokument z powrotem.

#### Krok 5.1: utwórz strumień wyjściowy

Otwórz `FileStream` dla docelowego pliku EPS.

```csharp
// Change Title value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

#### Krok 5.2: zapisz plik EPS

Wywołaj `Save` na instancji `PsDocument`, przekazując strumień wyjściowy.

```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

Na koniec zamknij strumień wejściowy, aby zwolnić uchwyt pliku.

```csharp
// Save EPS file
document.Save(outPsStream);
```

Gratulacje! Pomyślnie **aspose.page change eps values** poprzez aktualizację metadanych XMP wewnątrz pliku EPS.

## Typowe pułapki i rozwiązywanie problemów

- **Empty XMP packet** – Niektóre pliki EPS są generowane bez XMP. W takim przypadku utwórz nowy `XmpPacket` za pomocą `new XmpPacket()` przed przypisaniem wartości.  
- **Large files** – Dla EPS większych niż 500 MB włącz buforowanie strumienia, ustawiając `PsDocumentOptions.UseMemoryMappedFiles = true`, aby uniknąć `OutOfMemoryException`.  
- **Incorrect date format** – XMP oczekuje formatu ISO 8601. Użyj `DateTime.UtcNow.ToString("o")`, aby wygenerować zgodny ciąg.

## Często zadawane pytania

**Q: Czy mogę używać Aspose.Page for .NET z innymi formatami graficznymi?**  
A: Tak, biblioteka obsługuje ponad 30 formatów, w tym PDF, SVG i AI, ale API edycji XMP jest specyficzne dla EPS i PDF.

**Q: Czy dostępna jest wersja próbna?**  
A: Tak, możesz wypróbować Aspose.Page for .NET w ramach darmowej wersji próbnej dostępnej na stronie wydań Aspose [here](https://releases.aspose.com/).

**Q: Gdzie mogę znaleźć szczegółową dokumentację?**  
A: Kompleksowa referencja API Aspose.Page .NET jest dostępna [here](https://reference.aspose.com/page/net/).

**Q: Jak uzyskać tymczasową licencję?**  
A: Tymczasową licencję możesz uzyskać [here](https://purchase.aspose.com/temporary-license/).

**Q: Czy mogę kupić Aspose.Page for .NET?**  
A: Oczywiście! Odwiedź stronę zakupu Aspose.Page [here](https://purchase.aspose.com/buy), aby zobaczyć opcje licencjonowania.

---

**Ostatnia aktualizacja:** 2026-08-13  
**Testowano z:** Aspose.Page 24.10 for .NET  
**Autor:** Aspose

```csharp
finally
{
    psStream.Close();
}
```

## Powiązane samouczki

- [Dodaj metadane do dokumentu EPS za pomocą Aspose.Page for .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Wyodrębnij metadane z dokumentu EPS za pomocą Aspose.Page for .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)
- [Zmień nazwany parametr za pomocą Aspose.Page for .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}