---
title: Konwertuj XPS na PDF za pomocą Aspose.Page dla .NET
linktitle: Konwertuj XPS na PDF
second_title: Aspose.Page API .NET
description: Bez wysiłku konwertuj XPS do formatu PDF w .NET za pomocą Aspose.Page. Pobierz bibliotekę, zapoznaj się z dokumentacją i uzyskaj bezpłatną wersję próbną.
weight: 11
url: /pl/net/document-conversion/convert-xps-to-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konwertuj XPS na PDF za pomocą Aspose.Page dla .NET

## Wstęp

W tym samouczku zagłębimy się w proces konwersji dokumentów XPS (Specyfikacja papieru XML) do formatu PDF (Portable Document Format) przy użyciu potężnej biblioteki Aspose.Page dla .NET. Aspose.Page dla .NET zapewnia solidny zestaw funkcji do pracy z plikami XPS, umożliwiając programistom bezproblemową konwersję ich do formatu PDF z różnymi opcjami dostosowywania.

## Warunki wstępne

Zanim rozpoczniemy tę podróż ku konwersji, upewnij się, że spełniasz następujące wymagania wstępne:

-  Biblioteka Aspose.Page dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Page dla .NET w swoim środowisku programistycznym. Można go pobrać z[Dokumentacja Aspose.Page](https://reference.aspose.com/page/net/).

- Środowisko programistyczne: skonfiguruj środowisko programistyczne .NET za pomocą programu Visual Studio lub innego kompatybilnego IDE.

- Dokument XPS: Przygotuj dokument XPS, który chcesz przekonwertować na format PDF. Może to być przykładowy plik XPS przechowywany w wyznaczonym katalogu.

## Importuj przestrzenie nazw

Zanim zagłębimy się w kod, zaimportujmy niezbędne przestrzenie nazw, aby funkcje Aspose.Page dla .NET były dostępne w naszym kodzie:

```csharp
using Aspose.Page.XPS;
```

## Krok 1: Zainicjuj katalog dokumentów

```csharp
string dataDir = "Your Document Directory";
```

Zastąp „Twój katalog dokumentów” ścieżką do katalogu zawierającego dokument XPS.

## Krok 2: Zainicjuj strumienie PDF i XPS

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

Otwórz strumienie zarówno dla wyjściowego pliku PDF, jak i wejściowego pliku XPS. Upewnij się, że masz ustawione odpowiednie ścieżki plików.

## Krok 3: Załaduj dokument XPS

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

Załaduj dokument XPS, korzystając z biblioteki Aspose.Page dla .NET.

## Krok 4: Zainicjuj opcje zapisywania plików PDF

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

Skonfiguruj opcje zapisywania plików PDF, w tym parametry takie jak poziom jakości JPEG, kompresja obrazu, kompresja tekstu i określone numery stron do uwzględnienia.

## Krok 5: Utwórz urządzenie do renderowania plików PDF

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

Utwórz urządzenie renderujące dla formatu PDF, korzystając z biblioteki Aspose.Page dla .NET.

## Krok 6: Zapisz dokument w formacie PDF

```csharp
document.Save(device, options);
```

Zapisz dokument XPS w formacie PDF, korzystając z określonego urządzenia renderującego i opcji.

## Wniosek

Gratulacje! Pomyślnie przekonwertowałeś dokument XPS na format PDF przy użyciu Aspose.Page dla .NET. Ta wszechstronna biblioteka zapewnia programistom potężny zestaw narzędzi do łatwej obsługi różnych formatów dokumentów.

## Często zadawane pytania

### P1: Czy mogę przekonwertować wiele plików XPS na jeden plik PDF za pomocą Aspose.Page dla .NET?

Odpowiedź 1: Tak, możesz przeglądać wiele plików XPS i wykonywać te same czynności, aby połączyć je w jeden plik PDF.

### P2: Czy Aspose.Page dla .NET obsługuje inne formaty wyjściowe?

O2: Tak, Aspose.Page dla .NET obsługuje różne formaty wyjściowe, w tym TIFF, JPEG, PNG i inne.

### P3: Jak mogę dostosować wygląd przekonwertowanego dokumentu PDF?

O3: Możesz dostosować parametry obiektu opcji, takie jak kompresja obrazu i kompresja tekstu, aby uzyskać pożądany wygląd.

### P4: Czy dostępna jest wersja próbna Aspose.Page dla .NET?

 O4: Tak, możesz poznać możliwości Aspose.Page dla .NET, uzyskując bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/).

### P5: Gdzie mogę uzyskać wsparcie społeczności dla Aspose.Page dla .NET?

 A5: Odwiedź[Forum Aspose.Page](https://forum.aspose.com/c/page/39) za dyskusje społeczne i wsparcie.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
