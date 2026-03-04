---
date: 2025-12-21
description: Dowiedz się, jak Aspose.Page modyfikuje XMP w dokumentach EPS przy użyciu
  Javy. Szybko ulepsz metadane dzięki Aspose.Page dla Javy.
linktitle: Change Values in XMP using Java
second_title: Aspose.Page Java API
title: aspose.page modyfikuj XMP – Zmieniaj wartości w XMP przy użyciu Javy
url: /pl/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zmienianie wartości w XMP przy użyciu Javy

## Wprowadzenie
Jeśli potrzebujesz **aspose.page modify xmp** danych wewnątrz pliku EPS, trafiłeś we właściwe miejsce. W tym samouczku przeprowadzimy Cię krok po kroku przez dokładne czynności potrzebne do odczytania, zaktualizowania i zapisania wartości XMP (Extensible Metadata Platform) przy użyciu biblioteki Aspose.Page dla Javy. Po zakończeniu będziesz mógł dostosować metadane dokumentu — takie jak twórca, tytuł i data modyfikacji — do wymagań Twojego projektu.

## Szybkie odpowiedzi
- **Co robi “aspose.page modify xmp”?** Umożliwia odczyt i zapis metadanych XMP w plikach EPS za pośrednictwem API Aspose.Page dla Javy.  
- **Jakiej wersji biblioteki potrzebuję?** Dowolna aktualna wersja Aspose.Page dla Javy (API jest stabilne w różnych wersjach).  
- **Czy potrzebna jest licencja do uruchomienia przykładu?** Darmowa wersja próbna wystarczy do oceny; licencja komercyjna jest wymagana w środowisku produkcyjnym.  
- **Czy mogę zmienić wiele pól XMP jednocześnie?** Tak — wywołaj `put` dla każdego pola przed zapisaniem dokumentu.  
- **Czy potrzebna jest obsługa strefy czasowej?** Ustawienie domyślnej strefy czasowej (np. UTC) zapewnia spójność wartości dat.

## Co to jest XMP i dlaczego je modyfikować?
XMP (Extensible Metadata Platform) to ustandaryzowany sposób osadzania bogatych metadanych bezpośrednio w plikach takich jak EPS, PDF i obrazy. Aktualizacja XMP pozwala kontrolować sposób indeksowania, wyświetlania i wyszukiwania dokumentów — co jest kluczowe dla marki, zgodności i automatyzacji przepływów pracy.

## Dlaczego warto używać Aspose.Page dla Javy?
- **Pełnoprawne API** – nie ma potrzeby korzystania z zewnętrznych narzędzi; wszystko odbywa się w‑process.  
- **Wieloplatformowość** – działa na każdym systemie operacyjnym obsługującym Javę.  
- **Brak zależności natywnych** – czysta implementacja w Javie upraszcza wdrażanie.  
- **Solidne wsparcie** – obsługuje zarówno istniejące bloki XMP, jak i tworzy nowe z komentarzy PS, gdy ich brak.

## Wymagania wstępne
Zanim rozpoczniesz ten samouczek, upewnij się, że spełniasz następujące wymagania:
1. **Środowisko programistyczne Javy** – JDK (8 lub nowszy) oraz wybrane IDE lub narzędzie budujące.  
2. **Biblioteka Aspose.Page dla Javy** – Pobierz i zainstaluj bibliotekę Aspose.Page dla Javy. Potrzebny pakiet znajdziesz [tutaj](https://releases.aspose.com/page/java/).

## Importowanie pakietów
Rozpocznij od zaimportowania niezbędnych pakietów do projektu Javy. Pakiety te są kluczowe do interakcji i manipulacji dokumentami EPS.

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

## Krok 1: Pobranie metadanych XMP
Odczytaj metadane XMP z dokumentu EPS. Jeśli plik EPS nie zawiera metadanych XMP, zostanie utworzony nowy zestaw wartości na podstawie komentarzy PS, takich jak %%Creator, %%CreateDate i %%Title.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## Krok 2: Zmiana wartości „ModifyDate”
Zmień wartość „ModifyDate” w metadanych XMP, aby odzwierciedlała żądaną datę.

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## Krok 3: Zmiana wartości „Creator”
Zaktualizuj wartość „Creator” w metadanych XMP, aby określić twórcę dokumentu.

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## Krok 4: Zmiana wartości „Title”
Zmodyfikuj wartość „Title” w metadanych XMP, aby ustawić odpowiedni tytuł dokumentu.

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## Krok 5: Zapis dokumentu z zmienionymi metadanymi XMP
Zapisz dokument z zaktualizowanymi metadanymi XMP do nowego pliku EPS.

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
- **Błędy dostępu do plików** – Upewnij się, że ścieżki wejściowe i wyjściowe są poprawne oraz że aplikacja ma odpowiednie uprawnienia odczytu/zapisu.

## Najczęściej zadawane pytania

**P: Jak radzić sobie ze strefą czasową przy modyfikacji wartości XMP?**  
O: Użyj `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))`, aby zapewnić spójność ustawień strefy czasowej.

**P: Czy mogę zmienić wiele wartości XMP w jednej operacji?**  
O: Tak, wywołując metodę `put` dla każdej żądanej wartości, możesz jednocześnie modyfikować wiele pól XMP.

**P: Gdzie znajdę dodatkową dokumentację dla Aspose.Page dla Javy?**  
O: Zapoznaj się z obszerną dokumentacją [tutaj](https://reference.aspose.com/page/java/).

**P: Czy dostępna jest darmowa wersja próbna Aspose.Page dla Javy?**  
O: Tak, darmową wersję próbną znajdziesz [tutaj](https://releases.aspose.com/).

**P: Jak uzyskać tymczasową licencję dla Aspose.Page dla Javy?**  
O: Tymczasową licencję można pobrać [tutaj](https://purchase.aspose.com/temporary-license/).

**P: Czy modyfikacja XMP wpływa na zawartość wizualną EPS?**  
O: Nie. Zmiany w XMP dotyczą wyłącznie metadanych i nie modyfikują elementów graficznych pliku EPS.

**P: Czy mogę programowo odczytać zaktualizowane wartości w celu weryfikacji zmiany?**  
O: Oczywiście — po zapisaniu i przed zamknięciem dokumentu wywołaj `xmp.get("dc:creator")` (lub odpowiedni klucz).

## Zakończenie
Gratulacje! Pomyślnie przeprowadziłeś **aspose.page modify xmp** wartości w dokumentach EPS przy użyciu Aspose.Page dla Javy. Ten samouczek wyposażył Cię w wiedzę niezbędną do modyfikacji metadanych, zapewniając, że Twoje dokumenty będą zgodne z konkretnymi wymaganiami w sposób płynny.

---

**Ostatnia aktualizacja:** 2025-12-21  
**Testowano z:** Aspose.Page for Java (najnowsze wydanie)  
**Autor:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
