---
title: Usuń stronę z dokumentu XPS za pomocą Aspose.Page dla .NET
linktitle: Usuń stronę z dokumentu XPS
second_title: Aspose.Page API .NET
description: Zapoznaj się z obszernym samouczkiem na temat usuwania stron z dokumentów XPS przy użyciu Aspose.Page dla .NET. Poznaj szczegółowy proces, wymagania wstępne i często zadawane pytania dotyczące bezproblemowego manipulowania dokumentami.
type: docs
weight: 12
url: /pl/net/page-manipulation/remove-page-from-xps-document/
---
## Wstęp

W tym samouczku omówimy proces usuwania strony z dokumentu XPS przy użyciu Aspose.Page dla .NET. Aspose.Page to potężna biblioteka, która umożliwia programistom .NET bezproblemową pracę z dokumentami XPS (Specyfikacja papieru XML). Jeśli znajdziesz się w sytuacji, w której musisz usunąć konkretną stronę z dokumentu XPS, ten przewodnik krok po kroku przeprowadzi Cię przez ten proces.

## Warunki wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

-  Biblioteka Aspose.Page dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Page. Można go pobrać z[Aspose.Page dla dokumentacji .NET](https://reference.aspose.com/page/net/).

- Środowisko programistyczne .NET: Skonfiguruj działające środowisko programistyczne .NET na swoim komputerze.

- Przykładowy dokument XPS: Przygotuj przykładowy dokument XPS, którego będziesz używać do testowania procesu usuwania.

## Importuj przestrzenie nazw

W aplikacji .NET rozpocznij od zaimportowania przestrzeni nazw niezbędnych do pracy z Aspose.Page. Dodaj następujące wiersze na górze pliku kodu:

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

Pamiętaj, aby zastąpić „Twój katalog dokumentów” rzeczywistą ścieżką do katalogu dokumentów.

## Krok 2: Utwórz nowy dokument XPS

```csharp
// ExStart:4
// Utwórz nowy dokument XPS
XpsDocument doc = new XpsDocument(dataDir + "Sample.xps");
// RozwińKoniec:4
```

Ten kod inicjuje nowy dokument XPS na podstawie dostarczonego przykładowego pliku.

## Krok 3: Usuń stronę

```csharp
// ExStart:5
// Usuń pierwszą stronę (w indeksie 1).
doc.RemovePageAt(1);
// RozwińKoniec:5
```

Określ indeks strony, którą chcesz usunąć. W tym przykładzie kod usuwa stronę z indeksem 1.

## Krok 4: Zapisz wynikowy dokument XPS

```csharp
// ExStart:6
// Zapisz wynikowy dokument XPS
doc.Save(dataDir + "Sample_out.xps");
// RozwińKoniec:6
```

Zapisz zmodyfikowany dokument XPS z usuniętą stroną.

## Wniosek

Gratulacje! Pomyślnie usunąłeś stronę z dokumentu XPS przy użyciu Aspose.Page dla .NET. Ten prosty proces można bezproblemowo zintegrować z aplikacjami .NET, zapewniając elastyczność w zarządzaniu dokumentami XPS.

## Często zadawane pytania

### P1: Czy mogę usunąć wiele stron jednocześnie, używając Aspose.Page dla .NET?

O1: Tak, możesz zmodyfikować kod, aby usunąć wiele stron, wywołując metodę`RemovePageAt` metodę wielokrotnie.

### P2: Czy Aspose.Page jest kompatybilny z najnowszym frameworkiem .NET?

O2: Aspose.Page jest regularnie aktualizowany, aby zapewnić kompatybilność z najnowszymi wersjami platformy .NET.

### P3: Czy mogę używać Aspose.Page do zastosowań komercyjnych?

 O3: Tak, możesz używać Aspose.Page do celów komercyjnych. Odwiedzać[Złóż. Kup](https://purchase.aspose.com/buy) w celu uzyskania szczegółów licencji.

### P4: Gdzie mogę znaleźć dodatkowe wsparcie i dyskusje na Aspose.Page?

 A4: Dołącz do[Forum Aspose.Page](https://forum.aspose.com/c/page/39) nawiązać kontakt ze społecznością i poprosić o pomoc.

### P5: Czy potrzebuję tymczasowej licencji do testowania Aspose.Page?

 A5: Tak, możesz uzyskać[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) do celów testowych.