---
title: Dodaj okrągłą elipsę do PostScriptu (PS) za pomocą Aspose.Page
linktitle: Dodaj elipsę koła do PostScriptu (PS)
second_title: Aspose.Page API .NET
description: Dowiedz się, jak bez wysiłku dodawać elipsy kołowe do dokumentów PostScript (PS) za pomocą Aspose.Page dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby zapewnić bezproblemową integrację.
type: docs
weight: 10
url: /pl/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
---
## Wstęp

Witamy w tym kompleksowym samouczku na temat dodawania elips kołowych do dokumentów PostScript (PS) przy użyciu Aspose.Page dla .NET. Aspose.Page to potężna biblioteka, która umożliwia programistom płynną pracę z PostScriptem i innymi formatami dokumentów. W tym przewodniku przeprowadzimy Cię przez proces łatwego włączania elips kołowych do dokumentów PS.

## Warunki wstępne

Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

1.  Biblioteka Aspose.Page dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Page dla .NET z[Tutaj](https://releases.aspose.com/page/net/).

2. Środowisko programistyczne: Upewnij się, że na komputerze jest skonfigurowane działające środowisko programistyczne .NET.

Zacznijmy teraz od przewodnika krok po kroku.

## Importuj przestrzenie nazw

W pierwszym kroku musisz zaimportować niezbędne przestrzenie nazw, aby funkcjonalność Aspose.Page była dostępna w Twoim kodzie.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Podzielmy teraz podany przykład na kilka kroków, które poprowadzą Cię przez proces dodawania elips okręgów do dokumentu PostScript.

## Krok 1: Ustaw katalog dokumentów

```csharp
// ExStart:1
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";
```

Pamiętaj, aby zastąpić „Twój katalog dokumentów” rzeczywistą ścieżką do katalogu dokumentów.

## Krok 2: Utwórz strumień wyjściowy dla dokumentu PostScript

```csharp
//Utwórz strumień wyjściowy dla dokumentu PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

Tutaj tworzony jest FileStream w celu zapisania dokumentu PostScript, a tryb pliku jest ustawiony na utworzenie nowego pliku.

## Krok 3: Utwórz opcje zapisu i dokument PS

```csharp
//Twórz opcje zapisywania w formacie A4
PsSaveOptions options = new PsSaveOptions();

// Utwórz nowy 1-stronicowy dokument PS
PsDocument document = new PsDocument(outPsStream, options, false);
```

Ten krok obejmuje utworzenie opcji zapisu w formacie A4 i zainicjowanie nowego 1-stronicowego dokumentu PS.

## Krok 4: Utwórz ścieżkę graficzną dla pierwszej elipsy

```csharp
//Utwórz ścieżkę graficzną z pierwszej elipsy
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

Dla pierwszej elipsy tworzona jest ścieżka graficzna określająca jej położenie i wymiary.

## Krok 5: Ustaw farbę i wypełnij elipsę

```csharp
//Ustaw farbę
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//Wypełnij elipsę
document.Fill(path);
```

Tutaj ustawiana jest farba, a pierwsza elipsa jest wypełniana określonym kolorem.

## Krok 6: Utwórz ścieżkę graficzną dla drugiej elipsy

```csharp
//Utwórz ścieżkę graficzną z drugiej elipsy
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

Podobnie tworzona jest ścieżka graficzna dla drugiej elipsy, określająca jej położenie i wymiary.

## Krok 7: Ustaw obrys i narysuj elipsę

```csharp
//Ustaw skok
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//Obrysuj (zarysuj) elipsę
document.Draw(path);
```

W tym kroku ustawiany jest obrys, a druga elipsa jest obrysowana określonym kolorem i grubością linii.

## Krok 8: Zamknij bieżącą stronę i zapisz dokument

```csharp
//Zamknij bieżącą stronę
document.ClosePage();

//Zapisz dokument
document.Save();
```

Na koniec bieżąca strona zostaje zamknięta, a cały dokument zostaje zapisany, co kończy proces.

## Wniosek

Gratulacje! Pomyślnie nauczyłeś się dodawać elipsy kołowe do dokumentów PostScript przy użyciu Aspose.Page dla .NET. Ten samouczek zawiera szczegółowy przewodnik krok po kroku, który pomoże Ci bezproblemowo zintegrować tę funkcjonalność z projektami.

## Często zadawane pytania

### P1: Czy mogę używać Aspose.Page dla .NET z innymi formatami dokumentów?

 Odpowiedź 1: Aspose.Page koncentruje się głównie na PostScript, ale Aspose udostępnia inne biblioteki dla różnych formatów dokumentów. Sprawdź[Złóż dokumentację](https://reference.aspose.com/page/net/) po więcej szczegółów.

### P2: Gdzie mogę znaleźć dodatkowe wsparcie i dyskusje społeczności?

 A2: Odwiedź[Forum Aspose.Page](https://forum.aspose.com/c/page/39) za dyskusje społeczne i wsparcie.

### P3: Czy dostępna jest bezpłatna wersja próbna Aspose.Page dla .NET?

 A3: Tak, możesz uzyskać dostęp do[bezpłatna wersja próbna](https://releases.aspose.com/)aby poznać funkcje Aspose.Page dla .NET.

### P4: Jak mogę uzyskać tymczasową licencję na Aspose.Page?

 A4: Uzyskaj tymczasową licencję[Tutaj](https://purchase.aspose.com/temporary-license/) do celów testowania i oceny.

### P5: Gdzie mogę kupić Aspose.Page dla .NET?

 A5: Kup Aspose.Page dla .NET w sklepie[kup stronę](https://purchase.aspose.com/buy).