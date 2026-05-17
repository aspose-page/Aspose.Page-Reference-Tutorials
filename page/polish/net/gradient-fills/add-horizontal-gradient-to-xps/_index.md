---
date: 2026-02-25
description: Dowiedz się, jak stworzyć gradient XPS z poziomym wypełnieniem przy użyciu
  Aspose.Page dla .NET. Zwiększ atrakcyjność wizualną swoich dokumentów bez wysiłku.
linktitle: Add Horizontal Gradient to XPS
second_title: Aspose.Page .NET API
title: 'Utwórz gradient XPS: wypełnienie poziome z Aspose.Page dla .NET'
url: /pl/net/gradient-fills/add-horizontal-gradient-to-xps/
weight: 13
---

But "Aspose.Page for .NET" keep as is.

Let's translate.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tworzenie gradientu XPS – Dodawanie poziomego gradientu do XPS przy użyciu Aspose.Page dla .NET

## Wstęp

W tym samouczku **utworzysz wypełnienia gradientowe XPS**, które będą przebiegać poziomo po całych stronach. Dodanie poziomego gradientu może natychmiast sprawić, że dokument XPS będzie wyglądał bardziej dopracowanie i atrakcyjnie, szczególnie w raportach, broszurach lub innych wizualnie bogatych materiałach. Przeprowadzimy Cię przez cały proces przy użyciu Aspose.Page dla .NET, od konfiguracji środowiska po zapisanie finalnego pliku XPS.

## Szybkie odpowiedzi
- **Co obejmuje ten samouczek?** Dodanie poziomego gradientu do dokumentu XPS przy użyciu Aspose.Page dla .NET.  
- **Jakiej biblioteki potrzebujesz?** Aspose.Page dla .NET (dowolna aktualna wersja).  
- **Czy potrzebna jest licencja?** Wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji.  
- **Jak długo trwa implementacja?** Około 5–10 minut dla podstawowego gradientu.  
- **Czy mogę zmienić kierunek gradientu?** Tak – zmodyfikuj punkty początkowe/końcowe `LinearGradientBrush`.

## Jak stworzyć gradient XPS przy użyciu Aspose.Page dla .NET

Poniżej znajdziesz przewodnik krok po kroku, który wyjaśnia **dlaczego** każda linia kodu istnieje, a nie tylko **co** ona robi. Śmiało podążaj za nim w Visual Studio lub innym ulubionym edytorze .NET.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz spełnione następujące wymagania:

1. Biblioteka Aspose.Page dla .NET: Upewnij się, że biblioteka Aspose.Page dla .NET jest zainstalowana w Twoim środowisku programistycznym. Możesz ją pobrać z [dokumentacji Aspose.Page dla .NET](https://reference.aspose.com/page/net/).

2. Środowisko programistyczne: Skonfiguruj odpowiednie środowisko, w tym edytor kodu, np. Visual Studio.

## Importowanie przestrzeni nazw

Rozpocznij od zaimportowania niezbędnych przestrzeni nazw do projektu. Są one kluczowe do pracy z Aspose.Page dla .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Teraz rozbijmy podany przykład na kilka kroków.

## Krok 1: Ustawienie ścieżki katalogu dokumentu

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Krok 2: Utworzenie nowego dokumentu XPS

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Krok 3: Inicjalizacja przystanków gradientu

```csharp
// ExStart:5
// Initialize List of XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## Krok 4: Utworzenie nowej ścieżki

```csharp
// ExStart:6
// Create new path by defining geometry in abbreviation form
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Krok 5: Zapisanie wynikowego dokumentu XPS

```csharp
// ExStart:7
// Save resultant XPS document
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

Teraz pomyślnie dodałeś poziomy gradient do swojego dokumentu XPS przy użyciu Aspose.Page dla .NET.

## Typowe problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| Gradient wygląda jak jednolity kolor | Niepoprawnie dodane przystanki gradientu | Upewnij się, że `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` jest wywoływane po ustawieniu pędzla. |
| Zapisany plik jest pusty | `dataDir` wskazuje na nieistniejący folder | Sprawdź, czy folder istnieje lub użyj ścieżki bezwzględnej. |
| Błąd kompilacji przy `PointF` | Brak odwołania do `System.Drawing` | Dodaj odwołanie do `System.Drawing.Common` (dla .NET Core/5+). |

## FAQ

### Q1: Gdzie mogę znaleźć dokumentację Aspose.Page dla .NET?

A1: Dokumentację znajdziesz [tutaj](https://reference.aspose.com/page/net/).

### Q2: Jak pobrać Aspose.Page dla .NET?

A2: Bibliotekę możesz pobrać ze [strony pobierania Aspose.Page dla .NET](https://releases.aspose.com/page/net/).

### Q3: Gdzie mogę kupić Aspose.Page dla .NET?

A3: Zakup możesz dokonać na [stronie zakupu](https://purchase.aspose.com/buy).

### Q4: Czy dostępna jest darmowa wersja próbna?

A4: Tak, darmową wersję próbną znajdziesz [tutaj](https://releases.aspose.com/).

### Q5: Jak uzyskać tymczasową licencję dla Aspose.Page dla .NET?

A5: Tymczasową licencję można uzyskać pod [tym linkiem](https://purchase.aspose.com/temporary-license/).

## Najczęściej zadawane pytania

**P: Czy mogę używać tej techniki gradientu w dokumentach XPS, które już zawierają obrazy?**  
O: Oczywiście. Gradient jest nakładany na warstwę ścieżki, więc istniejące obrazy pozostają niezmienione.

**P: Czy można stworzyć gradient pionowy zamiast poziomego?**  
O: Tak. Zmień punkty początkowe i końcowe `LinearGradientBrush`, aby miały różne współrzędne Y przy stałym X.

**P: Czy Aspose.Page obsługuje .NET Core?**  
O: Biblioteka jest w pełni kompatybilna z .NET Core, .NET 5 i nowszymi wersjami.

**P: Jak mogę ponownie użyć tego samego gradientu na wielu stronach?**  
O: Utwórz jednorazowo obiekt `XpsLinearGradientBrush`, przechowaj go w zmiennej i przypisz do ścieżek na każdej stronie.

## Zakończenie

Wzbogacenie dokumentów XPS o gradienty nie tylko podnosi ich atrakcyjność wizualną, ale także zapewnia bardziej angażujące wrażenia użytkownika. Dzięki Aspose.Page dla .NET możesz **tworzyć wypełnienia gradientowe XPS** szybko i niezawodnie, nadając swoim raportom, broszurom czy e‑bookom profesjonalny wygląd.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-02-25  
**Testowano z:** Aspose.Page dla .NET 24.11  
**Autor:** Aspose  

---