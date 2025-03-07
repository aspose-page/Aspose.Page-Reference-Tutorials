---
title: Dodaj glif wypełniony obrazem i obraz obcy za pomocą Aspose.Page .NET
linktitle: Dodaj wypełniony obrazem glif i obcy obraz
second_title: Aspose.Page API .NET
description: Odblokuj moc przetwarzania dokumentów w .NET dzięki Aspose.Page. Bez wysiłku dodawaj glify wypełnione obrazami. Ulepsz efekty wizualne i usprawnij przepływ pracy.
weight: 11
url: /pl/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj glif wypełniony obrazem i obraz obcy za pomocą Aspose.Page .NET

## Wstęp

świecie programowania .NET Aspose.Page wyróżnia się jako potężny zestaw narzędzi do obsługi zadań związanych z przetwarzaniem dokumentów. Ten samouczek poprowadzi Cię przez proces dodawania glifów wypełnionych obrazami i włączania obcych obrazów za pomocą Aspose.Page dla .NET. Pod koniec tego przewodnika będziesz mieć solidną wiedzę na temat zwiększania możliwości przetwarzania dokumentów.

## Warunki wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

-  Aspose.Page dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Page. Można go pobrać z[Tutaj](https://releases.aspose.com/page/net/).

- Środowisko programistyczne: Skonfiguruj działające środowisko programistyczne .NET za pomocą programu Visual Studio lub innego preferowanego IDE.

- Katalog dokumentów: Utwórz katalog, w którym będziesz przechowywać swoje dokumenty. W przykładach kodu będzie to określane jako „katalog Twoich dokumentów”.

## Importuj przestrzenie nazw

W aplikacji .NET zacznij od zaimportowania niezbędnych przestrzeni nazw, aby uzyskać dostęp do klas i metod udostępnianych przez Aspose.Page:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Krok 1: Utwórz pierwszy dokument XPS

Rozpocznij od utworzenia pierwszego dokumentu XPS przy użyciu Aspose.Page. Dokument ten będzie podstawą do dodawania glifów wypełnionych obrazami.

```csharp
// ExStart:1
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";

// Utwórz pierwszy dokument XPS
XpsDocument doc1 = new XpsDocument();
```

## Krok 2: Dodaj glify do pierwszego dokumentu

Dodaj glify do pierwszego dokumentu, określając czcionkę, rozmiar, styl i położenie.

```csharp
// Dodaj glify do pierwszego dokumentu
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## Krok 3: Wypełnij glify pędzlem obrazu

Wypełnij glify pędzlem obrazu, wykorzystując obraz z katalogu danych.

```csharp
// Wypełnij glify pędzlem obrazu
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## Krok 4: Utwórz drugi dokument XPS

Teraz utwórz drugi dokument XPS, który będzie zawierał glify z pierwszego dokumentu.

```csharp
// Utwórz drugi dokument XPS
XpsDocument doc2 = new XpsDocument();
```

## Krok 5: Dodaj glify czcionką z pierwszego dokumentu

Dodaj glify do drugiego dokumentu, używając czcionki z pierwszego dokumentu.

```csharp
// Dodaj glify czcionką z pierwszego dokumentu do drugiego dokumentu
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## Krok 6: Utwórz pędzel obrazu z wypełnienia pierwszego dokumentu

Utwórz pędzel obrazu z wypełnienia pierwszego dokumentu i użyj go do wypełnienia glifów w drugim dokumencie.

```csharp
// Utwórz pędzel obrazu z wypełnienia pierwszego dokumentu i wypełnij glify w drugim dokumencie
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## Krok 7: Zapisz dokumenty

Zapisz zarówno pierwszy, jak i drugi dokument XPS.

```csharp
// Zapisz pierwszy dokument XPS
doc1.Save(dataDir + "out1.xps");

// Zapisz drugi dokument XPS
doc2.Save(dataDir + "out2.xps");
// RozwińKoniec:1
```

## Wniosek

Gratulacje! Udało Ci się dodać glify wypełnione obrazami i włączyć obce obrazy za pomocą Aspose.Page dla .NET. Ten samouczek stanowi podstawę do zwiększenia możliwości przetwarzania dokumentów, otwierając nowe możliwości tworzenia kreatywnych i atrakcyjnych wizualnie dokumentów.

## Często zadawane pytania

### P1: Czy mogę używać różnych formatów obrazów do wypełniania glifów?

O1: Tak, Aspose.Page obsługuje różne formaty obrazów. Zapewnij zgodność z wybranym formatem obrazu.

### P2: Jak mogę bardziej dostosować wygląd glifów?

Odpowiedź 2: Zapoznaj się z dokumentacją Aspose.Page, aby poznać dodatkowe właściwości i metody dostrajania wyglądu glifów.

### P3: Czy Aspose.Page nadaje się do obsługi dużych zestawów dokumentów?

A3: Aspose.Page został zaprojektowany tak, aby efektywnie obsługiwać zarówno małe, jak i duże zestawy dokumentów.

### P4: Czy mogę zastosować różne style do poszczególnych glifów?

O4: Tak, możesz dostosować style dla każdego glifu niezależnie, zapewniając wysoki poziom elastyczności.

### P5: Jakie są zalety korzystania z Aspose.Page w porównaniu z innymi narzędziami do przetwarzania dokumentów?

Odpowiedź 5: Aspose.Page oferuje kompleksowy zestaw funkcji, doskonałą wydajność i obszerną dokumentację, co czyni go preferowanym wyborem dla wielu programistów.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
