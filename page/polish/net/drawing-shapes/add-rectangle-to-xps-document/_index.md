---
title: Dodaj prostokąt do dokumentu XPS za pomocą Aspose.Page dla .NET
linktitle: Dodaj prostokąt do dokumentu XPS
second_title: Aspose.Page API .NET
description: Ulepsz tworzenie dokumentów za pomocą Aspose.Page dla .NET. Z tego samouczka krok po kroku dowiesz się, jak dodawać prostokąty do dokumentów XPS.
weight: 13
url: /pl/net/drawing-shapes/add-rectangle-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj prostokąt do dokumentu XPS za pomocą Aspose.Page dla .NET

## Wstęp

Aspose.Page dla .NET to potężna biblioteka zapewniająca różnorodne funkcje do pracy z dokumentami XPS (Specyfikacja papieru XML) w aplikacjach .NET. W tym samouczku skupimy się na dodaniu prostokąta do dokumentu XPS przy użyciu Aspose.Page dla .NET. Postępuj zgodnie z tym przewodnikiem krok po kroku, aby usprawnić proces tworzenia dokumentów.

## Warunki wstępne

Zanim zaczniesz korzystać z tego samouczka, upewnij się, że spełnione są następujące wymagania wstępne:

1.  Biblioteka Aspose.Page dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Page dla .NET w swoim środowisku programistycznym. Możesz go pobrać[Tutaj](https://releases.aspose.com/page/net/).

2. Katalog dokumentów: skonfiguruj katalog, w którym chcesz przechowywać dokumenty XPS.

## Importuj przestrzenie nazw

W swojej aplikacji .NET uwzględnij niezbędne przestrzenie nazw, aby móc korzystać z funkcjonalności Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Krok 1: Ustaw katalog dokumentów

```csharp
// ExStart:3
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";
// RozwińKoniec:3
```

## Krok 2: Utwórz nowy dokument XPS

```csharp
// ExStart:4
// Utwórz nowy dokument XPS
XpsDocument doc = new XpsDocument();
// RozwińKoniec:4
```

## Krok 3: Dodaj prostokąt

```csharp
// ExStart:5
// Obrysowany prostokąt w jednolitym kolorze CMYK (niebieski) w lewym dolnym rogu
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// RozwińKoniec:5
```

## Krok 4: Zapisz dokument

```csharp
// ExStart:6
// Zapisz wynikowy dokument XPS
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// RozwińKoniec:6
```

Gratulacje! Pomyślnie dodałeś prostokąt do dokumentu XPS przy użyciu Aspose.Page dla .NET.

## Wniosek

Aspose.Page dla .NET upraszcza zadania manipulacji dokumentami, umożliwiając programistom łatwe tworzenie i modyfikowanie dokumentów XPS. Ten przewodnik krok po kroku pokazuje, jak dodać prostokąt do dokumentu XPS, zapewniając solidną podstawę do dalszej eksploracji.

## Często zadawane pytania

### P1: Czy Aspose.Page jest kompatybilny ze wszystkimi aplikacjami .NET?

Odpowiedź 1: Tak, Aspose.Page został zaprojektowany do bezproblemowej współpracy ze wszystkimi aplikacjami .NET.

### P2: Gdzie mogę znaleźć dokumentację Aspose.Page dla .NET?

 Odpowiedź 2: Dokumentacja jest dostępna[Tutaj](https://reference.aspose.com/page/net/).

### P3: Czy przed zakupem mogę bezpłatnie wypróbować Aspose.Page dla .NET?

 A3: Tak, możesz uzyskać bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/).

### P4: Jak mogę uzyskać tymczasową licencję na Aspose.Page dla .NET?

 A4: Odwiedź[ten link](https://purchase.aspose.com/temporary-license/) w celu uzyskania licencji tymczasowej.

### P5: Gdzie mogę szukać wsparcia społeczności lub zadawać pytania związane z Aspose.Page dla .NET?

 A5: Odwiedź[Forum Aspose.Page](https://forum.aspose.com/c/page/39) za wsparcie społeczności.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
