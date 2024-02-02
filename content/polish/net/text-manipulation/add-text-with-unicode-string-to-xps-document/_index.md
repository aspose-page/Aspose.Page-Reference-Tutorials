---
title: Dodaj tekst za pomocą ciągu Unicode do dokumentu XPS za pomocą Aspose.Page
linktitle: Dodaj tekst za pomocą ciągu Unicode do dokumentu XPS
second_title: Aspose.Page API .NET
description: Odkryj możliwości Aspose.Page dla .NET dzięki naszemu przewodnikowi krok po kroku na temat dodawania tekstu Unicode do dokumentów XPS.
type: docs
weight: 12
url: /pl/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
---
## Wstęp

W stale rozwijającym się środowisku rozwoju .NET Aspose.Page wyróżnia się jako potężne narzędzie do obsługi dokumentów XPS. Wśród wielu funkcji cenną funkcjonalnością jest możliwość dodawania tekstu zawierającego ciągi znaków Unicode do dokumentu XPS. Ten przewodnik krok po kroku przeprowadzi Cię przez cały proces, zapewniając efektywne wykorzystanie tej możliwości.

## Warunki wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

- Podstawowa wiedza na temat programowania .NET.
- Program Visual Studio zainstalowany na Twoim komputerze.
-  Aspose.Page dla biblioteki .NET. Można go pobrać z[Tutaj](https://releases.aspose.com/page/net/).

## Importuj przestrzenie nazw

Na początek upewnij się, że zaimportowałeś niezbędne przestrzenie nazw do swojego projektu. Zapewni to wymagane klasy i funkcjonalności do pracy z Aspose.Page. Oto podstawowe przestrzenie nazw:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Krok 1: Skonfiguruj dokument

Najpierw utwórz nowy dokument XPS, w którym będziesz dodawał tekst Unicode. Postępuj zgodnie z poniższym fragmentem kodu:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";
// Utwórz nowy dokument XPS
XpsDocument doc = new XpsDocument();
```

## Krok 2: Dodaj tekst Unicode

Teraz dodajmy tekst Unicode do dokumentu XPS. W tym przykładzie użyto czcionki Arial, ustawiono rozmiar czcionki na 20 i ustawiono tekst we współrzędnych (400f, 200f). Ciąg znaków Unicode w tym przypadku to „TEN.rof SPX.esopsA”. Sprawdź poniższy fragment kodu:

```csharp
// Dodaj tekst
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Krok 3: Zapisz dokument

Po dodaniu tekstu Unicode zapisz wynikowy dokument XPS. Oto ostatni krok:

```csharp
// Zapisz wynikowy dokument XPS
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Gratulacje! Pomyślnie dodałeś tekst Unicode do dokumentu XPS przy użyciu Aspose.Page dla .NET.

## Wniosek

W tym samouczku zbadaliśmy proces dodawania tekstu Unicode do dokumentów XPS przy użyciu Aspose.Page dla .NET. Ta funkcjonalność otwiera drzwi do różnorodnego i dynamicznego tworzenia dokumentów w środowisku .NET.

## Często zadawane pytania

### P1: Czy Aspose.Page jest kompatybilny z najnowszymi frameworkami .NET?

O1: Tak, Aspose.Page jest regularnie aktualizowany, aby zapewnić kompatybilność z najnowszymi frameworkami .NET.

### P2: Czy mogę dostosować styl i rozmiar czcionki podczas dodawania tekstu?

A2: Absolutnie! Dostarczony przykładowy kod umożliwia łatwe dostosowanie stylu, rozmiaru i innych atrybutów czcionki.

### P3: Gdzie mogę znaleźć dodatkową dokumentację dla Aspose.Page?

 Odpowiedź 3: Możesz zapoznać się z dokumentacją[Tutaj](https://reference.aspose.com/page/net/) w celu uzyskania wyczerpujących informacji i przykładów.

### P4: Czy są jakieś darmowe zasoby, aby rozpocząć korzystanie z Aspose.Page?

 A4: Tak, możesz eksplorować[Forum Aspose.Page](https://forum.aspose.com/c/page/39) za wsparcie społeczności i dyskusje.

### P5: Czy przed dokonaniem zakupu dostępna jest wersja próbna?

 A5: Oczywiście! Możesz uzyskać dostęp do bezpłatnej wersji próbnej[Tutaj](https://releases.aspose.com/) przed dokonaniem zakupu.