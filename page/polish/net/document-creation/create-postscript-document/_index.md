---
date: 2026-01-12
description: Naucz się tworzyć dokumenty PostScript w .NET przy użyciu Aspose.Page.
  Ten przewodnik krok po kroku pokazuje, jak tworzyć pliki PostScript, ustawiać rozmiar
  strony PostScript oraz dostosowywać marginesy, aby zapewnić płynną integrację.
linktitle: Create PostScript Document
second_title: Aspose.Page .NET API
title: Jak utworzyć dokument PostScript przy użyciu Aspose.Page dla .NET
url: /pl/net/document-creation/create-postscript-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć dokument PostScript przy użyciu Aspose.Page dla .NET

## Wstęp

Witamy! W tym obszernej instrukcji dowiesz się **jak tworzyć dokumenty PostScript** programowo przy pomocy Aspose.Page dla .NET. Niezależnie od tego, czy generujesz faktury, etykiety wysyłkowe, czy jakikolwiek wektorowy wydruk, ten przewodnik poprowadzi Cię przez każdy krok — od konfiguracji środowiska po zapisanie gotowego pliku *.ps*. Zanurzmy się i zobaczmy, jak łatwo jest wyprodukować wysokiej jakości plik PostScript w zaledwie kilku linijkach C#.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebuję?** Aspose.Page for .NET  
- **Czy mogę ustawić rozmiar strony?** Tak – użyj `options.PageSize` (zobacz „ustaw rozmiar strony PostScript”).  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna wystarczy do testów; licencja jest wymagana w produkcji.  
- **Jakie wersje .NET są wspierane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Ile czasu zajmuje implementacja?** Zazwyczaj mniej niż 10 minut dla podstawowego dokumentu.

## Co to jest „jak utworzyć PostScript” w .NET?
Aspose.Page udostępnia bogate API, które abstrahuje niskopoziomową składnię EPS/PostScript, pozwalając skupić się na układzie strony, grafice i tekście. Korzystając z biblioteki, unikasz ręcznego kodu PS i zyskujesz wsparcie dla czcionek, obrazów oraz precyzyjnych pomiarów.

## Dlaczego warto używać Aspose.Page do tworzenia PostScript?
- **Pełna kontrola** nad wymiarami strony, marginesami i prymitywami rysunkowymi.  
- **Brak zewnętrznych zależności** – wszystko działa wewnątrz procesu .NET.  
- **Wsparcie wieloplatformowe** dla Windows, Linux i macOS.  
- **Solidna obsługa czcionek**, w tym własnych folderów czcionek.

## Wymagania wstępne

- Biblioteka Aspose.Page for .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Page for .NET. Możesz ją pobrać [tutaj](https://releases.aspose.com/page/net/).
- Środowisko .NET: Upewnij się, że masz skonfigurowane działające środowisko .NET na swoim komputerze.
- Edytor tekstu lub IDE: Użyj ulubionego edytora tekstu lub zintegrowanego środowiska programistycznego (IDE) do kodowania.

Teraz, gdy wszystko jest gotowe, rozpocznijmy budowanie dokumentu.

## Importowanie przestrzeni nazw

Najpierw zaimportuj przestrzenie nazw, które dają dostęp do podstawowych klas Aspose.Page.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.IO;
```

Te przestrzenie nazw udostępniają `PsDocument`, `PsSaveOptions` oraz klasy pomocnicze używane w całym samouczku.

## Krok 1: Ustaw katalog dokumentu

```csharp
string dir = "Your Document Directory";
```

Zastąp `"Your Document Directory"` absolutną lub względną ścieżką, w której ma zostać zapisany finalny plik **PostScript**.

## Krok 2: Utwórz strumień wyjściowy

```csharp
using (Stream outPsStream = new FileStream(dir + "document.ps", FileMode.Create))
```

`FileStream` otwiera zapisywalny strumień o nazwie **document.ps**. Wszystkie kolejne polecenia rysowania będą zapisywane do tego strumienia.

## Krok 3: Utwórz opcje zapisu

```csharp
PsSaveOptions options = new PsSaveOptions();
```

`PsSaveOptions` pozwala skonfigurować sposób renderowania i zapisu dokumentu.

## Krok 4: Ustaw rozmiar strony PostScript i marginesy

```csharp
options.PageSize = PageConstants.GetSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT);
options.Margins = PageConstants.GetMargins(PageConstants.MARGINS_ZERO);
```

Tutaj **ustawiamy rozmiar strony PostScript** na A4 w orientacji pionowej i usuwamy wszystkie marginesy. Możesz zamienić `SIZE_A4` na inne stałe (np. `SIZE_LETTER`), aby dopasować układ do swoich potrzeb.

## Krok 5: Dodaj dodatkowe foldery czcionek

```csharp
options.AdditionalFontsFolders = new string[] { dir };
```

Jeśli dokument korzysta z własnych czcionek, które nie są zainstalowane w systemie, wskaż Aspose.Page folder zawierający te pliki czcionek.

## Krok 6: Utwórz dokument wielostronicowy

```csharp
bool multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

Instancja `PsDocument` reprezentuje dokument PostScript. Ustawienie `multiPaged` na `false` tworzy dokument jednosstronicowy (możesz przełączyć na `true`, aby uzyskać wielostronicowy wynik).

## Krok 7: Zamknij i zapisz

```csharp
document.ClosePage();
document.Save();
```

Wywołanie `ClosePage()` finalizuje zawartość strony, a `Save()` zapisuje kompletny strumień PostScript na dysk.

Gratulacje! Właśnie nauczyłeś się **jak tworzyć dokumenty PostScript** przy użyciu Aspose.Page dla .NET.

## Typowe problemy i rozwiązania

- **Błędy ścieżki pliku** – Upewnij się, że zmienna `dir` kończy się separatorem ścieżki (`\` lub `/`) lub użyj `Path.Combine`.
- **Brak czcionek** – Jeśli tekst wyświetla się domyślną czcionką, sprawdź, czy `options.AdditionalFontsFolders` wskazuje właściwy katalog.
- **Nieprawidłowy rozmiar strony** – Podwójnie sprawdź stałe przekazywane do `PageConstants.GetSize`; możesz także podać własne wymiary za pomocą `new SizeF(width, height)`.

## Najczęściej zadawane pytania

### Q1: Gdzie mogę znaleźć dokumentację Aspose.Page dla .NET?
A1: Dokumentacja jest dostępna [tutaj](https://reference.aspose.com/page/net/).

### Q2: Jak pobrać Aspose.Page dla .NET?
A2: Możesz pobrać ją z [tego linku](https://releases.aspose.com/page/net/).

### Q3: Gdzie mogę kupić licencję na Aspose.Page dla .NET?
A3: Licencję możesz nabyć [tutaj](https://purchase.aspose.com/buy).

### Q4: Czy dostępna jest darmowa wersja próbna Aspose.Page dla .NET?
A4: Tak, darmową wersję próbną znajdziesz [tutaj](https://releases.aspose.com/).

### Q5: Jak uzyskać tymczasową licencję na Aspose.Page dla .NET?
A5: Tymczasową licencję uzyskasz [tutaj](https://purchase.aspose.com/temporary-license/).

### Q6: Czy mogę generować wielostronicowe pliki PostScript?
A6: Oczywiście. Ustaw `bool multiPaged = true` przy tworzeniu `PsDocument` i wywołuj `document.NewPage()` dla każdej dodatkowej strony.

### Q7: Czy Aspose.Page obsługuje zarządzanie kolorami?
A7: Tak, możesz osadzać profile ICC za pomocą `PsSaveOptions.ColorProfile`, jeśli jest to potrzebne.

---

**Ostatnia aktualizacja:** 2026-01-12  
**Testowano z:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}