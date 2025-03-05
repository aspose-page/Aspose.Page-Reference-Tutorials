---
title: Ustaw maskę krycia w dokumencie XPS za pomocą Aspose.Page dla .NET
linktitle: Ustaw maskę kryjącą w dokumencie XPS
second_title: Aspose.Page API .NET
description: Dowiedz się, jak ustawić maski kryjące w dokumentach XPS przy użyciu Aspose.Page dla .NET. Bez wysiłku poprawiaj estetykę dokumentów.
type: docs
weight: 12
url: /pl/net/transparency-effects/set-opacity-mask-in-xps-document/
---
## Wstęp

Maski kryjące są niezbędne, gdy chcesz tworzyć atrakcyjne wizualnie dokumenty o różnym poziomie przezroczystości. Aspose.Page dla .NET upraszcza ten proces, oferując programistom kompleksowy zestaw narzędzi do ulepszania dokumentów XPS. W tym samouczku krok po kroku dowiemy się, jak ustawić maskę kryjącą.

## Warunki wstępne

Przed przystąpieniem do samouczka upewnij się, że spełniasz następujące wymagania wstępne:

-  Aspose.Page dla .NET: Upewnij się, że masz zainstalowaną bibliotekę. Jeśli nie, możesz pobrać go ze strony[strona internetowa](https://releases.aspose.com/page/net/).

- Katalog dokumentów: skonfiguruj katalog do przechowywania dokumentów XPS.

## Importuj przestrzenie nazw

W projekcie .NET rozpocznij od zaimportowania niezbędnych przestrzeni nazw:

```csharp
using Aspose.Page.Xps;
using Aspose.Page.Xps.XpsModel;
using Aspose.Page.Xps.XpsModel.Shapes;
using Aspose.Page.Xps.XpsModel.Text;
using System.Drawing;
```

## Krok 1: Utwórz nowy dokument XPS

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";
// Utwórz nowy dokument XPS
XpsDocument doc = new XpsDocument();
```

Zacznij od utworzenia nowego dokumentu XPS przy użyciu Aspose.Page dla .NET.

## Krok 2: Dodaj Canvas do instancji XpsDocument

```csharp
// Dodaj Canvas do instancji XpsDocument
XpsCanvas canvas = doc.AddCanvas();
```

Teraz dodaj płótno do dokumentu XPS. Płótno posłuży jako pojemnik na różne elementy graficzne.

## Krok 3: Dodaj prostokąt z maską krycia

```csharp
// Prostokąt z nieprzezroczystością maskowaną przez ImageBrush
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.OpacityMask = doc.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)path.OpacityMask).TileMode = XpsTileMode.Tile;
```

 Dodaj prostokąt do płótna i ustaw jego krycie za pomocą`OpacityMask`nieruchomość. W tym przykładzie używamy obrazu jako maski kryjącej.

## Krok 4: Zapisz wynikowy dokument XPS

```csharp
// Zapisz wynikowy dokument XPS
doc.Save(dataDir + "OpacityMask_out.xps");
```

Na koniec zapisz zmodyfikowany dokument XPS z zastosowaną maską kryjącą.

## Wniosek

Gratulacje! Pomyślnie nauczyłeś się ustawiać maski kryjące w dokumentach XPS przy użyciu Aspose.Page dla .NET. Ta funkcja otwiera szereg kreatywnych możliwości projektowania wyrafinowanych i atrakcyjnych wizualnie dokumentów.

## Często zadawane pytania

### P1: Czy mogę zastosować maski kryjące do innych kształtów oprócz prostokątów?

O1: Tak, Aspose.Page dla .NET pozwala na zastosowanie masek kryjących do różnych kształtów, w tym okręgów, wielokątów i niestandardowych ścieżek.

### P2: Czy maska kryjąca jest ograniczona do obrazów?

Odpowiedź 2: Nie, chociaż w tym samouczku wykorzystano obraz jako maskę krycia, możesz użyć jednolitych kolorów, gradientów, a nawet wzorów.

### P3: Czy dostępne są zaawansowane opcje dostrajania poziomów krycia?

Odpowiedź 3: Oczywiście, Aspose.Page dla .NET zapewnia szczegółową kontrolę nad ustawieniami krycia, pozwalając na osiągnięcie precyzyjnych efektów przezroczystości.

### P4: Czy mogę zastosować wiele masek kryjących do jednego elementu?

O4: Tak, możesz nakładać wiele masek kryjących, aby uzyskać skomplikowane efekty przezroczystości.

### P5: Czy Aspose.Page jest kompatybilny z innymi formatami dokumentów?

Odpowiedź 5: Aspose.Page koncentruje się głównie na dokumentach XPS, ale Aspose zapewnia szereg produktów do obsługi różnych formatów.