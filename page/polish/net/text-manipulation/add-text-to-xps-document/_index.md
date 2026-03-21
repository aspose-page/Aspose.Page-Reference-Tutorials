---
date: 2026-03-21
description: Dowiedz się, jak tworzyć dokumenty XPS w .NET i dodawać tekst przy użyciu
  Aspose.Page dla .NET. Przewodnik krok po kroku dla programistów .NET.
linktitle: Add Text to XPS Document
second_title: Aspose.Page .NET API
title: Utwórz dokument XPS w .NET i dodaj tekst przy użyciu Aspose.Page
url: /pl/net/text-manipulation/add-text-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tworzenie dokumentu XPS w .NET i dodawanie tekstu przy użyciu Aspose.Page

W nowoczesnym programowaniu w .NET umiejętność **tworzenia dokumentu XPS w .NET** programowo jest bardzo cenna, szczególnie gdy trzeba generować raporty do druku, faktury lub własną grafikę. Ten samouczek pokaże, jak przy użyciu Aspose.Page **aspose.page add text** dodać tekst do dokumentu XPS, dając pełną kontrolę nad układem i stylizacją — wszystko z poziomu aplikacji .NET.

## Szybkie odpowiedzi
- **Co obejmuje ten samouczek?** Dodawanie tekstu do nowo utworzonego dokumentu XPS przy użyciu Aspose.Page dla .NET.  
- **Jak długo to zajmuje?** Około 5‑10 minut dla podstawowej implementacji.  
- **Jakie są wymagania wstępne?** Środowisko programistyczne .NET oraz biblioteka Aspose.Page.  
- **Czy wymagana jest licencja?** Tak, do użytku produkcyjnego potrzebna jest ważna licencja Aspose.Page.  
- **Czy działa na .NET Core / .NET 6+?** Oczywiście – Aspose.Page obsługuje wszystkie współczesne wersje .NET.

## Co to jest create xps document .net?

Tworzenie dokumentu XPS w .NET oznacza generowanie pliku o stałym układzie, który zachowuje dokładny wygląd treści na różnych urządzeniach i drukarkach. XPS (XML Paper Specification) to otwarty standard Microsoftu do opisu stron, podobny do PDF, ale w pełni oparty na XML.

## Dlaczego warto używać Aspose.Page do dodawania tekstu?

Aspose.Page oferuje wysokopoziomowe, obiektowo‑zorientowane API, które ukrywa niskopoziomowy znacznik XPS. Można dodawać tekst, grafikę i kształty bez konieczności ręcznego manipulowania surowym XML, co przyspiesza proces tworzenia i zmniejsza liczbę błędów.

## Wymagania wstępne

- Aspose.Page dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Page. Możesz ją pobrać z [dokumentacji Aspose.Page dla .NET](https://reference.aspose.com/page/net/).
- Środowisko programistyczne: Skonfiguruj swoje środowisko .NET. Jeśli jeszcze tego nie zrobiłeś, postępuj zgodnie z instrukcjami instalacji podanymi w [dokumentacji](https://reference.aspose.com/page/net/).
- Katalog dokumentów: Utwórz katalog, w którym będą przechowywane dokumenty. Zastąp w podanym fragmencie kodu „Your Document Directory” rzeczywistą ścieżką.

Teraz, gdy omówiliśmy podstawy, przejdźmy do kodu.

## Importowanie przestrzeni nazw

Najpierw zaimportuj niezbędne przestrzenie nazw, aby rozpocząć projekt:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Krok 1: Utworzenie dokumentu XPS w .NET

Utwórz nowy dokument XPS, który będzie pełnił rolę płótna dla naszego tekstu.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

## Krok 2: Utworzenie pędzla dla tekstu

Zdefiniuj pędzel jednokolorowy określający kolor tekstu. Tutaj używamy czerni.

```csharp
// ExStart:4
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
// ExEnd:4
```

## Krok 3: Dodanie glifów (aspose.page add text)

Glify to niskopoziomowa reprezentacja znaków w dokumencie XPS. To wywołanie dodaje tekst „Hello World!” w określonych współrzędnych.

```csharp
// ExStart:5
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.Fill = textFill;
// ExEnd:5
```

## Krok 4: Zapisanie powstałego dokumentu XPS

Zapisz dokument na dysku, aby móc go później wyświetlić lub wydrukować.

```csharp
// ExStart:6
doc.Save(dataDir + "AddText_out.xps");
// ExEnd:6
```

Postępując zgodnie z tymi krokami, pomyślnie **create XPS document .NET** i dodałeś własny tekst przy użyciu Aspose.Page.

## Typowe problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|-------|--------|-----|
| **Plik nie został znaleziony** podczas zapisu | `dataDir` wskazuje na nieistniejący folder | Upewnij się, że katalog istnieje lub użyj `Directory.CreateDirectory(dataDir)` przed zapisem. |
| **Tekst niewidoczny** | Kolor pędzla jest taki sam jak tło | Zmien `Color.Black` na inny kontrastujący kolor. |
| **Nieobsługiwana czcionka** | Czcionka nie jest zainstalowana w systemie | Użyj czcionki, która na pewno jest dostępna, lub osadź czcionkę przy pomocy funkcji osadzania czcionek Aspose.Page. |

## Najczęściej zadawane pytania

### Q1: Czy mogę dostosować czcionkę i rozmiar dodawanego tekstu?

A1: Tak, masz pełną kontrolę nad czcionką i rozmiarem. Dostosuj odpowiednie parametry w metodzie `AddGlyphs`.

### Q2: Czy Aspose.Page jest kompatybilny z .NET Core?

A2: Absolutnie! Aspose.Page obsługuje .NET Core, zapewniając zgodność z najnowszymi technologiami .NET.

### Q3: Czy istnieją wymagania licencyjne przy używaniu Aspose.Page?

A3: Tak, potrzebna jest ważna licencja. Opcje licencjonowania znajdziesz [tutaj](https://purchase.aspose.com/buy).

### Q4: Jak mogę uzyskać wsparcie lub pomoc?

A4: Odwiedź [forum Aspose.Page](https://forum.aspose.com/c/page/39), aby połączyć się ze społecznością i uzyskać pomoc.

### Q5: Czy dostępna jest bezpłatna wersja próbna?

A5: Oczywiście! Bezpłatną wersję próbną możesz pobrać [tutaj](https://releases.aspose.com/).

**Dodatkowe pytania i odpowiedzi**

**P: Czy mogę dodać wiele bloków tekstu na tej samej stronie?**  
O: Tak, po prostu wywołaj `doc.AddGlyphs` wielokrotnie, podając różne współrzędne.

**P: Czy Aspose.Page umożliwia obracanie tekstu?**  
O: Możesz zastosować macierz transformacji do obiektu `XpsGlyphs`, aby obrócić lub pochylić tekst.

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Ostatnia aktualizacja:** 2026-03-21  
**Testowano z:** Aspose.Page 24.11 dla .NET  
**Autor:** Aspose  

---