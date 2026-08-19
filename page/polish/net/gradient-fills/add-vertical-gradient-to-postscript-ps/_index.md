---
date: 2026-02-25
description: Dowiedz się, jak używać pędzla liniowego gradientu w C# do dodawania
  gradientu do plików PS oraz wypełniania prostokąta gradientem przy użyciu Aspose.Page
  dla .NET.
linktitle: Add Vertical Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: c# Linear Gradient Brush – Dodaj pionowy gradient do PostScript (PS) z Aspose.Page
url: /pl/net/gradient-fills/add-vertical-gradient-to-postscript-ps/
weight: 14
---

.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# c# Linear Gradient Brush – Dodaj pionowy gradient do PostScript (PS) z Aspose.Page

## Wprowadzenie

W dziedzinie manipulacji i tworzenia dokumentów **Aspose.Page for .NET** wyróżnia się jako potężne narzędzie dla programistów. W tym przewodniku dowiesz się, jak **dodać gradient do plików PS** przy użyciu **pędzla liniowego gradientu C#**, aby **wypełnić prostokąt gradientem**. Po zakończeniu tego samouczka będziesz mieć jasne, krok po kroku zrozumienie wymaganego kodu i dlaczego technika ta generuje płynny pionowy gradient w wyjściu PostScript.

## Szybkie odpowiedzi
- **Co robi pędzel liniowego gradientu C#?** Tworzy płynne przejście między wieloma kolorami na kształcie.
- **Czy mogę używać tego z dowolną wersją .NET?** Tak, Aspose.Page obsługuje .NET Framework 4.5+ oraz .NET Core/5+.
- **Czy potrzebna jest licencja do produkcji?** Wymagana jest licencja komercyjna dla wersji nie‑ewaluacyjnych.
- **Czy gradient jest naprawdę pionowy?** Pędzel jest obrócony o 90°, zapewniając pionowy przepływ.
- **Gdzie zapisywany jest wynik?** Do ścieżki podanej w `dataDir` (np. `VerticalGradient_outPS.ps`).

## Co to jest pędzel liniowego gradientu C#?
**Pędzel liniowego gradientu C#** to obiekt GDI+ (`LinearGradientBrush`), który maluje liniowe przejście kolorów pomiędzy określonymi punktami. W połączeniu z API rysowania Aspose.Page pozwala renderować zaawansowane gradienty bezpośrednio w dokumencie PostScript (PS).

## Dlaczego używać pędzla liniowego gradientu w PostScript?
- **Wysokiej jakości wynik:** Gradienty są renderowane na poziomie drukarki, zachowując wierność.
- **Pełna kontrola:** Możesz ustawić własne przystanki kolorów, obrót i skalowanie.
- **Kod wielokrotnego użytku:** Ta sama logika pędzla działa dla PDF, SVG i innych formatów obsługiwanych przez Aspose.Page.

## Wymagania wstępne

Zanim przejdziesz do samouczka, upewnij się, że masz następujące elementy:

- Aspose.Page for .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Page. Niezbędne zasoby i dokumentację znajdziesz [tutaj](https://reference.aspose.com/page/net/).
- Środowisko programistyczne: Skonfiguruj odpowiednie środowisko programistyczne, w tym zintegrowane środowisko programistyczne (IDE) do tworzenia aplikacji .NET.
- Podstawowa wiedza: Zapoznaj się z podstawami programowania w .NET, w tym pracą ze strumieniami, ścieżkami graficznymi i manipulacją kolorami.

## Importowanie przestrzeni nazw

W swoim projekcie C# dołącz wymagane przestrzenie nazw na początku pliku kodu:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Krok 1: Ustawienie katalogu dokumentu

Określ ścieżkę do katalogu, w którym zostanie zapisany dokument PS.

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: Utworzenie strumienia wyjściowego dla dokumentu PostScript

Wygeneruj strumień wyjściowy dla dokumentu PostScript przy użyciu klasy `FileStream`.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
```

## Krok 3: Utworzenie opcji zapisu i dokumentu PS

Utwórz opcje zapisu z rozmiarem A4 i zainicjuj nowy dokument PS składający się z jednej strony.

```csharp
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Krok 4: Definicja wymiarów prostokąta

Określ wymiary i położenie prostokąta, w którym zostanie zastosowany pionowy gradient.

```csharp
float offsetX = 200;
float offsetY = 100;
float width = 200;
float height = 100;
```

## Krok 5: Utworzenie ścieżki graficznej

Zbuduj ścieżkę graficzną na podstawie zdefiniowanego prostokąta.

```csharp
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(offsetX, offsetY, width, height));
```

## Krok 6: Definicja kolorów interpolacji

Ustal tablicę kolorów interpolacji oraz ich pozycje dla gradientu.

```csharp
Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
ColorBlend colorBlend = new ColorBlend();
colorBlend.Colors = colors;
colorBlend.Positions = positions;
```

## Krok 7: Utworzenie pędzla liniowego gradientu

Stwórz pędzel liniowego gradientu z prostokątem jako granicą, kolorem początkowym i końcowym.

```csharp
LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
brush.InterpolationColors = colorBlend;
```

## Krok 8: Ustawienie transformacji pędzla

Ustal transformację dla pędzla, zapewniając, że składniki skali X i Y odpowiadają szerokości i wysokości prostokąta.

```csharp
Matrix brushTransform = new Matrix(width, 0, 0, height, offsetX, offsetY);
brushTransform.Rotate(90);
brush.Transform = brushTransform;
```

## Krok 9: Ustawienie farby i wypełnienie prostokąta

Ustaw farbę dla dokumentu i **wypełnij prostokąt gradientem** przy użyciu wcześniej zdefiniowanej ścieżki.

```csharp
document.SetPaint(brush);
document.Fill(path);
```

## Krok 10: Zamknięcie bieżącej strony i zapis dokumentu

Zamknij bieżącą stronę i zapisz dokument PostScript.

```csharp
document.ClosePage();
document.Save();
```

Gratulacje! Pomyślnie **dodałeś pionowy gradient do dokumentu PostScript** przy użyciu **pędzla liniowego gradientu C#** z Aspose.Page for .NET. Eksperymentuj z różnymi parametrami i kolorami, aby uzyskać różnorodne efekty wizualne w swoich dokumentach.

## Typowe problemy i rozwiązania

| Problem | Dlaczego się pojawia | Jak naprawić |
|---------|----------------------|--------------|
| Gradient wygląda poziomo | Obrót pędzla nie został zastosowany | Upewnij się, że wywołano `brushTransform.Rotate(90);` przed przypisaniem do `brush.Transform`. |
| Kolory są wyblakłe | Strumień wyjściowy o niskiej rozdzielczości | Użyj `PsSaveOptions` o wyższej rozdzielczości lub zwiększ rozmiar dokumentu. |
| Plik wyjściowy jest pusty | Strumień nie został opróżniony | Sprawdź, czy wywołano `document.Save();` poza blokiem `using`. |

## Najczęściej zadawane pytania

**P1: Czy mogę zastosować wiele gradientów w różnych obszarach tego samego dokumentu?**  
O: Tak, możesz. Po prostu powtórz kroki dla każdego obszaru, podając jego konkretne wymiary i schemat kolorów.

**P2: Jak wkomponować ten kod w istniejący projekt .NET?**  
O: Skopiuj i wklej kod do pliku projektu oraz upewnij się, że biblioteka Aspose.Page jest dodana jako odwołanie.

**P3: Czy w Aspose.Page for .NET dostępne są inne typy gradientów?**  
O: Aspose.Page obsługuje różne typy gradientów, w tym radialne i gradienty ścieżkowe. Szczegóły znajdziesz w dokumentacji.

**P4: Czy mogę używać Aspose.Page w projektach komercyjnych?**  
O: Tak. Odwiedź [tutaj](https://purchase.aspose.com/buy), aby zapoznać się z opcjami licencjonowania.

**P5: Czy istnieje forum społecznościowe Aspose.Page, gdzie mogę uzyskać pomoc?**  
O: Oczywiście! Przejdź do [forum Aspose.Page](https://forum.aspose.com/c/page/39), aby połączyć się z innymi programistami i uzyskać wsparcie.

---

**Ostatnia aktualizacja:** 2026-02-25  
**Testowano z:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}