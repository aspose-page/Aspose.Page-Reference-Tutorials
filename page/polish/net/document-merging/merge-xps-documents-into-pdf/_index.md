---
date: 2026-01-20
description: Bezproblemowo dodawaj numery stron do PDF podczas łączenia dokumentów
  XPS w wysokiej jakości pliki PDF przy użyciu Aspose.Page dla .NET. Postępuj zgodnie
  z naszym przewodnikiem krok po kroku, aby przekonwertować XPS na PDF.
linktitle: Merge XPS Documents into PDF
second_title: Aspose.Page .NET API
title: Dodaj numery stron PDF – scal XPS do PDF przy użyciu Aspose.Page
url: /pl/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj numery stron PDF – Scal XPS do PDF przy użyciu Aspose.Page

## Wprowadzenie

## Szybkie odpowiedzi
- **Czy mogę dodać numery stron przy scalaniu XPS do PDF?** Tak – właściwość `PdfSaveOptions.PageNumbers` robi dokładnie to.  
- **Która biblioteka obsługuje konwersję?** Aspose.Page for .NET.  
- **Czy potrzebuję licencji do użytku produkcyjnego?** Wymagana jest ważna licencja Aspose.Page; tymczasowa licencja jest dostępna do testów.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, i .NET 5/6+.  
- **Czy możliwe jest uzyskanie obrazów wysokiej jakości?** Zdecydowanie – ustaw `JpegQualityLevel` na 100 i wybierz `PdfImageCompression.Jpeg`.

## Wymagania wstępne

Zanim rozpoczniesz tutorial, upewnij się, że spełniasz następujące wymagania:

- Aspose.Page for .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Page. Możesz ją pobrać [tutaj](https://releases.aspose.com/page/net/).

- Pliki dokumentów: Przygotuj dokument XPS (`input.xps`) w wybranym katalogu.

## Importuj przestrzenie nazw

W swoim projekcie .NET dołącz niezbędne przestrzenie nazw do pracy z Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

Ten krok zapewnia dostęp do klas i metod niezbędnych do konwersji dokumentu.

## Jak dodać numery stron PDF przy scalaniu dokumentów XPS

`PdfSaveOptions.PageNumbers` pozwala dokładnie określić, które strony (lub zakresy stron) mają pojawić się w wyjściowym PDF. Poprzez wypełnienie go żądanymi numerami stron, Aspose.Page automatycznie wstawia właściwe numerowanie.

### Krok 1: Inicjalizacja strumieni

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

Ten krok obejmuje ustawienie strumieni wejściowych i wyjściowych dla plików XPS i PDF. Upewnij się, że użyto prawidłowych ścieżek i nazw plików.

### Krok 2: Załaduj dokument XPS

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

Tutaj ładujemy dokument XPS do obiektu `XpsDocument`, przygotowując go do dalszego przetwarzania.

### Krok 3: Inicjalizacja opcji zapisu (scalanie XPS do PDF)

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }   // <-- adds page numbers PDF
};
// ExEnd:5
```

Dostosuj obiekt `PdfSaveOptions` według własnych preferencji, określając parametry takie jak kompresja obrazu, kompresja tekstu oraz **numery stron**, które mają pojawić się w ostatecznym PDF. Ustawienie `JpegQualityLevel` na 100 zapewnia **obrazy PDF wysokiej jakości**.

### Krok 4: Utwórz urządzenie renderujące

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

`PdfDevice` jest narzędziem odpowiedzialnym za renderowanie dokumentu XPS do formatu PDF.

### Krok 5: Zapisz dokument (C# XPS do PDF)

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

Na koniec zapisz dokument przy użyciu urządzenia renderującego i określonych opcji. Wyjściowy PDF będzie zawierał wybrane strony z automatycznie dodanymi numerami stron.

## Dlaczego warto używać Aspose.Page do tej konwersji?

- **Niezawodność** – Obsługuje złożone funkcje XPS bez utraty jakości.  
- **Wydajność** – Przetwarzanie oparte na strumieniach unika ładowania całych plików do pamięci.  
- **Elastyczność** – Precyzyjna kontrola jakości obrazu, kompresji i numeracji stron.  
- **Wieloplatformowość** – Działa na Windows, Linux i macOS z .NET Core.

## Typowe problemy i rozwiązania

| Problem | Rozwiązanie |
|-------|----------|
| **PDF wyjściowy jest pusty** | Sprawdź, czy ścieżka do pliku XPS jest poprawna i czy plik nie jest uszkodzony. |
| **Numery stron nie pojawiają się** | Upewnij się, że `PageNumbers` jest ustawione na prawidłowe indeksy stron zerobazowe (np. `new int[] {1,2,6}`). |
| **Obrazy niskiej jakości** | Zwiększ `JpegQualityLevel` i wybierz `PdfImageCompression.Jpeg`. |
| **Duże pliki XPS powodują obciążenie pamięci** | Przetwarzaj XPS w mniejszych fragmentach lub zwiększ limit pamięci aplikacji. |

## Najczęściej zadawane pytania

### P1: Czy mogę scalić wiele plików XPS w jeden PDF?

O1: Tak, możesz. Po prostu dostosuj parametr `PageNumbers` w `PdfSaveOptions`, aby uwzględnić żądane strony z różnych plików XPS, lub załaduj każdy XPS kolejno i wywołaj `document.Save` na tym samym `PdfDevice`.

### P2: Czy dostępna jest tymczasowa licencja dla Aspose.Page for .NET?

O2: Tak, możesz uzyskać tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/) do celów testowych.

### P3: Czy istnieją ograniczenia rozmiaru pliku przy użyciu Aspose.Page do konwersji dokumentów?

O3: Aspose.Page for .NET nie nakłada ścisłych ograniczeń rozmiaru pliku, ale optymalna wydajność uzyskiwana jest przy rozsądnie wielkości plikach. W przypadku bardzo dużych dokumentów XPS rozważ przetwarzanie ich w strumieniach, aby zmniejszyć zużycie pamięci.

### P4: Czy mogę dalej dostosować wyjściowy PDF, np. dodając znaki wodne lub adnotacje?

O4: Tak, Aspose.Page for .NET oferuje rozbudowane funkcje manipulacji PDF. Po konwersji możesz użyć biblioteki Aspose.PDF do dodania znaków wodnych, adnotacji lub innych ulepszeń.

### P5: Czy Aspose.Page for .NET wspiera rozwój wieloplatformowy?

O5: Tak, Aspose.Page for .NET jest zaprojektowany tak, aby działał płynnie na różnych platformach, w tym Windows, Linux i macOS, przy użyciu .NET Core lub .NET 5/6.

---

**Ostatnia aktualizacja:** 2026-01-20  
**Testowano z:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}