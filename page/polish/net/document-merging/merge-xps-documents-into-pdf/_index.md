---
title: Scal dokumenty XPS w formacie PDF za pomocą Aspose.Page dla .NET
linktitle: Scal dokumenty XPS w formacie PDF
second_title: Aspose.Page API .NET
description: Bez wysiłku łącz dokumenty XPS w wysokiej jakości pliki PDF za pomocą Aspose.Page dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby uzyskać płynną konwersję dokumentów.
type: docs
weight: 11
url: /pl/net/document-merging/merge-xps-documents-into-pdf/
---
## Wstęp

stale zmieniającym się środowisku przetwarzania dokumentów Aspose.Page dla .NET jawi się jako potężne narzędzie do płynnego łączenia dokumentów XPS w format PDF. Ten samouczek przeprowadzi Cię przez proces, szczegółowo opisując każdy krok, aby zapewnić płynne i skuteczne wykonanie.

## Warunki wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

-  Aspose.Page dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Page. Można go pobrać z[Tutaj](https://releases.aspose.com/page/net/).

- Pliki dokumentów: Mieć dokument XPS (`input.xps`) gotowy w określonym katalogu.

## Importuj przestrzenie nazw

W swoim projekcie .NET uwzględnij przestrzenie nazw niezbędne do pracy z Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

Ten krok zapewnia dostęp do klas i metod wymaganych do konwersji dokumentu.

## Krok 1: Zainicjuj strumienie

```csharp
// ExStart:3
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";
// Zainicjuj strumień wyjściowy PDF
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Zainicjuj strumień wejściowy XPS
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// RozwińKoniec:3
```

Ten krok obejmuje skonfigurowanie strumieni wejściowych i wyjściowych dla plików XPS i PDF. Upewnij się, że używane są prawidłowe ścieżki i nazwy plików.

## Krok 2: Załaduj dokument XPS

```csharp
// ExStart:4
// Załaduj dokument XPS ze strumienia
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// lub załaduj dokument XPS bezpośrednio z pliku. Nie jest wtedy potrzebny żaden xpsStream.
//Dokument XpsDocument = nowy dokument XpsDocument(nazwa pliku wejściowego, nowa opcja XpsLoad());
// RozwińKoniec:4
```

 Tutaj ładujemy dokument XPS do pliku`XpsDocument` obiektu, przygotowując go do dalszej obróbki.

## Krok 3: Zainicjuj opcje zapisu

```csharp
// ExStart:5
// Zainicjuj obiekt opcji z niezbędnymi parametrami.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
// RozwińKoniec:5
```

 Dostosuj`PdfSaveOptions` obiekt w oparciu o Twoje preferencje, określając parametry, takie jak kompresja obrazu, kompresja tekstu i numery stron.

## Krok 4: Utwórz urządzenie renderujące

```csharp
// ExStart:6
// Utwórz urządzenie renderujące dla formatu PDF
PdfDevice device = new PdfDevice(pdfStream);
// RozwińKoniec:6
```

 The`PdfDevice` to narzędzie odpowiedzialne za renderowanie dokumentu XPS do formatu PDF.

## Krok 5: Zapisz dokument

```csharp
// ExStart:7
document.Save(device, options);
// RozwińKoniec:7
```

Na koniec zapisz dokument, korzystając z urządzenia renderującego i określonych opcji.

## Wniosek

Gratulacje! Pomyślnie połączyłeś dokumenty XPS z formatem PDF za pomocą Aspose.Page dla .NET. Ten płynny proces zapewnia zachowanie jakości i formatowania dokumentu.

## Często zadawane pytania

### P1: Czy mogę połączyć wiele plików XPS w jeden plik PDF?

 A1: Tak, możesz. Po prostu wyreguluj`PageNumbers` parametr w`PdfSaveOptions` aby uwzględnić żądane strony z różnych plików XPS.

### P2: Czy dostępna jest tymczasowa licencja dla Aspose.Page dla .NET?

 Odpowiedź 2: Tak, możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/) do celów testowych.

### P3: Czy istnieją jakieś ograniczenia dotyczące rozmiaru pliku podczas używania Aspose.Page do konwersji dokumentów?

O3: Aspose.Page dla .NET nie nakłada ścisłych ograniczeń na rozmiar pliku, ale optymalną wydajność osiąga się przy rozsądnych rozmiarach plików.

### P4: Czy mogę dodatkowo dostosować wyjściowy plik PDF, na przykład dodając znaki wodne lub adnotacje?

O4: Tak, Aspose.Page dla .NET zapewnia rozbudowane funkcje do manipulacji plikami PDF. Sprawdź dokumentację dotyczącą zaawansowanych opcji dostosowywania.

### P5: Czy Aspose.Page dla .NET obsługuje rozwój międzyplatformowy?

Odpowiedź 5: Tak, Aspose.Page dla .NET jest zaprojektowany do bezproblemowej pracy na różnych platformach.