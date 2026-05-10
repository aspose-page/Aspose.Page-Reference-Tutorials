---
date: 2026-01-12
description: Dowiedz się, jak tworzyć dokumenty XPS przy użyciu Aspose.Page dla .NET
  – krok po kroku przewodnik generowania wysokiej jakości dokumentów elektronicznych.
linktitle: Create XPS Document
second_title: Aspose.Page .NET API
title: Utwórz dokument XPS przy użyciu Aspose.Page dla .NET
url: /pl/net/document-creation/create-xps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz dokument XPS przy użyciu Aspose.Page dla .NET

## Wprowadzenie

Witamy w naszym przewodniku krok po kroku, jak **utworzyć dokument XPS** przy użyciu Aspose.Page dla .NET. W tym samouczku przyjrzymy się procesowi generowania plików XPS, powszechnie używanego formatu dokumentów elektronicznych. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz pracę z Aspose.Page, ten przewodnik został przygotowany, aby pomóc Ci płynnie tworzyć dokumenty XPS z klarownymi przykładami i szczegółowymi wyjaśnieniami.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebuję?** Aspose.Page for .NET  
- **Czy mogę uruchomić to na .NET Core?** Tak, biblioteka w pełni obsługuje .NET Core oraz .NET 5/6  
- **Ile linii kodu?** Mniej niż 20 linii, aby wygenerować podstawowy plik XPS  
- **Czy potrzebna jest licencja do testów?** Dostępna jest bezpłatna wersja próbna; licencja jest wymagana w środowisku produkcyjnym  
- **Jaki format ma wynik?** XPS (XML Paper Specification)  

## Jak utworzyć dokument XPS przy użyciu Aspose.Page dla .NET

Poniżej znajdziesz wszystko, co potrzebne przed rozpoczęciem kodowania, a następnie zwięzły, numerowany przewodnik.

## Wymagania wstępne

Zanim zagłębimy się w samouczek, upewnij się, że masz spełnione następujące wymagania:

1. Biblioteka Aspose.Page dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Page z [linku do pobrania](https://releases.aspose.com/page/net/).
2. Katalog dokumentów: Wybierz lub utwórz katalog w swoim systemie, w którym chcesz zapisywać wygenerowane pliki XPS.

Teraz przejdźmy do samouczka!

## Importowanie przestrzeni nazw

Aby używać Aspose.Page dla .NET, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu. Postępuj zgodnie z poniższymi krokami:

### Krok 1: Dodaj odwołanie do Aspose.Page

W swoim projekcie dodaj odwołanie do biblioteki Aspose.Page dla .NET. Wymaganą bibliotekę DLL znajdziesz w pobranym pakiecie.

### Krok 2: Importuj przestrzenie nazw

Dołącz następujące przestrzenie nazw w swoim pliku kodu:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Teraz, gdy skonfigurowaliśmy wymagania wstępne i zaimportowaliśmy niezbędne przestrzenie nazw, rozbijmy proces tworzenia dokumentu XPS na kilka kroków.

## Krok 1: Ustaw katalog dokumentu

```csharp
string dir = "Your Document Directory";
```

Upewnij się, że zamienisz `"Your Document Directory"` na rzeczywistą ścieżkę, w której chcesz zapisać wygenerowany plik XPS.

## Krok 2: Utwórz dokument XPS

```csharp
XpsDocument xDocs = new XpsDocument();
```

Zainicjalizuj nowy dokument XPS przy użyciu klasy `XpsDocument`.

## Krok 3: Dodaj glify do dokumentu

```csharp
var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
```

Użyj metody `AddGlyphs`, aby dodać glify (tekst) do dokumentu. Dostosuj czcionkę, rozmiar, styl i pozycję według potrzeb.

## Krok 4: Ustaw kolor wypełnienia glifów

```csharp
glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);
```

Określ kolor wypełnienia dla dodanych glifów. W tym przykładzie używamy czerni, ale możesz wybrać dowolny kolor.

## Krok 5: Zapisz wynik

```csharp
xDocs.Save(dir + "output.xps");
```

Na koniec zapisz dokument XPS w określonym katalogu pod wybraną nazwą pliku. Powstały plik XPS będzie zawierał tekst „Hello World!”.

Gratulacje! Pomyślnie utworzyłeś dokument XPS przy użyciu Aspose.Page dla .NET.

## Wskazówki i pułapki

- **Ścieżka katalogu** – Użyj `Path.Combine(dir, "output.xps")`, aby uniknąć brakujących separatorów ścieżek na różnych systemach operacyjnych.  
- **Dostępność czcionki** – Czcionka, którą określisz, musi być zainstalowana na maszynie, na której uruchamiany jest kod; w przeciwnym razie Aspose zastąpi ją domyślną czcionką.  
- **Wiele stron** – Aby utworzyć wielostronicowe pliki XPS, utwórz dodatkowe obiekty `XpsPage` i dodaj treść do każdej strony przed zapisaniem.

## Podsumowanie

W tym samouczku przeprowadziliśmy proces tworzenia dokumentów XPS przy użyciu Aspose.Page dla .NET. Ta potężna biblioteka zapewnia płynny sposób generowania dokumentów elektronicznych z łatwością. Eksperymentuj z różnymi czcionkami, stylami i treścią, aby dostosować pliki XPS do swoich konkretnych potrzeb.

## FAQ

### Q1: Czy mogę używać własnych czcionek w moim dokumencie XPS?

A1: Tak, możesz określić rodzinę czcionki i rozmiar podczas dodawania glifów do swojego dokumentu XPS.

### Q2: Czy Aspose.Page jest kompatybilny z .NET Core?

A2: Tak, Aspose.Page obsługuje .NET Core, co pozwala używać go w aplikacjach wieloplatformowych.

### Q3: Jak mogę dodać obrazy do dokumentu XPS?

A3: Aspose.Page udostępnia metody dodawania obrazów do dokumentu XPS. Zapoznaj się z dokumentacją, aby uzyskać szczegółowe przykłady.

### Q4: Czy mogę tworzyć wielostronicowe dokumenty XPS?

A4: Oczywiście! Możesz dodać wiele stron do dokumentu XPS przy użyciu biblioteki Aspose.Page.

### Q5: Czy dostępna jest wersja próbna?

A5: Tak, możesz zapoznać się z funkcjami Aspose.Page, pobierając [bezpłatną wersję próbną](https://releases.aspose.com/).

---

**Ostatnia aktualizacja:** 2026-01-12  
**Testowano z:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}