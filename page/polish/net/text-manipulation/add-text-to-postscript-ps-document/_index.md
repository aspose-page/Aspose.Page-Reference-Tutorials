---
date: 2026-03-21
description: Dowiedz się, jak wypełniać tekst i dodawać tekst do dokumentów PS przy
  użyciu Aspose.Page dla .NET. Przewodnik krok po kroku z przykładami kodu.
linktitle: Add Text to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Jak wypełnić tekst w dokumentach PostScript (PS) za pomocą Aspose.Page
url: /pl/net/text-manipulation/add-text-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak wypełnić tekst w dokumentach PostScript (PS) przy użyciu Aspose.Page

## Wprowadzenie

Jeśli potrzebujesz **wypełnić tekst** w pliku PostScript (PS), Aspose.Page dla .NET umożliwia to w prosty sposób. Niezależnie od tego, czy generujesz raporty, faktury, czy własne grafiki, dodawanie i stylizowanie tekstu jest podstawowym wymogiem. W tym samouczku przeprowadzimy Cię przez cały proces — od konfiguracji środowiska po zapisanie finalnego dokumentu PS — abyś mógł pewnie dodawać tekst do plików PS w swoich aplikacjach .NET.

## Szybkie odpowiedzi
- **Co oznacza „fill text”?** Renderuje znaki przy użyciu jednolitego pędzla, malując glify bezpośrednio na stronie.  
- **Czy mogę używać własnych czcionek?** Tak — Aspose.Page obsługuje własne czcionki za pomocą funkcji `add custom font ps`.  
- **Jak zapisać dokument PS?** Wywołaj `document.Save()` po zamknięciu strony; zapisuje to plik na dysk (`save ps document`).  
- **Czy „fill and stroke text” jest obsługiwane?** Zdecydowanie; użyj `FillAndStrokeText`, aby zastosować zarówno wypełnienie, jak i kontur.  
- **Jakie wersje .NET są wymagane?** Dowolny .NET Framework 4.5+ lub środowisko .NET Core/5/6+.

## Co oznacza „how to fill text” w dokumencie PS?

Wypełnianie tekstu oznacza malowanie znaków jednolitym kolorem (lub pędzlem) bez konturu. W PostScript jest to odpowiednik operatora `fill`. Aspose.Page upraszcza to do łatwych w użyciu metod, takich jak `FillText` i `FillAndStrokeText`.

## Dlaczego warto używać Aspose.Page do dodawania własnych czcionek ps?

- **Pełne wsparcie czcionek** – czcionki systemowe i zewnętrzne TrueType/OpenType działają od razu.  
- **Precyzyjne pozycjonowanie** – kontrolujesz współrzędne X/Y, rozmiar i styl.  
- **Bogate stylowanie** – łącz wypełnienia, kontury i pióra, aby uzyskać efekty takie jak „fill and stroke text”.  
- **Wieloplatformowość** – działa na Windows, Linux i macOS przy użyciu tego samego API.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

- **Aspose.Page for .NET** – pobierz bibliotekę z [dokumentacji Aspose.Page .NET](https://reference.aspose.com/page/net/).  
- **Katalog dokumentów** – folder na Twoim komputerze, w którym będą znajdować się źródłowe i wyjściowe pliki PS (określany jako *Your Document Directory* w kodzie).  
- **Folder czcionek** – podfolder zawierający wszystkie własne czcionki, które zamierzasz używać.

## Importowanie przestrzeni nazw

Najpierw zaimportuj wymagane przestrzenie nazw, aby kompilator wiedział, gdzie znaleźć klasy, których będziemy używać:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Przewodnik krok po kroku

### Krok 1: Utwórz strumień wyjściowy dla dokumentu PS  

Otwieramy `FileStream`, który będzie przechowywać wygenerowany plik PS, konfigurować `PsSaveOptions`, aby wskazywał na nasz folder z własnymi czcionkami, oraz tworzymy instancję `PsDocument`.

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

> **Wskazówka:** Zachowaj blok `using`, aby zapewnić automatyczne zamknięcie strumienia, co jednocześnie finalizuje plik PS (`save ps document`).

### Krok 2: Wypełnij tekst czcionką systemową  

Tutaj demonstrujemy podstawową operację **wypełniania tekstu** przy użyciu wbudowanej czcionki *Times New Roman*.

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

### Krok 3: Wypełnij tekst własną czcionką  

Jeśli potrzebujesz konkretnego wyglądu, załaduj własną czcionkę z folderu czcionek przy użyciu `ExternalFontCache.FetchDrFont`. Spełnia to wymóg **add custom font ps**.

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

### Krok 4: Konturuj (obrysuj) tekst czcionką systemową  

Obrysowanie rysuje kontur glifu. Połącz je z wypełnieniem, aby uzyskać efekt „fill and stroke”.

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

> **Dlaczego to ważne:** Wywołanie `FillAndStrokeText` pokazuje, jak **wypełnić i obrysować tekst** w jednym kroku, dając Ci większą kontrolę typograficzną.

### Krok 5: Konturuj tekst własną czcionką  

Ta sama technika obrysowania działa z dowolną własną czcionką, którą załadowałeś.

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

### Krok 6: Zamknij stronę i zapisz dokument  

Zakończenie jest proste: zamknij bieżącą stronę i wywołaj `Save()`, aby zapisać plik PS na dysku.

```csharp
document.ClosePage();
document.Save();
}
```

> **Wynik:** Znajdziesz plik `AddText_outPS.ps` w *Your Document Directory*, zawierający zarówno wypełniony, jak i obrysowany tekst renderowany czcionkami systemowymi i własnymi.

## Typowe problemy i rozwiązania

| Problem | Rozwiązanie |
|-------|----------|
| **Custom font not found** | Sprawdź, czy plik czcionki (.ttf/.otf) istnieje w folderze wskazanym przez `AdditionalFontsFolders`. |
| **Text appears at wrong position** | Dostosuj współrzędne X/Y przekazywane do `FillText`/`OutlineText`. Pamiętaj, że PostScript używa punktów (1/72 cala). |
| **Colors look different** | Upewnij się, że używasz `SolidBrush` lub `Pen` z prawidłowymi wartościami `Color`. |
| **Document not saving** | Potwierdź, że blok `using` kończy się bez wyjątków i że aplikacja ma uprawnienia do zapisu w docelowym folderze. |

## Najczęściej zadawane pytania

**P: Czy mogę używać Aspose.Page z innymi bibliotekami .NET?**  
O: Tak, Aspose.Page integruje się płynnie z innymi komponentami .NET, pozwalając łączyć biblioteki PDF, obrazu lub wykresów w jednym rozwiązaniu.

**P: Czy własne czcionki są niezbędne w tym procesie?**  
O: Chociaż czcionki systemowe działają dobrze, własne czcionki dają pełną swobodę projektowania i są przydatne, gdy wymagana jest typografia specyficzna dla marki.

**P: Czy Aspose.Page jest odpowiedni do przetwarzania dokumentów na dużą skalę?**  
O: Zdecydowanie. Biblioteka jest zoptymalizowana pod kątem scenariuszy o wysokiej przepustowości i może efektywnie obsłużyć tysiące plików PS.

**P: Czy mogę zmodyfikować pozycję tekstu w dokumencie PS?**  
O: Oczywiście — wystarczy zmienić numeryczne wartości X/Y w wywołaniach `FillText` lub `OutlineText`.

**P: Gdzie mogę uzyskać pomoc w sprawach związanych z Aspose.Page?**  
O: Odwiedź [forum Aspose.Page](https://forum.aspose.com/c/page/39), aby połączyć się ze społecznością i uzyskać pomoc ekspertów.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-03-21  
**Testowano z:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose