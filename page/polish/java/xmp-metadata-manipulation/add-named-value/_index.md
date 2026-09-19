---
date: 2026-09-19
description: Dowiedz się, jak dodać named values XMP do plików EPS przy użyciu Aspose.Page
  for Java – przewodnik krok po kroku z przykładami kodu.
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
- EPS XMP manipulation
- Java metadata API
lastmod: 2026-09-19
linktitle: Dodaj Named Value w XMP przy użyciu Javy
og_description: Jak dodać named values XMP do plików EPS przy użyciu Aspose.Page for
  Java. Skorzystaj z tego zwięzłego przewodnika, aby w ciągu kilku minut wstrzyknąć
  niestandardowe metadata.
og_image_alt: Screenshot of Java code adding XMP named value to an EPS file with Aspose.Page
og_title: Jak dodać named value XMP w plikach EPS przy użyciu Javy
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  headline: How to add XMP named value in EPS files using Java
  type: TechArticle
- description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  name: How to add XMP named value in EPS files using Java
  steps:
  - name: Initialize input EPS file stream
    text: '**FileInputStream** is a Java I/O class that reads raw bytes from a file.
      Load the source EPS file into a `FileInputStream`. This stream feeds the document
      into Aspose’s API. > **Pro tip:** Keep the `dataDir` variable configurable so
      the same code works across environments.'
  - name: Obtain XMP metadata
    text: '**XmpMetadata** represents the XMP packet associated with an EPS document.
      Retrieve the existing XMP packet; if the EPS file lacks one, Aspose creates
      a fresh XMP object populated from the PS comments.'
  - name: Add named value
    text: '**NamedValue** is a key‑value pair stored within the XMP metadata namespace.
      Insert a custom named value into the XMP structure. In this example we add a
      new key under the `xmpTPg:MaxPageSize` namespace. > **Why this matters:** Named
      values let you store arbitrary key‑value pairs that downstream app'
  - name: Initialize output EPS file stream
    text: '**FileOutputStream** is a Java I/O class that writes raw bytes to a file.
      Prepare a `FileOutputStream` where the modified EPS will be saved.'
  - name: Save document
    text: The `save` method persists the changes. It writes the updated XMP packet
      back into the EPS file, guaranteeing that the new named value becomes part of
      the document’s metadata.
  - name: Close input EPS stream
    text: Closing the original file handle prevents resource leaks and ensures that
      the file is not locked for subsequent operations. By following these six steps,
      you have successfully **added a named value in XMP metadata** using **Aspose.Page
      for Java**.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly with other Java
      libraries, providing flexibility in your development environment.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can access a free trial of Aspose.Page for Java on the [Aspose
      releases page](https://releases.aspose.com/).
    question: Is a free trial available for Aspose.Page for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to obtain a temporary license for Aspose.Page for Java.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Explore the [documentation](https://reference.aspose.com/page/java/) for
      comprehensive tutorials and examples.
    question: Where can I find more tutorials and examples for Aspose.Page for Java?
  - answer: Absolutely, Aspose.Page for Java is designed to handle large‑scale projects
      efficiently, providing robust document manipulation capabilities.
    question: Is Aspose.Page for Java suitable for large‑scale projects?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- XMP metadata
- Aspose.Page
- Java EPS
- document automation
title: Jak dodać named value XMP w plikach EPS przy użyciu Javy
url: /pl/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj wartość nazwaną w metadanych XMP przy użyciu Javy

## Wprowadzenie
We współczesnym rozwoju Javy, nauka **jak dodać metadane XMP** do plików EPS jest niezbędna do zachowania pochodzenia dokumentu i poprawy możliwości wyszukiwania. Dzięki **Aspose.Page for Java** możesz bez wysiłku wstrzykiwać niestandardowe wartości nazwane do pakietu XMP. Ten samouczek przeprowadzi Cię przez dokładne kroki — wraz z fragmentami kodu — abyś mógł już dziś rozpocząć dodawanie metadanych XMP do swoich dokumentów EPS.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebujesz?** Aspose.Page for Java (Aspose)  
- **Jaki typ pliku jest celem?** Pliki EPS zawierające metadane XMP  
- **Główny przypadek użycia?** Dodawanie niestandardowych wartości nazwanych (np. limitów rozmiaru strony) do XMP  
- **Wymagania wstępne?** JDK 8+ oraz biblioteka Aspose.Page for Java  
- **Typowy czas implementacji?** 5–10 minut po skonfigurowaniu biblioteki  

## Co to jest asp?
**Aspose** jest skrótem od **Aspose**, zestawu interfejsów API umożliwiających programistom tworzenie, edytowanie, konwertowanie i renderowanie szerokiej gamy formatów dokumentów bez konieczności używania zewnętrznego oprogramowania. Komponent **Aspose.Page for Java** koncentruje się specjalnie na przetwarzaniu PostScript i EPS, zapewniając programowy dostęp do zawartości stron, grafiki i metadanych, takich jak XMP.

## Dlaczego dodawać wartości nazwane do metadanych XMP?
Wartości nazwane pozwalają przechowywać dowolne pary klucz‑wartość bezpośrednio w pakiecie XMP, czyniąc je natychmiast czytelnymi przez narzędzia downstream. Poprawia to przyjazność dla wyszukiwarek, umożliwia automatyzację przepływu pracy i spełnia wymogi zgodności, osadzając informacje regulacyjne bez zmiany treści wizualnej.

## Dlaczego to ma znaczenie
Dodawanie wartości nazwanych do XMP pozwala przechowywać dowolne pary klucz‑wartość, które można odczytać bez parsowania całego pliku EPS. Ta funkcja jest szczególnie cenna w zautomatyzowanych pipeline’ach publikacji, systemach zarządzania zasobami cyfrowymi oraz przepływach pracy opartych na zgodności, gdzie metadane sterują działaniami downstream.

## Wymagania wstępne
Before we dive in, ensure you have the following:

- **Java Development Kit (JDK):** Aktualny JDK (8 lub wyższy) zainstalowany na Twoim komputerze.  
- **Aspose.Page for Java Library:** Pobierz ją z oficjalnej [strony pobierania Aspose.Page for Java](https://releases.aspose.com/page/java/). Dodaj plik JAR do classpathu projektu.  
- **Plik EPS**, który już zawiera metadane XMP lub zostanie automatycznie wygenerowany.

## Importowanie pakietów
Rozpocznij od zaimportowania niezbędnych pakietów Java. Te importy zapewniają dostęp do strumieni plików, modelu dokumentu EPS oraz klas obsługujących XMP.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Jak dodać wartość nazwaną XMP w plikach EPS przy użyciu Javy
Aby dodać wartość nazwaną, wczytaj plik EPS przy użyciu `FileInputStream`, pobierz lub utwórz jego obiekt `XmpMetadata`, wstaw żądaną `NamedValue` do odpowiedniej przestrzeni nazw, a następnie zapisz zmodyfikowany dokument przy użyciu `FileOutputStream`. Aspose.Page automatycznie obsługuje tworzenie pakietu XMP, jeśli go brakuje, zapewniając prawidłowe osadzenie nowych metadanych.

### Krok 1: Zainicjalizuj strumień wejściowy pliku EPS
**FileInputStream** to klasa Java I/O odczytująca surowe bajty z pliku. Wczytaj źródłowy plik EPS do `FileInputStream`. Ten strumień przekazuje dokument do API Aspose.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **Wskazówka:** Utrzymuj zmienną `dataDir` konfigurowalną, aby ten sam kod działał w różnych środowiskach.

### Krok 2: Uzyskaj metadane XMP
**XmpMetadata** reprezentuje pakiet XMP powiązany z dokumentem EPS. Pobierz istniejący pakiet XMP; jeśli plik EPS go nie posiada, Aspose tworzy nowy obiekt XMP wypełniony danymi z komentarzy PS.

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### Krok 3: Dodaj wartość nazwaną
**NamedValue** to para klucz‑wartość przechowywana w przestrzeni nazw metadanych XMP. Wstaw niestandardową wartość nazwaną do struktury XMP. W tym przykładzie dodajemy nowy klucz w przestrzeni nazw `xmpTPg:MaxPageSize`.

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **Dlaczego to ważne:** Wartości nazwane pozwalają przechowywać dowolne pary klucz‑wartość, które aplikacje downstream mogą odczytać bez parsowania całego dokumentu.

### Krok 4: Zainicjalizuj strumień wyjściowy pliku EPS
**FileOutputStream** to klasa Java I/O zapisująca surowe bajty do pliku. Przygotuj `FileOutputStream`, w którym zostanie zapisany zmodyfikowany plik EPS.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### Krok 5: Zapisz dokument
Metoda `save` utrwala zmiany. Zapisuje zaktualizowany pakiet XMP z powrotem do pliku EPS, zapewniając, że nowa wartość nazwana stanie się częścią metadanych dokumentu.

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### Krok 6: Zamknij strumień wejściowy EPS
Zamknięcie oryginalnego uchwytu pliku zapobiega wyciekom zasobów i zapewnia, że plik nie jest zablokowany dla kolejnych operacji.

```java
psStream.close();
```

Postępując zgodnie z tymi sześcioma krokami, pomyślnie **dodałeś wartość nazwaną w metadanych XMP** przy użyciu **Aspose.Page for Java**.

## Częste problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| `NullPointerException` przy `xmp` | Plik EPS nie zawiera XMP, a Aspose nie udało się wygenerować | Upewnij się, że EPS zawiera co najmniej jeden komentarz PS lub ręcznie utwórz nową instancję `XmpMetadata`. |
| Plik wyjściowy jest pusty | Strumień wyjściowy nie został opróżniony/zamknięty | Sprawdź, czy `outPsStream.close()` jest wywoływane w bloku `finally` (jak pokazano). |
| Błąd duplikatu klucza | Ta sama wartość nazwana została dodana dwukrotnie | Sprawdź, czy klucz już istnieje przy pomocy `xmp.containsNamedValue(...)` przed dodaniem. |

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.Page for Java z innymi bibliotekami Java?**  
A: Tak, Aspose.Page for Java jest zaprojektowany tak, aby współpracować bezproblemowo z innymi bibliotekami Java, zapewniając elastyczność w Twoim środowisku programistycznym.

**Q: Czy dostępna jest bezpłatna wersja próbna Aspose.Page for Java?**  
A: Tak, możesz uzyskać dostęp do bezpłatnej wersji próbnej Aspose.Page for Java na [stronie wydań Aspose](https://releases.aspose.com/).

**Q: Jak mogę uzyskać tymczasową licencję na Aspose.Page for Java?**  
A: Odwiedź [stronę tymczasowej licencji](https://purchase.aspose.com/temporary-license/), aby uzyskać tymczasową licencję na Aspose.Page for Java.

**Q: Gdzie mogę znaleźć więcej samouczków i przykładów dla Aspose.Page for Java?**  
A: Przeglądaj [dokumentację](https://reference.aspose.com/page/java/) w celu uzyskania kompleksowych samouczków i przykładów.

**Q: Czy Aspose.Page for Java jest odpowiedni dla dużych projektów?**  
A: Zdecydowanie, Aspose.Page for Java jest zaprojektowany tak, aby efektywnie obsługiwać duże projekty, oferując solidne możliwości manipulacji dokumentami.

## Zakończenie
W tym przewodniku pokazaliśmy, jak **Aspose.Page for Java** ułatwia **dodawanie wartości nazwanych do metadanych XMP** w plikach EPS. Dzięki powyższym krokom możesz wzbogacić swoje dokumenty o niestandardowe metadane, poprawić ich wyszukiwalność i umożliwić inteligentniejsze przetwarzanie downstream.

---

**Last Updated:** 2026-09-19  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## Powiązane samouczki

- [Jak dodać przestrzeń nazw XMP w plikach EPS przy użyciu Aspose.Page – Samouczek Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Dodaj metadane XMP do plików EPS przy użyciu Javy](/page/java/xmp-metadata-manipulation/add-simple-properties/)
- [Odczytaj XMP przy użyciu Aspose.Page – Przewodnik Java](/page/java/xmp-metadata-manipulation/get-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}