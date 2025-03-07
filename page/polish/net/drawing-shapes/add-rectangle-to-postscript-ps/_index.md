---
title: Dodaj prostokąt do PostScript (PS) za pomocą Aspose.Page dla .NET
linktitle: Dodaj prostokąt do PostScriptu (PS)
second_title: Aspose.Page API .NET
description: Usprawnij tworzenie dokumentów w .NET dzięki Aspose.Page. Dowiedz się, jak krok po kroku dodawać prostokąty do plików PostScript (PS).
weight: 12
url: /pl/net/drawing-shapes/add-rectangle-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj prostokąt do PostScript (PS) za pomocą Aspose.Page dla .NET

## Wstęp

Jeśli chcesz zwiększyć swoje możliwości tworzenia dokumentów w .NET, Aspose.Page zapewnia potężne rozwiązanie do obsługi dokumentów PostScript. W tym samouczku przeprowadzimy Cię przez proces dodawania prostokątów do dokumentu PostScript przy użyciu Aspose.Page dla .NET.

## Warunki wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

-  Biblioteka Aspose.Page dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Page dla .NET z[Tutaj](https://releases.aspose.com/page/net/).

- Środowisko programistyczne: Upewnij się, że na komputerze jest skonfigurowane środowisko programistyczne .NET.

## Importuj przestrzenie nazw

Zanim zaczniesz kodować, pamiętaj o zaimportowaniu niezbędnych przestrzeni nazw, aby uzyskać dostęp do wymaganych klas i metod:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Podzielmy teraz przykład na kilka kroków:

## Krok 1: Skonfiguruj katalog dokumentów

```csharp
// ExStart:1
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";
```

W tym kroku zastąp „Twój katalog dokumentów” ścieżką, w której chcesz zapisać dokument PostScript.

## Krok 2: Utwórz strumień wyjściowy dla dokumentu PostScript

```csharp
//Utwórz strumień wyjściowy dla dokumentu PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Tutaj tworzymy strumień wyjściowy dla dokumentu PostScript i określamy nazwę pliku („AddRectangle_outPS.ps”). Dostosuj nazwę i lokalizację pliku zgodnie ze swoimi preferencjami.

## Krok 3: Ustaw opcje zapisywania i utwórz dokument PS

```csharp
//Twórz opcje zapisywania w formacie A4
PsSaveOptions options = new PsSaveOptions();

// Utwórz nowy 1-stronicowy dokument PS
PsDocument document = new PsDocument(outPsStream, options, false);
```

Ustaw opcje zapisu, określając żądany rozmiar strony (w tym przypadku A4). Następnie utwórz nowy jednostronicowy dokument PostScript.

## Krok 4: Dodaj prostokąt i wypełnienie

```csharp
//Utwórz ścieżkę graficzną z pierwszego prostokąta
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Ustaw farbę
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Wypełnij prostokąt
document.Fill(path);
```

Tutaj tworzymy ścieżkę graficzną reprezentującą pierwszy prostokąt, ustalamy kolor farby (w tym przypadku pomarańczowy) i wypełniamy prostokąt.

## Krok 5: Dodaj kolejny prostokąt i obrys

```csharp
//Utwórz ścieżkę graficzną z drugiego prostokąta
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Ustaw skok
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Obrysuj (obrysuj) prostokąt
document.Draw(path);
```

Podobnie jak w poprzednim kroku tworzymy ścieżkę graficzną dla drugiego prostokąta, ustalamy kolor obrysu (czerwony o grubości 3) i obrysowujemy prostokąt.

## Krok 6: Zamknij stronę i zapisz dokument

```csharp
//Zamknij bieżącą stronę
document.ClosePage();

//Zapisz dokument
document.Save();
```

Na koniec zamknij bieżącą stronę i zapisz cały dokument.

## Wniosek

Gratulacje! Pomyślnie dodałeś prostokąty do dokumentu PostScript przy użyciu Aspose.Page dla .NET. W tym samouczku omówiono podstawowe kroki, od skonfigurowania środowiska programistycznego po zapisanie ostatecznego dokumentu.

## Często zadawane pytania

### P1: Czy mogę dostosować kolory prostokątów?

Odpowiedź 1: Tak, możesz dostosować kolory, dostosowując parametry w pliku`SolidBrush` I`Pen` zajęcia.

### P2: Czy Aspose.Page jest kompatybilny z innymi formatami dokumentów?

O2: Tak, Aspose.Page obsługuje różne formaty dokumentów, w tym XPS i PostScript.

### P3: Jak mogę dodać tekst do dokumentu?

 A3: Możesz użyć`TextFragment` class w Aspose.Page, aby dodać tekst do swojego dokumentu.

### P4: Gdzie mogę znaleźć dodatkowe przykłady i dokumentację?

 Odpowiedź 4: Zapoznaj się z dokumentacją[Tutaj](https://reference.aspose.com/page/net/) i odwiedź[Forum Aspose.Page](https://forum.aspose.com/c/page/39) za wsparcie społeczności.

### P5: Czy mogę wypróbować Aspose.Page przed zakupem?

 Odpowiedź 5: Tak, możesz otrzymać bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/) , a w przypadku długotrwałego użytkowania rozważ a[licencja tymczasowa](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
