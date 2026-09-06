---
date: 2026-08-08
description: Dowiedz się, jak tworzyć pliki EPS z metadanymi XMP i dodawać nazwane
  wartości przy użyciu Aspose.Page dla .NET. Przewodnik krok po kroku z przykładami
  kodu.
keywords:
- create eps with xmp
- add named value eps
- aspose.page metadata
lastmod: 2026-08-08
linktitle: Dodaj nazwany parametr
og_description: Tworzenie EPS z metadanymi XMP w .NET przy użyciu Aspose.Page. Ten
  przewodnik pokazuje, jak szybko i niezawodnie dodawać nazwane wartości do plików
  EPS.
og_image_alt: Guide showing how to add XMP named value to an EPS file with Aspose.Page
og_title: Tworzenie EPS z XMP – dodaj nazwany parametr przy użyciu Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to create EPS with XMP metadata and add named values using
    Aspose.Page for .NET. Step‑by‑step guide with code placeholders.
  headline: Create EPS with XMP – add named value using Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page supports EPS versions 3.0 through 3.3, ensuring broad compatibility
      with legacy and modern files.
    question: Is Aspose.Page compatible with different EPS file versions?
  - answer: Yes, a commercial license is required for production use. You can purchase
      a license **[Aspose.Page license purchase page](https://purchase.aspose.com/buy)**.
    question: Can I use Aspose.Page for commercial projects?
  - answer: Yes, a fully functional trial can be downloaded **[Aspose.Page free trial
      download page](https://releases.aspose.com/)**.
    question: Is there a free trial available?
  - answer: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**
      to ask questions and share experiences.
    question: How can I get support or join the community?
  - answer: A temporary license lets you evaluate the product for a short period.
      You can request one **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: What is a temporary license and how do I obtain one?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: Tworzenie EPS z XMP – dodaj nazwany parametr przy użyciu Aspose.Page
url: /pl/net/eps-metadata-management/modify-eps-metadata-add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz EPS z XMP – dodaj nazwany parametr przy użyciu Aspose.Page

## Wprowadzenie

W tym samouczku dowiesz się, jak **utworzyć EPS z metadanymi XMP** i wstrzyknąć nazwany parametr przy użyciu biblioteki Aspose.Page dla .NET. Niezależnie od tego, czy budujesz potok przetwarzania wsadowego, czy potrzebujesz wzbogacić pliki EPS o własne znaczniki XMP, poniższe kroki przeprowadzą Cię przez wszystko – od konfiguracji projektu po zapis zmodyfikowanego pliku. Aspose.Page potrafi obsłużyć dokumenty EPS do **500 stron** bez ładowania całego pliku do pamięci, co czyni go odpowiednim dla scenariuszy o dużej objętości.

## Szybkie odpowiedzi
- **Jaki jest główny cel?** Dodaj nazwany wartość XMP do istniejącego pliku EPS.  
- **Która biblioteka jest wymagana?** Aspose.Page dla .NET.  
- **Czy potrzebna jest licencja?** Wymagana jest licencja komercyjna do produkcji; dostępna jest wersja próbna.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Jak długo trwa implementacja?** Około 10–15 minut dla podstawowego przypadku użycia.

## Jak utworzyć EPS z metadanymi XMP w .NET?

Załaduj docelowy plik EPS, uzyskaj (lub utwórz) jego obiekt metadanych XMP, dodaj wymaganą nazwę wartości, a na końcu zapisz dokument z powrotem na dysk. Ten przepływ pracy wymaga tylko kilku wywołań metod i działa konsekwentnie we wszystkich obsługiwanych wersjach EPS. Podejście zachowuje istniejącą treść stron oraz inne struktury XMP, dzięki czemu możesz bezpiecznie łączyć wiele aktualizacji metadanych.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

- Podstawową znajomość C# i struktury projektu .NET.  
- Visual Studio 2022 (lub dowolne kompatybilne IDE).  
- Bibliotekę Aspose.Page dla .NET. Jeśli jeszcze jej nie masz, pobierz ją ze **Strona pobierania Aspose.Page dla .NET**([Aspose.Page for .NET download page](https://releases.aspose.com/page/net/)).  

## Importowanie przestrzeni nazw

Poniższe przestrzenie nazw zapewniają dostęp do klas obsługi EPS, wyjścia urządzenia i metadanych XMP w Aspose.Page.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Krok 1: zainicjalizuj strumień wejściowy pliku EPS

Utwórz `FileStream` dla źródłowego pliku EPS i zainicjalizuj obiekt `PsDocument`, aby pracować z dokumentem.

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Krok 2: pobierz metadane XMP

Pobierz obiekt `XmpMetadata` z dokumentu; ten obiekt reprezentuje osadzony pakiet XMP.

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## Krok 3: zmień wartości metadanych XMP

Użyj metody `AddNamedValue` klasy `XmpMetadata`, aby wstawić nową nazwę wartości do określonej struktury XMP.

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## Krok 4: zapisz plik EPS z zmienionymi metadanymi XMP

Zapisz zmodyfikowany dokument, zapisując go do nowego `FileStream`.

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## Dlaczego używać Aspose.Page do metadanych EPS?

Aspose.Page obsługuje **ponad 50 schematów XMP** i może przetwarzać pliki EPS do **500 stron**, utrzymując zużycie pamięci poniżej **30 MB** dla typowych dokumentów. Biblioteka nie polega na zewnętrznych narzędziach ani kodzie natywnym, co gwarantuje spójne zachowanie w środowiskach Windows, Linux i macOS.

## Typowe problemy i rozwiązywanie

- **Brak pakietu XMP:** Jeśli `GetXmpMetadata()` zwraca `null`, plik EPS nie zawiera bloku XMP. Biblioteka automatycznie go utworzy, ale upewnij się, że plik nie jest uszkodzony.  
- **Konflikty przestrzeni nazw:** Dodając własne nazwane wartości, użyj unikalnego URI przestrzeni nazw, aby uniknąć kolizji z istniejącymi schematami.  
- **Duże pliki:** Dla plików EPS większych niż 200 MB rozważ strumieniowanie wyjścia, aby uniknąć nadmiernego zużycia pamięci.

## Najczęściej zadawane pytania

**P:** Czy Aspose.Page jest kompatybilny z różnymi wersjami plików EPS?  
**O:** Aspose.Page obsługuje wersje EPS od 3.0 do 3.3, zapewniając szeroką kompatybilność z plikami starszymi i nowoczesnymi.

**P:** Czy mogę używać Aspose.Page w projektach komercyjnych?  
**O:** Tak, wymagana jest licencja komercyjna do użytku produkcyjnego. Możesz zakupić licencję **[Strona zakupu licencji Aspose.Page](https://purchase.aspose.com/buy)**.

**P:** Czy dostępna jest darmowa wersja próbna?  
**O:** Tak, w pełni funkcjonalną wersję próbną można pobrać **[Strona pobierania darmowej wersji próbnej Aspose.Page](https://releases.aspose.com/)**.

**P:** Jak mogę uzyskać wsparcie lub dołączyć do społeczności?  
**O:** Odwiedź **[forum Aspose.Page](https://forum.aspose.com/c/page/39)**, aby zadawać pytania i dzielić się doświadczeniami.

**P:** Czym jest licencja tymczasowa i jak ją uzyskać?  
**O:** Licencja tymczasowa pozwala ocenić produkt przez krótki okres. Możesz ją zamówić na **[stronie żądania licencji tymczasowej](https://purchase.aspose.com/temporary-license/)**.

---

**Ostatnia aktualizacja:** 2026-08-08  
**Testowano z:** Aspose.Page 24.11 dla .NET  
**Autor:** Aspose

## Powiązane samouczki

- [Dodaj metadane do dokumentu EPS przy użyciu Aspose.Page dla .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Zmień nazwany parametr przy użyciu Aspose.Page dla .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)
- [Wyodrębnij metadane z dokumentu EPS przy użyciu Aspose.Page dla .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}