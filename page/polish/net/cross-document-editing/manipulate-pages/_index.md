---
date: 2026-01-10
description: Dowiedz się, jak scalać dokumenty XPS przy użyciu Aspose.Page dla .NET.
  Ten przewodnik krok po kroku pokazuje techniki manipulacji stronami dla uzyskania
  efektywnych rezultatów.
linktitle: Manipulate Pages
second_title: Aspose.Page .NET API
title: Scal dokumenty XPS przy użyciu Aspose.Page dla .NET
url: /pl/net/cross-document-editing/manipulate-pages/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Scalanie dokumentów XPS przy użyciu Aspose.Page dla .NET

## Wprowadzenie

W tym samouczku dowiesz się, jak **scalać dokumenty XPS** i manipulować ich stronami przy użyciu biblioteki Aspose.Page w środowisku .NET. Niezależnie od tego, czy potrzebujesz połączyć wiele raportów w jeden plik XPS, czy przearanżować strony dla uzyskania dopracowanego wyniku, ten przewodnik przeprowadzi Cię krok po kroku przez proces, z jasnymi wyjaśnieniami i gotowym do uruchomienia kodem.

## Szybkie odpowiedzi
- **Co mogę zrobić z Aspose.Page?** Scalanie dokumentów XPS, wstawianie, dodawanie lub usuwanie stron oraz zapisywanie wyniku.  
- **Czy potrzebuję licencji do testów?** Dostępna jest tymczasowa licencja do oceny.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Czy wymagany jest Visual Studio?** Nie, działa każde IDE obsługujące C#, ale Visual Studio jest zalecane.  
- **Jak długo trwa scalanie?** Zazwyczaj kilka sekund dla standardowych plików XPS.

## Czym jest scalanie dokumentów XPS?

Scalanie dokumentów XPS oznacza pobranie stron z dwóch lub więcej istniejących plików XPS i połączenie ich w jeden dokument XPS. Jest to przydatne przy tworzeniu skonsolidowanych raportów, kompilacji wielostronicowych podręczników lub przygotowywaniu gotowych do druku pakietów bez konwertowania do innego formatu.

## Dlaczego warto używać Aspose.Page dla .NET?

Aspose.Page oferuje **czyste API .NET**, które działa bezpośrednio na plikach XPS — nie wymaga zewnętrznych narzędzi ani komponentów firm trzecich. Daje Ci precyzyjną kontrolę nad kolejnością stron, punktami wstawiania i zachowaniem zawartości, co sprawia, że proces scalania jest niezawodny i szybki.

## Wymagania wstępne

- **Aspose.Page for .NET** – pobierz z [dokumentacji Aspose.Page for .NET](https://reference.aspose.com/page/net/).  
- **Środowisko programistyczne** – Visual Studio, Rider lub dowolne IDE obsługujące C#.  
- **Pliki XPS wejściowe** – trzy przykładowe pliki (`input1.xps`, `input2.xps`, `input3.xps`) umieszczone w znanym folderze.

## Importowanie przestrzeni nazw

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Te przestrzenie nazw zapewniają dostęp do podstawowych klas dokumentu XPS, modeli stron oraz podstawowych narzędzi rysunkowych.

## Krok 1: Ustaw katalog dokumentów

```csharp
string dataDir = "Your Document Directory";
```

Zastąp **Your Document Directory** pełną ścieżką, w której przechowywane są Twoje pliki XPS, np. `C:\\Docs\\XpsFiles\\`.

## Krok 2: Utwórz instancje dokumentów XPS

```csharp
XpsDocument doc1 = new XpsDocument(dataDir + "input1.xps");
XpsDocument doc2 = new XpsDocument(dataDir + "input2.xps");
XpsDocument doc3 = new XpsDocument(dataDir + "input3.xps");
XpsDocument doc4 = new XpsDocument();
```

- `doc1`, `doc2` i `doc3` reprezentują dokumenty źródłowe, które chcesz scalić.  
- `doc4` jest pustym dokumentem XPS, który będzie przechowywał wynik scalania.

## Krok 3: Wstawianie, dodawanie i usuwanie stron

```csharp
doc4.InsertPage(1, doc2.Page, false);
doc4.AddPage(doc3.Page, false);
doc4.RemovePageAt(2);
doc4.InsertPage(2, doc1.SelectActivePage(3), false);
```

Oto, co robi każda linia:

1. **InsertPage(1, doc2.Page, false)** – umieszcza pierwszą stronę `doc2` na pozycji 1 w `doc4`.  
2. **AddPage(doc3.Page, false)** – dodaje pierwszą stronę `doc3` na koniec `doc4`.  
3. **RemovePageAt(2)** – usuwa stronę znajdującą się teraz pod indeksem 2 (przydatne do eliminacji niechcianych stron).  
4. **InsertPage(2, doc1.SelectActivePage(3), false)** – wstawia trzecią stronę `doc1` na pozycję 2, kończąc scalanie.

Te operacje ilustrują, jak można **scalać dokumenty XPS**, jednocześnie przestawiając lub usuwając strony w razie potrzeby.

## Krok 4: Zapisz scalony dokument

```csharp
doc4.Save(dataDir + "out.xps");
```

Końcowy scalony plik XPS (`out.xps`) jest zapisywany w tym samym katalogu. Możesz go teraz otworzyć w dowolnym przeglądarce XPS lub dalej przetwarzać przy użyciu Aspose.Page.

## Typowe problemy i rozwiązania
- **Plik nie znaleziony** – sprawdź ponownie ścieżkę `dataDir` i upewnij się, że pliki wejściowe istnieją.  
- **Nieprawidłowy indeks strony** – indeksy stron zaczynają się od 1; próba wstawienia nieistniejącej strony powoduje wyrzucenie wyjątku.  
- **Błędy licencji** – użyj tymczasowej lub pełnej licencji przed wdrożeniem do produkcji.

## FAQ

### Q1: Czy mogę manipulować stronami z różnych dokumentów XPS?

A1: Tak, jak pokazano w samouczku, możesz wstawiać strony z wielu dokumentów XPS do nowego dokumentu.

### Q2: Jak mogę usunąć konkretną stronę z dokumentu?

A2: Użyj metody `RemovePageAt`, podając indeks strony, którą chcesz usunąć.

### Q3: Czy Aspose.Page jest kompatybilny z Visual Studio?

A3: Tak, Aspose.Page jest w pełni kompatybilny z Visual Studio, co ułatwia integrację w Twoich projektach .NET.

### Q4: Czy dostępne są opcje licencjonowania?

A4: Tak, możesz zapoznać się z opcjami licencjonowania i uzyskać tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/).

### Q5: Gdzie mogę uzyskać wsparcie lub zadać pytania?

A5: Odwiedź [forum Aspose.Page](https://forum.aspose.com/c/page/39), aby uzyskać wsparcie i uczestniczyć w społeczności.

## Często zadawane pytania

**Q: Czy mogę scalić więcej niż trzy pliki XPS?**  
A: Oczywiście. Utwórz dodatkowe instancje `XpsDocument` i używaj wielokrotnie `InsertPage` lub `AddPage`, aby zbudować większy scalony dokument.

**Q: Czy scalanie zachowuje oryginalne formatowanie i grafikę?**  
A: Tak. Aspose.Page kopiuje zawartość strony bajt po bajcie, więc tekst, obrazy i grafika wektorowa pozostają niezmienione.

**Q: Jak wstawić stronę na koniec bez podawania indeksu?**  
A: Użyj `AddPage(sourcePage, false)`, który dodaje stronę na koniec dokumentu.

**Q: Czy można scalać dokumenty XPS na serwerze bez interfejsu użytkownika?**  
A: API jest w pełni bezgłowe; możesz uruchomić ten sam kod w ASP.NET, Azure Functions lub dowolnym środowisku .NET po stronie serwera.

**Q: Co jeśli moje pliki XPS są zabezpieczone hasłem?**  
A: Aspose.Page obecnie nie obsługuje zaszyfrowanych plików XPS; musisz je odszyfrować przed scaleniem.

---

**Ostatnia aktualizacja:** 2026-01-10  
**Testowano z:** Aspose.Page for .NET 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}