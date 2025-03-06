---
title: Dodaj obraz kafelkowy do dokumentu XPS za pomocą Aspose.Page dla .NET
linktitle: Dodaj obraz sąsiadujący do dokumentu XPS
second_title: Aspose.Page API .NET
description: Przeglądaj bezproblemowe dodawanie obrazów kafelkowych do dokumentów XPS dzięki Aspose.Page dla .NET. Zwiększ atrakcyjność wizualną i twórz wspaniałe dokumenty.
weight: 12
url: /pl/net/image-management/add-tiled-image-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj obraz kafelkowy do dokumentu XPS za pomocą Aspose.Page dla .NET

## Wstęp

Czy chcesz ulepszyć swoje dokumenty XPS, dodając atrakcyjne wizualnie obrazy kafelkowe? Aspose.Page dla .NET umożliwia programistom bezproblemowe osiągnięcie tego celu. W tym przewodniku krok po kroku przeprowadzimy Cię przez proces dodawania obrazu sąsiadującego do dokumentu XPS przy użyciu Aspose.Page dla .NET.

## Warunki wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

-  Aspose.Page dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Page. Możesz znaleźć szczegółową dokumentację i pobrać bibliotekę[Tutaj](https://reference.aspose.com/page/net/).
- Środowisko programistyczne: skonfiguruj preferowane środowisko programistyczne .NET, takie jak Visual Studio.

## Importuj przestrzenie nazw

Aby rozpocząć, zaimportuj niezbędne przestrzenie nazw do swojego projektu. Dzięki temu masz dostęp do klas i metod wymaganych do pracy z Aspose.Page. Dodaj następujące przestrzenie nazw na początku kodu:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Podzielmy teraz przykład na wiele kroków.

## Krok 1: Zdefiniuj katalog dokumentów

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";
```

Pamiętaj, aby zastąpić „Twój katalog dokumentów” rzeczywistą ścieżką, w której chcesz zapisać dokument XPS.

## Krok 2: Utwórz nowy dokument XPS

```csharp
// Utwórz nowy dokument XPS
XpsDocument doc = new XpsDocument();
```

 Utwórz instancję nowego dokumentu XPS za pomocą`XpsDocument` klasa.

## Krok 3: Dodaj obraz kafelkowy

```csharp
// Obraz kafelkowy
// Prostokąt wypełniony ImageBrush w prawym górnym rogu poniżej
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

Ten krok dodaje obraz sąsiadujący z dokumentem XPS. Dostosuj współrzędne i ścieżkę pliku obrazu zgodnie ze swoimi wymaganiami.

## Krok 4: Zapisz wynikowy dokument XPS

```csharp
// Zapisz wynikowy dokument XPS
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

Zapisz zmodyfikowany dokument XPS w określonym katalogu.

## Wniosek

Gratulacje! Pomyślnie nauczyłeś się, jak dodać obraz sąsiadujący do dokumentu XPS przy użyciu Aspose.Page dla .NET. Ta prosta, ale zaawansowana funkcja pozwala bez wysiłku poprawić atrakcyjność wizualną dokumentów.

## Często zadawane pytania

### P1: Czy Aspose.Page jest kompatybilny ze wszystkimi środowiskami programistycznymi .NET?

O1: Tak, Aspose.Page został zaprojektowany do bezproblemowej współpracy z różnymi środowiskami programistycznymi .NET, w tym Visual Studio.

### P2: Czy mogę dostosować przezroczystość obrazu kafelkowego?

Odpowiedź 2: Oczywiście, jak pokazano w przykładzie, możesz ustawić przezroczystość wypełnionego prostokąta za pomocą`Opacity` nieruchomość.

### P3: Czy w Aspose.Page dla .NET dostępne są inne tryby kafelków?

 O3: Tak, Aspose.Page udostępnia różne tryby kafelków. W tym samouczku użyliśmy`XpsTileMode.Tile`, ale możesz zapoznać się z innymi opcjami w dokumentacji.

### P4: Jak postępować z tymczasowymi licencjami dla Aspose.Page?

 A4: Patrz[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) na stronie internetowej Aspose, aby uzyskać wskazówki dotyczące uzyskiwania i wdrażania licencji tymczasowych.

### P5: Gdzie mogę szukać pomocy lub nawiązać kontakt ze społecznością Aspose.Page?

 A5: Odwiedź[Forum Aspose.Page](https://forum.aspose.com/c/page/39) aby nawiązać kontakt ze społecznością, zadawać pytania i znajdować rozwiązania.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
