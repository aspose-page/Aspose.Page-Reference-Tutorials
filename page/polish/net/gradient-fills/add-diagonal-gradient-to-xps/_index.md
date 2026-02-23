---
date: 2026-02-23
description: Dowiedz się, jak tworzyć dokumenty XPS z ukośnym gradientem przy użyciu
  Aspose.Page dla .NET i podnieś swoje prezentacje wizualne bez wysiłku.
linktitle: Add Diagonal Gradient to XPS
second_title: Aspose.Page .NET API
title: Utwórz przekątny gradient XPS przy użyciu Aspose.Page dla .NET
url: /pl/net/gradient-fills/add-diagonal-gradient-to-xps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz skośny gradient XPS przy użyciu Aspose.Page dla .NET

## Introduction

Jeśli potrzebujesz **tworzyć skośne gradienty XPS**, które przyciągają uwagę, Aspose.Page dla .NET ułatwia to zadanie. W tym samouczku nauczysz się, jak dodać skośny gradient do dokumentu XPS, krok po kroku, korzystając z API Aspose.Page. Po zakończeniu będziesz mieć wielokrotnego użytku wzorzec, który możesz dostosować do dowolnego kształtu lub schematu kolorów.

## Quick Answers
- **Co robi metoda API?** Tworzy pędzel liniowego gradientu, który rozciąga się skośnie wzdłuż ścieżki.  
- **Która klasa reprezentuje dokument XPS?** `XpsDocument`.  
- **Czy potrzebna jest licencja do uruchomienia przykładu?** Darmowa wersja próbna działa w środowisku deweloperskim; licencja jest wymagana w produkcji.  
- **Czy mogę zmienić kierunek gradientu?** Tak — dostosuj wartości początkowego i końcowego `PointF`.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is **create diagonal gradient xps**?
Skośny gradient to płynne przejście kolorów, które przebiega od jednego rogu kształtu do przeciwległego rogu. W XPS efekt ten uzyskuje się poprzez zastosowanie `LinearGradientBrush` do właściwości wypełnienia ścieżki. Biblioteka Aspose.Page abstrahuje niskopoziomowy znacznik XPS, pozwalając skupić się na kolorach i geometrii.

## Why use Aspose.Page for diagonal gradients?
- **Wysokiej wierności renderowanie** – wynik dokładnie odpowiada specyfikacji XPS.  
- **Pełna integracja z .NET** – działa z C#, VB.NET i dowolnym językiem .NET.  
- **Brak zewnętrznych zależności** – wszystko obsługiwane w procesie, bez COM ani Office.  
- **Skalowalność do złożonych dokumentów** – możesz łączyć wiele gradientów, obrazów i tekstu na tej samej stronie.

## Prerequisites

1. **Biblioteka Aspose.Page dla .NET** – download it [here](https://releases.aspose.com/page/net/).  
2. **Środowisko programistyczne** – Visual Studio, Rider lub dowolny edytor obsługujący projekty .NET.  

Teraz zanurzmy się w kod.

## Import Namespaces

W swoim projekcie .NET dołącz niezbędne przestrzenie nazw z biblioteki Aspose.Page, aby uzyskać dostęp do wymaganych klas i metod. Dodaj następujące przestrzenie nazw na początku swojego kodu:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Step 1: Set the Document Directory

Ustaw katalog dokumentu

Rozpocznij od określenia ścieżki do katalogu dokumentów. To miejsce, w którym zostanie zapisany wynikowy dokument XPS ze skośnym gradientem.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Step 2: Create a New XPS Document

Utwórz nowy dokument XPS

Zainicjalizuj nowy `XpsDocument` przy użyciu biblioteki Aspose.Page.

```csharp
XpsDocument doc = new XpsDocument();
```

## Step 3: Define Gradient Colors

Zdefiniuj kolory gradientu

Utwórz listę obiektów `XpsGradientStop`, z których każdy reprezentuje kolor w skośnym gradiencie.

```csharp
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 142, 4), 0f));
// ... Repeat for other colors
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 199, 80), 1f));
```

## Step 4: Add a Diagonal Gradient to a Path

Dodaj skośny gradient do ścieżki

Utwórz nową ścieżkę z określoną geometrią i zastosuj do niej skośny gradient. W razie potrzeby dostosuj transformację renderowania oraz właściwości wypełnienia.

```csharp
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 10f), new PointF(228f, 100f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
```

## Step 5: Save the Resultant XPS Document

Zapisz wynikowy dokument XPS

Na koniec zapisz zmodyfikowany dokument XPS w określonym katalogu.

```csharp
doc.Save(dataDir + "AddDiagonalGradient_outXPS.xps");
```

Udało Ci się **utworzyć plik XPS ze skośnym gradientem**. Śmiało eksperymentuj z różnymi punktami kolorów, ciągami geometrii lub macierzami transformacji, aby uzyskać różnorodne efekty wizualne.

## Common Issues and Solutions
- **Gradient nie jest widoczny** – Sprawdź, czy geometria ścieżki jest zamknięta oraz czy punkty początkowy/końcowy pędzla znajdują się w granicach ścieżki.  
- **Nieprawidłowe kolory** – Upewnij się, że używasz `CreateColor` z prawidłowymi wartościami ARGB; metoda oczekuje wartości w zakresie 0‑255.  
- **Plik nie został zapisany** – Sprawdź, czy `dataDir` wskazuje istniejący folder i czy aplikacja ma uprawnienia do zapisu.

## Frequently Asked Questions

**Q: Czy mogę zastosować wiele gradientów do różnych części dokumentu?**  
A: Tak, możesz utworzyć wiele ścieżek i zastosować do każdej oddzielny gradient.

**Q: Czy dostępne są predefiniowane style gradientów?**  
A: Aspose.Page umożliwia własne gradienty, dając pełną kontrolę nad przejściami kolorów.

**Q: Czy mogę używać Aspose.Page dla .NET z innymi formatami dokumentów?**  
A: Aspose.Page koncentruje się głównie na manipulacji dokumentami XPS.

**Q: Jak mogę obsłużyć błędy związane z przetwarzaniem dokumentu?**  
A: Odwołaj się do [documentation](https://reference.aspose.com/page/net/) w celu uzyskania najlepszych praktyk obsługi błędów.

**Q: Czy dostępna jest wersja próbna przed zakupem?**  
A: Tak, możesz wypróbować [free trial](https://releases.aspose.com/), aby doświadczyć Aspose.Page dla .NET.

**Q: Jak zmienić kierunek gradientu na pionowy lub poziomy?**  
A: Zmodyfikuj argumenty `PointF` w `CreateLinearGradientBrush`, aby ustawić nowe punkty początkowy i końcowy.

**Q: Czy biblioteka obsługuje przezroczystość w gradientach?**  
A: Tak — uwzględnij wartość alfa przy tworzeniu kolorów za pomocą `CreateColor`.

## Conclusion

Aspose.Page dla .NET upraszcza proces wzbogacania dokumentów XPS o skośne gradienty. Ten przewodnik poprowadził Cię od przygotowania wymagań wstępnych po zapisanie finalnego pliku. Kontynuuj eksperymenty z różnymi kształtami i paletami kolorów, aby Twoje raporty, broszury lub faktury w formacie XPS naprawdę się wyróżniały.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-02-23  
**Testowano z:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

---