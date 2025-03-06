---
title: Zmień nazwaną wartość za pomocą Aspose.Page dla .NET
linktitle: Zmień nazwaną wartość
second_title: Aspose.Page API .NET
description: Dowiedz się, jak zmieniać nazwane wartości w plikach EPS przy użyciu Aspose.Page dla .NET. Dostosuj metadane XMP bez wysiłku, aby dostosować przetwarzanie dokumentów.
weight: 16
url: /pl/net/eps-metadata-management/modify-eps-metadata-change-named-value/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zmień nazwaną wartość za pomocą Aspose.Page dla .NET

## Wstęp

świecie przetwarzania dokumentów Aspose.Page dla .NET wyróżnia się jako potężne narzędzie do manipulowania plikami EPS. Jedną z kluczowych funkcjonalności, jakie oferuje, jest możliwość zmiany nazwanych wartości w metadanych XMP. Ten samouczek poprowadzi Cię przez proces zmiany nazwanej wartości przy użyciu Aspose.Page dla .NET, umożliwiając dostosowanie plików EPS do Twoich konkretnych potrzeb.

## Warunki wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

-  Aspose.Page dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Page dla .NET. Jeśli nie, możesz go pobrać[Tutaj](https://releases.aspose.com/page/net/).

- Katalog dokumentów: Przygotuj wyznaczony katalog na pliki EPS, w którym możesz wprowadzać zmiany nazwanych wartości.

## Importuj przestrzenie nazw

W projekcie .NET musisz zaimportować niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności zapewnianych przez Aspose.Page. Dodaj następujące przestrzenie nazw do swojego kodu:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Podzielmy teraz kod na wiele kroków, aby uzyskać kompleksowe zrozumienie:

## Krok 1: Zainicjuj strumień wejściowy pliku EPS

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// RozwińKoniec:1
```

tym kroku konfigurujemy strumień wejściowy dla pliku EPS, który chcesz zmodyfikować. Pamiętaj, aby zastąpić „Twój katalog dokumentów” rzeczywistą ścieżką do katalogu dokumentów.

## Krok 2: Uzyskaj metadane XMP

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

Pobierz istniejące metadane XMP z pliku EPS. Jeżeli plik EPS nie zawiera metadanych XMP, zostanie wygenerowany nowy z wartościami z komentarzy do metadanych PS.

## Krok 3: Zmień wartości metadanych XMP

```csharp
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

Tutaj demonstrujemy zmianę dwóch nazwanych wartości w strukturze „xmpTPg:MaxPageSize”. Można to dostosować do swoich konkretnych wymagań.

## Krok 4: Zapisz plik EPS ze zmienionymi metadanymi XMP

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

Zapisz zmodyfikowany plik EPS w strumieniu wyjściowym. Plik będzie teraz odzwierciedlał zmiany wprowadzone w metadanych XMP.

## Wniosek

W tym samouczku nauczyłeś się wykorzystywać Aspose.Page dla .NET do zmiany nazwanych wartości w metadanych XMP w plikach EPS. Ta funkcjonalność otwiera świat możliwości dostosowywania i dostosowywania dokumentów do konkretnych wymagań.

## Często zadawane pytania

### P1: Czy mogę używać Aspose.Page dla .NET z innymi formatami dokumentów?

O1: Tak, Aspose.Page obsługuje różne formaty dokumentów, w tym EPS, XPS i PDF.

### P2: Czy dostępna jest wersja próbna Aspose.Page dla .NET?

 Odpowiedź 2: Tak, możesz uzyskać dostęp do bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).

### P3: Gdzie mogę znaleźć więcej dokumentacji na temat Aspose.Page dla .NET?

 Odpowiedź 3: Zapoznaj się z dokumentacją[Tutaj](https://reference.aspose.com/page/net/).

### P4: Jak mogę uzyskać tymczasową licencję na Aspose.Page dla .NET?

 A4: Możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).

### P5: Jakie opcje wsparcia są dostępne dla użytkowników Aspose.Page dla .NET?

 Odpowiedź 5: Odwiedź forum społeczności[Tutaj](https://forum.aspose.com/c/page/39) za wsparcie i dyskusje.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
