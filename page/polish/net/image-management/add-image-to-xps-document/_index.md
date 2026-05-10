---
date: 2026-02-28
description: Dowiedz się, jak tworzyć dokumenty XPS w .NET i dodawać obrazy przy użyciu
  Aspose.Page dla .NET. Skorzystaj z tego przewodnika krok po kroku, aby uzyskać płynne
  doświadczenie programistyczne.
linktitle: Add Image to XPS Document
second_title: Aspose.Page .NET API
title: Utwórz dokument XPS .NET – Dodaj obraz przy użyciu Aspose.Page
url: /pl/net/image-management/add-image-to-xps-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj obraz do dokumentu XPS przy użyciu Aspose.Page dla .NET

W tym samouczku dowiesz się, jak **create XPS document .NET** i osadzić obraz przy użyciu potężnej biblioteki Aspose.Page. Niezależnie od tego, czy generujesz raporty, faktury, czy własne grafiki, dodawanie elementów wizualnych do plików XPS jest częstym wymogiem dla programistów .NET.

## Wprowadzenie

W świecie programowania w .NET wprowadzanie obrazów do dokumentów XPS jest powszechnym wymaganiem. Aspose.Page dla .NET upraszcza ten proces, oferując potężny zestaw narzędzi do manipulacji i ulepszania dokumentów XPS bez wysiłku. Ten samouczek poprowadzi Cię krok po kroku przez proces dodawania obrazu do dokumentu XPS przy użyciu Aspose.Page dla .NET.

## Szybkie odpowiedzi
- **Co obejmuje ten samouczek?** Dodanie obrazu do dokumentu XPS przy użyciu Aspose.Page dla .NET.  
- **Jakie jest główne słowo kluczowe?** *create xps document .net*  
- **Czy potrzebna jest licencja?** Dostępna jest bezpłatna wersja próbna; licencja jest wymagana w środowisku produkcyjnym.  
- **Jakie wersje .NET są obsługiwane?** Działa z .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Jak długo trwa implementacja?** Około 5‑10 minut dla podstawowego wstawienia obrazu.

## Co to jest „create XPS document .NET”?
Tworzenie dokumentu XPS w .NET oznacza programowe generowanie pliku XML Paper Specification (XPS) — formatu dokumentu o stałym układzie — przy użyciu C# lub VB.NET. Aspose.Page udostępnia płynne API, które abstrahuje szczegóły niskiego poziomu, pozwalając skupić się na treści takiej jak tekst, kształty i obrazy.

## Dlaczego używać Aspose.Page do dodania obrazu?
- **Full control** nad pozycjonowaniem, skalowaniem i przycinaniem obrazów.  
- **No external dependencies** – biblioteka obsługuje dekodowanie obrazów wewnętrznie.  
- **Cross‑platform** wsparcie dla środowisk Windows i Linux.  
- **High fidelity** renderowanie, które zachowuje jakość obrazu w ostatecznym pliku XPS.

## Wymagania wstępne

Przed przystąpieniem do samouczka upewnij się, że spełniasz następujące wymagania:

1. Biblioteka Aspose.Page dla .NET: Pobierz i zainstaluj bibliotekę z [Aspose.Page .NET Documentation](https://reference.aspose.com/page/net/).

2. Środowisko programistyczne: Skonfiguruj środowisko .NET, np. Visual Studio.

3. Przykładowy obraz: Przygotuj plik obrazu (np. „QL_logo_color.tif”), który chcesz dodać do dokumentu XPS.

## Importowanie przestrzeni nazw

Rozpocznij od zaimportowania niezbędnych przestrzeni nazw do swojego projektu .NET. Są one kluczowe dla wykorzystania funkcji udostępnianych przez Aspose.Page dla .NET.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Dodawanie obrazu do dokumentu XPS przy użyciu Aspose.Page

Poniżej przeprowadzimy Cię przez każdy krok niezbędny do **create XPS document .NET** i osadzenia obrazu.

### Krok 1: Ustaw katalog dokumentu

Rozpocznij od określenia ścieżki do katalogu dokumentu. Ten krok zapewnia, że projekt wie, gdzie znajdować i zapisywać pliki.

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
// ExEnd:1
```

### Krok 2: Utwórz dokument XPS

Utwórz nowy dokument XPS przy użyciu Aspose.Page dla .NET.

```csharp
// ExStart:1
XpsDocument doc = new XpsDocument();
// ExEnd:1
```

### Krok 3: Dodaj obraz do dokumentu XPS

Teraz dodajmy obraz do dokumentu XPS. W tym przykładzie użyjemy przykładowego obrazu o nazwie „QL_logo_color.tif”.

```csharp
// ExStart:1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// ExEnd:1
```

### Krok 4: Zapisz wynikowy dokument XPS

Zapisz dokument XPS z dodanym obrazem.

```csharp
// ExStart:1
doc.Save(dataDir + "AddImage_outXPS.xps");
// ExEnd:1
```

Teraz pomyślnie dodałeś obraz do dokumentu XPS przy użyciu Aspose.Page dla .NET!

## Typowe problemy i rozwiązania

- **File not found error** – Sprawdź, czy `dataDir` wskazuje na właściwy folder i czy nazwa pliku obrazu jest dokładnie taka sama, łącznie z uwzględnieniem wielkości liter w systemie Linux.  
- **Image appears distorted** – Dostosuj współczynniki skalowania w `CreateMatrix` lub parametry `RectangleF`, aby kontrolować rozmiar i proporcje.  
- **Unsupported image format** – Aspose.Page obsługuje popularne formaty rastrowe (PNG, JPEG, TIFF). Przekonwertuj nieobsługiwane formaty przed użyciem `CreateImageBrush`.

## Najczęściej zadawane pytania

### Q1: Czy Aspose.Page dla .NET jest kompatybilny z najnowszymi wersjami .NET framework?

**A1:** Aspose.Page dla .NET został zaprojektowany tak, aby był kompatybilny z szerokim zakresem wersji .NET framework, w tym z najnowszymi wydaniami. Zapoznaj się z [documentation](https://reference.aspose.com/page/net/) po szczegółowe informacje.

### Q2: Czy mogę używać Aspose.Page dla .NET zarówno w środowiskach Windows, jak i Linux?

**A2:** Tak, Aspose.Page dla .NET jest niezależny od platformy, co czyni go odpowiednim do użycia zarówno w środowiskach Windows, jak i Linux.

### Q3: Czy istnieją opcje licencjonowania Aspose.Page dla .NET?

**A3:** Tak, możesz zapoznać się z opcjami licencjonowania i dokonać zakupu [here](https://purchase.aspose.com/buy).

### Q4: Czy dostępna jest bezpłatna wersja próbna Aspose.Page dla .NET?

**A4:** Tak, możesz wypróbować Aspose.Page dla .NET za darmo, korzystając z [free trial](https://releases.aspose.com/).

### Q5: Gdzie mogę uzyskać pomoc lub skontaktować się ze społecznością Aspose.Page dla .NET?

**A5:** Odwiedź [Aspose.Page for .NET forum](https://forum.aspose.com/c/page/39), aby połączyć się ze społecznością i uzyskać wsparcie.

## Zakończenie

W tym samouczku przedstawiliśmy, jak wykorzystać Aspose.Page dla .NET do płynnego włączania obrazów do dokumentów XPS. Ten przewodnik krok po kroku zapewnia płynny proces integracji, zwiększając możliwości Twojego rozwoju w .NET i pomagając **create XPS document .NET** z bogactwem wizualnym.

---

**Ostatnia aktualizacja:** 2026-02-28  
**Testowano z:** Aspose.Page for .NET 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}