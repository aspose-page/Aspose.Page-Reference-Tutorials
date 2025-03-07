---
title: Dodaj elementy tablicy za pomocą Aspose.Page
linktitle: Dodaj elementy tablicy
second_title: Aspose.Page API .NET
description: Dowiedz się, jak dodawać elementy tablicy w plikach EPS za pomocą Aspose.Page dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby bezproblemowo manipulować dokumentami.
weight: 11
url: /pl/net/eps-metadata-management/modify-eps-metadata-add-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj elementy tablicy za pomocą Aspose.Page

## Wstęp

obszarze manipulacji i przetwarzania dokumentów w .NET Aspose.Page wyróżnia się jako potężne narzędzie. Wśród jego wielu możliwości częstym wymaganiem jest obsługa elementów tablicy w pliku EPS. W tym samouczku omówimy krok po kroku proces dodawania elementów tablicy przy użyciu Aspose.Page w środowisku .NET. Niezależnie od tego, czy jesteś doświadczonym programistą, czy nowicjuszem, ten przewodnik przeprowadzi Cię przez proces w sposób przejrzysty i precyzyjny.

## Warunki wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

- Podstawowa znajomość programowania .NET.
-  Zainstalowano Aspose.Page dla .NET. Jeśli nie, możesz go pobrać z[Tutaj](https://releases.aspose.com/page/net/).
- Edytor kodu, taki jak Visual Studio, do naśladowania wraz z przykładami.

## Importuj przestrzenie nazw

W projekcie .NET pamiętaj o zaimportowaniu niezbędnych przestrzeni nazw, aby móc korzystać z funkcjonalności Aspose.Page. Dodaj następujące wiersze na początku kodu:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Te przestrzenie nazw zapewniają dostęp do podstawowych klas i metod wymaganych do manipulacji plikami EPS.

## Krok 1: Zainicjuj strumień wejściowy pliku EPS

```csharp
// ExStart:3
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";
// Zainicjuj strumień wejściowy pliku EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//Utwórz instancję PsDocument ze strumienia
PsDocument document = new PsDocument(psStream);            
// RozwińKoniec:3
```

 Tutaj konfigurujemy początkowy strumień wejściowy dla pliku EPS i tworzymy plik`PsDocument` instancja.

## Krok 2: Uzyskaj metadane XMP

```csharp
// ExStart:4
// Pobierz metadane XMP. Jeżeli plik EPS nie zawiera metadanych XMP, otrzymamy nowy wypełniony wartościami z komentarzy do metadanych PS (%%Creator, %%CreateDate, %%Title itp.)
XmpMetadata xmp = document.GetXmpMetadata();
// RozwińKoniec:4
```

Pobierz metadane XMP z pliku EPS. Jeśli w pliku EPS brakuje metadanych XMP, tworzony jest nowy z wartościami z komentarzy do metadanych PS.

## Krok 3: Zmień wartości metadanych XMP

```csharp
// ExStart:5
// Zmień wartości metadanych XMP

// Dodaj jeszcze jeden tytuł. Domyślnie zostanie dodany na końcu tablicy.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Dodaj jeszcze jednego twórcę. Zostanie dodany do tablicy poprzez indeks (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// RozwińKoniec:5
```

Zmodyfikuj metadane XMP, dodając do tablicy nowe tytuły i twórców.

## Krok 4: Zapisz plik EPS ze zmienionymi metadanymi XMP

```csharp
// ExStart:6
// Zapisz plik EPS ze zmienionymi metadanymi XMP

// Utwórz strumień wyjściowy
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Zapisz plik EPS
    document.Save(outPsStream);
}
// RozwińKoniec:6
```

Na koniec zapisz plik EPS ze zaktualizowanymi metadanymi XMP. Zmiany wprowadzone w elementach tablicy zostaną odzwierciedlone w pliku wyjściowym.

## Wniosek

Dodawanie elementów tablicy za pomocą Aspose.Page w .NET jest prostym procesem, jak pokazano w tym samouczku. Dzięki odpowiednim wymaganiom wstępnym i przewodnikowi krok po kroku programiści mogą bezproblemowo manipulować plikami EPS, upewniając się, że ich dokumenty spełniają określone wymagania dotyczące metadanych.

## Często zadawane pytania

### P1: Czy Aspose.Page jest kompatybilny ze wszystkimi środowiskami .NET?

Odpowiedź 1: Tak, Aspose.Page został zaprojektowany tak, aby bezproblemowo współpracować ze wszystkimi środowiskami .NET, zapewniając spójną funkcjonalność na wszystkich platformach.

### P2: Czy mogę korzystać z Aspose.Page za darmo?

 Odpowiedź 2: Aspose.Page oferuje bezpłatną wersję próbną, umożliwiającą użytkownikom odkrywanie jego funkcji. Aby móc dalej korzystać, należy zakupić licencję od[Tutaj](https://purchase.aspose.com/buy).

### P3: Czy dostępne są licencje tymczasowe dla Aspose.Page?

 Odpowiedź 3: Tak, można uzyskać tymczasowe licencje[Tutaj](https://purchase.aspose.com/temporary-license/) na potrzeby krótkoterminowych projektów.

### P4: Gdzie mogę znaleźć wsparcie społeczności dla Aspose.Page?

Odpowiedź 4: Aby zapoznać się z dyskusjami i wsparciem społeczności, odwiedź stronę[Forum Aspose.Page](https://forum.aspose.com/c/page/39).

### P5: Jaka jest najnowsza wersja Aspose.Page dla .NET?

 O5: Aby uzyskać dostęp do najnowszej wersji Aspose.Page dla .NET, zapoznaj się z[dokumentacja](https://reference.aspose.com/page/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
