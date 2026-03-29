---
date: 2026-03-29
description: Dowiedz się, jak dodawać przezroczyste obiekty do dokumentów XPS, a następnie
  eksportować XPS do PDF przy użyciu Aspose.Page dla .NET. Przewodnik krok po kroku
  z praktycznymi wskazówkami.
linktitle: Add Transparent Object to XPS Document
second_title: Aspose.Page .NET API
title: Eksport XPS do PDF – Dodaj przezroczysty obiekt przy użyciu Aspose.Page
url: /pl/net/transparency-effects/add-transparent-object-to-xps-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Eksportuj XPS do PDF – Dodaj przezroczysty obiekt przy użyciu Aspose.Page

## Wprowadzenie

W tym samouczku nauczysz się, jak dodać przezroczyste obiekty do dokumentu XPS, a następnie **export XPS to PDF** przy użyciu Aspose.Page dla .NET. Przezroczystość może sprawić, że dokumenty będą wyglądały bardziej nowocześnie i pomóc wyróżnić ważne informacje. Przejdziemy przez każdy krok, wyjaśnimy powody stojące za kodem i pokażemy, jak zakończyć proces, konwertując plik XPS na PDF w celu łatwego udostępniania.

## Szybkie odpowiedzi
- **Co oznacza „export XPS to PDF”?** Konwertowanie pliku XPS na plik PDF przy zachowaniu układu, kolorów i przezroczystości.  
- **Dlaczego najpierw dodać przezroczystość?** Przezroczyste obiekty pozwalają tworzyć warstwowe grafiki, które wyglądają świetnie w ostatecznym PDF.  
- **Czy potrzebuję licencji?** Tak, wymagana jest ważna licencja Aspose.Page do użytku produkcyjnego.  
- **Czy to działa na .NET Core?** Absolutnie – Aspose.Page obsługuje .NET Core, .NET 5/6 oraz pełny .NET Framework.  
- **Gdzie mogę znaleźć więcej przykładów?** Sprawdź dokumentację Aspose.Page oraz forum społeczności podane poniżej.

## Wymagania wstępne

Zanim zanurzysz się w samouczek, upewnij się, że masz spełnione następujące wymagania wstępne:

- Aspose.Page dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Page dla .NET. Możesz ją pobrać z [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

## Importowanie przestrzeni nazw

Aby rozpocząć, dołącz niezbędne przestrzenie nazw do swojego projektu:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Teraz przejdźmy do przewodnika krok po kroku.

## Krok 1: Utwórz nowy dokument XPS

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Ten kod inicjalizuje nowy dokument XPS przy użyciu Aspose.Page dla .NET.

## Krok 2: Demonstracja przezroczystości

```csharp
// Just to demonstrate transparency
doc.AddPath(doc.CreatePathGeometry("M120,0 H400 v1000 H120")).Fill = doc.CreateSolidColorBrush(Color.Gray);
doc.AddPath(doc.CreatePathGeometry("M300,120 h600 V420 h-600")).Fill = doc.CreateSolidColorBrush(Color.Gray);
```

Te linie tworzą dwie szare ścieżki, które będą służyły jako tło dla przezroczystych kształtów, które dodamy później.

## Krok 3: Utwórz ścieżkę z zamkniętą geometrią prostokąta

```csharp
XpsPath path1 = doc.CreatePath(doc.CreatePathGeometry("M20,20 h200 v200 h-200 z"));
path1.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

Tutaj tworzymy niebieski prostokąt. Ponieważ później zmienimy jego przezroczystość, prostokąt będzie wyglądał półprzezroczysto w ostatecznym PDF.

## Krok 4: Manipulowanie ścieżkami i kolorami

```csharp
XpsPath path2 = doc.Add(path1);
path2.Fill = doc.CreateSolidColorBrush(Color.Green);
```

Klonujemy pierwszy prostokąt, dodajemy go do strony i zmieniamy jego kolor wypełnienia na zielony. To pokazuje, jak łatwo można ponownie wykorzystać istniejącą geometrię.

## Krok 5: Klonowanie i transformacja ścieżek

```csharp
XpsPath path3 = doc.Add(path2);
path3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 300);
path3.Fill = doc.CreateSolidColorBrush(Color.Red);
```

Sklonowana ścieżka jest przesunięta w dół o 300 jednostek i pomalowana na czerwono, co daje efekt warstwowego układu.

## Krok 6: Powtórz i modyfikuj ścieżki

```csharp
XpsPath path4 = doc.AddPath(path2.Data);
path4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 300, 0);
path4.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

Ponownie używamy danych geometrii z `path2`, przesuwamy je w prawo i ponownie stosujemy niebieskie wypełnienie.

## Krok 7: Zarządzanie przezroczystością

```csharp
XpsPath path5 = doc.Add(path4);
path5.RenderTransform = path5.RenderTransform.Clone();
path5.RenderTransform.Translate(0, 300);
path5.Fill.Opacity = 0.8f;
```

Ustawienie właściwości `Opacity` na 0,8 sprawia, że ten prostokąt jest w 80 % nieprzezroczysty, co ilustruje, jak można precyzyjnie dostosować przezroczystość każdego elementu.

## Krok 8: Zapisz dokument XPS

```csharp
doc.Save(dataDir + "WorkingWithTransparency_out.xps");
```

Plik XPS jest teraz zapisany ze wszystkimi zastosowanymi przezroczystymi obiektami.  

**Eksport do PDF:** Aby **export XPS to PDF**, po prostu wywołaj ponownie `doc.Save` z rozszerzeniem `.pdf`, np. `doc.Save(dataDir + "TransparentDocument.pdf");`. Ta sama jakość wizualna, w tym ustawienia przezroczystości, jest zachowana w powstałym PDF.

## Dlaczego eksportować XPS do PDF po dodaniu przezroczystości?

- **Uniwersalna kompatybilność:** PDF jest szeroko wspierany na różnych platformach, podczas gdy XPS jest bardziej niszowy.  
- **Zachowane efekty wizualne:** Aspose.Page utrzymuje przezroczystość, gradienty i przekształcenia macierzy nienaruszone podczas konwersji.  
- **Łatwe udostępnianie:** PDF-y mogą być otwierane w przeglądarkach, na urządzeniach mobilnych i w wielu czytnikach innych firm bez dodatkowych wtyczek.

## Typowe przypadki użycia

- **Broszury marketingowe**, w których warstwowa grafika nadaje premium wygląd.  
- **Diagramy techniczne**, które wymagają podświetlonych sekcji bez zagracania układu.  
- **Generowanie raportów**, gdzie chcesz nałożyć znaki wodne lub loga z częściową przezroczystością.

## Porady i pułapki

- **Wskazówka:** Zawsze ustawiaj wartość `Opacity` między 0 a 1. Wartości poza tym zakresem są ograniczane i mogą dawać nieoczekiwane rezultaty.  
- **Wskazówka wydajnościowa:** Ponowne użycie geometrii (`path2.Data`) zmniejsza zużycie pamięci, gdy potrzebujesz wielu podobnych kształtów.  
- **Pułapka:** Zapis bezpośrednio do PDF po dodaniu przezroczystości działa od razu, ale jeśli później edytujesz PDF innymi narzędziami, niektóre starsze przeglądarki mogą nie renderować poprawnie przezroczystości.

## Podsumowanie

Dodawanie przezroczystych obiektów do dokumentów XPS przy użyciu Aspose.Page dla .NET zapewnia wszechstronny sposób na ulepszenie prezentacji wizualnych. Gdy Twój plik XPS wygląda tak, jak chcesz, możesz **export XPS to PDF** w jednej linii kodu, zachowując wszystkie efekty przezroczystości do szerokiej dystrybucji.

## FAQ

### Q1: Czy mogę zastosować przezroczystość do dowolnego obiektu w dokumencie XPS?
A1: Tak, przezroczystość może być zastosowana do różnych obiektów, takich jak ścieżki, kształty i obrazy w dokumencie XPS.

### Q2: Jak mogę dostosować przezroczystość konkretnego elementu?
A2: Możesz ustawić właściwość opacity wypełnienia (Fill) lub obrysu (Stroke), aby dostosować przezroczystość konkretnego elementu.

### Q3: Czy Aspose.Page jest kompatybilny z .NET Core?
A3: Tak, Aspose.Page obsługuje .NET Core, umożliwiając rozwój wieloplatformowy.

### Q4: Czy mogę eksportować dokumenty XPS do innych formatów przy użyciu Aspose.Page?
A4: Aspose.Page zapewnia funkcjonalność eksportu dokumentów XPS do różnych formatów, w tym PDF i obrazów.

### Q5: Gdzie mogę znaleźć dodatkowe wsparcie i dyskusje społecznościowe?
A5: Aby uzyskać dodatkowe wsparcie i dyskusje społecznościowe, odwiedź [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

### Q6: Czy konwersja do PDF zachowuje moje ustawienia przezroczystości?
A6: Absolutnie. Gdy eksportujesz XPS do PDF przy użyciu Aspose.Page, wszystkie ustawienia przezroczystości i mieszania są zachowane.

### Q7: Czy mogę przetwarzać wsadowo wiele plików XPS do PDF?
A7: Tak, możesz przeiterować kolekcję plików XPS i wywołać `doc.Save(...".pdf")` dla każdego, automatyzując konwersje zbiorcze.

---

**Ostatnia aktualizacja:** 2026-03-29  
**Testowano z:** Aspose.Page 24.12 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}