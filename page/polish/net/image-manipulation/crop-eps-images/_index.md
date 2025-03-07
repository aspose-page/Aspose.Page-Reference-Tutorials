---
title: Przycinaj obrazy EPS za pomocą Aspose.Page dla .NET
linktitle: Przytnij obrazy EPS
second_title: Aspose.Page API .NET
description: Poznaj płynny świat manipulacji obrazami EPS w .NET dzięki Aspose.Page. Przycinaj i zmieniaj rozmiar obrazów bez wysiłku, aby uzyskać oszałamiające rezultaty.
weight: 10
url: /pl/net/image-manipulation/crop-eps-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Przycinaj obrazy EPS za pomocą Aspose.Page dla .NET

## Wstęp

Czy masz trudności z manipulowaniem obrazami EPS w aplikacjach .NET? Nie szukaj dalej! W tym samouczku przeprowadzimy Cię przez proces przycinania obrazów EPS przy użyciu potężnej biblioteki Aspose.Page dla .NET. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten przewodnik krok po kroku pomoże Ci bez wysiłku uzyskać precyzyjne przycięcie obrazu.

## Warunki wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

- Praktyczna wiedza na temat programowania .NET.
-  Zainstalowana biblioteka Aspose.Page dla .NET. Jeśli nie, możesz go pobrać[Tutaj](https://releases.aspose.com/page/net/).
- Przykładowy obraz EPS (zastąp „input.eps” w kodzie rzeczywistym plikiem).

## Importuj przestrzenie nazw

Zacznijmy od zaimportowania niezbędnych przestrzeni nazw, aby nasz kod działał płynnie. 

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

Podzielmy teraz samouczek na kilka kroków.

## Krok 1: Zainicjuj PsDocument

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

 Zainicjuj a`PsDocument` obiekt z wejściowym strumieniem EPS.

## Krok 2: Wyodrębnij obwiednię

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

Pobierz początkową ramkę ograniczającą obrazu EPS.

## Krok 3: Utwórz strumień wyjściowy

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

Utwórz strumień wyjściowy dla przyciętego obrazu EPS.

## Krok 4: Zdefiniuj nową ramkę ograniczającą

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

Zdefiniuj nową ramkę ograniczającą do przycięcia. Upewnij się, że nowe wartości mieszczą się w początkowej ramce ograniczającej.

## Krok 5: Przytnij i zapisz

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

Przytnij obraz EPS za pomocą nowej ramki ograniczającej i zapisz go w strumieniu wyjściowym.

Powtórz te kroki dla różnych scenariuszy zmiany rozmiaru.

## Zmiana rozmiaru obrazów EPS

### Zmień rozmiar w calach

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

Zmień rozmiar obrazu EPS i zapisz go z określonymi wymiarami w calach.

### Zmień rozmiar w milimetrach

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

Zmień rozmiar obrazu EPS i zapisz go z określonymi wymiarami w milimetrach.

### Zmień rozmiar w procentach

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

Zmień rozmiar obrazu EPS i zapisz go z określonymi wymiarami w procentach.

## Wniosek

Gratulacje! Pomyślnie nauczyłeś się przycinać i zmieniać rozmiar obrazów EPS przy użyciu Aspose.Page dla .NET. Teraz zwiększ swoje możliwości manipulacji obrazami i przenieś swoje aplikacje .NET na wyższy poziom.

## Często zadawane pytania

### P1: Czy mogę używać Aspose.Page dla .NET z innymi formatami obrazów?

Odpowiedź 1: Aspose.Page koncentruje się głównie na obrazach EPS, ale Aspose udostępnia różne biblioteki dla różnych formatów. Sprawdź ich dokumentację pod kątem określonych formatów.

### P2: Jak mogę uzyskać tymczasową licencję na Aspose.Page dla .NET?

 A2: Odwiedź[ten link](https://purchase.aspose.com/temporary-license/) aby uzyskać tymczasową licencję na testowanie.

### P3: Czy są jakieś ograniczenia dotyczące rozmiaru obrazu, który mogę przetwarzać za pomocą Aspose.Page dla .NET?

A3: Aspose.Page jest przeznaczony do obsługi obrazów o różnych rozmiarach. Jednakże wydajność może się różnić w zależności od złożoności obrazu.

### P4: Czy istnieje forum społecznościowe do dyskusji na temat Aspose.Page?

 Odpowiedź 4: Tak, możesz nawiązać kontakt ze społecznością Aspose.Page[Tutaj](https://forum.aspose.com/c/page/39).

### P5: Gdzie mogę znaleźć szczegółową dokumentację Aspose.Page dla .NET?

 Odpowiedź 5: Zapoznaj się z dokumentacją[Tutaj](https://reference.aspose.com/page/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
