---
date: 2026-03-19
description: Dowiedz się, jak dodać bilet, tworząc własne bilety do druku za pomocą
  Aspose.Page dla .NET. Dostosuj swoje doświadczenie drukowania dzięki precyzyjnej
  kontroli.
linktitle: Create Custom Print Ticket
second_title: Aspose.Page .NET API
title: 'Jak dodać bilet: Tworzenie niestandardowego biletu drukowania przy użyciu
  Aspose.Page dla .NET'
url: /pl/net/print-ticket-management/create-custom-print-ticket/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dodać bilet: Utwórz niestandardowy bilet drukowania z Aspose.Page dla .NET

## Wstęp

Jeśli potrzebujesz **funkcjonalności dodawania biletu** w aplikacji .NET, Aspose.Page daje możliwość generowania niestandardowych biletów drukowania bezpośrednio z kodu. W tym samouczku przeprowadzimy Cię przez cały proces — konfigurację środowiska, tworzenie dokumentu XPS, dołączanie niestandardowego biletu drukowania zadania oraz zapis wyniku. Po zakończeniu będziesz mógł dodać obsługę biletu do dowolnego przepływu drukowania z pełnym przekonaniem.

## Szybkie odpowiedzi
- **Co oznacza „dodawanie biletu”?** Odnosi się do osadzania niestandardowego biletu drukowania (metadane XPS), który kontroluje ustawienia drukarki.  
- **Jakiej biblioteki potrzebujesz?** Aspose.Page dla .NET.  
- **Czy potrzebna jest licencja?** Tymczasowa licencja wystarczy do oceny; pełna licencja jest wymagana w środowisku produkcyjnym.  
- **Czy mogę używać tego z .NET Core?** Tak, Aspose.Page obsługuje .NET Framework i .NET Core.  
- **Jak długo trwa implementacja?** Zazwyczaj poniżej 15 minut dla podstawowego biletu.

## Co to jest niestandardowy bilet drukowania?
Niestandardowy bilet drukowania to opis w formacie XML preferencji drukarki (takich jak sortowanie, liczba kopii, zarządzanie kolorem itp.), który podróżuje razem z dokumentem XPS. Umożliwia programistom programowe określenie, jak dokument ma być drukowany, eliminując ręczną konfigurację po stronie klienta.

## Dlaczego warto dodać obsługę biletu z Aspose.Page?
- **Precyzyjna kontrola:** Ustawiaj sortowanie, liczbę kopii, typ nośnika i wiele innych z poziomu kodu.  
- **Spójność wieloplatformowa:** Ten sam bilet działa na każdej drukarce rozumiejącej metadane XPS.  
- **Bezproblemowa integracja:** Działa bezpośrednio w istniejących projektach .NET bez dodatkowych usług.

## Wymagania wstępne

Zanim przejdziesz dalej, upewnij się, że masz:

- Podstawową znajomość C# i programowania w .NET.  
- Zainstalowane Visual Studio (dowolna nowsza wersja).  
- Bibliotekę Aspose.Page dla .NET dodaną do projektu.  

Jeśli jeszcze nie dodałeś biblioteki, możesz ją pobrać z [dokumentacji Aspose.Page dla .NET](https://reference.aspose.com/page/net/). W celu uzyskania pomocy społeczności, odwiedź [forum Aspose.Page](https://forum.aspose.com/c/page/39).

## Importowanie przestrzeni nazw

Rozpocznij od zaimportowania przestrzeni nazw, które udostępniają klasy XPS i metadane.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsMetadata;
using Aspose.Page.XPS.XpsModel;
using System;
using System.Drawing;
```

Teraz przeanalizujemy implementację krok po kroku.

## Krok 1: Ustaw katalog dokumentu

Zdefiniuj, gdzie zostanie zapisany wygenerowany plik XPS.

```csharp
string dir = "Your Document Directory";
```

## Krok 2: Utwórz nowy dokument XPS

Zainicjuj nowy dokument XPS, który będzie zawierał strony oraz bilet.

```csharp
XpsDocument xDocs = new XpsDocument();
```

## Krok 3: Dodaj niestandardowy bilet drukowania zadania

Dołącz niestandardowy bilet drukowania zadania do dokumentu. To jest sedno **funkcjonalności dodawania biletu** — tutaj określasz sortowanie, liczbę kopii, intencję renderowania, zarządzanie kolorem i inne potrzebne ustawienia.

```csharp
xDocs.JobPrintTicket = new JobPrintTicket(
    new PageDevModeSnaphot("SABlAGwAbABvACEAAAA="),
    new DocumentCollate(Collate.CollateOption.Collated),
    // Add other print settings as needed
);
```

> **Wskazówka:** Zastąp ciąg zastępczy snapshotu zakodowanym w Base64 strukturą DEVMODE, która odpowiada możliwościom Twojej drukarki.

## Krok 4: Zapisz dokument

Zapisz dokument XPS (z osadzonym biletem) na dysku.

```csharp
xDocs.Save(dir + "output1.xps");
```

Gdy otworzysz *output1.xps* w przeglądarce respektującej metadane XPS, drukarka automatycznie zastosuje ustawienia zdefiniowane w bilecie.

## Typowe problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| Bilet nie został zastosowany | Przeglądarka ignoruje metadane XPS | Użyj sterownika drukarki obsługującego bilety XPS lub przeglądarki takiej jak Microsoft XPS Viewer. |
| Nieprawidłowy snapshot Base64 | Uszkodzone dane DEVMODE | Wygeneruj ponownie snapshot z sterownika drukarki przy użyciu API `GetPrinter`. |
| Brak uprawnień | Brak dostępu do zapisu w `dir` | Upewnij się, że aplikacja działa z wystarczającymi prawami systemu plików. |

## Najczęściej zadawane pytania

**P: Czy mogę używać Aspose.Page dla .NET z innymi frameworkami .NET?**  
O: Tak, Aspose.Page działa z .NET Framework, .NET Core, .NET 5/6 i nowszymi.

**P: Jak mogę uzyskać tymczasową licencję dla Aspose.Page?**  
O: Odwiedź [ten link](https://purchase.aspose.com/temporary-license/), aby uzyskać tymczasową licencję dla Aspose.Page.

**P: Czy istnieje forum społecznościowe wsparcia dla Aspose.Page?**  
O: Oczywiście, pomocne dyskusje i wsparcie znajdziesz na [forum Aspose.Page](https://forum.aspose.com/c/page/39).

**P: Jakie typy nośników są obsługiwane w niestandardowych biletach drukowania?**  
O: Aspose.Page obsługuje różne typy nośników, w tym zwykły papier, błyskawiczny oraz własne definicje mediów.

**P: Czy dostępne są przykładowe projekty dla Aspose.Page dla .NET?**  
O: Przeglądaj [dokumentację](https://reference.aspose.com/page/net/) w poszukiwaniu przykładów projektów i fragmentów kodu, które pomogą Ci rozpocząć.

## Zakończenie

Omówiliśmy **jak dodać bilet** do dokumentu XPS przy użyciu Aspose.Page dla .NET. Postępując zgodnie z tymi krokami, możesz osadzić bogate instrukcje drukowania bezpośrednio w swoich plikach, uzyskując pełną kontrolę nad przepływem drukowania z poziomu aplikacji .NET. Zachęcamy do eksperymentowania z dodatkowymi ustawieniami biletu, aby dopasować je do konkretnego środowiska drukowania.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-03-19  
**Testowano z:** Aspose.Page dla .NET (najnowsza stabilna wersja)  
**Autor:** Aspose  

---