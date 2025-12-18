---
date: 2025-12-18
description: Dowiedz się, jak tworzyć dokumenty PostScript w Javie i dodawać przezroczyste
  obrazy przy użyciu Aspose.Page for Java. Ten przewodnik pokazuje, jak łatwo dodać
  obraz do PostScripta.
linktitle: Create PostScript Document Java – Add Transparent Image
second_title: Aspose.Page Java API
title: Utwórz dokument PostScript w Javie – Dodaj przezroczysty obraz
url: /pl/java/postscript-transparency/add-transparent-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj przezroczysty obraz w Java PostScript

## Wprowadzenie
W świecie Java PostScript, zwiększanie atrakcyjności wizualnej dokumentów często polega na dodawaniu przezroczystych obrazów. Ten samouczek poprowadzi Cię przez proces **create postscript document java** przy użyciu potężnej biblioteki Aspose.Page for Java. Zobaczysz, jak dodać obraz do postscriptu, precyzyjnie go pozycjonować i kontrolować jego przezroczystość, aby uzyskać profesjonalny wygląd.

## Szybkie odpowiedzi
- **Co obejmuje ten samouczek?** Dodanie przezroczystego PNG do dokumentu PostScript przy użyciu Aspose.Page for Java.  
- **Jakiej biblioteki wymaga?** Aspose.Page for Java (pobierz z oficjalnej strony).  
- **Czy potrzebna jest licencja?** Wymagana jest tymczasowa lub pełna licencja do produkcji; dostępna jest darmowa wersja próbna.  
- **Czy mogę używać innych formatów obrazów?** Tak, ale PNG z kanałem alfa działa najlepiej dla przezroczystości.  
- **Jak długo trwa implementacja?** Około 10‑15 minut dla podstawowego przykładu.

## Co to jest dokument PostScript w Javie?
Dokument PostScript to plik języka opisu strony, który opisuje tekst, grafikę i obrazy. Korzystając z Javy, możesz programowo generować te pliki, uzyskując pełną kontrolę nad układem i renderowaniem. Główne słowo kluczowe **create postscript document java** odzwierciedla tę możliwość.

## Dlaczego dodawać przezroczyste obrazy?
Przezroczyste obrazy pozwalają nakładać grafikę bez zasłaniania zawartości pod spodem, co jest idealne dla znaków wodnych, logo lub elementów dekoracyjnych. Połączenie przezroczystości z precyzyjnym pozycjonowaniem tworzy dopracowane, spójne z marką dokumenty.

## Prerequisites
1. Java Development Kit (JDK): Upewnij się, że masz zainstalowaną najnowszą wersję JDK na swoim komputerze.  
2. Aspose.Page for Java: Pobierz i zainstaluj bibliotekę Aspose.Page for Java ze [strony internetowej](https://releases.aspose.com/page/java/).  
3. Katalog dokumentów: Utwórz katalog w swoim systemie, w którym będziesz przechowywać dokumenty Java PostScript.  
4. Plik przezroczystego obrazu: Przygotuj plik przezroczystego obrazu (np. „mask1.png”), którego użyjesz w samouczku.

## Importowanie pakietów
W swoim projekcie Java zaimportuj niezbędne pakiety, aby wykorzystać funkcjonalności udostępniane przez Aspose.Page for Java. Poniżej znajduje się dokładny blok importów, którego będziesz potrzebować:

```java
import java.awt.Color;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## How to create postscript document java with a transparent image?
Poniżej znajduje się przewodnik krok po kroku. Każdy krok zawiera krótkie wyjaśnienie, a następnie oryginalny blok kodu (niezmieniony).

### Krok 1: Ustaw kolor tła
Zaczynamy od utworzenia dokumentu PostScript, otwarcia strumienia wyjściowego i namalowania czerwonego prostokąta jako wizualnego odniesienia dla przezroczystego obrazu.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTransparentImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Add a red rectangle under images for visual contrast
document.setPaint(new Color(211, 8, 48));
document.fill(new Rectangle2D.Float(0, 0, (int) options.getPageSize().getWidth(), 300));
```

### Krok 2: Przesuń współrzędne
Przed rysowaniem przesuwamy początek układu współrzędnych w wygodne miejsce na stronie, aby obraz pojawił się tam, gdzie tego chcemy.

```java
// Translate to a specific position on the page
document.writeGraphicsSave();
document.translate(20, 100);
```

### Krok 3: Utwórz obiekt obrazu
Wczytaj plik PNG zawierający kanał alfa. Ten obraz będzie używany zarówno do renderowania nieprzezroczystego, jak i przezroczystego.

```java
// Create an image from the translucent image file
BufferedImage image = ImageIO.read(new File(dataDir + "mask1.png"));
```

### Krok 4: Dodaj nieprzezroczysty obraz
Najpierw rysujemy obraz jako zwykły bitmapowy RGB. To pokazuje różnicę, gdy później zastosujemy przezroczystość.

```java
// Add the image to the document as an opaque RGB image
document.drawImage(image, new AffineTransform(1, 0, 0, 1, 100, 0), null);
```

### Krok 5: Dodaj przezroczysty obraz
Teraz rysujemy ten sam obraz z pełną nieprzezroczystością (255) lub dowolną wartością w zakresie 0‑255, aby kontrolować przezroczystość. Tutaj używamy 255 dla pełnej nieprzezroczystości, ale możesz obniżyć wartość, aby uzyskać efekt prześwitu.

```java
// Add the image to the document as a transparent image
document.drawTransparentImage(image, new AffineTransform(1, 0, 0, 1, 350, 0), 255);
```

### Krok 6: Zapisz i zamknij
Na koniec przywracamy stan graficzny, zamykamy stronę i zapisujemy dokument na dysku.

```java
// Save and close the document
document.writeGraphicsRestore();
document.closePage();
document.save();
```

## Częste problemy i rozwiązania
- **FileNotFoundException** – Sprawdź, czy `dataDir` wskazuje na właściwy folder i czy plik `mask1.png` istnieje.  
- **ImageIO.read returns null** – Upewnij się, że PNG ma prawidłowy format i nie jest uszkodzony.  
- **Transparent image appears opaque** – Dostosuj trzeci parametr funkcji `drawTransparentImage` (0 = całkowicie przezroczysty, 255 = całkowicie nieprzezroczysty).  

## Najczęściej zadawane pytania
### Czy mogę używać Aspose.Page for Java z innymi bibliotekami Java?
Tak, Aspose.Page for Java może być bezproblemowo integrowany z innymi bibliotekami Java, aby zwiększyć możliwości przetwarzania dokumentów.

### Czy dostępna jest darmowa wersja próbna Aspose.Page for Java?
Tak, możesz uzyskać darmową wersję próbną Aspose.Page for Java z [tutaj](https://releases.aspose.com/).

### Jak mogę uzyskać tymczasową licencję na Aspose.Page for Java?
Możesz uzyskać tymczasową licencję pod [ten link](https://purchase.aspose.com/temporary-license/).

### Czy istnieją fora wsparcia Aspose.Page for Java?
Tak, odwiedź [forum Aspose.Page for Java](https://forum.aspose.com/c/page/39), aby uzyskać wsparcie społeczności i dyskusje.

### Gdzie mogę znaleźć dokumentację Aspose.Page for Java?
Zapoznaj się ze szczegółową [dokumentacją](https://reference.aspose.com/page/java/), aby uzyskać szczegółowe informacje o Aspose.Page for Java.

## Zakończenie
Gratulacje! Pomyślnie nauczyłeś się, jak **create postscript document java** i dodawać przezroczyste obrazy przy użyciu Aspose.Page for Java. Eksperymentuj z różnymi obrazami, poziomami nieprzezroczystości i pozycjami, aby tworzyć wizualnie zachwycające dokumenty spełniające potrzeby Twojej marki.

---

**Last Updated:** 2025-12-18  
**Testowano z:** Aspose.Page for Java 24.11 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}