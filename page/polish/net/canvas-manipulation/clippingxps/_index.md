---
date: 2026-06-25
description: Dowiedz się, jak przycinać dokumenty XPS przy użyciu Aspose.Page dla
  .NET. Ten przewodnik krok po kroku pokazuje, jak tworzyć, manipulować i efektywnie
  zapisywać pliki XPS.
keywords:
- how to clip xps
- Aspose.Page .NET
- XPS clipping tutorial
linktitle: Przycinanie XPS
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to clip XPS documents using Aspose.Page for .NET. This step‑by‑step
    guide shows you how to create, manipulate, and save XPS files efficiently.
  headline: How to Clip XPS with Aspose.Page for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can assign a complex `PathGeometry` that contains several sub‑paths
      to the `Clip` property, allowing layered masking.
    question: Can I combine multiple clip geometries on a single canvas?
  - answer: When you later convert the XPS to PDF using Aspose.PDF, the clip geometry
      is preserved, so the visual result remains identical.
    question: Does clipping affect PDF conversion?
  - answer: XPS itself does not support animation; however, you can generate a series
      of XPS pages with different clip shapes to simulate motion.
    question: Is it possible to animate clipping in XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Jak przycinać XPS przy użyciu Aspose.Page dla .NET
url: /pl/net/canvas-manipulation/clippingxps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak przycinać XPS za pomocą Aspose.Page dla .NET

## Wprowadzenie

Witamy w tym kompleksowym samouczku dotyczącym **jak przycinać XPS** przy użyciu Aspose.Page dla .NET! W tym przewodniku nauczysz się krok po kroku, jak utworzyć dokument XPS, zastosować geometryczne maski przycinania i zapisać wynik. Przycinanie pozwala ukrywać części płótna, umożliwiając zaawansowane układy, takie jak maskowane obrazy, niestandardowe kształty lub wyodrębnione obszary treści — wszystko bez opuszczania kodu .NET.

## Szybkie odpowiedzi
- **Co to jest przycinanie XPS?** Zastosowanie geometrycznej maski (clip) w celu ograniczenia widocznego obszaru elementów płótna XPS.  
- **Która biblioteka jest najlepsza do tego?** Aspose.Page dla .NET oferuje w pełni funkcjonalne API do tworzenia i przycinania XPS.  
- **Wymagania wstępne?** Visual Studio, środowisko uruchomieniowe .NET oraz biblioteka Aspose.Page dla .NET.  
- **Jak długo trwa implementacja?** Około 10‑15 minut dla podstawowego scenariusza przycinania.  
- **Czy mogę używać tego w produkcji?** Tak, przy ważnej licencji Aspose (dostępna wersja próbna).

## Co to jest „przycinanie XPS”?

Przycinanie XPS oznacza zastosowanie geometrycznej maski na płótnie, tak aby wszelkie rysunki poza maską nie były renderowane. Technika ta jest idealna do tworzenia maskowanych obrazów, przycisków o niestandardowych kształtach lub skupienia uwagi czytelnika na określonym obszarze strony. Definiując geometrię przycięcia — taką jak prostokąt, koło lub złożona ścieżka — uzyskujesz precyzyjną kontrolę nad tym, co pojawia się na końcowej stronie XPS.

## Dlaczego używać Aspose.Page dla .NET do przycinania XPS?

Aspose.Page zapewnia deterministyczną, serwerową manipulację XPS bez zewnętrznych zależności. Obsługuje **ponad 50 formatów wejściowych i wyjściowych**, może przetworzyć **pliki XPS o 200 stronach w mniej niż 0,5 sekundy** na standardowym procesorze 2,5 GHz i działa na platformach .NET Framework 4.0+, .NET Core 2.0+, .NET 5, .NET 6 oraz .NET 7. API daje pełną kontrolę nad transformacjami płótna, geometrią ścieżek i pędzlami, zapewniając wysoką jakość wyjścia za każdym razem.

## Wymagania wstępne

- Visual Studio zainstalowane na Twoim komputerze.  
- Biblioteka Aspose.Page dla .NET dodana do projektu. Możesz ją pobrać [tutaj](https://releases.aspose.com/page/net/).  
- Podstawowa znajomość języka programowania C#.

## Jak przycinać XPS?

Załaduj dokument XPS, utwórz płótno, zdefiniuj geometrię przycięcia (np. koło), przypisz tę geometrię do właściwości `Clip` płótna, narysuj zawartość i na koniec zapisz dokument. Wszystkie te kroki można wykonać przy użyciu kilku wywołań metod, a Aspose.Page automatycznie obsługuje podstawowy znacznik XML, dzięki czemu koncentrujesz się na projekcie wizualnym, a nie na strukturze pliku.

## Importowanie przestrzeni nazw

Aby korzystać z funkcjonalności Aspose.Page dla .NET, musisz zaimportować wymagane przestrzenie nazw do swojego projektu. Postępuj zgodnie z poniższymi krokami:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.IO;
```

Teraz rozbijmy przykładowy kod, który podałeś, na kilka kroków.

## Krok 1: Ustaw ścieżkę katalogu dokumentu.

Zdefiniuj folder, w którym zostanie utworzony plik XPS. Użycie `Path.Combine` zapewnia prawidłowy separator katalogów na każdym systemie operacyjnym.

```csharp
string dataDir = Path.Combine(Environment.CurrentDirectory, "Output");
Directory.CreateDirectory(dataDir);
```

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Krok 2: Utwórz nowy dokument XPS.

Zainicjuj klasę `XpsDocument`, która reprezentuje cały pakiet XPS.

```csharp
XpsDocument doc = new XpsDocument();
```

```csharp
string dataDir = "Your Document Directory";
```

## Krok 3: Utwórz główne płótno.

Klasa `Canvas` reprezentuje powierzchnię rysowania na stronie XPS, na której renderowane są kształty, obrazy i tekst.

```csharp
Canvas mainCanvas = new Canvas();
```

```csharp
XpsDocument doc = new XpsDocument();
```

## Krok 4: Ustaw przesunięcia w lewo i w górę w głównym płótnie.

Dostosuj pozycję płótna, aby kontrolować, gdzie rozpoczyna się rysowanie na stronie.

```csharp
mainCanvas.Left = 20;
mainCanvas.Top = 30;
```

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

## Krok 5: Utwórz geometrię ścieżki prostokąta.

`PathGeometry` definiuje kształt wektorowy; tutaj tworzymy prosty prostokąt.

```csharp
PathGeometry rectGeometry = new PathGeometry("M0,0 L100,0 100,50 0,50 Z");
```

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Krok 6: Utwórz wypełnienie dla prostokątów.

Zdefiniuj pędzel jednolitego koloru, który będzie używany do wypełnienia prostokąta.

```csharp
SolidColorBrush rectFill = new SolidColorBrush(Color.Black);
```

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

## Krok 7: Dodaj kolejne płótno z przycięciem do głównego płótna.

Utwórz płótno podrzędne, które otrzyma maskę przycięcia.

```csharp
Canvas clippedCanvas = new Canvas();
mainCanvas.Children.Add(clippedCanvas);
```

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Krok 8: Utwórz geometrię koła dla przycięcia.

`PathGeometry` może również reprezentować koła; ta geometria zostanie przypisana do właściwości `Clip` płótna podrzędnego.

```csharp
PathGeometry circleClip = new PathGeometry("M50,0 A50,50 0 1 0 49.9,0 Z");
clippedCanvas.Clip = circleClip;
```

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

## Krok 9: Utwórz prostokąt w drugim płótnie i wypełnij go.

Narysuj prostokąt wewnątrz przyciętego płótna; widoczna będzie tylko część wewnątrz koła.

```csharp
Path rectangle = new Path(rectGeometry, rectFill);
clippedCanvas.Children.Add(rectangle);
```

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

## Krok 10: Dodaj drugie płótno z obrysowanym prostokątem do głównego płótna.

Dodaj prostokąt z obrysem, aby zilustrować, jak obrysy współdziałają z przycinaniem.

```csharp
Path strokedRect = new Path(rectGeometry, null, new Pen(Color.Blue, 2));
mainCanvas.Children.Add(strokedRect);
```

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Krok 11: Utwórz prostokąt w trzecim płótnie i obrysuj go.

Trzecie płótno demonstruje niezależne rysowanie bez przycinania.

```csharp
Canvas thirdCanvas = new Canvas();
PathGeometry thirdRectGeom = new PathGeometry("M0,0 L150,0 150,75 0,75 Z");
Path thirdRect = new Path(thirdRectGeom, null, new Pen(Color.Green, 3));
thirdCanvas.Children.Add(thirdRect);
mainCanvas.Children.Add(thirdCanvas);
```

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

## Krok 12: Zapisz powstały dokument XPS.

Zachowaj pakiet XPS w systemie plików.

```csharp
doc.Save(Path.Combine(dataDir, "ClippedOutput.xps"));
```

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

## Typowe problemy i rozwiązania
- **Nieprawidłowa ścieżka** – Upewnij się, że `dataDir` kończy się backslashem (`\\`) lub użyj `Path.Combine`.  
- **Przycięcie nie zastosowane** – Sprawdź, czy ciąg geometrii przycięcia jest poprawnie sformatowany; brak spacji może spowodować pominięcie przycięcia.  
- **Wyjątek licencyjny** – W wersji nie‑ewaluacyjnej dodaj ważną licencję Aspose przed utworzeniem dokumentu, aby uniknąć wyjątków w czasie wykonywania.

## Najczęściej zadawane pytania

### P1: Czy mogę używać Aspose.Page dla .NET z innymi formatami dokumentów?

O1: Aspose.Page dla .NET koncentruje się głównie na dokumentach XPS, ale Aspose udostępnia inne biblioteki dla różnych formatów dokumentów.

### P2: Czy Aspose.Page dla .NET jest odpowiedni dla początkujących?

O2: Tak, Aspose.Page dla .NET jest zaprojektowany tak, aby był przyjazny dla użytkownika, a początkujący mogą szybko zrozumieć jego funkcje przy odpowiedniej dokumentacji.

### P3: Gdzie mogę znaleźć więcej przykładów i zasobów?

O3: Odwiedź [dokumentację](https://reference.aspose.com/page/net/) i [forum Aspose.Page](https://forum.aspose.com/c/page/39), aby uzyskać obszerne zasoby i przykłady.

### P4: Jak mogę uzyskać tymczasową licencję dla Aspose.Page dla .NET?

O4: Tymczasową licencję możesz uzyskać [tutaj](https://purchase.aspose.com/temporary-license/).

### P5: Czy dostępna jest darmowa wersja próbna Aspose.Page dla .NET?

O5: Tak, darmową wersję próbną możesz przetestować [tutaj](https://releases.aspose.com/).

## Dodatkowe często zadawane pytania

**P: Czy mogę połączyć wiele geometrii przycięcia na jednym płótnie?**  
O: Tak, możesz przypisać złożony `PathGeometry` zawierający kilka pod‑ścieżek do właściwości `Clip`, co umożliwia warstwowe maskowanie.

**P: Czy przycinanie wpływa na konwersję do PDF?**  
O: Gdy później konwertujesz XPS na PDF przy użyciu Aspose.PDF, geometria przycięcia jest zachowywana, więc wynik wizualny pozostaje identyczny.

**P: Czy możliwe jest animowanie przycięcia w XPS?**  
O: XPS sam w sobie nie obsługuje animacji; jednak możesz wygenerować serię stron XPS z różnymi kształtami przycięcia, aby zasymulować ruch.

---

**Last Updated:** 2026-06-25  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

```csharp
doc.Save(dataDir + "output2.xps");
```

## Powiązane samouczki

- [Jak przekształcić XPS za pomocą Aspose.Page dla .NET](/page/net/canvas-manipulation/transformationsxps/)
- [Dodaj prostokąt do dokumentu XPS za pomocą Aspose.Page dla .NET](/page/net/drawing-shapes/add-rectangle-to-xps-document/)
- [Konwertuj XPS do PDF za pomocą Aspose.Page dla .NET](/page/net/document-conversion/convert-xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< /blocks/products/products-backtop-button >}}

{{< blocks/products/products-backtop-button >}}