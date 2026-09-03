---
date: 2026-05-25
description: Dowiedz się, jak modyfikować xmp w dokumentach EPS przy użyciu Java i
  Aspose.Page. Aktualizuj metadane szybko i niezawodnie.
keywords:
- how to modify xmp
- Aspose.Page Java
- XMP metadata EPS
linktitle: Zmienianie wartości w XMP przy użyciu Java
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to modify xmp in EPS documents using Java with Aspose.Page.
    Update metadata quickly and reliably.
  headline: how to modify xmp with Aspose.Page – Change Values in XMP using Java
  type: TechArticle
- questions:
  - answer: Utilize `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` to ensure consistency
      in time zone settings.
    question: How can I handle time zone considerations when modifying XMP values?
  - answer: Yes, by using the `put` method for each desired value, you can modify
      multiple XMP values concurrently.
    question: Can I change multiple XMP values in a single operation?
  - answer: Explore the comprehensive documentation [here](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation for Aspose.Page for Java?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: Jak modyfikować xmp za pomocą Aspose.Page – Zmienianie wartości w XMP przy
  użyciu Java
url: /pl/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zmienianie wartości w XMP przy użyciu Javy

## Wprowadzenie
Jeśli szukasz **how to modify xmp** wewnątrz pliku EPS przy użyciu Javy, trafiłeś we właściwe miejsce. Ten samouczek przeprowadzi Cię przez każdy krok — od odczytania istniejącego bloku XMP, aktualizacji pól takich jak twórca, tytuł i data modyfikacji, aż po zapisanie zmian z powrotem do dokumentu EPS. Na końcu będziesz mieć ponownie używalny fragment kodu, który pasuje do każdego zautomatyzowanego przepływu pracy, zapewniając, że Twoje pliki zawierają prawidłowe metadane pod kątem marki, zgodności lub indeksowania przez wyszukiwarki.

## Szybkie odpowiedzi
- **Co robi „aspose.page modify xmp”?** Umożliwia odczyt i zapis metadanych XMP w plikach EPS za pośrednictwem API Aspose.Page Java.  
- **Jakiej wersji biblioteki wymaga?** Dowolna najnowsza wersja Aspose.Page dla Javy (API jest stabilne w różnych wersjach).  
- **Czy potrzebna jest licencja do uruchomienia przykładu?** Darmowa wersja próbna wystarczy do oceny; licencja komercyjna jest wymagana w środowisku produkcyjnym.  
- **Czy mogę zmienić wiele pól XMP jednocześnie?** Tak — wywołaj `put` dla każdego pola przed zapisaniem dokumentu.  
- **Czy potrzebne jest obsłużenie strefy czasowej?** Ustawienie domyślnej strefy czasowej (np. UTC) zapewnia spójne wartości dat.

## Czym jest XMP i dlaczego go modyfikować?
XMP (Extensible Metadata Platform) to ustandaryzowany, oparty na XML format umożliwiający osadzanie bogatych metadanych bezpośrednio w plikach, takich jak EPS, PDF i obrazy. Aktualizacja XMP pozwala kontrolować, jak dokumenty są indeksowane, wyświetlane i wyszukiwane — co jest kluczowe dla spójności marki, zgodności regulacyjnej oraz zautomatyzowanych pipeline’ów treści.

## Dlaczego używać Aspose.Page dla Javy?
Aspose.Page oferuje **pełnofunkcyjne, czysto‑Java API**, które eliminuje potrzebę zewnętrznych narzędzi lub bibliotek natywnych. Obsługuje **ponad 50 formatów wejścia i wyjścia** i może przetwarzać pliki EPS do **500 MB** bez ładowania całego dokumentu do pamięci, zapewniając szybkie, niskopamięciowe manipulowanie metadanymi na dowolnym systemie operacyjnym z Javą.

## Wymagania wstępne
Zanim rozpoczniesz ten samouczek, upewnij się, że spełniasz następujące wymagania:
1. **Środowisko programistyczne Java** – JDK (8 lub nowszy) oraz IDE lub narzędzie budujące według własnego wyboru.  
2. **Biblioteka Aspose.Page dla Javy** – Pobierz i zainstaluj bibliotekę Aspose.Page dla Javy. Niepotrzebny pakiet znajdziesz [tutaj](https://releases.aspose.com/page/java/).

## Importowanie pakietów
Rozpocznij od zaimportowania wymaganych pakietów do swojego projektu Java. Pakiety te są niezbędne do interakcji i manipulacji dokumentami EPS.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Jak modyfikować XMP w EPS przy użyciu Javy?
`Document` jest klasą Aspose.Page reprezentującą plik EPS i zapewnia dostęp do jego zawartości oraz metadanych. `XmpMetadata` reprezentuje blok XMP dołączony do dokumentu i umożliwia odczyt oraz zapis pól metadanych. `put` dodaje lub aktualizuje wpis w obiekcie XmpMetadata. `save` zapisuje zmodyfikowany dokument, w tym zaktualizowane metadane XMP, do pliku.

Załaduj plik EPS przy pomocy `new Document("input.eps")`, pobierz jego obiekt `XmpMetadata`, zaktualizuj pożądane klucze przy użyciu `put`, a na końcu wywołaj `save`, aby zapisać zmiany do nowego pliku. Ten zwięzły przepływ automatycznie obsługuje brakujące bloki XMP, tworzy je z komentarzy PostScript w razie potrzeby i zapewnia daty niezależne od strefy czasowej.

## Krok 1: Pobierz metadane XMP
Klasa `XmpMetadata` reprezentuje blok XMP dołączony do dokumentu EPS. Gdy wywołujesz `document.getXmpMetadata()`, API zwraca istniejący blok lub tworzy nowy na podstawie komentarzy PS, takich jak `%%Creator`, `%%CreateDate` i `%%Title`.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## Krok 2: Zmień wartość „ModifyDate”
Zaktualizuj wpis `"ModifyDate"`, aby odzwierciedlał nowy znacznik czasu modyfikacji. Użyj `java.util.Date` w połączeniu z `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))`, aby zagwarantować, że przechowywana wartość jest niezależna od strefy czasowej.

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## Krok 3: Zmień wartość „Creator”
Klucz `"Creator"` przechowuje nazwę aplikacji lub osoby, która wygenerowała plik EPS. Wywołaj `xmp.put("dc:creator", "Your Company Name")`, aby zastąpić istniejącą wartość własnym identyfikatorem.

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## Krok 4: Zmień wartość „Title”
Pole `"Title"` jest wyświetlane przez wiele systemów zarządzania zasobami. Ustawienie go za pomocą `xmp.put("dc:title", "New Document Title")` zapewnia prawidłowe wyświetlanie dokumentu w katalogach i wynikach wyszukiwania.

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## Krok 5: Zapisz dokument ze zmienionymi metadanymi XMP
Po wprowadzeniu wszystkich modyfikacji wywołaj `document.save("output.eps")`. Biblioteka zapisuje zaktualizowany blok XMP z powrotem do strumienia EPS, zachowując niezmienioną oryginalną zawartość graficzną.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Typowe problemy i rozwiązania
- **Brak bloku XMP** – API automatycznie tworzy go z komentarzy PS, ale w razie potrzeby możesz ręcznie zainicjować `XmpMetadata`.  
- **Niezgodności stref czasowych** – Zawsze ustaw `TimeZone.setDefault` przed utworzeniem obiektu `Date`, aby uniknąć nieoczekiwanych przesunięć.  
- **Błędy dostępu do plików** – Upewnij się, że ścieżki wejścia i wyjścia są poprawne oraz że aplikacja ma uprawnienia do odczytu i zapisu.

## Najczęściej zadawane pytania

**Q: Jak radzić sobie z kwestiami strefy czasowej przy modyfikacji wartości XMP?**  
A: Użyj `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))`, aby zapewnić spójność ustawień strefy czasowej.

**Q: Czy mogę zmienić wiele wartości XMP w jednej operacji?**  
A: Tak, używając metody `put` dla każdego żądanego pola, możesz jednocześnie modyfikować wiele wartości XMP.

**Q: Gdzie znajdę dodatkową dokumentację dla Aspose.Page dla Javy?**  
A: Zapoznaj się z obszerną dokumentacją [tutaj](https://reference.aspose.com/page/java/).

**Q: Czy dostępna jest darmowa wersja próbna Aspose.Page dla Javy?**  
A: Tak, darmową wersję próbną znajdziesz [tutaj](https://releases.aspose.com/).

**Q: Jak mogę uzyskać tymczasową licencję dla Aspose.Page dla Javy?**  
A: Tymczasową licencję uzyskasz [tutaj](https://purchase.aspose.com/temporary-license/).

**Q: Czy modyfikacja XMP wpływa na wizualną zawartość EPS?**  
A: Nie. Zmiany w XMP dotyczą wyłącznie metadanych i nie modyfikują elementów graficznych pliku EPS.

**Q: Czy mogę programowo odczytać zaktualizowane wartości w celu weryfikacji zmiany?**  
A: Oczywiście — po zapisaniu i przed zamknięciem dokumentu wywołaj `xmp.get("dc:creator")` (lub odpowiedni klucz), aby sprawdzić zmienioną wartość.

## Podsumowanie
Gratulacje! Opanowałeś **how to modify xmp** w dokumentach EPS przy użyciu Aspose.Page dla Javy. Dzięki osadzeniu dokładnych metadanych twórcy, tytułu i daty modyfikacji zapewniasz, że Twoje zasoby są wyszukiwalne, zgodne i zgodne ze standardami marki. Śmiało włącz ten wzorzec do przetwarzania wsadowego, kroków CI/CD lub dowolnego zautomatyzowanego procesu generowania dokumentów.

---

**Last Updated:** 2026-05-25  
**Tested With:** Aspose.Page for Java (latest release)  
**Author:** Aspose

## Powiązane samouczki

- [Samouczek Aspose Page Java – Dodawanie metadanych XMP do plików EPS](/page/java/xmp-metadata-manipulation/add-metadata/)
- [Jak odczytać metadane XMP przy użyciu Javy – przewodnik Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page xmp java - Zmiana elementów tablicy w XMP przy użyciu Javy](/page/java/xmp-metadata-manipulation/change-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}