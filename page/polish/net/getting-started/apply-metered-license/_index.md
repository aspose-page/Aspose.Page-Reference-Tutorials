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

## Introduction

Odblokuj pełny potencjał Aspose.Page dla .NET, **konwertując EPS do PNG** i stosując licencję metrową. Ten samouczek przeprowadzi Cię przez każdy krok — od załadowania pliku EPS po zapisanie go jako obrazu PNG — abyś mógł przetwarzać dokumenty wydajnie i bez znaków wodnych wersji próbnej.

## Quick Answers
- **Co obejmuje ten samouczek?** Konwersja plików EPS do obrazów PNG oraz zastosowanie licencji metrowej z Aspose.Page dla .NET.  
- **Czy potrzebuję licencji?** Tak, do użytku produkcyjnego wymagana jest licencja metrowa.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Jak długo trwa implementacja?** Około 10–15 minut dla podstawowej konwersji.  
- **Czy mogę uruchomić to na Linux/macOS?** Oczywiście — Aspose.Page jest wieloplatformowy.

## What is “convert EPS to PNG”?

Konwersja EPS do PNG oznacza rasteryzację wektorowego pliku Encapsulated PostScript (EPS) do bitmapowego obrazu PNG. Jest to przydatne, gdy trzeba wyświetlić lub osadzić grafikę na stronach internetowych, w raportach lub komponentach UI, które nie obsługują formatu EPS.

## Why use a metered license for EPS to image conversion?

Licencja metrowa pozwala płacić tylko za przetworzone strony, co jest idealne przy obciążeniach o zmiennej wielkości. Usuwa także czerwony baner oceny pojawiający się w wersji próbnej, zapewniając czyste wyniki dla końcowych użytkowników.

## Prerequisites

Zanim przejdziesz do kolejnych kroków, upewnij się, że spełniasz następujące wymagania:

- Ważna licencja Aspose.Page dla .NET: możesz ją uzyskać na [purchase.aspose.com](https://purchase.aspose.com/buy).  
- Zainstalowana biblioteka Aspose.Page: zobacz [documentation](https://reference.aspose.com/page/net/) po instrukcje instalacji.  
- Środowisko programistyczne .NET: upewnij się, że masz działające środowisko .NET skonfigurowane na swoim komputerze.

## Import Namespaces

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

## How to convert EPS to PNG with a metered license?

Poniżej znajduje się przewodnik krok po kroku, który obejmuje wszystko, co musisz wiedzieć.

### Step 1: Set Metered Public and Private Keys

Zainicjalizuj klasę `Aspose.Page.Metered` i ustaw publiczny oraz prywatny klucz metrowy. Zastąp `<type public key here>` i `<type private key here>` swoimi rzeczywistymi kluczami.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

### Step 2: Load EPS File and Create Document

Podaj ścieżkę do pliku EPS i utwórz strumień do odczytu jego zawartości. Następnie utwórz instancję klasy `PsDocument` ze strumienia.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

### Step 3: Convert EPS to PNG Image

Utwórz `ImageDevice` do konwersji pliku EPS na obraz PNG. Zapisz plik EPS jako obraz przy użyciu `ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

### Step 4: Retrieve Image Bytes

Pobierz bajty obrazu, gdzie każdy tablica bajtów reprezentuje jedną stronę. W tym przypadku mamy jedną stronę.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

### Step 5: Save Image Bytes to File

Zapisz bajty obrazu do pliku, zapewniając pomyślną konwersję z EPS do PNG.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

### Step 6: Verify Metered License

Sprawdź wizualnie, czy licencja metrowa została pomyślnie zastosowana. Jeśli wynikowy obraz nie zawiera czerwonej wiadomości oceny, oznacza to, że licencja metrowa została zastosowana bez problemów.

Teraz możesz w pełni wykorzystać możliwości Aspose.Page dla .NET z licencją metrową!

## Common Issues and Solutions

| Issue | Cause | Fix |
|-------|-------|-----|
| Czerwony baner oceny nadal się pojawia | Licencja nie ustawiona lub nieprawidłowe klucze | Sprawdź ponownie klucze publiczny/prywatny i upewnij się, że `SetMeteredKey` jest wywoływany przed przetwarzaniem dokumentu |
| Nie utworzono pliku wyjściowego | Nieprawidłowa ścieżka `dataDir` lub uprawnienia do pliku | Sprawdź, czy katalog istnieje i aplikacja ma uprawnienia do zapisu |
| Wiele stron nie zapisano | Zapisano tylko pierwszą stronę | Iteruj przez `imagesBytes` i zapisz każdą tablicę do osobnego pliku PNG |

## Frequently Asked Questions

**P:** Czy mogę używać licencji metrowej w pipeline CI/CD?  
**O:** Tak, możesz przechowywać klucze w bezpieczny sposób (np. w zmiennych środowiskowych) i wywołać `SetMeteredKey` podczas procesu budowania.

**P:** Czy Aspose.Page obsługuje zachowanie profilu kolorów przy konwersji do PNG?  
**O:** Wyjście PNG zachowuje oryginalne informacje o kolorach, ale możesz je dalej dostosować za pomocą `ImageSaveOptions`.

**P:** Czy można konwertować EPS do innych formatów rastrowych (JPEG, BMP)?  
**O:** Oczywiście — wystarczy zmienić `ImageSaveOptions` na żądany format.

**P:** Jaki jest maksymalny obsługiwany rozmiar pliku EPS?  
**O:** Aspose.Page obsługuje duże pliki, ale zużycie pamięci rośnie wraz z rozdzielczością obrazu. Rozważ przetwarzanie stron pojedynczo w przypadku bardzo dużych dokumentów.

**P:** Jak programowo uzyskać liczbę stron w pliku EPS?  
**O:** Użyj `document.PagesCount` po załadowaniu `PsDocument`.

## FAQ's

### Q1: Jak uzyskać licencję metrową dla Aspose.Page dla .NET?

A1: Odwiedź [purchase.aspose.com](https://purchase.aspose.com/buy), aby nabyć ważną licencję.

### Q2: Gdzie mogę znaleźć dokumentację Aspose.Page dla .NET?

A2: Zobacz [Aspose.Page .NET](https://reference.aspose.com/page/net/) po kompleksową dokumentację.

### Q3: Czy istnieje forum dyskusyjne i wsparcie dla Aspose.Page?

A3: Tak, odwiedź [forum](https://forum.aspose.com/c/page/39), aby wziąć udział w społeczności i uzyskać pomoc.

### Q4: Czy mogę wypróbować Aspose.Page dla .NET przed zakupem?

A4: Oczywiście! Uzyskaj dostęp do wersji próbnej pod [here](https://releases.aspose.com/).

### Q5: Jak mogę uzyskać tymczasową licencję dla Aspose.Page dla .NET?

A5: Odwiedź [temporary license/](https://purchase.aspose.com/temporary-license/), aby uzyskać tymczasową licencję.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

---

**Last Updated:** 2026-01-28  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}