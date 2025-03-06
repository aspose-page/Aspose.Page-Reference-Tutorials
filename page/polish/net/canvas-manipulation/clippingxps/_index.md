---
title: Przycinanie XPS za pomocą Aspose.Page dla .NET
linktitle: Przycinanie XPS
second_title: Aspose.Page API .NET
description: Poznaj możliwości Aspose.Page dla .NET w tym przewodniku krok po kroku dotyczącym wycinania dokumentów XPS. Twórz, manipuluj i zapisuj pliki XPS bez wysiłku.
weight: 11
url: /pl/net/canvas-manipulation/clippingxps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Przycinanie XPS za pomocą Aspose.Page dla .NET

## Wstęp

Witamy w tym kompleksowym samouczku na temat przycinania XPS przy użyciu Aspose.Page dla .NET! W tym przewodniku przeprowadzimy Cię przez proces tworzenia, manipulowania i zapisywania dokumentów XPS przy użyciu Aspose.Page dla .NET. XPS, czyli specyfikacja papieru XML, to ustandaryzowany i otwarty format dokumentu, a Aspose.Page dla .NET zapewnia potężne narzędzia do pracy z dokumentami XPS w aplikacjach .NET.

## Warunki wstępne

Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

- Program Visual Studio zainstalowany na Twoim komputerze.
-  Biblioteka Aspose.Page dla .NET dodana do Twojego projektu. Możesz go pobrać[Tutaj](https://releases.aspose.com/page/net/).
- Podstawowa znajomość języka programowania C#.

## Importuj przestrzenie nazw

Aby korzystać z funkcjonalności Aspose.Page for .NET, musisz zaimportować wymagane przestrzenie nazw do swojego projektu. Wykonaj następujące kroki:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Podzielmy teraz podany przykładowy kod na kilka kroków.

## Krok 1: Ustaw ścieżkę katalogu dokumentu.

```csharp
string dataDir = "Your Document Directory";
```

Pamiętaj, aby zastąpić „Twój katalog dokumentów” rzeczywistą ścieżką do katalogu dokumentów.

## Krok 2: Utwórz nowy dokument XPS.

```csharp
XpsDocument doc = new XpsDocument();
```

Spowoduje to utworzenie nowego dokumentu XPS, z którym będziesz pracować.

## Krok 3: Utwórz główne płótno.

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

Ten krok tworzy główne płótno, które jest wspólne dla wszystkich elementów strony.

## Krok 4: Ustaw przesunięcie w lewo i u góry na głównym płótnie.

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

Dostosuj przesunięcie lewe i górne zgodnie ze swoimi wymaganiami.

## Krok 5: Utwórz prostokątną geometrię ścieżki.

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

Tworzy to geometrię ścieżki dla prostokąta.

## Krok 6: Utwórz wypełnienie prostokątów.

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

Określ kolor wypełnienia prostokątów.

## Krok 7: Dodaj kolejne płótno z klipsem do płótna głównego.

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

Ten krok dodaje kolejne płótno do głównego płótna.

## Krok 8: Utwórz geometrię okręgu dla klipu.

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

Spowoduje to utworzenie okrągłej geometrii klipu i zastosowanie jej do drugiego obszaru roboczego.

## Krok 9: Utwórz prostokąt na drugim płótnie i wypełnij go.

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Ten krok tworzy prostokąt na drugim płótnie i wypełnia go.

## Krok 10: Dodaj drugie płótno z obrysowanym prostokątem do głównego płótna.

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

Spowoduje to dodanie kolejnego płótna do głównego płótna.

## Krok 11: Utwórz prostokąt na trzecim płótnie i obrysuj go.

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

Spowoduje to utworzenie prostokąta na trzecim płótnie i zastosowanie do niego obrysu.

## Krok 12: Zapisz powstały dokument XPS.

```csharp
doc.Save(dataDir + "output2.xps");
```

Spowoduje to zapisanie dokumentu XPS w określonym katalogu.

## Wniosek

Gratulacje! Pomyślnie nauczyłeś się wycinać XPS za pomocą Aspose.Page dla .NET. W tym przewodniku szczegółowo omówiono etapy tego procesu.

## Często zadawane pytania

### P1: Czy mogę używać Aspose.Page dla .NET z innymi formatami dokumentów?

O1: Aspose.Page dla .NET koncentruje się głównie na dokumentach XPS, ale Aspose udostępnia inne biblioteki dla różnych formatów dokumentów.

### P2: Czy Aspose.Page dla .NET jest odpowiedni dla początkujących?

Odpowiedź 2: Tak, Aspose.Page dla .NET został zaprojektowany tak, aby był przyjazny dla użytkownika, a początkujący mogą szybko zrozumieć jego funkcje dzięki odpowiedniej dokumentacji.

### P3: Gdzie mogę znaleźć więcej przykładów i zasobów?

 A3: Odwiedź[dokumentacja](https://reference.aspose.com/page/net/) I[Forum Aspose.Page](https://forum.aspose.com/c/page/39) w celu uzyskania obszernych zasobów i przykładów.

### P4: Jak mogę uzyskać tymczasową licencję na Aspose.Page dla .NET?

 A4: Możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).

### P5: Czy dostępna jest bezpłatna wersja próbna Aspose.Page dla .NET?

 Odpowiedź 5: Tak, możesz skorzystać z bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
