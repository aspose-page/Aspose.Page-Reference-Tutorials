---
date: 2026-04-03
description: Dowiedz się, jak dodać przezroczysty prostokąt i zastosować pędzel Grid
  Visual Brush w .NET przy użyciu Aspose.Page, aby tworzyć zachwycające dokumenty
  XPS.
keywords:
- add transparent rectangle
- grid visual brush
- Aspose.Page .NET
linktitle: Zastosuj pędzel wizualny siatki
second_title: Aspose.Page .NET API
title: Dodaj przezroczysty prostokąt przy użyciu pędzla wizualnego siatki (.NET)
url: /pl/net/visual-brushes/apply-grid-visual-brush/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj przezroczysty prostokąt przy użyciu pędzla wizualnego siatki (.NET)

## Wprowadzenie

Jeśli chcesz **dodać przezroczysty prostokąt** do dokumentu XPS, jednocześnie stosując stylowy pędzel wizualny siatki, trafiłeś we właściwe miejsce. W tym samouczku przeprowadzimy Cię krok po kroku przez niezbędne czynności przy użyciu Aspose.Page dla .NET, abyś mógł tworzyć wizualnie bogate dokumenty, które się wyróżniają. Po zakończeniu będziesz mieć kompletny, gotowy do uruchomienia przykład, który demonstruje obie techniki w jednym, łatwym do śledzenia przepływie pracy.

## Szybkie odpowiedzi
- **Co robi przezroczysty prostokąt?** Dodaje półprzezroczystą warstwę, która pozwala na prześwitywanie zawartości tła.  
- **Które API tworzy pędzel?** `XpsDocument.CreateVisualBrush` buduje pędzel wizualny siatki.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa do testów; licencja komercyjna jest wymagana w produkcji.  
- **Jakie wersje .NET są wspierane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Jak długo trwa implementacja?** Około 10‑15 minut dla podstawowego przykładu.

## Co to jest przezroczysty prostokąt w XPS?
Przezroczysty prostokąt to po prostu kształt, którego kolor wypełnienia zawiera komponent alfa mniejszy niż 1.0, co pozwala na częściowe widzenie grafiki leżącej pod nim. Jest to idealne rozwiązanie do podświetlania sekcji bez całkowitego zasłaniania tła.

## Dlaczego używać pędzla wizualnego siatki?
Pędzel wizualny siatki pozwala na rozmieszczanie małej grafiki wektorowej na większym obszarze, tworząc wzory takie jak siatki, kreskowanie lub własne tekstury. Połączenie go z przezroczystym prostokątem daje warstwowe efekty wizualne, które są jednocześnie lekkie i niezależne od rozdzielczości.

## Wymagania wstępne

Zanim zagłębisz się w kod, upewnij się, że masz:

- **Aspose.Page for .NET** – możesz go pobrać [tutaj](https://releases.aspose.com/page/net/).
- Środowisko programistyczne .NET (Visual Studio, VS Code lub dowolne IDE, które preferujesz).
- Folder, w którym zostaną zapisane wygenerowane pliki XPS.

## Importowanie przestrzeni nazw

W swoim pliku C# zaimportuj wymagane przestrzenie nazw:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Teraz podzielmy rozwiązanie na jasne, numerowane kroki.

## Krok 1: Inicjalizacja XpsDocument

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

Zaczynamy od utworzenia instancji `XpsDocument`, która będzie przechowywać wszystkie późniejsze operacje rysowania.

## Krok 2: Utworzenie geometrycznej siatki magenty

```csharp
// ExStart:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExEnd:4
```

Ta geometria definiuje kontur siatki, którą wypełni pędzel wizualny.

## Krok 3: Projektowanie magentowego pędzla wizualnego siatki

```csharp
// ExStart:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExEnd:5
```

Tutaj rysujemy mały magentowy kafelek, który będzie powtarzany na siatce.

## Krok 4: Zastosowanie pędzla wizualnego do siatki

```csharp
// ExStart:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExEnd:6
```

Wywołanie `CreateVisualBrush` łączy magentowy kafelek z geometrią siatki i umożliwia powielanie.

## Krok 5: Dodanie siatki do płótna

```csharp
// ExStart:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExEnd:7
```

Umieszczamy powieloną siatkę na płótnie i stosujemy transformację translacji, aby pojawiła się w żądanej lokalizacji.

## Krok 6: Dodanie przezroczystego prostokąta

```csharp
// ExStart:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f; // This opacity makes the rectangle transparent
// ExEnd:8
```

W tym kroku **dodajemy przezroczysty prostokąt** (czerwony kształt z `Opacity = 0.7f`). Dostosuj wartość przezroczystości, aby kontrolować stopień prześwitu prostokąta.

## Krok 7: Zapisanie dokumentu

```csharp
// ExStart:9
doc.Save(dataDir + "AddGrid_out.xps");
// ExEnd:9
```

Plik XPS zostaje zapisany w folderze, który określiłeś wcześniej.

## Typowe przypadki użycia

- **Podświetlanie raportu:** Nałóż półprzezroczysty prostokąt, aby podkreślić wykres lub tabelę.  
- **Efekty znaku wodnego:** Połącz powieloną siatkę z przezroczystą warstwą dla subtelnego brandingu.  
- **Interaktywne PDF/XPS:** Użyj wzoru jako tła dla pól formularza, zachowując czytelność interfejsu.

## Porady rozwiązywania problemów

- **Nie widać przezroczystości?** Upewnij się, że Twój przeglądarka obsługuje przezroczystość XPS; niektóre starsze przeglądarki mogą ignorować właściwość `Opacity`.  
- **Nieprawidłowy rozmiar kafelka?** Sprawdź, czy prostokąt źródłowy (`new RectangleF(0f, 0f, 10f, 10f)`) odpowiada wymiarom wektorowego kafelka.  
- **Plik nie został zapisany?** Sprawdź ponownie, czy `dataDir` wskazuje istniejący, zapisywalny katalog.

## Najczęściej zadawane pytania

**P: Czy mogę używać Aspose.Page for .NET zarówno w aplikacjach webowych, jak i desktopowych?**  
O: Tak, biblioteka działa we wszystkich typach aplikacji .NET.

**P: Czy dostępna jest wersja próbna przed zakupem?**  
O: Oczywiście, możesz uzyskać dostęp do wersji próbnej [tutaj](https://releases.aspose.com/).

**P: Gdzie mogę znaleźć dodatkowe wsparcie lub dyskusje społeczności?**  
O: Odwiedź [Forum Aspose.Page](https://forum.aspose.com/c/page/39), aby uzyskać pomoc od społeczności i inżynierów Aspose.

**P: Jak mogę uzyskać tymczasową licencję do oceny?**  
O: Możesz uzyskać tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/).

**P: Jaką inną dokumentację można znaleźć dla Aspose.Page for .NET?**  
O: Zapoznaj się ze szczegółową dokumentacją [tutaj](https://reference.aspose.com/page/net/).

---

**Ostatnia aktualizacja:** 2026-04-03  
**Testowano z:** Aspose.Page 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}