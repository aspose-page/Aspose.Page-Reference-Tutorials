---
date: 2026-02-18
description: Dowiedz się, jak ustawić kolor farby i utworzyć elipsę PostScript w Javie
  przy użyciu Aspose.Page. Ten przewodnik pokazuje, jak wypełnić elipsę w Javie, narysować
  obrys elipsy i ustawić grubość linii.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Ustaw kolor malowania, aby narysować elipsę PostScript w Javie
url: /pl/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw kolor farby, aby narysować elipsę PostScript w Javie

## Wprowadzenie
Jeśli potrzebujesz **ustawić kolor farby** podczas rysowania grafiki wektorowej, biblioteka Aspose.Page for Java daje pełną kontrolę nad każdym pociągnięciem i wypełnieniem. W tym samouczku dowiesz się, jak **ustawić kolor farby**, **wypełnić elipsę w Javie** i **narysować kontur elipsy** używając prostego, krok po kroku podejścia. Po zakończeniu będziesz mógł dodawać wysokiej jakości elipsy PostScript do faktur, raportów lub dowolnego dokumentu do druku.

## Szybkie odpowiedzi
- **Jaka biblioteka jest najlepsza do rysowania grafiki PostScript w Javie?** Aspose.Page for Java.  
- **Czy mogę wypełnić elipsę jednolitym kolorem?** Tak – użyj `document.setPaint(Color.YOUR_COLOR)` przed `fill`.  
- **Jak narysować tylko kontur elipsy?** Ustaw farbę i pędzel, a następnie wywołaj `document.draw(...)`.  
- **Czy potrzebna jest licencja do użytku produkcyjnego?** Wymagana jest licencja komercyjna; tymczasowa licencja jest dostępna do testów.  
- **Jaką wersję Javy obsługuje?** Każde środowisko uruchomieniowe Java 8+ działa z bieżącą wersją Aspose.Page.

## Czym jest elipsa PostScript?
Elipsa PostScript to kształt wektorowy definiowany przez prostokąt ograniczający. W przeciwieństwie do obrazów rastrowych, skaluje się bez utraty jakości, co czyni ją idealną do druku wysokiej rozdzielczości i konwersji do PDF.

## Dlaczego używać Aspose.Page do tworzenia elipsy PostScript?
- **Pełna kontrola** nad prymitywami rysowania (linia, krzywe, elipsy).  
- **Wieloplatformowość** – działa na Windows, Linux i macOS.  
- **Brak zewnętrznych zależności** – czyste API Java, bez kodu natywnego.  
- **Łatwa integracja** z istniejącymi aplikacjami Java i narzędziami budowania.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

1. Działające środowisko programistyczne Java (JDK 8 lub nowszy).  
2. Bibliotekę Aspose.Page for Java dodaną do projektu. Możesz ją pobrać **[tutaj](https://releases.aspose.com/page/java/)**.  

## Importowanie pakietów
W swoim pliku źródłowym Java zaimportuj klasy wymagane do rysowania i zapisywania treści PostScript.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Jak ustawić kolor farby dla elipsy
Ustawienie koloru farby jest pierwszym krokiem przed każdą operacją wypełniania lub obrysu. Metoda `setPaint` określa kolor, który zostanie użyty w następnym poleceniu rysowania.

### Krok 1: Przygotowanie dokumentu PostScript
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

### Krok 2: Jak wypełnić elipsę – użyj ustawienia koloru farby
Aby **wypełnić elipsę**, najpierw wywołaj `setPaint` z żądanym kolorem wypełnienia, a następnie wywołaj `fill` z instancją `Ellipse2D`.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Krok 3: Narysuj kontur elipsy i ustaw grubość pędzla
Po wypełnieniu możesz zmienić farbę na inny kolor, zdefiniować `BasicStroke` kontrolujący szerokość linii i narysować kontur elipsy.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Krok 4: Zamknij i zapisz dokument
Zakończ stronę i zapisz plik PostScript na dysku.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Masz teraz plik PostScript zawierający dwie elipsy — jedną wypełnioną pomarańczowym, a drugą z konturem w czerwonym. Śmiało eksperymentuj z różnymi współrzędnymi, rozmiarami i kolorami, aby dopasować je do swoich potrzeb projektowych.

## Typowe pułapki i rozwiązywanie problemów
- **Nieprawidłowa ścieżka pliku** – Upewnij się, że `dataDir` kończy się separatorem (`/` lub `\\`) odpowiednim dla Twojego systemu operacyjnego.  
- **Brak licencji** – Bez ważnej licencji biblioteka działa w trybie ewaluacyjnym i może dodawać znaki wodne.  
- **Kolor nie zastosowany** – Pamiętaj, aby ustawić `document.setPaint(...)` *przed* każdym wywołaniem `fill` lub `draw`; ustawienie farby nie jest automatycznie zachowywane między oddzielnymi operacjami.

## Najczęściej zadawane pytania

**P: Czy mogę używać Aspose.Page for Java z innymi bibliotekami Java?**  
O: Tak, Aspose.Page for Java jest zaprojektowany tak, aby płynnie integrować się z innymi bibliotekami Java.

**P: Jak mogę uzyskać tymczasową licencję dla Aspose.Page for Java?**  
O: Uzyskaj tymczasową licencję **[tutaj](https://purchase.aspose.com/temporary-license/)** do celów testowych.

**P: Czy Aspose.Page jest odpowiedni dla projektów komercyjnych?**  
O: Zdecydowanie! Odwiedź **[tutaj](https://purchase.aspose.com/buy)**, aby zapoznać się z opcjami licencjonowania do użytku komercyjnego.

**P: Gdzie mogę uzyskać pomoc lub dyskutować o zapytaniach związanych z Aspose.Page?**  
O: Dołącz do społeczności na **[forum Aspose.Page](https://forum.aspose.com/c/page/39)**, aby uczestniczyć w dyskusjach i uzyskać pomoc.

**P: Czy istnieją darmowe zasoby, aby dowiedzieć się więcej o Aspose.Page for Java?**  
O: Skorzystaj z **[bezpłatnej wersji próbnej](https://releases.aspose.com/)** i przeglądaj przykłady w dokumentacji.

## Zakończenie
Aspose.Page for Java ułatwia **ustawienie koloru farby**, **wypełnienie elipsy** i **narysowanie konturu elipsy** — niezależnie od tego, czy potrzebujesz prostej wypełnionej figury, czy skomplikowanej grafiki z obrysem. Dzięki powyższym krokom szybko dodasz profesjonalne grafiki wektorowe do dowolnego dokumentu do druku. Aby zgłębić temat dalej — np. łączyć wiele kształtów, stosować gradienty lub konwertować do PDF — zapoznaj się z oficjalną **[dokumentacją](https://reference.aspose.com/page/java/)**.

---

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}