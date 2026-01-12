---
date: 2026-01-12
description: Dowiedz się, jak modyfikować dokument XPS przy użyciu Aspose.Page dla
  .NET i odkryj, jak dodać tekst do plików XPS za pomocą prostych przykładów kodu.
linktitle: Modify XPS Document
second_title: Aspose.Page .NET API
title: Modyfikuj dokument XPS przy użyciu Aspose.Page dla .NET
url: /pl/net/document-creation/modify-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Modyfikacja dokumentu XPS przy użyciu Aspose.Page dla .NET

## Wprowadzenie

Witamy w naszym przewodniku krok po kroku, jak **modyfikować pliki dokumentów XPS** przy użyciu Aspose.Page dla .NET. Niezależnie od tego, czy musisz wstawić podpis, dodać znak wodny, czy po prostu umieścić własny tekst na stronie, ten tutorial pokaże Ci dokładnie **jak dodać tekst** do dokumentu XPS w kilka minut. Przejdziemy przez każdy wiersz kodu, wyjaśnimy, dlaczego każdy krok ma znaczenie, i podpowiemy, jak uniknąć typowych pułapek.

### Szybkie odpowiedzi
- **Co obejmuje ten tutorial?** Dodanie tekstu podpisu („Confirmed”) do wybranych stron pliku XPS.  
- **Jakiej biblioteki wymaga?** Aspose.Page dla .NET (najnowsza wersja).  
- **Czy potrzebna jest licencja?** Tymczasowa licencja wystarczy do testów; pełna licencja jest wymagana w produkcji.  
- **Jakie wersje .NET są wspierane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Jak długo trwa implementacja?** Około 10 minut dla podstawowego wstawienia podpisu.

## Co to jest modyfikacja dokumentu XPS?

XPS (XML Paper Specification) to format dokumentu o stałym układzie firmy Microsoft, podobny do PDF. Modyfikacja dokumentu XPS oznacza programowe zmienianie jego zawartości wizualnej — dodawanie tekstu, obrazów lub kształtów — bez konwertowania pliku na inny format. Aspose.Page udostępnia rozbudowany model obiektowy, który pozwala edytować pliki XPS bezpośrednio z kodu .NET.

## Dlaczego używać Aspose.Page do modyfikacji dokumentów XPS?

* **Pełna kontrola** – praca ze stronami, glifami, pędzlami i przekształceniami na niskim poziomie.  
* **Brak zewnętrznych zależności** – czysta biblioteka .NET, bez potrzeby używania komponentów Office lub Adobe.  
* **Wieloplatformowość** – działa na Windows, Linux i macOS poprzez .NET Core.  
* **Wydajność** – efektywnie obsługuje duże dokumenty i wspiera zaawansowaną typografię.

## Wymagania wstępne

- **Aspose.Page dla .NET** – Zainstaluj pakiet NuGet lub pobierz bibliotekę z oficjalnej dokumentacji **[tutaj](https://reference.aspose.com/page/net/)**.  
- **Plik wejściowy XPS** – Pobierz przykładowy dokument XPS (np. `input1.xps`) ze **[strony wydań Aspose](https://releases.aspose.com/page/net/)**.  
- **Katalog roboczy** – Utwórz folder na swoim komputerze, w którym będą przechowywane pliki wejściowe i wyjściowe, i zanotuj jego pełną ścieżkę; przypiszesz tę ścieżkę do zmiennej `dir` w kodzie.  
- **Środowisko programistyczne** – Visual Studio 2019/2022, .NET Framework 4.7.2 lub nowszy, albo dowolny projekt .NET Core/5/6.

Teraz, gdy wszystko jest gotowe, przejdźmy do kodu.

## Importowanie przestrzeni nazw

W swoim projekcie .NET rozpocznij od zaimportowania wymaganych przestrzeni nazw dla Aspose.Page:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
using System.IO;
```

## Krok 1: Otwórz strumień dokumentu XPS

Otworzymy plik źródłowy XPS jako strumień i utworzymy obiekt `XpsDocument`, który reprezentuje cały dokument.

```csharp
// ExStart:3
// The path to the documents directory.
string dir = "Your Document Directory";
// Open a stream of XPS file
using (FileStream xpsStream = File.Open(dir + "input1.xps", FileMode.Open, FileAccess.Read))
{
    // Create PS document from stream
    XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
    // Continue to the next step...
}
// ExEnd:3
```

*Wskazówka:* Umieść strumień w bloku `using`, aby zapewnić automatyczne zwolnienie uchwytu pliku.

## Krok 2: Utwórz tekst podpisu

Następnie tworzymy pędzel jednolitego koloru, który będzie używany do rysowania glifów podpisu.

```csharp
// ExStart:4
// Create fill of the signature text
XpsSolidColorBrush textFill = document.CreateSolidColorBrush(Color.BlueViolet);
// Continue to the next step...
// ExEnd:4
```

Możesz zmienić `Color.BlueViolet` na dowolny `System.Drawing.Color`, który pasuje do Twojej identyfikacji wizualnej.

## Krok 3: Określ strony i dodaj podpis

Określimy, które strony mają otrzymać podpis, a następnie dodamy glify do każdej ze stron.

```csharp
// ExStart:5
// Define pages where signature will be set
int[] pageNumbers = new int[] {1, 2, 3};

// For every defined page set signature "Confirmed" at coordinates x=650 and y=950
for (int i = 0; i < pageNumbers.Length; i++)
{
    // Define active page
    document.SelectActivePage(pageNumbers[i]);

    // Create glyphs object
    XpsGlyphs glyphs = document.AddGlyphs("Arial", 24, FontStyle.Bold, 650, 900, "Confirmed");

    // Define fill for glyphs
    glyphs.Fill = textFill;
}
// Continue to the next step...
// ExEnd:5
```

*Dlaczego te współrzędne?* Wartości X i Y są mierzone w punktach (1/72 cala). Dostosuj je, aby umieścić tekst dokładnie tam, gdzie potrzebujesz w układzie strony.

## Krok 4: Zapisz zmiany w dokumencie XPS

Na koniec zapisz zmodyfikowany dokument z powrotem na dysk.

```csharp
// ExStart:6
// Save changed XPS document
document.Save(dir + "input1_out.xps");
// ExEnd:6
```

Nowy plik `input1_out.xps` zawiera teraz podpis „Confirmed” na stronach 1‑3.

## Typowe problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|-------|-------|----------|
| **Podpis niewidoczny** | Nieprawidłowe współrzędne lub nie wybrano strony | Sprawdź, czy `SelectActivePage` jest wywoływany dla każdej strony i dostosuj wartości X/Y. |
| **Wyjątek przy `AddGlyphs`** | Czcionka nie jest zainstalowana na serwerze | Upewnij się, że określona czcionka (np. Arial) jest dostępna, lub osadź własną czcionkę używając `document.AddFont`. |
| **Plik wyjściowy jest uszkodzony** | Strumień nie został prawidłowo zamknięty | Użyj instrukcji `using` dla wszystkich strumieni i wywołaj `document.Dispose()`, jeśli to konieczne. |
| **Spowolnienie wydajności przy dużych plikach** | Ładowanie całego dokumentu do pamięci | Przetwarzaj strony w partiach lub użyj `XpsLoadOptions` z opcjami strumieniowania (jeśli dostępne w nowszych wersjach). |

## Najczęściej zadawane pytania

**P: Czy Aspose.Page jest kompatybilny z najnowszymi frameworkami .NET?**  
O: Tak, Aspose.Page jest regularnie aktualizowany, aby wspierać .NET Framework 4.5+, .NET Core 3.1+, .NET 5 i .NET 6.

**P: Czy mogę dostosować czcionkę i styl dodawanego tekstu?**  
O: Oczywiście. Zmień parametry `AddGlyphs` (nazwa czcionki, rozmiar, `FontStyle`), aby dopasować je do swojego projektu.

**P: Czy istnieją limity rozmiaru plików XPS?**  
O: Aspose.Page radzi sobie z dużymi dokumentami, ale zużycie pamięci rośnie wraz z rozmiarem pliku. W przypadku bardzo dużych plików rozważ przetwarzanie stron pojedynczo.

**P: Jak uzyskać tymczasową licencję dla Aspose.Page?**  
O: Tymczasową licencję możesz uzyskać **[tutaj](https://purchase.aspose.com/temporary-license/)**.

**P: Gdzie mogę uzyskać pomoc lub połączyć się ze społecznością Aspose?**  
O: Odwiedź **[forum Aspose.Page](https://forum.aspose.com/c/page/39)**, aby zadawać pytania i dzielić się doświadczeniami.

## Podsumowanie

W tym tutorialu pokazaliśmy, jak **modyfikować pliki dokumentów XPS** poprzez dodanie własnego tekstu podpisu przy użyciu Aspose.Page dla .NET. Masz teraz solidne podstawy, aby wstawiać dowolny tekst, znak wodny lub adnotację na wybranych stronach pliku XPS. Eksperymentuj z różnymi czcionkami, kolorami i pozycjami, aby spełnić wymagania brandingowe Twojej aplikacji, i odkrywaj szersze możliwości API Aspose.Page w zakresie zaawansowanej grafiki i układu.

---

**Ostatnia aktualizacja:** 2026-01-12  
**Testowano z:** Aspose.Page 24.11 dla .NET (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}