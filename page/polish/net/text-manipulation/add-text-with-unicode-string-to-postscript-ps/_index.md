---
date: 2026-03-21
description: Dowiedz się, jak tworzyć dokumenty PostScript w C# z tekstem Unicode
  przy użyciu Aspose.Page dla .NET – szybki sposób na usprawnienie manipulacji dokumentami.
linktitle: Add Text with Unicode String to PostScript (PS)
second_title: Aspose.Page .NET API
title: Tworzenie dokumentu PostScript w C# z tekstem Unicode – Aspose.Page
url: /pl/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj tekst Unicode do PostScript (PS) przy użyciu Aspose.Page

## Wprowadzenie

Jeśli potrzebujesz **create a PostScript document C#** i osadzić znaki Unicode, Aspose.Page dla .NET upraszcza ten proces. W tym samouczku przeprowadzimy Cię przez kompletny, praktyczny przykład, który pokaże, jak dodać japoński tekst (lub dowolny ciąg Unicode) do pliku PS, wybrać własną czcionkę i zapisać wynik. Po zakończeniu będziesz mieć fragment kodu, który możesz wstawić do dowolnego projektu C#.

## Szybkie odpowiedzi
- **What does this tutorial cover?** Dodawanie tekstu Unicode do pliku PostScript przy użyciu Aspose.Page w C#.
- **Which library is required?** Aspose.Page dla .NET (najnowsza wersja).
- **Do I need a special font?** Dowolna czcionka TrueType/OpenType obsługująca żądany zakres Unicode, np. *Arial Unicode MS*.
- **How many lines of code?** Około 30 linii, podzielonych na przejrzyste kroki.
- **Is a license needed?** Tymczasowa licencja wystarcza do oceny; pełna licencja jest wymagana w produkcji.

## Co to jest „create postscript document c#”?
Tworzenie dokumentu PostScript w C# oznacza programowe generowanie pliku .ps, który spełnia specyfikacje języka PostScript. Aspose.Page abstrahuje szczegóły niskiego poziomu, pozwalając skupić się na treści, takiej jak tekst, grafika i czcionki.

## Dlaczego używać Aspose.Page do tekstu Unicode?
- **Full Unicode support** – renderowanie znaków z dowolnego języka bez ręcznego kodowania.
- **Device‑independent** – ten sam kod działa dla wyjść PS, EPS i PDF.
- **No external dependencies** – biblioteka obsługuje ładowanie czcionek i mapowanie glifów wewnętrznie.

## Wymagania wstępne

- Podstawowa znajomość C# i programowania w .NET.
- Zainstalowana biblioteka Aspose.Page dla .NET. Możesz ją pobrać z [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/).
- Folder zawierający czcionki, które zamierzasz używać (np. *Arial Unicode MS*).

## Importowanie przestrzeni nazw

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Krok 1: Konfiguracja katalogu dokumentu i folderu czcionek

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## Krok 2: Utworzenie strumienia wyjściowego dla dokumentu PostScript

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    // ... (Additional options can be set here)
    
    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (Further steps will be explained below)
    
    // Save the document
    document.Save();
}
```

## Krok 3: Dodanie tekstu Unicode z własną czcionką

```csharp
string str = "試してみます.";  // Unicode text
int fontSize = 48;

// Using custom font for filling text
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## Krok 4: Zamknięcie bieżącej strony

```csharp
document.ClosePage();
```

## Krok 5: Finalizacja i zapis dokumentu

```csharp
document.Save();
```

## Typowe problemy i rozwiązania

- **Font not found** – Upewnij się, że ścieżka `AdditionalFontsFolders` wskazuje na folder zawierający pliki .ttf/.otf oraz że nazwa czcionki jest dokładnie taka sama.
- **Garbage characters** – Sprawdź, czy ciąg źródłowy jest zakodowany jako UTF‑8 w Twoim pliku źródłowym C# (w razie potrzeby użyj `#pragma warning disable 1591`).
- **File not created** – Sprawdź uprawnienia zapisu do `dataDir` oraz czy strumień jest prawidłowo zwalniany (blok `using` to obsługuje).

## Najczęściej zadawane pytania

**Q: Can I use Aspose.Page for .NET with other programming languages?**  
A: Aspose.Page jest głównie przeznaczony dla .NET, ale dostępne są odpowiedniki w Javie.

**Q: How do I obtain a temporary license for Aspose.Page for .NET?**  
A: Odwiedź [Temporary License](https://purchase.aspose.com/temporary-license/) aby uzyskać tymczasową licencję.

**Q: Is there a community forum for Aspose.Page discussions?**  
A: Tak, odwiedź [Aspose.Page forum](https://forum.aspose.com/c/page/39) aby uzyskać wsparcie społeczności.

**Q: What formats can Aspose.Page for .NET work with?**  
A: Aspose.Page obsługuje różne formaty, w tym XPS, PS, EPS, PDF i inne.

**Q: Can I customize the appearance of the added text?**  
A: Tak, możesz dostosować czcionkę, rozmiar, kolor i inne właściwości tekstu w Aspose.Page.

## Zakończenie

W tym samouczku pokazaliśmy, jak **create a PostScript document C#** i osadzić tekst Unicode przy użyciu Aspose.Page. Postępując zgodnie z powyższymi krokami, możesz szybko zintegrować renderowanie wielojęzycznego tekstu w dowolnej aplikacji .NET, uzyskując pełną kontrolę nad generowaniem dokumentów i ich układem.

---

**Ostatnia aktualizacja:** 2026-03-21  
**Testowano z:** Aspose.Page 24.11 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}