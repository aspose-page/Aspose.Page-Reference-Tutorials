---
title: Dodaj obraz do dokumentu XPS za pomocą Aspose.Page dla .NET
linktitle: Dodaj obraz do dokumentu XPS
second_title: Aspose.Page API .NET
description: Poznaj bezproblemową integrację obrazów z dokumentami XPS za pomocą Aspose.Page dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby zapewnić płynne programowanie.
weight: 11
url: /pl/net/image-management/add-image-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj obraz do dokumentu XPS za pomocą Aspose.Page dla .NET

## Wstęp

W świecie programowania .NET częstym wymogiem jest dołączanie obrazów do dokumentów XPS. Aspose.Page dla .NET upraszcza ten proces, oferując potężny zestaw narzędzi do łatwego manipulowania i ulepszania dokumentów XPS. Ten samouczek poprowadzi Cię przez etapy dodawania obrazu do dokumentu XPS przy użyciu Aspose.Page dla .NET.

## Warunki wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

1.  Aspose.Page dla biblioteki .NET: Pobierz i zainstaluj bibliotekę z[Dokumentacja Aspose.Page .NET](https://reference.aspose.com/page/net/).

2. Środowisko programistyczne: skonfiguruj środowisko programistyczne .NET, takie jak Visual Studio.

3. Przykładowy obraz: Przygotuj przykładowy plik obrazu (np. „QL_logo_color.tif”), który chcesz dodać do dokumentu XPS.

## Importuj przestrzenie nazw

Zacznij od zaimportowania niezbędnych przestrzeni nazw do projektu .NET. Te przestrzenie nazw są niezbędne do wykorzystania funkcji udostępnianych przez Aspose.Page dla .NET.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Krok 1: Ustaw katalog dokumentów

Rozpocznij od określenia ścieżki do katalogu dokumentów. Ten krok gwarantuje, że projekt będzie wiedział, gdzie zlokalizować i zapisać pliki.

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
// RozwińKoniec:1
```

## Krok 2: Utwórz dokument XPS

Utwórz nowy dokument XPS za pomocą Aspose.Page dla .NET.

```csharp
// ExStart:1
XpsDocument doc = new XpsDocument();
// RozwińKoniec:1
```

## Krok 3: Dodaj obraz do dokumentu XPS

Teraz dodajmy obraz do dokumentu XPS. W tym przykładzie użyjemy przykładowego obrazu o nazwie „QL_logo_color.tif”.

```csharp
// ExStart:1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// RozwińKoniec:1
```

## Krok 4: Zapisz wynikowy dokument XPS

Zapisz dokument XPS z dodanym obrazem.

```csharp
// ExStart:1
doc.Save(dataDir + "AddImage_outXPS.xps");
// RozwińKoniec:1
```

Teraz pomyślnie dodałeś obraz do dokumentu XPS przy użyciu Aspose.Page dla .NET!

## Wniosek

W tym samouczku omówiliśmy, jak wykorzystać Aspose.Page dla .NET do płynnego włączania obrazów do dokumentów XPS. Ten przewodnik krok po kroku zapewnia płynny proces integracji, zwiększając możliwości programowania .NET.

## Często zadawane pytania

### P1: Czy Aspose.Page dla .NET jest kompatybilny z najnowszymi wersjami platformy .NET?

 O1: Aspose.Page dla .NET został zaprojektowany tak, aby był kompatybilny z szeroką gamą wersji platformy .NET, w tym najnowszymi wydaniami. Patrz[dokumentacja](https://reference.aspose.com/page/net/) dla konkretnych szczegółów.

### P2: Czy mogę używać Aspose.Page dla .NET zarówno w środowisku Windows, jak i Linux?

O2: Tak, Aspose.Page dla .NET jest niezależny od platformy, dzięki czemu nadaje się do użytku zarówno w środowiskach Windows, jak i Linux.

### P3: Czy istnieją opcje licencjonowania Aspose.Page dla .NET?

 Odpowiedź 3: Tak, możesz zapoznać się z opcjami licencjonowania i dokonać zakupu[Tutaj](https://purchase.aspose.com/buy).

### P4: Czy dostępna jest bezpłatna wersja próbna Aspose.Page dla .NET?

 O4: Tak, możesz wypróbować Aspose.Page dla .NET za darmo, uzyskując dostęp do[bezpłatna wersja próbna](https://releases.aspose.com/).

### P5: Gdzie mogę szukać pomocy lub nawiązać kontakt ze społecznością Aspose.Page dla .NET?

 A5: Odwiedź[Aspose.Page dla forum .NET](https://forum.aspose.com/c/page/39) aby nawiązać kontakt ze społecznością i uzyskać wsparcie.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
