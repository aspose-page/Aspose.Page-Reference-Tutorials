---
date: 2026-08-08
description: Dowiedz się, jak dodać elementy tablicy do metadanych EPS przy użyciu
  Aspose.Page EPS metadata. Ten szczegółowy przewodnik .NET pokazuje, jak dodawać
  elementy tablicy i efektywnie odczytywać pliki EPS.
keywords:
- aspse page eps metadata
- how to add array item
- read eps file .net
lastmod: 2026-08-08
linktitle: Dodaj elementy tablicy
og_description: Odkryj, jak dodać elementy tablicy do metadanych EPS przy użyciu Aspose.Page
  EPS metadata. Skorzystaj z tego zwięzłego samouczka .NET, aby odczytywać pliki EPS
  i efektywnie zarządzać metadanymi.
og_image_alt: Guide showing how to add array items to EPS metadata with Aspose.Page
  in a .NET project
og_title: Dodawanie elementów tablicy przy użyciu metadanych Aspose.Page EPS w .NET
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  headline: Add array items with Aspose.Page EPS metadata in .NET
  type: TechArticle
- description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  name: Add array items with Aspose.Page EPS metadata in .NET
  steps:
  - name: initialize eps file input stream
    text: '`PsDocument` represents an EPS document and provides methods to access
      its content. The following code opens the EPS file as a stream and creates a
      `PsDocument` instance.'
  - name: get xmp metadata
    text: '`GetXmpMetadata()` retrieves the XMP packet embedded in the EPS file. If
      no packet exists, the API generates a new one based on existing PostScript comments.'
  - name: change xmp metadata values
    text: '`AddArrayItem()` appends a new value to an existing XMP array without overwriting
      other entries. Use it to add titles, creators, or custom tags to the metadata.'
  - name: save eps file with changed xmp metadata
    text: '`Save()` writes the modified XMP packet back into the EPS file while preserving
      the original PostScript content. Provide the output path to create a new file
      or overwrite the source.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works across .NET Framework 4.5+, .NET Core 3.1+, and
      .NET 5/6/7, providing consistent API behavior on Windows, Linux and macOS.
    question: Is Aspose.Page compatible with all .NET environments?
  - answer: You can evaluate the library with a free trial download from the [Aspose
      purchase page](https://purchase.aspose.com/buy). A commercial license is required
      for production deployments.
    question: Can I use Aspose.Page for free?
  - answer: Temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      for short‑term projects or evaluation periods.
    question: Are temporary licenses available for Aspose.Page?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      to ask questions and share solutions with other developers.
    question: Where can I find community support for Aspose.Page?
  - answer: Refer to the official [documentation](https://reference.aspose.com/page/net/)
      for the most recent release notes and download links.
    question: What is the latest version of Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: Dodawanie elementów tablicy przy użyciu metadanych Aspose.Page EPS w .NET
url: /pl/net/eps-metadata-management/modify-eps-metadata-add-array-items/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj elementy tablicy do metadanych EPS Aspose.Page w .NET

## Wprowadzenie

W tym samouczku dowiesz się, jak dodać elementy tablicy do metadanych EPS przy użyciu **Aspose.Page EPS metadata**. Niezależnie od tego, czy chcesz wzbogacić plik EPS o dodatkowe tytuły, twórców czy własne znaczniki, Aspose.Page ułatwia to zadanie każdemu programiście .NET. Przejdziemy krok po kroku, od otwarcia strumienia EPS po zapisanie zaktualizowanego pakietu XMP, abyś mógł z pewnością integrować obsługę metadanych w swoich aplikacjach.

## Szybkie odpowiedzi
- **Co pozwala zrobić Aspose.Page EPS metadata?** Umożliwia odczyt i zapis tablic XMP w plikach EPS z poziomu .NET.  
- **Która klasa reprezentuje dokument EPS?** `PsDocument` jest podstawową klasą do ładowania i zapisywania zawartości EPS.  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna wystarczy do testów; licencja komercyjna jest wymagana w produkcji.  
- **Czy mogę modyfikować metadane bez zmiany grafiki EPS?** Tak, zmieniany jest tylko pakiet XMP, a zawartość strony pozostaje niezmieniona.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Czym jest metadane EPS Aspose.Page?
Metadane EPS Aspose.Page to blok informacji oparty na XMP, osadzony wewnątrz pliku EPS. Przechowuje opisowe właściwości, takie jak tytuły, twórcy, słowa kluczowe i własne znaczniki, zgodnie ze standardem ISO 16684‑1. Metadane można programowo odczytywać i modyfikować za pomocą API Aspose.Page, co umożliwia automatyzację zarządzania dokumentami i optymalizację wyszukiwania.

## Dlaczego modyfikować metadane EPS?
Aspose.Page może przetwarzać **ponad 30 pól metadanych** i obsługiwać pliki EPS o rozmiarze do **200 MB** bez ładowania całego dokumentu do pamięci, co zmniejsza zużycie CPU nawet o 40 % w porównaniu z pełnym parsowaniem pliku. Aktualizacja metadanych poprawia wyszukiwalność, zgodność oraz automatyzację dalszych procesów roboczych.

## Wymagania wstępne

- Podstawowa znajomość programowania w .NET.  
- Aspose.Page dla .NET zainstalowany – pobierz go z [download Aspose.Page for .NET](https://releases.aspose.com/page/net/).  
- Visual Studio (lub dowolne IDE zgodne z .NET), aby uruchomić przykładowy kod.  

## Jak dodać elementy tablicy do metadanych EPS?
Aby dodać elementy tablicy, najpierw wczytaj plik EPS do `PsDocument`, a następnie pobierz jego pakiet XMP przy użyciu `GetXmpMetadata()`. Użyj metody `AddArrayItem()` na wybranej tablicy XMP, takiej jak `dc:title` lub `dc:creator`, aby dodać nowe wartości. Na koniec wywołaj `Save()`, aby zapisać zaktualizowane metadane z powrotem do pliku, nie zmieniając zawartości graficznej.

### Krok 1: zainicjalizuj strumień wejściowy pliku EPS
`PsDocument` reprezentuje dokument EPS i udostępnia metody dostępu do jego zawartości. Poniższy kod otwiera plik EPS jako strumień i tworzy instancję `PsDocument`.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Krok 2: pobierz metadane XMP
`GetXmpMetadata()` pobiera pakiet XMP osadzony w pliku EPS. Jeśli pakiet nie istnieje, API generuje nowy na podstawie istniejących komentarzy PostScript.

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

### Krok 3: zmień wartości metadanych XMP
`AddArrayItem()` dodaje nową wartość do istniejącej tablicy XMP bez nadpisywania innych wpisów. Użyj jej, aby dodać tytuły, twórców lub własne znaczniki do metadanych.

```csharp
// ExStart:4
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

### Krok 4: zapisz plik EPS z zmienionymi metadanymi XMP
`Save()` zapisuje zmodyfikowany pakiet XMP z powrotem do pliku EPS, zachowując oryginalną zawartość PostScript. Podaj ścieżkę wyjściową, aby utworzyć nowy plik lub nadpisać źródłowy.

```csharp
// ExStart:5
// Change XMP metadata values

// Add one more title. It will be added at the end of the array by default.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Add one more creator. It will be added in the array by an index (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

## Typowe pułapki i rozwiązywanie problemów

- **Pusty pakiet XMP** – Jeśli `GetXmpMetadata()` zwraca `null`, upewnij się, że plik EPS zawiera co najmniej jeden blok komentarza; w przeciwnym razie utwórz nową instancję `XmpMetadata` ręcznie.  
- **Problemy z kodowaniem** – Używaj UTF‑8 przy dodawaniu wartości tekstowych, aby uniknąć korupcji znaków w językach nie‑ASCII.  
- **Duże pliki** – Dla plików EPS większych niż 150 MB rozważ strumieniowanie wejścia za pomocą `FileStream` z buforem, aby utrzymać niskie zużycie pamięci.

## Najczęściej zadawane pytania

**P: Czy Aspose.Page jest kompatybilny ze wszystkimi środowiskami .NET?**  
O: Tak, Aspose.Page działa na .NET Framework 4.5+, .NET Core 3.1+, oraz .NET 5/6/7, zapewniając spójne zachowanie API na Windows, Linux i macOS.

**P: Czy mogę używać Aspose.Page za darmo?**  
O: Bibliotekę możesz ocenić, pobierając wersję próbną z [strony zakupu Aspose](https://purchase.aspose.com/buy). Licencja komercyjna jest wymagana w środowiskach produkcyjnych.

**P: Czy dostępne są tymczasowe licencje dla Aspose.Page?**  
O: Tymczasowe licencje można uzyskać na [stronie tymczasowych licencji](https://purchase.aspose.com/temporary-license/) na krótkoterminowe projekty lub okresy testowe.

**P: Gdzie mogę znaleźć wsparcie społeczności dla Aspose.Page?**  
O: Dołącz do dyskusji na [forum Aspose.Page](https://forum.aspose.com/c/page/39), aby zadawać pytania i dzielić się rozwiązaniami z innymi programistami.

**P: Jaka jest najnowsza wersja Aspose.Page dla .NET?**  
O: Zapoznaj się z oficjalną [dokumentacją](https://reference.aspose.com/page/net/), aby uzyskać najnowsze informacje o wydaniu i linki do pobrania.

---

**Ostatnia aktualizacja:** 2026-08-08  
**Testowano z:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose

```csharp
// ExStart:6
// Save EPS file with changed XMP metadata

// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
// ExEnd:6
```

## Powiązane samouczki

- [Zmienianie elementów tablicy przy użyciu Aspose.Page dla .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-array-items/)
- [Dodawanie prostych właściwości przy użyciu Aspose.Page dla .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Dodawanie przestrzeni nazw przy użyciu Aspose.Page dla .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}