---
date: 2026-02-25
description: Dowiedz się, jak utworzyć dokument XPS i zastosować gradient liniowy
  przy użyciu Aspose.Page dla .NET. Skorzystaj z naszego przewodnika krok po kroku,
  aby zapisać plik XPS.
linktitle: Add Vertical Gradient to XPS
second_title: Aspose.Page .NET API
title: Utwórz dokument XPS z pionowym gradientem przy użyciu Aspose.Page
url: /pl/net/gradient-fills/add-vertical-gradient-to-xps/
weight: 15
---

 good.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj pionowy gradient do XPS przy użyciu Aspose.Page dla .NET

## Wprowadzenie

W tym tutorialu **utworzysz dokument XPS**, który zawiera płynny pionowy gradient. Dodawanie gradientów to powszechny sposób, aby pliki XPS wyglądały bardziej profesjonalnie — idealne do raportów, broszur lub wszelkich grafik do druku. Przeprowadzimy Cię przez każdy krok, od skonfigurowania projektu po zapisanie finalnego pliku XPS, abyś mógł szybko zastosować gradient liniowy do dowolnej ścieżki.

## Szybkie odpowiedzi
- **Co obejmuje ten tutorial?** Dodanie pionowego gradientu liniowego do ścieżki w dokumencie XPS.  
- **Jakiej biblioteki wymaga?** Aspose.Page for .NET.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji.  
- **Jak długo trwa implementacja?** Około 10‑15 minut dla podstawowego przykładu.  
- **Czy mogę zapisać wynik jako plik XPS?** Tak, metoda `Save` zapisuje plik na dysku.

## Czym jest pionowy gradient w XPS?

Pionowy gradient to przejście koloru, które biegnie od górnej części kształtu do dolnej. W XPS osiąga się to za pomocą **linear gradient brush**, który definiuje punkty początkowy i końcowy oraz kolekcję punktów gradientu kontrolujących kolor w określonych pozycjach.

## Dlaczego używać Aspose.Page do tworzenia dokumentu XPS z gradientami?

- **Pełna integracja z .NET** – działa z .NET Framework, .NET Core oraz .NET 5/6+.  
- **Brak zewnętrznych zależności** – całe renderowanie jest obsługiwane przez bibliotekę.  
- **Wysoka wierność** – gradienty renderują się dokładnie tak, jak zdefiniowano, zgodnie ze specyfikacją XPS.  
- **Łatwe w utrzymaniu** – przejrzysty model obiektowy dla ścieżek, pędzli i kolorów.

## Wymagania wstępne

- Aspose.Page for .NET Library: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Page for .NET w swoim środowisku deweloperskim. Możesz ją pobrać [tutaj](https://releases.aspose.com/page/net/).  
- Development Environment: Skonfiguruj środowisko .NET z ulubionym IDE, takim jak Visual Studio.

Teraz, gdy wszystko jest gotowe, przejdźmy do kodu.

## Importowanie przestrzeni nazw

W swojej aplikacji .NET dołącz niezbędne przestrzenie nazw, aby uzyskać dostęp do klas i metod Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Krok 1: Skonfiguruj katalog dokumentu

Zdefiniuj folder, w którym zostanie zapisany wygenerowany plik XPS.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Krok 2: Utwórz nowy dokument XPS

Zainicjuj nowy dokument XPS, który później wypełnimy ścieżką z gradientem.

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Krok 3: Zdefiniuj punkty gradientu

Punkty gradientu określają kolory i ich pozycje wzdłuż linii gradientu. Tutaj tworzymy pięć punktów, aby uzyskać płynne pionowe przejście.

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExEnd:5
```

## Krok 4: Utwórz ścieżkę z gradientem

Rysujemy ścieżkę w kształcie prostokąta i stosujemy **linear gradient brush**, który biegnie pionowo od punktu (10, 110) do punktu (10, 200). Pędzel otrzymuje wcześniej zdefiniowane punkty gradientu.

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Krok 5: Zapisz wynikowy dokument XPS

Na koniec zapisujemy dokument XPS na dysku. Ten krok **save XPS file** tworzy plik `AddVerticalGradient_outXPS.xps` w wybranym folderze.

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

**Wskazówka:** Zweryfikuj wynik, otwierając plik XPS w Windows XPS Viewer lub dowolnym innym przeglądarce, aby upewnić się, że gradient wygląda zgodnie z oczekiwaniami.

## Typowe problemy i rozwiązywanie

| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|---------|--------------|-----|
| Gradient wyświetla się jako jednolity kolor | Punkty gradientu nie zostały dodane do pędzla | Upewnij się, że `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` jest wykonywane. |
| Plik nie został znaleziony podczas zapisu | `dataDir` wskazuje na nieistniejący folder | Utwórz najpierw katalog lub użyj ścieżki bezwzględnej. |
| Kolory wyglądają inaczej | Wartości kolorów używają kolejności ARGB; sprawdź kolejność kanałów | Użyj poprawnie `CreateColor(alpha, red, green, blue)`. |

## Najczęściej zadawane pytania

**P: Czy Aspose.Page jest kompatybilny z Visual Studio 2019?**  
O: Tak, Aspose.Page jest kompatybilny z Visual Studio 2019. Upewnij się, że masz zainstalowaną właściwą wersję biblioteki.

**P: Czy mogę używać Aspose.Page w projektach komercyjnych?**  
O: Tak, Aspose.Page może być używany w projektach komercyjnych. Odwiedź [tutaj](https://purchase.aspose.com/buy), aby zapoznać się z opcjami licencjonowania.

**P: Czy dostępna jest darmowa wersja próbna?**  
O: Tak, darmową wersję próbną Aspose.Page można uzyskać [tutaj](https://releases.aspose.com/).

**P: Gdzie mogę znaleźć dokumentację Aspose.Page?**  
O: Dokumentacja jest dostępna [tutaj](https://reference.aspose.com/page/net/).

**P: Jak mogę uzyskać wsparcie lub zadać pytania?**  
O: Odwiedź [forum Aspose.Page](https://forum.aspose.com/c/page/39) w celu uzyskania wsparcia społeczności.

## Podsumowanie

Teraz wiesz, jak **utworzyć dokument XPS**, **zastosować gradient liniowy** i **zapisać plik XPS** przy użyciu Aspose.Page dla .NET. To podejście daje pełną kontrolę nad stylizacją wizualną w wyjściach XPS, sprawiając, że Twoje dokumenty do druku wyróżniają się.

---  

**Ostatnia aktualizacja:** 2026-02-25  
**Testowano z:** Aspose.Page for .NET 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}