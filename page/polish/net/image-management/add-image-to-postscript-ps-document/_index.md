---
title: Dodaj obraz do dokumentu PostScript (PS) za pomocą Aspose.Page
linktitle: Dodaj obraz do dokumentu PostScript (PS).
second_title: Aspose.Page API .NET
description: Dowiedz się, jak ulepszyć dokumenty PostScript, dodając obrazy za pomocą Aspose.Page dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby zapewnić bezproblemową obsługę.
weight: 10
url: /pl/net/image-management/add-image-to-postscript-ps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj obraz do dokumentu PostScript (PS) za pomocą Aspose.Page

## Wstęp

W tym samouczku omówimy proces dodawania obrazów do dokumentu PostScript (PS) przy użyciu potężnej biblioteki Aspose.Page dla .NET. Aspose.Page upraszcza manipulowanie dokumentami PS, oferując skuteczny i prosty sposób na wzbogacenie dokumentu obrazami. Ten przewodnik krok po kroku przeprowadzi Cię przez proces, zapewniając dokładne zrozumienie każdej koncepcji.

## Warunki wstępne

Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

-  Biblioteka Aspose.Page dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Page dla .NET z[Tutaj](https://releases.aspose.com/page/net/).
- Katalog dokumentów: Utwórz katalog w swoim systemie do przechowywania plików dokumentów i obrazów.

## Importuj przestrzenie nazw

Zacznij od zaimportowania niezbędnych przestrzeni nazw do swojego projektu. Te przestrzenie nazw umożliwiają wykorzystanie funkcjonalności Aspose.Page w aplikacji .NET:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Krok 1: Skonfiguruj katalog dokumentów

 Upewnij się, że masz dedykowany katalog na swoje dokumenty. Zastępować`"Your Document Directory"` w poniższym fragmencie kodu ze ścieżką do katalogu dokumentów.

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: Utwórz strumień wyjściowy dla dokumentu PS

Skonfiguruj strumień wyjściowy dla dokumentu PostScript. Strumień ten zostanie wykorzystany do zapisania zmodyfikowanego dokumentu.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddImage_outPS.ps", FileMode.Create))
```

## Krok 3: Utwórz opcje zapisu

Utwórz opcje zapisywania dokumentu PS, określając żądane ustawienia, takie jak rozmiar strony.

```csharp
PsSaveOptions options = new PsSaveOptions();
```

## Krok 4: Utwórz dokument PS

Zainicjuj nowy 1-stronicowy dokument PS i przygotuj się do operacji graficznych.

```csharp
PsDocument document = new PsDocument(outPsStream, options, false);
document.WriteGraphicsSave();
document.Translate(100, 100);
```

## Krok 5: Dodaj obraz do dokumentu

Załaduj obiekt Bitmap z pliku obrazu i zastosuj przekształcenia. Dodaj obraz do dokumentu PS.

```csharp
using (Bitmap image = new Bitmap(dataDir + "TestImage Format24bppRgb.jpg"))
{
    System.Drawing.Drawing2D.Matrix transform = new System.Drawing.Drawing2D.Matrix();
    transform.Translate(35, 300);
    transform.Scale(3, 3);
    transform.Rotate(-45);
    
    document.DrawImage(image, transform, Color.Empty);
}
```

## Krok 6: Sfinalizuj operacje graficzne

Zakończ operacje graficzne i zamknij bieżącą stronę.

```csharp
document.WriteGraphicsRestore();
document.ClosePage();
```

## Krok 7: Zapisz dokument

Zapisz zmodyfikowany dokument PS.

```csharp
document.Save();
```

## Wniosek

Gratulacje! Pomyślnie dodałeś obraz do dokumentu PostScript przy użyciu Aspose.Page dla .NET. Ten samouczek zawiera jasny i zwięzły przewodnik dotyczący włączania obrazów do dokumentów PS, dzięki czemu dokumenty będą atrakcyjne wizualnie i wciągające.

## Często zadawane pytania

### P1: Czy mogę dodać wiele obrazów do jednego dokumentu PS przy użyciu Aspose.Page?

A1: Tak, możesz. Po prostu powtórz kroki dodawania obrazu w dokumencie.

### P2: Jakie formaty obrazów są obsługiwane przez Aspose.Page dla .NET?

O2: Aspose.Page dla .NET obsługuje różne formaty obrazów, w tym JPEG, PNG, BMP i GIF.

### P3: Czy istnieje ograniczenie rozmiaru obrazów, które można dodać?

Odpowiedź 3: Limit rozmiaru zależy od specyfikacji dokumentu PS i zasobów systemowych. Aspose.Page obsługuje szeroką gamę rozmiarów obrazów.

### P4: Czy mogę zastosować do obrazów dodatkowe efekty, takie jak filtry lub nakładki?

O4: Tak, Aspose.Page umożliwia zastosowanie różnych przekształceń i efektów do obrazów przed dodaniem ich do dokumentu.

### P5: Jak wyodrębnić obrazy z dokumentu PS?

O5: Aspose.Page dla .NET udostępnia metody wyodrębniania obrazów z dokumentów PS. Szczegółowe informacje można znaleźć w dokumentacji.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
