---
date: 2026-01-05
description: Dowiedz się, jak bez wysiłku przekształcać dokumenty XPS za pomocą Aspose.Page
  dla .NET. Skorzystaj z naszego przewodnika krok po kroku, aby uzyskać płynne przekształcenia.
linktitle: Transformations XPS
second_title: Aspose.Page .NET API
title: Jak przekształcić XPS przy użyciu Aspose.Page dla .NET
url: /pl/net/canvas-manipulation/transformationsxps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak przekształcić XPS przy użyciu Aspose.Page dla .NET

## Wprowadzenie

Witamy w świecie Aspose.Page dla .NET, potężnej biblioteki umożliwiającej łatwe wykonywanie różnych przekształceń dokumentów XPS. **W tym samouczku dowiesz się, jak przekształcać dokumenty XPS przy użyciu Aspose.Page dla .NET**, niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz. Przejdziemy przez każdy krok, wyjaśnimy powody poszczególnych przekształceń i podamy praktyczne wskazówki, które możesz zastosować w rzeczywistych projektach.

## Quick Answers
- **Co możesz osiągnąć?** Tworzyć, przesuwać, skalować i obracać elementy płótna XPS programowo.  
- **Jakiej biblioteki potrzebujesz?** Aspose.Page dla .NET (najnowsza wersja).  
- **Czy potrzebna jest licencja?** Bezpłatna wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji.  
- **Obsługiwane platformy?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Jak długo trwa implementacja?** Około 10‑15 minut dla podstawowych przekształceń przedstawionych tutaj.

## What is “how to transform xps”?

Wyrażenie *how to transform xps* odnosi się do programowego modyfikowania układu, rozmiaru i orientacji elementów wewnątrz dokumentu XPS (XML Paper Specification). Korzystając z Aspose.Page, możesz stosować transformacje oparte na macierzach do płócien, co daje precyzyjną kontrolę nad pozycjonowaniem, skalowaniem i rotacją bez ręcznej edycji XML XPS.

## Why use Aspose.Page for XPS transformations?

- **Pełna integracja z .NET** – działa bezproblemowo z Visual Studio, Rider i innymi IDE.  
- **Brak zewnętrznych zależności** – API obsługuje wszystkie szczegóły XPS niskiego poziomu.  
- **Bogate wsparcie transformacji** – przesuwanie, skalowanie, obracanie i łączenie wielu transformacji w jednym wywołaniu.  
- **Wydajność zoptymalizowana** – odpowiednie do generowania raportów, faktur lub dowolnej grafiki do druku w locie.

## Prerequisites

Zanim zaczniemy, upewnij się, że masz:

- **Bibliotekę Aspose.Page dla .NET** – pobierz i zainstaluj ją z oficjalnej dokumentacji: [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).  
- **Środowisko programistyczne** – Visual Studio, Visual Studio Code lub dowolne inne IDE kompatybilne z .NET.  
- **Katalog dokumentów** – folder na Twoim komputerze, w którym będziesz odczytywać/zapisywać pliki XPS. Zastąp symbol zastępczy w kodzie rzeczywistą ścieżką.

Teraz, gdy wszystko jest gotowe, przejdźmy do kodu.

## Import Namespaces

Najpierw zaimportuj przestrzenie nazw, które udostępniają klasy Aspose.Page, których będziesz potrzebować:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## How to Transform XPS – Step‑by‑Step Guide

### Krok 1: Utwórz nowy dokument XPS

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

*Wyjaśnienie*: Najpierw definiujemy folder zawierający nasze pliki źródłowe i wyjściowe, a następnie tworzymy pusty `XpsDocument`. Ten obiekt będzie płótnem dla wszystkich kolejnych transformacji.

### Krok 2: Utwórz główne płótno

```csharp
// Create main canvas, common for all page elements
XpsCanvas canvas1 = doc.AddCanvas();

// Make left and top offsets in the main canvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

*Dlaczego to ważne*: Główne płótno pełni rolę kontenera dla wszystkich pozostałych płócien. Stosując niewielkie przesunięcie, zapewniamy, że zawartość nie zostanie przycięta przy krawędzi strony.

### Krok 3: Utwórz geometrię ścieżki prostokąta

```csharp
// Create rectangle path geometry
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

*Wskazówka*: Ciąg ścieżki używa standardowej składni XPS (`M` – move, `L` – line, `Z` – close). Dostosuj współrzędne, aby zmienić rozmiar prostokąta.

### Krok 4: Dodaj wypełnienie dla prostokątów

```csharp
// Create a fill for rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

*Profesjonalna wskazówka*: Użyj `CreateColor` z wartościami RGB, aby dopasować paletę do swojej marki.

### Krok 5: Dodaj nowe płótno bez transformacji

```csharp
// Add new canvas without any transformations to the main canvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Create rectangle in this canvas and fill it
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Tutaj po prostu umieszczamy prostokąt na stronie bez dodatkowych transformacji — przydatny jako element bazowy.

### Krok 6: Dodaj nowe płótno z transformacją przesunięcia

```csharp
// Add new canvas with translate transformation to the main canvas
XpsCanvas canvas3 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Translate this canvas to the right side of the page
canvas3.RenderTransform.Translate(500, 0);

// Create rectangle in this canvas and fill it
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

*Co się dzieje?* Pierwsza macierz przesuwa prostokąt w dół o 200 jednostek. Następne wywołanie `Translate` przesuwa go o 500 jednostek w prawo, pokazując, jak można łączyć wiele przesunięć.

### Krok 7: Dodaj nowe płótno z podwójną transformacją skalowania

```csharp
// Add new canvas with double scale transformation to the main canvas
XpsCanvas canvas4 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Scale this canvas
canvas4.RenderTransform.Scale(2, 2);

// Create rectangle in this canvas and fill it
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

*Dlaczego skalować?* Skalowanie o 2 podwaja szerokość i wysokość prostokąta, umożliwiając tworzenie większej grafiki bez ponownego definiowania geometrii.

### Krok 8: Dodaj nowe płótno z transformacją obrotu wokół punktu

```csharp
// Add new canvas with rotation around a point transformation to the main canvas
XpsCanvas canvas5 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Rotate this canvas around a point on 45 degrees
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Create rectangle in this canvas and fill it
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

*Kluczowa uwaga*: `RotateAround` obraca płótno wokół własnego punktu (tutaj (100, 50)), dając precyzyjną kontrolę nad punktami obrotu.

### Krok 9: Zapisz wynikowy dokument XPS

```csharp
// Save resultant XPS document
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

Po zastosowaniu wszystkich transformacji dokument zostaje zapisany jako `output1.xps`. Otwórz plik w dowolnym przeglądarce XPS, aby zobaczyć ułożone prostokąty z ich odpowiednimi przesunięciami, skalowaniem i obrotem.

## Common Issues & Troubleshooting

| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|---------|--------------|-----|
| Pusty plik wyjściowy | `dataDir` wskazuje na nieistniejący folder | Upewnij się, że katalog istnieje lub użyj ścieżki bezwzględnej |
| Prostokąty nie są rozmieszczone zgodnie z oczekiwaniami | Nieprawidłowe wartości macierzy | Sprawdź kolejność wywołań `Translate`, `Scale` i `RotateAround` |
| Kolory są nieprawidłowe | Wartości RGB poza zakresem 0‑255 | Użyj prawidłowych wartości bajtowych dla każdego kanału |

## Frequently Asked Questions

**P: Czy Aspose.Page dla .NET jest kompatybilny ze wszystkimi środowiskami programistycznymi .NET?**  
O: Tak, działa bezproblemowo z Visual Studio, Visual Studio Code, Rider oraz każdym IDE obsługującym .NET.

**P: Gdzie mogę znaleźć dodatkowe przykłady i szczegółową dokumentację API?**  
O: Odwiedź oficjalną dokumentację pod adresem [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

**P: Czy mogę wypróbować Aspose.Page przed zakupem licencji?**  
O: Oczywiście. Bezpłatna wersja próbna jest dostępna tutaj: [Aspose.Page Free Trial](https://releases.aspose.com/).

**P: Jak uzyskać tymczasową licencję do testów?**  
O: Możesz ją zamówić na stronie tymczasowej licencji: [Temporary License](https://purchase.aspose.com/temporary-license/).

**P: Gdzie mogę kupić pełną licencję?**  
O: Zakup bezpośrednio w sklepie Aspose: [Aspose.Page Buy](https://purchase.aspose.com/buy).

---

**Ostatnia aktualizacja:** 2026-01-05  
**Testowano z:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}