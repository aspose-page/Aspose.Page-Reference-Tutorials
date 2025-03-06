---
title: Dostosuj Java PostScript - Dodawanie prostokątów za pomocą Aspose.Page
linktitle: Dodaj prostokąt w Java PostScript
second_title: Aspose.Page API Java
description: Zapoznaj się z przewodnikiem krok po kroku dotyczącym dodawania żywych prostokątów do dokumentów Java PostScript przy użyciu Aspose.Page dla Java. Zwiększ możliwości dostosowywania dokumentów bez wysiłku!
weight: 11
url: /pl/java/postscript-shapes/add-rectangle/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dostosuj Java PostScript - Dodawanie prostokątów za pomocą Aspose.Page

## Wstęp
Czy chcesz wzbogacić swoje dokumenty Java PostScript o żywe prostokąty? Nie szukaj dalej! W tym przewodniku krok po kroku odkryjemy, jak używać Aspose.Page dla Java do dodawania prostokątów do dokumentów PostScript. Aspose.Page to potężna biblioteka zapewniająca niezawodne funkcje do pracy z plikami PostScript, co czyni ją idealnym wyborem dla programistów chcących manipulować i dostosowywać swoje dokumenty.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Podstawowa znajomość programowania w języku Java.
-  Zainstalowana biblioteka Aspose.Page dla Java. Jeśli nie, pobierz go z[Aspose.Page dla dokumentacji Java](https://reference.aspose.com/page/java/).
- Środowisko programistyczne Java skonfigurowane na Twoim komputerze.
## Importuj pakiety
W swoim projekcie Java zacznij od zaimportowania niezbędnych pakietów:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Samouczek: Dodawanie prostokątów w Java PostScript
## Krok 1: Ustaw farbę do wypełnienia prostokąta
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz strumień wyjściowy dla dokumentu PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Twórz opcje zapisywania w formacie A4
PsSaveOptions options = new PsSaveOptions();
// Utwórz nowy dokument PS z otwartą stroną
PsDocument document = new PsDocument(outPsStream, options, false);
// Ustaw farbę do wypełnienia prostokąta
document.setPaint(Color.ORANGE);        
// Wypełnij pierwszy prostokąt
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```
## Krok 2: Ustaw farbę do obrysowywania prostokąta
```java
// Ustaw farbę do obrysowania prostokąta
document.setPaint(Color.RED);
// Ustaw skok
document.setStroke(new BasicStroke(3));
// Obrysuj (obrysuj) drugi prostokąt
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```
## Krok 3: Zamknij bieżącą stronę i zapisz dokument
```java
// Zamknij bieżącą stronę
document.closePage();
// Zapisz dokument
document.save();
```
Gratulacje! Pomyślnie dodałeś żywe prostokąty do dokumentu Java PostScript za pomocą Aspose.Page.
## Wniosek
W tym samouczku zbadaliśmy proces ulepszania dokumentów Java PostScript za pomocą prostokątów przy użyciu Aspose.Page dla Java. Ta potężna biblioteka otwiera świat możliwości dla programistów, którzy chcą bez wysiłku dostosowywać swoje dokumenty i manipulować nimi.
Baw się dobrze, eksperymentując z różnymi kształtami i kolorami, aby Twoje dokumenty były atrakcyjne wizualnie!
## Często Zadawane Pytania

### Czy mogę używać Aspose.Page dla Java z innymi językami programowania?
Aspose.Page obsługuje przede wszystkim Javę, ale podobne biblioteki są dostępne dla innych języków.
### Czy dostępna jest wersja próbna Aspose.Page dla Java?
 Tak, możesz poznać funkcje Aspose.Page dla Java za pomocą[bezpłatna wersja próbna](https://releases.aspose.com/).
### Gdzie mogę znaleźć dodatkową pomoc i dyskusje?
 Odwiedzić[Forum Aspose.Page](https://forum.aspose.com/c/page/39) nawiązać kontakt ze społecznością i uzyskać pomoc.
### Jak mogę uzyskać tymczasową licencję na Aspose.Page dla Java?
 Zdobądź licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
### Gdzie mogę kupić licencjonowaną wersję Aspose.Page dla Java?
 Kup wersję licencjonowaną[Tutaj](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
