---
title: Utwórz dokument XPS za pomocą Aspose.Page dla .NET
linktitle: Utwórz dokument XPS
second_title: Aspose.Page API .NET
description: Poznaj świat tworzenia dokumentów XPS za pomocą Aspose.Page dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby bez wysiłku generować dokumenty elektroniczne.
weight: 10
url: /pl/net/document-creation/create-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz dokument XPS za pomocą Aspose.Page dla .NET

## Wstęp

Witamy w naszym przewodniku krok po kroku dotyczącym tworzenia dokumentów XPS przy użyciu Aspose.Page dla .NET. W tym samouczku omówimy proces generowania plików XPS, powszechnie używanego formatu dokumentów elektronicznych. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz pracę z Aspose.Page, ten przewodnik został opracowany tak, aby pomóc Ci w bezproblemowym tworzeniu dokumentów XPS z jasnymi przykładami i szczegółowymi objaśnieniami.

## Warunki wstępne

Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

1.  Biblioteka Aspose.Page dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Page z[link do pobrania](https://releases.aspose.com/page/net/).

2. Twój katalog dokumentów: Wybierz lub utwórz katalog w swoim systemie, w którym chcesz zapisywać wyjściowe pliki XPS.

Przejdźmy teraz do samouczka!

## Importuj przestrzenie nazw

Aby używać Aspose.Page dla .NET, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu. Wykonaj następujące kroki:

### Krok 1: Dodaj odniesienie do Aspose.Page

W swoim projekcie dodaj odwołanie do biblioteki Aspose.Page dla .NET. Wymaganą bibliotekę DLL znajdziesz w pobranym pakiecie.

### Krok 2: Importuj przestrzenie nazw

Uwzględnij następujące przestrzenie nazw w pliku kodu:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Teraz, gdy skonfigurowaliśmy wymagania wstępne i zaimportowaliśmy niezbędne przestrzenie nazw, podzielmy proces tworzenia dokumentu XPS na kilka kroków.

## Krok 1: Ustaw katalog dokumentów

```csharp
string dir = "Your Document Directory";
```

 Pamiętaj o wymianie`"Your Document Directory"` z rzeczywistą ścieżką, w której chcesz zapisać wyjściowy plik XPS.

## Krok 2: Utwórz dokument XPS

```csharp
XpsDocument xDocs = new XpsDocument();
```

 Zainicjuj nowy dokument XPS za pomocą`XpsDocument` klasa.

## Krok 3: Dodaj glify do dokumentu

```csharp
var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
```

 Użyj`AddGlyphs` metoda dodawania glifów (tekstu) do dokumentu. W razie potrzeby dostosuj czcionkę, rozmiar, styl i położenie.

## Krok 4: Ustaw kolor wypełnienia glifami

```csharp
glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);
```

Określ kolor wypełnienia dodanych glifów. W tym przykładzie użyliśmy koloru czarnego, ale możesz wybrać dowolny kolor.

## Krok 5: Zapisz wynik

```csharp
xDocs.Save(dir + "output.xps");
```

Na koniec zapisz dokument XPS w określonym katalogu z żądaną nazwą pliku. Wynikowy plik XPS będzie zawierał tekst „Hello World!” tekst.

Gratulacje! Pomyślnie utworzyłeś dokument XPS przy użyciu Aspose.Page dla .NET.

## Wniosek

W tym samouczku przeszliśmy przez proces tworzenia dokumentów XPS przy użyciu Aspose.Page dla .NET. Ta potężna biblioteka zapewnia płynny sposób łatwego generowania dokumentów elektronicznych. Eksperymentuj z różnymi czcionkami, stylami i zawartością, aby dostosować pliki XPS do swoich konkretnych potrzeb.

## Często zadawane pytania

### P1: Czy mogę używać niestandardowych czcionek w dokumencie XPS?

O1: Tak, możesz określić rodzinę i rozmiar czcionki podczas dodawania glifów do dokumentu XPS.

### P2: Czy Aspose.Page jest kompatybilny z .NET Core?

O2: Tak, Aspose.Page obsługuje .NET Core, co pozwala na używanie go w aplikacjach wieloplatformowych.

### P3: Jak mogę dodać obrazy do dokumentu XPS?

O3: Aspose.Page udostępnia metody dodawania obrazów do dokumentu XPS. Szczegółowe przykłady można znaleźć w dokumentacji.

### P4: Czy mogę tworzyć wielostronicowe dokumenty XPS?

A4: Absolutnie! Możesz dodać wiele stron do swojego dokumentu XPS, korzystając z biblioteki Aspose.Page.

### P5: Czy dostępna jest wersja próbna?

 O5: Tak, możesz poznać funkcje Aspose.Page, pobierając plik[bezpłatna wersja próbna](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
