---
date: 2026-01-10
description: Bezproblemowo konwertuj XPS na PDF w .NET za pomocą Aspose.Page. Pobierz
  bibliotekę, zapoznaj się z dokumentacją i skorzystaj z darmowej wersji próbnej.
linktitle: Convert XPS to PDF
second_title: Aspose.Page .NET API
title: Konwertuj XPS na PDF przy użyciu Aspose.Page dla .NET
url: /pl/net/document-conversion/convert-xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konwertuj XPS do PDF przy użyciu Aspose.Page dla .NET

## Wprowadzenie

W tym samouczku dowiesz się **jak konwertować XPS do PDF** przy użyciu biblioteki Aspose.Page dla .NET. Konwersja XPS do PDF jest częstym wymogiem, gdy trzeba udostępnić dokumenty XPS użytkownikom posiadającym jedynie czytniki PDF lub gdy chcesz osadzić zawartość XPS w większych przepływach pracy opartych na PDF. Przejdziemy krok po kroku, wyjaśnimy, dlaczego każde ustawienie ma znaczenie, i pokażemy, jak dopracować wynik — np. ustawiając jakość JPEG i stosując kompresję obrazów w PDF.

## Szybkie odpowiedzi
- **Jaka biblioteka jest najlepsza do konwersji XPS na PDF?** Aspose.Page dla .NET
- **Czy potrzebna jest licencja do produkcji?** Tak, wymagana jest licencja komercyjna; dostępna jest wersja próbna.
- **Czy mogę kontrolować jakość obrazu?** Oczywiście — użyj `JpegQualityLevel` i `PdfImageCompression`.
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Czy można konwertować wiele plików XPS do jednego PDF?** Tak, poprzez iterację po plikach i łączenie wyników.

## Wymagania wstępne

Zanim rozpoczniemy tę podróż konwersji, upewnij się, że masz spełnione następujące wymagania:

- **Aspose.Page dla .NET** – Upewnij się, że biblioteka Aspose.Page dla .NET jest zainstalowana w Twoim środowisku programistycznym. Możesz ją pobrać z [dokumentacji Aspose.Page](https://reference.aspose.com/page/net/).
- **Środowisko programistyczne** – Skonfiguruj środowisko .NET z Visual Studio lub innym kompatybilnym IDE.
- **Dokument XPS** – Przygotuj dokument XPS, który chcesz przekonwertować na PDF. Może to być przykładowy plik XPS przechowywany w wyznaczonym katalogu.

## Importowanie przestrzeni nazw

Zanim przejdziesz do kodu, zaimportuj niezbędną przestrzeń nazw, aby funkcje Aspose.Page dla .NET były dostępne w Twoim projekcie:

```csharp
using Aspose.Page.XPS;
```

## Przewodnik krok po kroku

### Krok 1: Inicjalizacja katalogu dokumentów

Zdefiniuj folder, w którym znajduje się źródłowy plik XPS oraz miejsce, w którym zostanie zapisany wynikowy PDF.

```csharp
string dataDir = "Your Document Directory";
```

Zastąp `"Your Document Directory"` absolutną lub względną ścieżką do folderu zawierającego dokument XPS.

### Krok 2: Otwórz strumienie dla wyjścia PDF i wejścia XPS

Używamy dwóch strumieni plikowych — jednego do odczytu pliku XPS i drugiego do zapisu wygenerowanego PDF.

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

> **Wskazówka:** Upewnij się, że ścieżki są poprawne i że aplikacja ma uprawnienia odczytu/zapisu w docelowym folderze.

### Krok 3: Załaduj dokument XPS

Utwórz instancję `XpsDocument` z strumienia XPS. Obiekt `XpsLoadOptions` pozwala określić preferencje ładowania, ale domyślne ustawienia działają w większości scenariuszy.

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

### Krok 4: Skonfiguruj opcje zapisu PDF

Tutaj ustawiamy preferencje wyjścia PDF. Zwróć uwagę na użycie **kompresji obrazów PDF** (`PdfImageCompression.Jpeg`) oraz **jakości JPEG** (`JpegQualityLevel = 100`). Te ustawienia bezpośrednio wpływają na rozmiar pliku i jakość wizualną.

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

- **`JpegQualityLevel`** – Kontroluje jakość obrazów JPEG osadzonych w PDF (wyższa = lepsza jakość, większy plik).
- **`ImageCompression`** – Wybiera algorytm kompresji; JPEG jest idealny dla zdjęć.
- **`TextCompression`** – Kompresja Flate zmniejsza rozmiar PDF bez utraty jakości tekstu.
- **`PageNumbers`** – Umożliwia **zapis XPS jako PDF** tylko dla wybranych stron.

### Krok 5: Utwórz urządzenie renderujące PDF

`PdfDevice` działa jako cel renderowania, który zapisuje dane PDF do wcześniej otwartego strumienia.

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

### Krok 6: Zapisz dokument jako PDF

Na koniec wywołaj metodę `Save`, przekazując urządzenie renderujące oraz skonfigurowane opcje.

```csharp
document.Save(device, options);
```

Po zakończeniu wykonywania kodu plik `XPStoPDF_out.pdf` pojawi się w określonym katalogu, zawierając przekonwertowane strony z zastosowaną kompresją i ustawieniami jakości, które zdefiniowałeś.

## Dlaczego warto konwertować XPS do PDF?

- **Uniwersalna dostępność** – Czytniki PDF są zainstalowane praktycznie na każdym urządzeniu, podczas gdy czytniki XPS są rzadkością.
- **Zachowanie układu** – PDF zachowuje dokładny układ wizualny, czcionki i grafikę oryginalnego XPS.
- **Dalsze przetwarzanie** – Po konwersji do PDF możesz łączyć, anotować lub cyfrowo podpisywać dokument przy użyciu innych bibliotek Aspose.

## Typowe scenariusze użycia

- **Raportowanie w przedsiębiorstwie** – Generuj raporty XPS z systemów legacy i konwertuj je na PDF do dystrybucji.
- **Archiwizacja** – Przechowuj dokumenty jako PDF dla długoterminowej zachowalności, jednocześnie tworząc je ze źródeł XPS.
- **Usługi internetowe** – Udostępnij punkt API, który przyjmuje pliki XPS i zwraca pliki PDF w locie.

## Rozwiązywanie problemów i wskazówki

- **Plik nie znaleziony** – Sprawdź dokładnie ścieżkę `dataDir` i upewnij się, że nazwa pliku XPS jest zgodna.
- **Błędy uprawnień** – Uruchom Visual Studio jako Administrator lub przyznaj uprawnienia zapisu do folderu wyjściowego.
- **Duże pliki PDF** – Jeśli wynikowy PDF jest zbyt duży, obniż `JpegQualityLevel` lub zmień `ImageCompression` na `PdfImageCompression.Zip`.

## FAQ

### Q1: Czy mogę konwertować wiele plików XPS do jednego PDF przy użyciu Aspose.Page dla .NET?

A1: Tak, możesz iterować po wielu plikach XPS i stosować te same kroki, aby połączyć je w jeden PDF.

### Q2: Czy Aspose.Page dla .NET obsługuje inne formaty wyjściowe?

A2: Tak, Aspose.Page dla .NET obsługuje różne formaty wyjściowe, w tym TIFF, JPEG, PNG i inne.

### Q3: Jak mogę dostosować wygląd konwertowanego dokumentu PDF?

A3: Możesz modyfikować parametry obiektu opcji, takie jak kompresja obrazu i kompresja tekstu, aby uzyskać pożądany wygląd.

### Q4: Czy dostępna jest wersja próbna Aspose.Page dla .NET?

A4: Tak, możesz wypróbować możliwości Aspose.Page dla .NET, pobierając darmową wersję próbną [tutaj](https://releases.aspose.com/).

### Q5: Gdzie mogę uzyskać wsparcie społeczności dla Aspose.Page dla .NET?

A5: Odwiedź [forum Aspose.Page](https://forum.aspose.com/c/page/39) w celu dyskusji i uzyskania pomocy.

## Frequently Asked Questions (AI‑Friendly)

**Q: Jak ustawić jakość JPEG przy konwersji XPS do PDF?**  
A: Użyj właściwości `JpegQualityLevel` w obiekcie `PdfSaveOptions`. Ustawienie 100 zapewnia maksymalną jakość.

**Q: Co oznacza „kompresja obrazu PDF” w tym kontekście?**  
A: Odnosi się do opcji `ImageCompression`, która określa, w jaki sposób obrazy są kompresowane wewnątrz PDF (np. JPEG, Zip).

**Q: Czy mogę programowo generować PDF bez źródła XPS?**  
A: Tak, Aspose.Page obsługuje **c# generate pdf** bezpośrednio z poleceń rysowania, ale to wykracza poza zakres tego samouczka.

**Q: Czy istnieje sposób konwersji XPS do PDF bez utraty grafiki wektorowej?**  
A: Konwersja zachowuje dane wektorowe; wystarczy nie rasteryzować obrazów, pozostawiając `ImageCompression` ustawione na JPEG lub Zip w zależności od potrzeb.

**Q: Czy biblioteka obsługuje .NET Core?**  
A: Oczywiście – Aspose.Page dla .NET działa z .NET Core, .NET 5, .NET 6 i nowszymi wersjami.

---

**Ostatnia aktualizacja:** 2026-01-10  
**Testowane z:** Aspose.Page 24.11 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}