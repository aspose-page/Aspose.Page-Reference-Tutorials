---
date: 2025-12-11
description: Dowiedz się, jak tworzyć elipsę w formacie PostScript w Javie przy użyciu
  Aspose.Page. Ten przewodnik krok po kroku pokazuje, jak wypełnić elipsę kolorem
  i narysować elipsę w Javie.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Jak utworzyć elipsę PostScript w Javie przy użyciu Aspose.Page
url: /pl/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak stworzyć elipsę PostScript w Javie przy użyciu Aspose.Page

## Wprowadzenie
Tworzenie **elipsy PostScript** programowo daje precyzyjną kontrolę nad grafiką wektorową w raportach, fakturach lub dowolnym dokumencie do druku. W tym samouczku nauczysz się, jak **tworzyć kształty elipsy PostScript** przy użyciu biblioteki Aspose.Page dla Javy, wypełniać elipsę kolorem oraz rysować jej kontur. Po zakończeniu będziesz gotów wstawiać własne grafiki bezpośrednio do wyjścia PostScript.

## Szybkie odpowiedzi
- **Jaka biblioteka jest najlepsza do rysowania grafiki PostScript w Javie?** Aspose.Page dla Javy.  
- **Czy mogę wypełnić elipsę jednolitym kolorem?** Tak – użyj `document.setPaint(Color.YOUR_COLOR)` przed wywołaniem `fill`.  
- **Jak narysować tylko kontur elipsy?** Ustaw farbę i pędzel, a następnie wywołaj `document.draw(...)`.  
- **Czy potrzebna jest licencja do użytku produkcyjnego?** Wymagana jest licencja komercyjna; tymczasowa licencja jest dostępna do testów.  
- **Jaką wersję Javy obsługuje biblioteka?** Działa z dowolnym środowiskiem Java 8+ w bieżącym wydaniu Aspose.Page.

## Czym jest elipsa PostScript?
Elipsa PostScript to kształt wektorowy definiowany przez prostokąt ograniczający. W przeciwieństwie do obrazów rastrowych, skaluje się bez utraty jakości, co czyni ją idealną do druku wysokiej rozdzielczości i konwersji do PDF.

## Dlaczego używać Aspose.Page do tworzenia elipsy PostScript?
- **Pełna kontrola** nad prymitywami rysowania (linie, krzywe, elipsy).  
- **Wieloplatformowość** – działa na Windows, Linux i macOS.  
- **Brak zewnętrznych zależności** – czyste API Java, bez kodu natywnego.  
- **Łatwa integracja** z istniejącymi aplikacjami Java i narzędziami budującymi.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

1. Działające środowisko programistyczne Java (JDK 8 lub nowszy).  
2. Bibliotekę Aspose.Page dla Javy dodaną do projektu. Możesz ją pobrać **[tutaj](https://releases.aspose.com/page/java/)**.  

## Importowanie pakietów
W swoim pliku źródłowym Java zaimportuj klasy niezbędne do rysowania i zapisywania treści PostScript.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Przewodnik krok po kroku

### Krok 1: Konfiguracja dokumentu PostScript
Utwórz strumień wyjściowy, skonfiguruj rozmiar strony i zainicjuj `PsDocument`.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Krok 2: Wypełnienie elipsy kolorem
Ustaw farbę na żądany kolor wypełnienia i wywołaj `fill` z instancją `Ellipse2D`.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Krok 3: Kontur elipsy
Zmień farbę na kolor linii, zdefiniuj `BasicStroke` określający grubość linii i narysuj kontur elipsy.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Krok 4: Zamknięcie i zapisanie dokumentu
Zakończ stronę i zapisz plik PostScript na dysku.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Masz teraz plik PostScript zawierający dwie elipsy — jedną wypełnioną pomarańczowym, a drugą z konturem w czerwonym. Śmiało eksperymentuj z różnymi współrzędnymi, rozmiarami i kolorami, aby dopasować je do swoich potrzeb projektowych.

## Typowe problemy i rozwiązywanie
- **Nieprawidłowa ścieżka pliku** – Upewnij się, że `dataDir` kończy się separatorem (`/` lub `\\`) odpowiednim dla Twojego systemu operacyjnego.  
- **Brak licencji** – Bez ważnej licencji biblioteka działa w trybie ewaluacyjnym i może dodawać znaki wodne.  
- **Kolor nie został zastosowany** – Pamiętaj, aby ustawić `document.setPaint(...)` *przed* każdym wywołaniem `fill` lub `draw`; ustawienie farby nie jest zachowywane automatycznie między oddzielnymi operacjami.

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.Page dla Javy razem z innymi bibliotekami Java?**  
A: Tak, Aspose.Page dla Javy jest zaprojektowane tak, aby bezproblemowo integrować się z innymi bibliotekami Java.

**Q: Jak mogę uzyskać tymczasową licencję dla Aspose.Page dla Javy?**  
A: Uzyskaj tymczasową licencję **[tutaj](https://purchase.aspose.com/temporary-license/)** do celów testowych.

**Q: Czy Aspose.Page nadaje się do projektów komercyjnych?**  
A: Zdecydowanie! Odwiedź **[tutaj](https://purchase.aspose.com/buy)**, aby zapoznać się z opcjami licencjonowania dla użytku komercyjnego.

**Q: Gdzie mogę szukać pomocy lub dyskutować o zagadnieniach związanych z Aspose.Page?**  
A: Dołącz do społeczności na **[forum Aspose.Page](https://forum.aspose.com/c/page/39)**, gdzie prowadzona jest dyskusja i udzielane są wsparcie.

**Q: Czy są dostępne darmowe zasoby, aby dowiedzieć się więcej o Aspose.Page dla Javy?**  
A: Skorzystaj z **[bezpłatnej wersji próbnej](https://releases.aspose.com/)** i przeglądaj przykłady w dokumentacji.

## Podsumowanie
Aspose.Page dla Javy umożliwia łatwe **tworzenie grafiki elipsy PostScript**, niezależnie od tego, czy potrzebujesz prostego wypełnionego kształtu, czy skomplikowanego konturu. Dzięki powyższym krokom szybko dodasz profesjonalne grafiki wektorowe do dowolnego dokumentu do druku. Aby zgłębić temat – np. łączyć wiele kształtów, stosować gradienty lub konwertować do PDF – zajrzyj do oficjalnej **[dokumentacji](https://reference.aspose.com/page/java/)**.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose