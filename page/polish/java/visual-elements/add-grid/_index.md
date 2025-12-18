---
date: 2025-12-18
description: Dowiedz się, jak dodać siatkę i przezroczysty prostokąt w dokumentach
  XPS w Javie przy użyciu Aspose.Page. Przewodnik krok po kroku, jak efektywnie zapisać
  dokument XPS.
linktitle: How to Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: Jak dodać siatkę przy użyciu Visual Brush w Javie
url: /pl/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dodać siatkę przy użyciu Visual Brush w Javie

## Introduction
Jeśli szukasz **jak dodać siatkę** elementów do swoich dokumentów XPS generowanych w Javie, trafiłeś we właściwe miejsce. W tym samouczku przeprowadzimy Cię przez dodanie siatki przy użyciu Visual Brush, nałożenie przezroczystego prostokąta i w końcu **zapisanie dokumentu XPS** przy użyciu Aspose.Page Java API. Po zakończeniu będziesz mieć dopracowaną wizualizację, którą można ponownie wykorzystać w raportach, fakturach lub w każdej aplikacji intensywnie pracującej z dokumentami.

## Quick Answers
- **Co robi Visual Brush?** Maluje określony obszar przy użyciu wielokrotnego użycia treści wizualnej, idealny do powtarzających się wzorów, takich jak siatki.  
- **Czy mogę zmienić kolor siatki?** Tak – zmodyfikuj ustawienia pędzla o stałym kolorze.  
- **Jak dodać przezroczysty prostokąt na wierzchu siatki?** Użyj `setOpacity` na ścieżce wypełnionej stałym kolorem.  
- **Jaką metodą zapisuje się plik?** `doc.save(...)` zapisuje plik XPS na dysku.  
- **Czy potrzebna jest licencja?** Wymagana jest tymczasowa lub pełna licencja do użytku produkcyjnego.

## What is a Visual Brush Grid?
Visual Brush pozwala zdefiniować mały element wizualny (wzór siatki), a następnie powielać go na większym obszarze. Takie podejście jest bardziej oszczędne pod względem pamięci niż rysowanie każdej linii osobno i zapewnia idealną powtarzalność pikselową.

## Why use Aspose.Page for this task?
- **Cross‑platform** – Działa na każdym systemie operacyjnym obsługującym Javę.  
- **High‑fidelity rendering** – Precyzyjna kontrola nad kolorami, przezroczystością i powielaniem.  
- **No external dependencies** – Wszystko obsługiwane jest przez bibliotekę Aspose.Page.

## Prerequisites
Zanim przejdziemy dalej, upewnij się, że masz:

- Podstawową wiedzę programistyczną w Javie.  
- Zainstalowaną bibliotekę Aspose.Page – możesz ją pobrać z [dokumentacji Aspose.Page for Java](https://reference.aspose.com/page/java/).  
- Zainstalowany JDK 8 lub nowszy na swojej maszynie deweloperskiej.

## Import Packages
Najpierw zaimportuj wymagane klasy, aby kompilator wiedział, gdzie znaleźć typy, które będziemy używać:

```java
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsTileMode;
import com.aspose.xps.XpsVisualBrush;
```

## Step‑by‑Step Guide

### Step 1: Set Up Your Project
Utwórz nową instancję `XpsDocument` i wskaż folder, w którym ma być zapisany plik wyjściowy.

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### Step 2: Create a Magenta Grid Visual Brush
Definiujemy mały magentowy kształt, który będzie powielany na obszarze siatki.

```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### Step 3: Define Geometry for the Grid Brush
Ustaw prostokątny obszar, który otrzyma powielany element wizualny.

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### Step 4: Create a New Canvas for the Document
Dodaj canvas do dokumentu i umieść go tam, gdzie ma się pojawić siatka.

```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### Step 5: Add the Grid to the Canvas
Zastosuj visual brush do geometrii, umożliwiając powielanie.

```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### Step 6: Add a Transparent Red Rectangle (Secondary Feature)
Tutaj demonstrujemy **dodanie przezroczystego prostokąta** na wierzchu siatki w celu podkreślenia.

```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### Step 7: Save the Resulting XPS Document
Na koniec zapisz dokument na dysku — to jest krok **zapisania dokumentu XPS**.

```java
doc.save(dataDir + "AddGrid_out.xps");
```

Postępuj zgodnie z tymi krokami, a uzyskasz profesjonalnie wyglądającą siatkę z przezroczystą nakładką, wygenerowaną programowo.

## Common Issues & Tips

- **Nieprawidłowy rozmiar kafelka:** Upewnij się, że `Rectangle2D` użyty dla pędzla odpowiada zamierzonemu rozmiarowi powtórzenia; w przeciwnym razie wzór może się rozciągać.  
- **Przezroczystość nie zastosowana:** Pamiętaj, aby wywołać `setOpacity` na ścieżce, którą chcesz uczynić przezroczystą; nie wpłynie to na sam pędzel.  
- **Plik nie został zapisany:** Sprawdź, czy `dataDir` wskazuje istniejący folder i czy aplikacja ma uprawnienia do zapisu.

## Frequently Asked Questions

**P: Czy Aspose.Page jest odpowiedni do profesjonalnego generowania dokumentów?**  
O: Tak, Aspose.Page to solidna biblioteka zaprojektowana do generowania wysokiej jakości dokumentów XPS i PDF w Javie.

**P: Czy mogę dostosować kolory siatki przy użyciu Visual Brush?**  
O: Oczywiście! Zmień parametry `createColor` w wywołaniu `setFill` pędzla na dowolne wartości RGBA, które są potrzebne.

**P: Gdzie mogę znaleźć dodatkowe wsparcie dla Aspose.Page?**  
O: Odwiedź [forum Aspose.Page](https://forum.aspose.com/c/page/39), aby uzyskać pomoc społeczności i oficjalne odpowiedzi.

**P: Czy dostępna jest darmowa wersja próbna Aspose.Page?**  
O: Tak, możesz uzyskać dostęp do [darmowej wersji próbnej](https://releases.aspose.com/), aby wypróbować wszystkie funkcje przed zakupem.

**P: Jak mogę uzyskać tymczasową licencję do testów?**  
O: Pobierz [tymczasową licencję](https://purchase.aspose.com/temporary-license/), która działa w środowisku deweloperskim i ewaluacyjnym.

---

**Ostatnia aktualizacja:** 2025-12-18  
**Testowano z:** Aspose.Page for Java 23.12 (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}