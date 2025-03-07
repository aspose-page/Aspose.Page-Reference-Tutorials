---
title: Dodaj tekst za pomocą ciągu Unicode do PostScript (PS) za pomocą Aspose.Page
linktitle: Dodaj tekst za pomocą ciągu Unicode do PostScript (PS)
second_title: Aspose.Page API .NET
description: Dowiedz się, jak dodać tekst Unicode do plików PostScript przy użyciu Aspose.Page dla .NET. Ulepsz manipulację dokumentami z łatwością.
weight: 11
url: /pl/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj tekst za pomocą ciągu Unicode do PostScript (PS) za pomocą Aspose.Page

## Wstęp

W dziedzinie manipulacji dokumentami Aspose.Page dla .NET wyróżnia się jako solidna biblioteka, która umożliwia programistom tworzenie, edytowanie i konwertowanie różnych formatów dokumentów. Jedną z jego zaawansowanych funkcji jest możliwość dodawania tekstu przy użyciu ciągów Unicode do plików PostScript (PS). W tym samouczku omówimy krok po kroku wykonanie tego zadania, zapewniając płynną obsługę programistom pracującym z Aspose.Page.

## Warunki wstępne

Przed przystąpieniem do samouczka upewnij się, że spełniasz następujące wymagania wstępne:

- Praktyczna znajomość języka programowania C#.
-  Zainstalowana biblioteka Aspose.Page dla .NET. Można go pobrać z[Aspose.Page dla dokumentacji .NET](https://reference.aspose.com/page/net/).
- Skonfigurowane środowisko programistyczne z niezbędnymi konfiguracjami.

## Importuj przestrzenie nazw

W kodzie C# zaimportuj wymagane przestrzenie nazw do korzystania z funkcjonalności Aspose.Page dla .NET:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Krok 1: Skonfiguruj katalog dokumentów i folder czcionek

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## Krok 2: Utwórz strumień wyjściowy dla dokumentu PostScript

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    // Twórz opcje zapisywania w formacie A4
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    // ... (Tutaj można ustawić dodatkowe opcje)
    
    // Utwórz nowy 1-stronicowy dokument PS
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (Dalsze kroki zostaną wyjaśnione poniżej)
    
    // Zapisz dokument
    document.Save();
}
```

## Krok 3: Dodaj tekst Unicode z niestandardową czcionką

```csharp
string str = "試してみます.";  // Tekst Unicode
int fontSize = 48;

// Używanie niestandardowej czcionki do wypełniania tekstu
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## Krok 4: Zamknij bieżącą stronę

```csharp
document.ClosePage();
```

## Krok 5: Sfinalizuj i zapisz dokument

```csharp
document.Save();
```

## Wniosek

W tym samouczku omówiliśmy proces dodawania tekstu Unicode do dokumentu PostScript przy użyciu Aspose.Page dla .NET. Wykorzystując jego potężne możliwości, programiści mogą usprawnić przepływ pracy z dokumentami, zapewniając elastyczność i precyzję.

## Często zadawane pytania

### P1: Czy mogę używać Aspose.Page dla .NET z innymi językami programowania?

Odpowiedź 1: Aspose.Page jest przeznaczony głównie dla .NET, ale dostępne są inne wersje dla Java.

### P2: Jak uzyskać tymczasową licencję na Aspose.Page dla .NET?

 A2: Odwiedź[Licencja tymczasowa](https://purchase.aspose.com/temporary-license/) w celu uzyskania licencji tymczasowej.

### P3: Czy istnieje forum społecznościowe do dyskusji na temat Aspose.Page?

 A3: Tak, odwiedź[Forum Aspose.Page](https://forum.aspose.com/c/page/39) za wsparcie społeczności.

### P4: Z jakimi formatami może współpracować Aspose.Page dla .NET?

A4: Aspose.Page obsługuje różne formaty, w tym XPS, PS, EPS, PDF i inne.

### P5: Czy mogę dostosować wygląd dodanego tekstu?

O5: Tak, możesz dostosować czcionkę, rozmiar, kolor i inne właściwości tekstu w Aspose.Page.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
