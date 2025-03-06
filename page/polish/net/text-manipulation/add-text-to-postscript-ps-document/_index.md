---
title: Dodaj tekst do dokumentu PostScript (PS) za pomocą Aspose.Page
linktitle: Dodaj tekst do dokumentu PostScript (PS).
second_title: Aspose.Page API .NET
description: Popraw swoje umiejętności programistyczne .NET, ucząc się dodawać tekst do dokumentów PostScript (PS) za pomocą Aspose.Page. Przeglądaj przykłady krok po kroku i uwolnij moc manipulacji dokumentami.
weight: 10
url: /pl/net/text-manipulation/add-text-to-postscript-ps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj tekst do dokumentu PostScript (PS) za pomocą Aspose.Page

## Wstęp

W dynamicznym świecie programowania .NET manipulowanie i ulepszanie dokumentów PostScript (PS) jest powszechnym wymogiem. Aspose.Page dla .NET zapewnia potężny zestaw narzędzi do łatwego dodawania tekstu do dokumentów PS. Ten samouczek przeprowadzi Cię przez cały proces, zapewniając bezproblemową integrację tej funkcjonalności ze swoimi projektami.

## Warunki wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

-  Aspose.Page dla .NET: Upewnij się, że biblioteka Aspose.Page jest zintegrowana z projektem .NET. Można go pobrać z[Dokumentacja Aspose.Page .NET](https://reference.aspose.com/page/net/).

- Katalog dokumentów: skonfiguruj katalog, w którym będą przechowywane Twoje dokumenty. W przykładach będzie to nazywane „katalogiem Twoich dokumentów”.

- Folder czcionek: Utwórz folder do przechowywania niestandardowych czcionek, w przykładach nazywany „Twoim katalogiem dokumentów”.

## Importuj przestrzenie nazw

Zanim zaczniesz, pamiętaj o uwzględnieniu w projekcie niezbędnych przestrzeni nazw:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Podzielmy teraz przykład na wiele kroków.

## Krok 1: Utwórz strumień wyjściowy dla dokumentu PS

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## Krok 2: Wypełnij tekst czcionką systemową

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

## Krok 3: Wypełnij tekst niestandardową czcionką

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## Krok 4: Obrysuj tekst czcionką systemową

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

## Krok 5: Obrysuj tekst niestandardową czcionką

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

## Krok 6: Zamknij i zapisz

```csharp
document.ClosePage();
document.Save();
}
```

## Wniosek

Gratulacje! Pomyślnie nauczyłeś się, jak dodawać tekst do dokumentu PostScript (PS) przy użyciu Aspose.Page dla .NET. Zachęcamy do odkrywania większej liczby funkcji i zwiększania możliwości manipulowania dokumentami.

## Często zadawane pytania

### P1: Czy mogę używać Aspose.Page z innymi bibliotekami .NET?

Odpowiedź 1: Tak, Aspose.Page płynnie integruje się z innymi bibliotekami .NET, zapewniając wszechstronne środowisko do manipulacji dokumentami.

### P2: Czy niestandardowe czcionki są niezbędne w tym procesie?

O2: Chociaż można używać czcionek systemowych, włączenie czcionek niestandardowych pozwala na większą elastyczność i wybór projektów.

### P3: Czy Aspose.Page nadaje się do przetwarzania dokumentów na dużą skalę?

A3: Absolutnie! Aspose.Page został zaprojektowany do wydajnej i niezawodnej obsługi przetwarzania dokumentów na dużą skalę.

### P4: Czy mogę modyfikować położenie tekstu w dokumencie PS?

A4: Oczywiście! Dostosuj współrzędne w podanych przykładach, aby zmienić położenie dodanego tekstu.

### P5: Gdzie mogę szukać pomocy w przypadku zapytań związanych z Aspose.Page?

 A5: Odwiedź[Forum Aspose.Page](https://forum.aspose.com/c/page/39) nawiązać kontakt ze społecznością i zasięgnąć porady ekspertów.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
