---
date: 2026-01-15
description: Dowiedz się, jak scalać dokumenty XPS przy użyciu Aspose.Page dla .NET
  – krok po kroku przewodnik po płynnym łączeniu dokumentów.
linktitle: Merge XPS Documents
second_title: Aspose.Page .NET API
title: Jak scalić dokumenty XPS przy użyciu Aspose.Page dla .NET
url: /pl/net/document-merging/merge-xps-documents/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak scalać dokumenty XPS przy użyciu Aspose.Page dla .NET

## Wprowadzenie

Szukasz niezawodnego sposobu **jak scalać pliki XPS** programowo? W tym samouczku przeprowadzimy Cię krok po kroku przez proces scalania dokumentów XPS przy użyciu Aspose.Page dla .NET. Niezależnie od tego, czy musisz połączyć raporty, faktury, czy inne zasoby oparte na XPS, proces jest prosty i w pełni zautomatyzowany. Zanurzmy się i zobaczmy, jak uzyskać czysty, scalony plik XPS przy użyciu kilku linii kodu C#.

## Szybkie odpowiedzi
- **Jaką bibliotekę obsługuje scalanie XPS?** Aspose.Page dla .NET  
- **Jak długo trwa implementacja?** Zazwyczaj poniżej 10 minut  
- **Czy potrzebna jest licencja?** Licencja jest wymagana do użytku produkcyjnego; dostępna jest bezpłatna wersja próbna  
- **Obsługiwane wersje .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Czy mogę scalać zaszyfrowane pliki XPS?** Tak – Aspose.Page radzi sobie z zaszyfrowanymi dokumentami  

## Co to jest scalanie dokumentów XPS?
XPS (XML Paper Specification) to format dokumentów o stałym układzie opracowany przez Microsoft. Scalanie plików XPS oznacza łączenie wielu dokumentów XPS w jeden, ciągły plik, przy zachowaniu oryginalnego układu, czcionek i grafiki.

## Dlaczego warto używać Aspose.Page dla .NET?
- **Pełna kontrola** nad procesem scalania bez potrzeby korzystania z Microsoft XPS Viewer  
- **Brak zewnętrznych zależności** – wszystko działa wewnątrz Twojej aplikacji .NET  
- **Wysoka wydajność** – efektywnie działa nawet przy dużych dokumentach  
- **Cross‑platform** – kompatybilny z .NET Framework, .NET Core i .NET 5+  

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

- Podstawową znajomość C# i ekosystemu .NET.  
- **Aspose.Page dla .NET** zainstalowany – możesz go pobrać [tutaj](https://releases.aspose.com/page/net/).  
- Jeden lub więcej plików XPS, które chcesz połączyć.

## Importowanie przestrzeni nazw

W swoim projekcie C# zaimportuj przestrzeń nazw, która daje dostęp do API XPS:

```csharp
using Aspose.Page.XPS;
```

## Krok 1: Konfiguracja projektu

Utwórz nowy projekt konsolowy lub biblioteczny C# w Visual Studio, Rider lub wybranym IDE. Dodaj odwołanie do biblioteki Aspose.Page DLL (lub zainstaluj pakiet NuGet `Aspose.Page`). Dzięki temu uzyskasz dostęp do klasy `XpsDocument`, której użyjemy później.

## Krok 2: Inicjalizacja strumieni

Otwórz źródłowe pliki XPS jako strumienie wejściowe i utwórz strumień wyjściowy dla scalonego dokumentu. Instrukcje `using` zapewniają prawidłowe zamknięcie wszystkich strumieni po zakończeniu operacji.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Initialize XPS output stream
using (System.IO.Stream outStream = System.IO.File.Open(dataDir + "mergedXPSfiles.xps", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream inStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

## Krok 3: Ładowanie dokumentu XPS

Utwórz instancję `XpsDocument` z głównego strumienia wejściowego. Obiekt `XpsLoadOptions` pozwala dostosować zachowanie ładowania, jeśli zajdzie taka potrzeba.

```csharp
XpsDocument document = new XpsDocument(inStream, new XpsLoadOptions());
```

## Krok 4: Utworzenie tablicy plików XPS

Przygotuj tablicę typu string, która zawiera wszystkie pliki XPS, które chcesz scalić. Kolejność elementów w tablicy określa kolejność w finalnym dokumencie.

```csharp
string[] filesToMerge = new string[] { dataDir + "Demo.xps", dataDir + "sample.xps" };
```

## Krok 5: Scalanie plików XPS

Wywołaj metodę `Merge`, przekazując tablicę ścieżek do plików oraz strumień wyjściowy. Aspose.Page zajmuje się całą ciężką pracą – łączeniem stron, zachowaniem zasobów i zapisem finalnego pliku XPS.

```csharp
document.Merge(filesToMerge, outStream);
```

## Typowe problemy i wskazówki

- **Plik nie znaleziony** – Sprawdź dokładnie ścieżki w `filesToMerge`. Użycie `Path.Combine` może pomóc uniknąć błędów separatorów ścieżek.  
- **Zużycie pamięci** – Przy scalaniu dużej liczby plików rozważ przetwarzanie ich w partiach, aby utrzymać niskie zużycie pamięci.  
- **Zaszyfrowane dokumenty** – Jeśli którykolwiek źródłowy plik XPS jest chroniony hasłem, załaduj go przy użyciu odpowiednich poświadczeń przed scaleniem.

## Najczęściej zadawane pytania

**P1: Czy mogę scalać pliki XPS o różnych rozmiarach stron?**  
O: Tak. Aspose.Page automatycznie normalizuje wymiary stron podczas scalania.

**P2: Czy istnieje limit liczby plików XPS, które mogę połączyć?**  
O: Nie ma sztywnego limitu, ale bardzo duże kolekcje mogą wpływać na wydajność; monitoruj zużycie pamięci.

**P3: Czy potrzebuję specjalnej licencji do scalania zaszyfrowanych dokumentów XPS?**  
O: Pełna licencja Aspose.Page jest wymagana dla każdej funkcji na poziomie produkcyjnym, w tym obsługi zaszyfrowanych dokumentów.

**P4: Jak dodać własny stopka do każdej strony po scaleniu?**  
O: Po scaleniu możesz ponownie otworzyć wynikowy plik XPS przy użyciu `XpsDocument` i skorzystać z API rysowania, aby wstawić stopki.

**P5: Czy Aspose.Page obsługuje .NET Core?**  
O: Absolutnie. Biblioteka jest kompatybilna z .NET Core 3.1 i nowszymi, a także z .NET 5/6/7.

## Zakończenie

Teraz wiesz **jak scalać dokumenty XPS** efektywnie przy użyciu Aspose.Page dla .NET. Postępując zgodnie z powyższymi krokami, możesz zautomatyzować konsolidację dokumentów w dowolnej aplikacji .NET, oszczędzając czas i redukując ręczną pracę. Eksploruj dalej API, aby dodawać znaki wodne, szyfrować finalny plik lub manipulować poszczególnymi stronami według potrzeb.

---

**Ostatnia aktualizacja:** 2026-01-15  
**Testowano z:** Aspose.Page dla .NET (najnowsza wersja)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}