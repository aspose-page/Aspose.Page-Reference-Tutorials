---
date: 2026-07-19
description: Dowiedz się, jak tworzyć dokument XPS .NET i dodać prostokąt przy użyciu
  Aspose.Page dla .NET w zwięzłym przewodniku krok po kroku.
keywords:
- create xps document .net
- add rectangle xps
- aspose.page .net
lastmod: 2026-07-19
linktitle: Dodaj prostokąt do dokumentu XPS
og_description: Szybko twórz dokument XPS .NET. Ten samouczek pokazuje, jak dodać
  prostokąt do pliku XPS przy użyciu Aspose.Page dla .NET, z przejrzystym kodem i
  wskazówkami.
og_image_alt: Guide to adding a rectangle to an XPS document using Aspose.Page for
  .NET
og_title: Tworzenie dokumentu XPS .NET – Dodaj prostokąt za pomocą Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  headline: Create XPS Document .NET – Add Rectangle with Aspose.Page
  type: TechArticle
- description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  name: Create XPS Document .NET – Add Rectangle with Aspose.Page
  steps:
  - name: Create a New XPS Document
    text: The `XpsDocument` class represents the XPS file you are building and provides
      methods to add pages, graphics, and other resources.
  - name: Add a Rectangle
    text: '`XpsPath` defines a drawable path object within the XPS document, allowing
      you to set geometry, stroke, fill, and other visual properties.'
  - name: Save the Document
    text: The `Save` method writes the constructed XPS document to the specified file
      path on disk. Congratulations! You have successfully added a rectangle to an
      XPS document using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works seamlessly with desktop, web, and cloud .NET applications.
    question: Is Aspose.Page compatible with all .NET applications?
  - answer: The full API reference is available [here](https://reference.aspose.com/page/net/).
    question: Where can I find the documentation for Aspose.Page for .NET?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Can I try Aspose.Page for .NET for free before purchasing?
  - answer: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain
      a temporary license.
    question: How can I obtain a temporary license for Aspose.Page for .NET?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support.
    question: Where can I seek community support or ask questions related to Aspose.Page
      for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- xps document
- aspose.page
- .net drawing
title: Tworzenie dokumentu XPS .NET – Dodaj prostokąt za pomocą Aspose.Page
url: /pl/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz dokument XPS .NET – Dodaj prostokąt za pomocą Aspose.Page

## Wprowadzenie

W tym samouczku nauczysz się, jak **utworzyć dokument XPS .NET** i narysować w nim prostokąt przy użyciu Aspose.Page dla .NET. Niezależnie od tego, czy tworzysz silnik raportowania, fakturę do druku, czy własną warstwę graficzną, możliwość programowego generowania plików XPS daje pełną kontrolę nad układem i jakością. Postępuj zgodnie z poniższymi krokami, a w ciągu kilku minut będziesz mieć gotowy plik XPS do użycia.

## Szybkie odpowiedzi
- **Jaki jest główny cel?** Utworzyć dokument XPS .NET i dodać kształt prostokąta.  
- **Która biblioteka jest wymagana?** Aspose.Page for .NET (do pobrania ze strony oficjalnej).  
- **Czy potrzebuję licencji do testowania?** Darmowa wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.  
- **Jak długo trwa implementacja?** Około 5‑10 minut dla podstawowego prostokąta.

## Czym jest Aspose.Page dla .NET?
Aspose.Page dla .NET to wysokowydajny, w pełni zarządzany interfejs API, który umożliwia programistom programowo tworzyć, edytować i renderować dokumenty XPS (XML Paper Specification) bez konieczności korzystania z zewnętrznych komponentów. Oferuje bogaty model obiektowy do rysowania kształtów, tekstu i obrazów oraz obsługuje zaawansowane funkcje, takie jak zarządzanie kolorami, kompresja i konwersja do PDF, co czyni go odpowiednim dla szerokiego zakresu scenariuszy generowania dokumentów.

## Dlaczego warto używać Aspose.Page do tworzenia dokumentu XPS .NET?
Aspose.Page obsługuje **ponad 30 funkcji XPS** — w tym grafikę wektorową, układ tekstu i zarządzanie kolorami — i może generować pliki do **500 MB** bez wczytywania całego dokumentu do pamięci. Ta wymierna zdolność zapewnia płynną wydajność nawet przy dużych zadaniach drukowania.

## Wymagania wstępne

Zanim rozpoczniesz ten samouczek, upewnij się, że spełniasz następujące wymagania wstępne:

1. Biblioteka Aspose.Page dla .NET: Upewnij się, że biblioteka Aspose.Page dla .NET jest zainstalowana w Twoim środowisku programistycznym. Możesz ją pobrać [tutaj](https://releases.aspose.com/page/net/).
2. Katalog dokumentów: Utwórz katalog, w którym chcesz przechowywać swoje dokumenty XPS.

## Importowanie przestrzeni nazw

W swojej aplikacji .NET dołącz niezbędne przestrzenie nazw, aby korzystać z funkcjonalności Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Jak dodać prostokąt do dokumentu XPS w .NET?

Załaduj dokument XPS, utwórz obiekt `Graphics`, zdefiniuj `RectangleF` o żądanym rozmiarze i wywołaj `DrawRectangle`. Ta sekwencja rysuje prostokąt w jednej linii kodu i automatycznie obsługuje skalowanie DPI. Dla typowych stron formatu A4 prostokąt 200 × 100 pt pojawia się wyśrodkowany bez dodatkowych obliczeń.

### Krok 1: Ustaw katalog dokumentów

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

### Krok 2: Utwórz nowy dokument XPS

Klasa `XpsDocument` reprezentuje plik XPS, który tworzysz, i udostępnia metody do dodawania stron, grafiki oraz innych zasobów.

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

### Krok 3: Dodaj prostokąt

`XpsPath` definiuje obiekt ścieżki rysowalnej w dokumencie XPS, umożliwiając ustawienie geometrii, obrysu, wypełnienia i innych właściwości wizualnych.

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

### Krok 4: Zapisz dokument

Metoda `Save` zapisuje skonstruowany dokument XPS do określonej ścieżki pliku na dysku.

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Gratulacje! Pomyślnie dodałeś prostokąt do dokumentu XPS przy użyciu Aspose.Page dla .NET.

## Typowe problemy i wskazówki

- **Brakujące czcionki:** Upewnij się, że czcionki, do których odwołujesz się, są zainstalowane na serwerze; w przeciwnym razie Aspose.Page zastąpi je domyślną czcionką, co może zmienić układ.  
- **Duże dokumenty:** Podczas generowania plików większych niż 200 MB rozważ wywołanie `document.SaveOptions.Compress = true`, aby zmniejszyć zużycie pamięci.  
- **System współrzędnych:** XPS używa punktów (1/72 cala). Pamiętaj, aby przeliczyć piksele na punkty, jeśli pracujesz z wymiarami opartymi na ekranie.

## Najczęściej zadawane pytania

**Q: Czy Aspose.Page jest kompatybilny ze wszystkimi aplikacjami .NET?**  
A: Tak, Aspose.Page działa bezproblemowo z aplikacjami .NET na komputerze stacjonarnym, w sieci i w chmurze.

**Q: Gdzie mogę znaleźć dokumentację Aspose.Page dla .NET?**  
A: Pełna referencja API jest dostępna [tutaj](https://reference.aspose.com/page/net/).

**Q: Czy mogę wypróbować Aspose.Page dla .NET za darmo przed zakupem?**  
A: Tak, darmową wersję próbną można uzyskać [tutaj](https://releases.aspose.com/).

**Q: Jak mogę uzyskać tymczasową licencję na Aspose.Page dla .NET?**  
A: Odwiedź [ten link](https://purchase.aspose.com/temporary-license/), aby uzyskać tymczasową licencję.

**Q: Gdzie mogę uzyskać wsparcie społeczności lub zadać pytania dotyczące Aspose.Page dla .NET?**  
A: Odwiedź [forum Aspose.Page](https://forum.aspose.com/c/page/39), aby uzyskać wsparcie społeczności.

---

**Ostatnia aktualizacja:** 2026-07-19  
**Testowano z:** Aspose.Page for .NET 24.9  
**Autor:** Aspose

## Powiązane samouczki

- [Utwórz dokument XPS przy użyciu Aspose.Page dla .NET](/page/net/document-creation/create-xps-document/)
- [Aspose.Page .NET – Rysowanie kształtów](/page/net/drawing-shapes/)
- [Dodaj tekst do dokumentu XPS przy użyciu Aspose.Page dla .NET](/page/net/text-manipulation/add-text-to-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}