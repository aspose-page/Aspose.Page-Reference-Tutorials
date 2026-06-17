---
date: 2026-01-28
description: Dowiedz się, jak konwertować EPS na PNG przy użyciu Aspose.Page dla .NET
  i zastosować licencję rozliczaną według zużycia, aby zapewnić płynne przetwarzanie
  dokumentów.
linktitle: Apply Metered License
second_title: Aspose.Page .NET API
title: Konwertuj EPS na PNG i zastosuj licencję metrową z Aspose.Page dla .NET
url: /pl/net/getting-started/apply-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konwertuj EPS do PNG i zastosuj licencję metrową z Aspose.Page dla .NET

## Wstęp

Odblokuj pełny potencjał Aspose.Page dla .NET, **konwertując EPS do PNG** i zapewniając metrową. Ten samouczek przeprowadził Cię przez każdy krok — od pliku EPS po zapisanie go jako obrazu PNG — umożliwia przetwarzanie dokumentów bez znaków wodnych wersji.

## Szybkie odpowiedzi
- **Co dodać ten samouczek?** Konwersja plików EPS do obrazów PNG oraz aplikacja licencji metrowej z Aspose.Page dla .NET.
- **Czy potrzebujesz licencji?** Tak, do użytku produkcyjnego wymagana jest licencja metrowa.
- **Jakie wersje .NET są pobierane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Jak długo trwa realizacja?** Około 10–15 minut dla normalnego okresu.
- **Czy mogę przekazać do systemu Linux/macOS?** Oczywiście — Aspose.Page jest wieloplatformowy.

## Co to jest „konwertuj EPS na PNG”?

Konwersja EPS oznacza PNG rasteryzację pliku Encapsulated PostScript (EPS) do bitmapowego obrazu PNG. Jest do dystrybucji, gdy trzeba lub osadzić grafikę na stronach internetowych, w raportach lub komponentach UI, które nie obsługują formatu EPS.

## Dlaczego warto używać licencji licznikowej do konwersji EPS na obraz?

Licencja metrowa pozwala tylko na przetworzone strony, co jest idealnym rozwiązaniem przy uwzględnieniu zmiennych wielkości. Usuwa także czerwony baner oceny pojawiającej się w wersji próbnej, opartej na wynikach końcowych dla użytkowników.

## Warunki wstępne

Zanim przejdziesz do wykonania czynności, zostanie spełniony, że spełniasz szczegółowe wymagania:

- Ważna licencjat Aspose.Page dla .NET: możesz ją uzyskać na [purchase.aspose.com](https://purchase.aspose.com/buy).
- Zainstalowana biblioteka Aspose.Page: zobacz [dokumentacja](https://reference.aspose.com/page/net/) po instrukcjach instalacji.
- Środowisko programistyczne .NET: kontrolowane, że masz działające środowisko .NET skonfigurowane na swoim komputerze.

## Importuj przestrzenie nazw

W swoim projekcie .NET zaimportuj niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcji Aspose.Page:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

## Jak przekonwertować EPS na PNG za pomocą licencji licznikowej?

Zawiera przewodnik krok po kroku, który zawiera wszystko, co musisz wiedzieć.

### Krok 1: Ustaw mierzone klucze publiczne i prywatne

Zainicjalizuj klasę `Aspose.Page.Metered` i ustaw publiczny oraz prywatny klucz metrowy. Zastąp `<type public key here>` i `<type private key here>` swoimi rzeczywistymi kluczami.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

### Krok 2: Załaduj plik EPS i utwórz dokument

Podaj ścieżkę do pliku EPS i utwórz strumień do odczytu jego zawartości. Następnie utwórz instancję klasy `PsDocument` ze strumienia.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

### Krok 3: Konwertuj EPS na obraz PNG

Utwórz `ImageDevice` do konwersji pliku EPS na obraz PNG. Zapisz plik EPS jako obraz przy użyciu `ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

### Krok 4: Pobierz bajty obrazu

Pobierz bajty obrazu, gdzie każdy tablica bajtów reprezentuje jedną stronę. W tym przypadku mamy jedną stronę.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

### Krok 5: Zapisz bajty obrazu do pliku

Zapisz bajty obrazu do pliku, zapewniając pomyślną konwersję z EPS do PNG.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

### Krok 6: Zweryfikuj licencję taryfową

Sprawdź wizualnie, czy licencja metrowa została pomyślnie zastosowana. Jeśli wynikowy obraz nie zawiera czerwonej wiadomości oceny, oznacza to, że licencja metrowa została zastosowana bez problemów.

Teraz możesz w pełni wykorzystać możliwości Aspose.Page dla .NET z licencją metrową!

## Typowe problemy i rozwiązania

| Wydanie | Przyczyna | Napraw |
|-------|-------|-----|
| Czerwony baner oceny nadal się pojawia | Licencja nie skonfigurowana lub klucze | Sprawdź ponownie klucze inspektor/prywatny i dokument się, że `SetMeteredKey` jest wywoływany przed przekazanym dokumentem |
| Nie utworzono pliku wyjściowego | Nieprawidłowa ścieżka `dataDir` lub zezwolenie do pliku | Sprawdź, czy katalog istnieje w aplikacji mającej uprawnienia do zapisu |
| Wiele stron nie zapisano | Zapisano tylko pierwszą stronę | Iteruj przez `imagesBytes` i zapisz każdą tablicę do sprawdzania pliku PNG |

## Często zadawane pytania

**P:** Czy można zastosować licencję metrową w rurociągu CI/CD?
**O:** Tak, może być klucze w bezpieczny sposób (np. w alternatywnych metodach) i wywoływanie `SetMeteredKey` podczas procesu.

**P:** Czy Aspose.Page obsługuje zachowanie profili przyzwyczajonych do PNG?
**O:** Wyjście PNG zawiera oryginalne informacje o kolorach, ale możesz je dalej dostosować za pomocą `ImageSaveOptions`.

**P:** Czy można konwertować EPS do innych formatów rastrowych (JPEG, BMP)?
**O:** Oczywiście — wystarczy zmienić `ImageSaveOptions` na używany format.

**P:** Jaki jest maksymalny rozmiar pliku EPS?
**O:** Aspose.Page obsługuje duże pliki, ale pamięć rozszerzona wraz z rozdzielczością obrazu. Rozważ interpretację pojedynczego słowa w przypadku bardzo dużych dokumentów.

**P:** Jak programowo uzyskać miejsce w pliku EPS?
**O:** wykorzystuje `document.PagesCount` po przeniesieniu `PsDocument`.

---

**Ostatnia aktualizacja:** 2026-01-28
**Testowano z:** Aspose.Page 24.12 dla .NET
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}