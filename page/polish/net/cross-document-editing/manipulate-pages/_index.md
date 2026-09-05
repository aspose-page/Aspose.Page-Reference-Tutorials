---
date: 2026-07-24
description: Dowiedz się, jak scalać dokumenty XPS przy użyciu Aspose.Page for .NET.
  Ten przewodnik krok po kroku przedstawia techniki page manipulation dla uzyskania
  efektywnych wyników.
keywords:
- merge xps documents
- how to merge xps
- asp page .net tutorial
lastmod: 2026-07-24
linktitle: Manipuluj stronami
og_description: Efektywne scalanie dokumentów XPS przy użyciu Aspose.Page for .NET.
  Ten przewodnik przeprowadza Cię przez merging, inserting i removing pages, prezentując
  przejrzyste przykłady kodu.
og_image_alt: Guide showing how to merge XPS documents using Aspose.Page in a .NET
  application
og_title: Scal dokumenty XPS przy użyciu Aspose.Page for .NET – Fast Page Manipulation
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Learn how to merge XPS documents with Aspose.Page for .NET. This step‑by‑step
    guide shows page manipulation techniques for efficient results.
  headline: Merge XPS Documents with Aspose.Page for .NET
  type: TechArticle
- description: Learn how to merge XPS documents with Aspose.Page for .NET. This step‑by‑step
    guide shows page manipulation techniques for efficient results.
  name: Merge XPS Documents with Aspose.Page for .NET
  steps:
  - name: '**InsertPage(1, doc2.Page, false)** – places the first page of `doc2` at
      position 1 in `doc4`.'
    text: '**InsertPage(1, doc2.Page, false)** – places the first page of `doc2` at
      position 1 in `doc4`.'
  - name: '**AddPage(doc3.Page, false)** – appends the first page of `doc3` to the
      end of `doc4`.'
    text: '**AddPage(doc3.Page, false)** – appends the first page of `doc3` to the
      end of `doc4`.'
  - name: '**RemovePageAt(2)** – removes the page now at index 2 (useful for eliminating
      unwanted pages).'
    text: '**RemovePageAt(2)** – removes the page now at index 2 (useful for eliminating
      unwanted pages).'
  - name: '**InsertPage(2, doc1.SelectActivePage(3), false)** – inserts the third
      page of `doc1` into position 2, completing the merge.'
    text: '**InsertPage(2, doc1.SelectActivePage(3), false)** – inserts the third
      page of `doc1` into position 2, completing the merge.'
  type: HowTo
- questions:
  - answer: Absolutely. Create additional `XpsDocument` instances and use `InsertPage`
      or `AddPage` repeatedly to build a larger merged document.
    question: Can I merge more than three XPS files?
  - answer: Yes. Aspose.Page copies the page content byte‑for‑byte, so text, images,
      and vector graphics remain unchanged.
    question: Does the merge preserve original formatting and graphics?
  - answer: Use `AddPage(sourcePage, false)` which appends the page to the document’s
      end.
    question: How do I insert a page at the end without specifying an index?
  - answer: The API is fully headless; you can run the same code in ASP.NET, Azure
      Functions, or any server‑side .NET environment.
    question: Is it possible to merge XPS documents on a server without a UI?
  - answer: Aspose.Page currently does not support encrypted XPS files; you must decrypt
      them before merging.
    question: What if my XPS files are password‑protected?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- merge xps
- Aspose.Page
- .NET XPS manipulation
- document merging
- C# XPS processing
title: Scal dokumenty XPS przy użyciu Aspose.Page for .NET
url: /pl/net/cross-document-editing/manipulate-pages/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Scal dokumenty XPS przy użyciu Aspose.Page dla .NET

## Wprowadzenie

W tym samouczku dowiesz się, jak **scalić dokumenty XPS** i manipulować ich stronami przy użyciu biblioteki Aspose.Page w środowisku .NET. Niezależnie od tego, czy musisz połączyć wiele raportów w jeden plik XPS, zmienić kolejność stron dla uzyskania dopracowanego wyniku, czy usunąć niechciane sekcje, ten przewodnik przeprowadzi Cię przez cały proces z jasnymi, konwersacyjnymi wyjaśnieniami i gotowymi do uruchomienia fragmentami kodu.

## Szybkie odpowiedzi
- **Co mogę zrobić z Aspose.Page?** Scal dokumenty XPS, wstawiać, dodawać lub usuwać strony oraz zapisać wynik.  
- **Czy potrzebuję licencji do testów?** Dostępna jest tymczasowa licencja do oceny.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Czy Visual Studio jest wymagane?** Nie, każde IDE obsługujące C# działa, ale zalecane jest Visual Studio.  
- **Jak długo trwa scalanie?** Zazwyczaj kilka sekund dla standardowych plików XPS.

## Czym jest scalanie dokumentów XPS?

Scalanie dokumentów XPS oznacza pobieranie stron z dwóch lub więcej istniejących plików XPS i łączenie ich w jeden dokument XPS. Takie podejście pozwala tworzyć skonsolidowane raporty, kompilować podręczniki wielochapterowe lub przygotowywać pakiety gotowe do druku bez konwertowania do innego formatu, oszczędzając zarówno czas, jak i miejsce na dysku.

## Dlaczego używać Aspose.Page dla .NET?

Aspose.Page oferuje **czyste API .NET**, które działa bezpośrednio na plikach XPS — nie ma potrzeby używania zewnętrznych narzędzi ani komponentów firm trzecich. Zapewnia precyzyjną kontrolę nad kolejnością stron, punktami wstawiania i zachowaniem zawartości, co czyni proces scalania niezawodnym i szybkim. Biblioteka obsługuje **ponad 30 metod manipulacji XPS** i może obsługiwać dokumenty do **500 stron** bez ładowania całego pliku do pamięci, zapewniając wydajność klasy korporacyjnej.

## Wymagania wstępne

- **Aspose.Page for .NET** – pobierz z [dokumentacji Aspose.Page for .NET](https://reference.aspose.com/page/net/).  
- **Środowisko programistyczne** – Visual Studio, Rider lub dowolne IDE obsługujące C#.  
- **Pliki XPS wejściowe** – trzy przykładowe pliki (`input1.xps`, `input2.xps`, `input3.xps`) umieszczone w znanym folderze.

## Importowanie przestrzeni nazw

Te przestrzenie nazw zapewniają dostęp do podstawowych klas dokumentu XPS, modeli stron oraz podstawowych narzędzi rysunkowych.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Krok 1: Ustaw katalog dokumentów

Zastąp **Your Document Directory** pełną ścieżką, w której przechowywane są Twoje pliki XPS, np. `C:\\Docs\\XpsFiles\\`.

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: Utwórz instancje dokumentów XPS

Klasa `XpsDocument` reprezentuje pojedynczy plik XPS i udostępnia metody do odczytu, edycji i zapisu jego stron.  

```csharp
XpsDocument doc1 = new XpsDocument(dataDir + "input1.xps");
XpsDocument doc2 = new XpsDocument(dataDir + "input2.xps");
XpsDocument doc3 = new XpsDocument(dataDir + "input3.xps");
XpsDocument doc4 = new XpsDocument();
```

- `doc1`, `doc2` i `doc3` reprezentują dokumenty źródłowe, które chcesz scalić.  
- `doc4` jest pustym dokumentem XPS, który będzie przechowywał wynik scalania.

## Krok 3: Wstawianie, dodawanie i usuwanie stron

Metoda `InsertPage` wstawia stronę źródłową w określonej pozycji w docelowym dokumencie XPS.  
Metoda `AddPage` dodaje stronę źródłową na koniec docelowego dokumentu.  
Metoda `RemovePageAt` usuwa stronę o podanym indeksie zerowym.  
Metoda `SelectActivePage` pobiera określoną stronę z dokumentu źródłowego do dalszych operacji.  

```csharp
doc4.InsertPage(1, doc2.Page, false);
doc4.AddPage(doc3.Page, false);
doc4.RemovePageAt(2);
doc4.InsertPage(2, doc1.SelectActivePage(3), false);
```

Oto, co robi każda linia:

1. **InsertPage(1, doc2.Page, false)** – umieszcza pierwszą stronę `doc2` na pozycji 1 w `doc4`.  
2. **AddPage(doc3.Page, false)** – dodaje pierwszą stronę `doc3` na koniec `doc4`.  
3. **RemovePageAt(2)** – usuwa stronę znajdującą się obecnie pod indeksem 2 (przydatne do eliminacji niechcianych stron).  
4. **InsertPage(2, doc1.SelectActivePage(3), false)** – wstawia trzecią stronę `doc1` na pozycję 2, kończąc scalanie.

Te operacje ilustrują, jak można **scalić dokumenty XPS**, jednocześnie zmieniając kolejność lub usuwając strony w razie potrzeby.

## Krok 4: Zapisz scalony dokument

Metoda `Save` zapisuje strukturę XPS znajdującą się w pamięci do fizycznego pliku.  

```csharp
doc4.Save(dataDir + "out.xps");
```

Końcowy scalony plik XPS (`out.xps`) jest zapisywany w tym samym katalogu. Teraz możesz otworzyć go w dowolnym przeglądarce XPS lub dalej przetwarzać przy użyciu Aspose.Page.

## Typowe problemy i rozwiązania
- **File not found** – sprawdź ponownie ścieżkę `dataDir` i upewnij się, że pliki wejściowe istnieją.  
- **Invalid page index** – indeksy stron są liczone od 1; próba wstawienia nieistniejącej strony powoduje wyjątek.  
- **License errors** – użyj tymczasowej lub pełnej licencji przed wdrożeniem do produkcji.

## Najczęściej zadawane pytania

**Q: Czy mogę scalić więcej niż trzy pliki XPS?**  
A: Oczywiście. Utwórz dodatkowe instancje `XpsDocument` i używaj wielokrotnie `InsertPage` lub `AddPage`, aby zbudować większy scalony dokument.

**Q: Czy scalanie zachowuje oryginalne formatowanie i grafikę?**  
A: Tak. Aspose.Page kopiuje zawartość strony bajt po bajcie, więc tekst, obrazy i grafika wektorowa pozostają niezmienione.

**Q: Jak wstawić stronę na koniec bez podawania indeksu?**  
A: Użyj `AddPage(sourcePage, false)`, co dodaje stronę na koniec dokumentu.

**Q: Czy można scalić dokumenty XPS na serwerze bez interfejsu użytkownika?**  
A: API jest w pełni bezgłowe; możesz uruchomić ten sam kod w ASP.NET, Azure Functions lub w dowolnym środowisku .NET po stronie serwera.

**Q: Co jeśli moje pliki XPS są chronione hasłem?**  
A: Aspose.Page obecnie nie obsługuje zaszyfrowanych plików XPS; musisz je odszyfrować przed scalaniem.

---

**Ostatnia aktualizacja:** 2026-07-24  
**Testowano z:** Aspose.Page for .NET 24.10  
**Autor:** Aspose

## Powiązane samouczki

- [Utwórz dokument XPS – Aspose.Page dla .NET](/page/net/document-creation/create-xps-document/)
- [Dodaj stronę do dokumentu XPS przy użyciu Aspose.Page dla .NET](/page/net/page-manipulation/add-page-to-xps-document/)
- [Scal dokumenty XPS do PDF przy użyciu Aspose.Page dla .NET](/page/net/document-merging/merge-xps-documents-into-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}