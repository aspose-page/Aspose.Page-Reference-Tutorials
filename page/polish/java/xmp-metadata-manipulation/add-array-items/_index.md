---
date: 2026-03-05
description: Dowiedz się, jak dodać elementy tablicy dc:title w metadanych XMP plików EPS
  przy użyciu Aspose.Page dla Javy. Postępuj zgodnie z tym przewodnikiem krok po kroku,
  aby uzyskać szybkie rezultaty.
linktitle: How to Add dc:title Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Jak dodać elementy tablicy dc:title w metadanych XMP przy użyciu Javy
url: /pl/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodawanie elementów tablicy w metadanych XMP przy użyciu Javy

## Wprowadzenie
W tym samouczku dowiesz się **jak dodać dc:title** (oraz inne elementy tablicy) do metadanych XMP wewnątrz pliku EPS przy użyciu Aspose.Page for Java. Aktualizacja metadanych XMP jest przydatna, gdy trzeba osadzić informacje możliwe do wyszukiwania — takie jak tytuły, twórcy lub słowa kluczowe — bezpośrednio w plikach graficznych. Przejdziemy przez każdy krok, wyjaśnimy, dlaczego każda linia ma znaczenie, i pokażemy, jak zweryfikować zmiany.

## Szybkie odpowiedzi
- **Co oznacza „dc:title”?** To właściwość tytułu Dublin Core przechowywana jako tablica XMP.  
- **Dlaczego modyfikować metadane XMP?** Umożliwia lepsze zarządzanie zasobami, możliwość wyszukiwania i zgodność ze standardami.  
- **Czy potrzebny jest istniejący blok XMP?** Nie — Aspose.Page wygeneruje go z komentarzy PS, jeśli go brakuje.  
- **Jaka wersja biblioteki jest wymagana?** Dowolna aktualna wersja Aspose.Page for Java (testowane z najnowszą wersją 2026).  
- **Czy mogę dodać inne właściwości tablicowe?** Tak — użyj tej samej metody `addArrayItem` dla właściwości takich jak `dc:creator`.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz:

- Zainstalowaną bibliotekę Aspose.Page for Java (dodaj plik JAR do classpath projektu).  
- Podstawowe doświadczenie w programowaniu w Javie (zalecany JDK 8+).  
- Plik EPS, który już zawiera metadane XMP lub przynajmniej komentarze metadanych PS (np. `%%Title`, `%%Creator`).  

## Importowanie pakietów
Na początek zaimportuj klasy niezbędne do odczytu, manipulacji i zapisu plików EPS:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Krok 1: Załaduj dokument EPS i pobierz metadane XMP
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

Tutaj otwieramy plik EPS i prosimy Aspose.Page o jego blok XMP. Jeśli plik nie zawiera XMP, biblioteka automatycznie tworzy go, wykorzystując istniejące komentarze PS, zapewniając, że zawsze masz kontener metadanych do pracy.

## Krok 2: Dodaj nowy element tablicy **dc:title**
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```

Ten wiersz pokazuje **jak dodać dc:title**. Zastąp `"NewTitle"` rzeczywistym tytułem, który chcesz osadzić. Metoda dołącza wartość do istniejącej tablicy tytułów, zachowując poprzednie tytuły.

## Krok 3: Dodaj nowy element tablicy **dc:creator**
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```

Podobnie możesz wzbogacić właściwość `dc:creator`. Można przechowywać wielu twórców; każde wywołanie dodaje kolejny wpis.

## Krok 4: Przygotuj strumień wyjściowy
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

Tworzymy strumień dla zmodyfikowanego pliku EPS. Użycie innej nazwy pliku (`xmp3_changed.eps`) pozostawia oryginalny plik nienaruszony.

## Krok 5: Zapisz dokument z zaktualizowanymi metadanymi XMP
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

Wywołanie `save` zapisuje dane EPS wraz z zaktualizowanym blokiem XMP. Blok `finally` zapewnia zwolnienie uchwytu pliku, nawet jeśli wystąpi wyjątek.

## Dlaczego to ma znaczenie
Osadzenie dokładnych wartości `dc:title` i `dc:creator` poprawia:

- **Możliwość wyszukiwania** w systemach zarządzania zasobami cyfrowymi (DAM).  
- **Zgodność** ze standardami publikacji wymagającymi metadanych.  
- **Współpracę**, ponieważ członkowie zespołu mogą szybko zidentyfikować zawartość pliku bez otwierania EPS.

## Typowe pułapki i wskazówki
- **Pułapka:** Nieumyślne nadpisywanie istniejących elementów tablicy.  
  **Wskazówka:** Użyj `xmp.getArrayItems("dc:title")`, aby sprawdzić bieżące wartości przed dodaniem nowych.  
- **Pułapka:** Zapominanie o zamknięciu strumieni, co prowadzi do blokad plików.  
  **Wskazówka:** Zawsze otaczaj operacje I/O blokiem try‑with‑resources lub `finally`, jak pokazano.  
- **Wskazówka:** Możesz łańcuchowo wywoływać wiele metod `addArrayItem`, aby dodać kilka tytułów lub twórców w jednym przebiegu.

## Najczęściej zadawane pytania

### Czy mogę używać Aspose.Page for Java z innymi formatami dokumentów?
Tak, Aspose.Page obsługuje różne formaty dokumentów, w tym EPS, PDF i XPS.

### Czy dostępna jest darmowa wersja próbna Aspose.Page for Java?
Tak, darmową wersję próbną można uzyskać [tutaj](https://releases.aspose.com/).

### Gdzie mogę znaleźć dokumentację Aspose.Page for Java?
Dokumentacja jest dostępna [tutaj](https://reference.aspose.com/page/java/).

### Jak mogę kupić Aspose.Page for Java?
Produkt można kupić [tutaj](https://purchase.aspose.com/buy).

### Czy dostępne są tymczasowe licencje dla Aspose.Page for Java?
Tak, tymczasową licencję można uzyskać [tutaj](https://purchase.aspose.com/temporary-license/).

---

**Ostatnia aktualizacja:** 2026-03-05  
**Testowano z:** Aspose.Page for Java (najnowsze wydanie 2026)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}