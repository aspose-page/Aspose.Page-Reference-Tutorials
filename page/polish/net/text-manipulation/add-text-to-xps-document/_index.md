---
title: Dodaj tekst do dokumentu XPS za pomocą Aspose.Page dla .NET
linktitle: Dodaj tekst do dokumentu XPS
second_title: Aspose.Page API .NET
description: Zapoznaj się z przewodnikiem krok po kroku dotyczącym dodawania tekstu do dokumentów XPS przy użyciu Aspose.Page dla .NET. Ulepsz swoje projekty .NET bez wysiłku.
weight: 13
url: /pl/net/text-manipulation/add-text-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj tekst do dokumentu XPS za pomocą Aspose.Page dla .NET

## Wstęp

W dynamicznym świecie rozwoju .NET Aspose.Page wyróżnia się jako potężne narzędzie do pracy z dokumentami XPS. Dodawanie tekstu do dokumentów XPS jest częstym wymogiem, a Aspose.Page upraszcza ten proces. W tym samouczku omówimy, jak używać Aspose.Page dla .NET do płynnego dodawania tekstu do dokumentów XPS.

## Warunki wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

- Aspose.Page dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Page. Można go pobrać z[Aspose.Page dla dokumentacji .NET](https://reference.aspose.com/page/net/).

-  Środowisko programistyczne: Skonfiguruj środowisko programistyczne .NET. Jeśli jeszcze tego nie zrobiłeś, postępuj zgodnie z instrukcjami instalacji zawartymi w pliku[dokumentacja](https://reference.aspose.com/page/net/).

- Katalog dokumentów: Utwórz katalog, w którym będziesz przechowywać swoje dokumenty. Zastąp „Twój katalog dokumentów” w podanym fragmencie kodu rzeczywistą ścieżką.

Przejdźmy teraz do przewodnika krok po kroku.

## Importuj przestrzenie nazw

Po pierwsze, zaimportujmy niezbędne przestrzenie nazw, aby rozpocząć nasz projekt:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Krok 1: Utwórz nowy dokument XPS

Aby rozpocząć pracę z Aspose.Page, utwórz nowy dokument XPS. To będzie płótno, na którym dodamy nasz tekst.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// RozwińKoniec:3
```

## Krok 2: Utwórz pędzel do tekstu

Teraz utwórzmy pędzel, aby zdefiniować kolor tekstu. W tym przykładzie używamy pędzla w kolorze czarnym.

```csharp
// ExStart:4
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
// RozwińKoniec:4
```

## Krok 3: Dodaj glify do dokumentu

Glify reprezentują tekst w dokumentach XPS. Dodaj glify do dokumentu z żądaną czcionką, rozmiarem, stylem i położeniem.

```csharp
// ExStart:5
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.Fill = textFill;
// RozwińKoniec:5
```

## Krok 4: Zapisz wynikowy dokument XPS

Na koniec zapisz dokument XPS z dodanym tekstem w określonym katalogu.

```csharp
// ExStart:6
doc.Save(dataDir + "AddText_out.xps");
// RozwińKoniec:6
```

Wykonując te proste kroki, pomyślnie dodałeś tekst do dokumentu XPS przy użyciu Aspose.Page dla .NET.

## Wniosek

Podsumowując, Aspose.Page dla .NET zapewnia proste rozwiązanie do dodawania tekstu do dokumentów XPS w projektach .NET. Prostota biblioteki w połączeniu z jej solidnymi funkcjami czyni ją nieocenionym narzędziem do manipulacji dokumentami.

## Często Zadawane Pytania

### P1: Czy mogę dostosować czcionkę i rozmiar dodanego tekstu?

 Odpowiedź 1: Tak, masz pełną kontrolę nad czcionką i rozmiarem. Dostosuj parametry w pliku`AddGlyphs` odpowiednio metodę.

### P2: Czy Aspose.Page jest kompatybilny z .NET Core?

A2: Absolutnie! Aspose.Page obsługuje .NET Core, zapewniając kompatybilność z najnowszymi technologiami .NET.

### P3: Czy istnieją jakieś wymagania licencyjne dotyczące korzystania z Aspose.Page?

 A3: Tak, potrzebujesz ważnej licencji. Poznaj opcje licencjonowania[Tutaj](https://purchase.aspose.com/buy).

### P4: Jak mogę uzyskać wsparcie lub szukać pomocy?

 A4: Odwiedź[Forum Aspose.Page](https://forum.aspose.com/c/page/39) aby nawiązać kontakt ze społecznością i uzyskać pomoc.

### P5: Czy dostępny jest bezpłatny okres próbny?

 A5: Oczywiście! Możesz skorzystać z bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
