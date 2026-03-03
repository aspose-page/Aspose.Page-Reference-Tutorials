---
date: 2026-03-03
description: Dowiedz się, jak ustawić niestandardowy rozmiar strony i dodać drugą
  stronę PS do dokumentu PostScript przy użyciu Aspose.Page dla .NET.
linktitle: Add Page to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Ustaw niestandardowy rozmiar strony w dokumencie PS przy użyciu Aspose.Page
url: /pl/net/page-manipulation/add-page-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj stronę do dokumentu PostScript (PS) przy użyciu Aspose.Page

## Introduction

W programowaniu .NET możliwość **ustawienia własnego rozmiaru strony** i **dodania drugiej strony PS** do dokumentu PostScript (PS) daje precyzyjną kontrolę nad układem generowanych wydruków, raportów lub grafiki. Aspose.Page dla .NET upraszcza to zadanie dzięki przejrzystemu, obiektowemu API. W tym samouczku nauczysz się, jak stworzyć wielostronicowy plik PS, zdefiniować własny rozmiar dla każdej strony i zapisać wynik — wszystko w kilku linijkach kodu C#.

## Quick Answers
- **Czy mogę ustawić własny rozmiar strony?** Tak – wystarczy podać szerokość i wysokość przy otwieraniu strony.  
- **Jak dodać drugą stronę PS?** Wywołaj `document.OpenPage(width, height)` po raz drugi.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Czy potrzebna jest licencja?** Licencja tymczasowa działa w testach; pełna licencja jest wymagana w produkcji.  
- **Gdzie mogę pobrać Aspose.Page?** Ze strony pobierania podanej poniżej.

## Prerequisites

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania:

- Znajomość programowania w .NET.  
- Zainstalowane Visual Studio na komputerze.  
- Biblioteka Aspose.Page dla .NET, którą możesz pobrać [tutaj](https://releases.aspose.com/page/net/).  
- Preferowany katalog dokumentów do testów.

## Import Namespaces

Upewnij się, że w projekcie dołączasz niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności oferowanych przez Aspose.Page. W podanym przykładzie przestrzenie nazw są domyślnie uwzględnione, ale warto je sprawdzić i ewentualnie dostosować do struktury Twojego projektu.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Step 1: Set Up Your Project

Utwórz nowy projekt .NET w Visual Studio i skonfiguruj niezbędne ustawienia. Upewnij się, że w projekcie odwołujesz się do biblioteki Aspose.Page.

## Set Custom Page Size and Add Second PS Page

Ta sekcja dokładnie pokazuje, jak **ustawić własny rozmiar strony** dla każdej strony oraz jak **dodać drugą stronę PS** do tego samego dokumentu.

### Step 2: Initialize the Document

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "document1.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create a new 2-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, 2);
```

### Step 3: Add the First Page (default size)

```csharp
    // Add the first page
    document.OpenPage();

    // Add content

    // Close the first page
    document.ClosePage();
```

### Step 4: Add the Second Page with a Different (Custom) Size

```csharp
    // Add the second page with a different size
    document.OpenPage(400, 700);

    // Add content

    // Close the second page
    document.ClosePage();
```

### Step 5: Save the Document

```csharp
    // Save the document
    document.Save();
}
// ExEnd:1
```

Postępuj zgodnie z tymi krokami dokładnie, a pomyślnie **ustawisz własny rozmiar strony** i dodasz **drugą stronę PS** do dokumentu PostScript przy użyciu Aspose.Page dla .NET.

## Why This Matters

- **Precyzyjny układ** – Własne wymiary strony pozwalają dopasować specyfikacje drukarki lub stworzyć unikalne formaty broszur.  
- **Wiele stron** – Dodanie drugiej (lub kolejnych) stron umożliwia tworzenie raportów wielostronicowych bez zewnętrznych narzędzi scalających.  
- **Cross‑Platform** – Wygenerowany plik PS może być renderowany na dowolnym urządzeniu obsługującym PostScript lub później konwertowany do PDF.

## Common Pitfalls & Troubleshooting

- **Nieprawidłowa ścieżka** – Upewnij się, że `dataDir` kończy się separatorem ścieżki lub użyj `Path.Combine`.  
- **Problemy z licencją** – Bez ważnej licencji biblioteka może dodać znak wodny lub ograniczyć liczbę stron.  
- **Niejasność jednostek** – Szerokość i wysokość są mierzone w punktach (1 punkt = 1/72 cala). Dostosuj odpowiednio.

## Frequently Asked Questions

**Q1: Czy Aspose.Page jest kompatybilny z różnymi formatami dokumentów?**  
A1: Aspose.Page koncentruje się głównie na manipulacji dokumentami PostScript. Dla innych formatów możesz rozważyć biblioteki Aspose przeznaczone do konkretnych potrzeb.

**Q2: Czy mogę dostosować rozmiar strony w Aspose.Page?**  
A2: Oczywiście! Jak pokazano w samouczku, możesz określić różne rozmiary dla każdej strony zgodnie z wymaganiami.

**Q3: Gdzie mogę znaleźć więcej przykładów i dokumentację?**  
A3: Odwiedź [dokumentację](https://reference.aspose.com/page/net/), aby uzyskać pełne informacje i wiele przykładów.

**Q4: Jak uzyskać tymczasową licencję dla Aspose.Page?**  
A4: Przejdź do [tego linku](https://purchase.aspose.com/temporary-license/), aby uzyskać tymczasową licencję do testów.

**Q5: Gdzie mogę uzyskać wsparcie społeczności lub zadać pytania?**  
A5: Dołącz do [forum społeczności Aspose.Page](https://forum.aspose.com/c/page/39), aby połączyć się z innymi programistami, podzielić się doświadczeniami i uzyskać pomoc.

**Last Updated:** 2026-03-03  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}