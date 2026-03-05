---
date: 2026-03-05
description: Dowiedz się, jak ustawić kolor tła w Javie i dodać przezroczyste obrazy
  do PostScript przy użyciu Aspose.Page dla Javy. Łatwo konwertuj PNG do PostScript.
linktitle: Add Transparent Image in Java PostScript
second_title: Aspose.Page Java API
title: 'Ustaw kolor tła w Javie: Dodaj przezroczysty obraz do PS'
url: /pl/java/postscript-transparency/add-transparent-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw kolor tła w Java: Dodaj przezroczysty obraz do PS

## Wprowadzenie
Jeśli potrzebujesz **set background color java** podczas pracy z Java PostScript, dodanie przezroczystych obrazów może nadać Twoim dokumentom wykończony, profesjonalny wygląd. W tym samouczku przeprowadzimy Cię przez cały proces ustawiania kolorowego tła, konwersji PNG do PostScript oraz rysowania zarówno nieprzezroczystych, jak i przezroczystych obrazów przy użyciu biblioteki Aspose.Page for Java. Po zakończeniu będziesz w stanie **add image to postscript** pliki z pełną kontrolą nad przezroczystością.

## Szybkie odpowiedzi
- **Jaka biblioteka obsługuje przezroczystość w Java PostScript?** Aspose.Page for Java.  
- **Czy mogę ustawić kolor tła przed rysowaniem obrazów?** Tak – użyj `document.setPaint()` i `fill()`.  
- **Jak przekonwertować PNG do PostScript?** Załaduj PNG przy pomocy `ImageIO.read()` i narysuj go przy użyciu `drawImage` lub `drawTransparentImage`.  
- **Czy obsługiwana jest przezroczystość obrazów?** Użyj `drawTransparentImage`, aby określić wartość przezroczystości (0‑255).  
- **Czy potrzebna jest licencja do użytku produkcyjnego?** Wymagana jest ważna licencja Aspose.Page for Java; dostępna jest darmowa wersja próbna.

## Wymagania wstępne
1. **Java Development Kit (JDK)** – najnowsza wersja zainstalowana.  
2. **Aspose.Page for Java** – pobierz ze [website](https://releases.aspose.com/page/java/).  
3. **Document Directory** – folder, w którym będziesz zapisywać pliki PostScript.  
4. **Translucent Image File** – np. `mask1.png`, którego użyjemy do demonstracji przezroczystości.

## Importowanie pakietów
W swoim projekcie Java zaimportuj niezbędne klasy. Ten blok pozostaje niezmieniony:

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

## Krok 1: Ustaw kolor tła w Java
Tutaj tworzymy dokument, wybieramy rozmiar A4 i wypełniamy czerwony prostokąt, aby zilustrować kontrast tła.

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

## Krok 2: Przesuń współrzędne
Przesuń kursor rysowania do wygodnego miejsca na stronie przed umieszczeniem obrazów.

```java
// Translate to a specific position on the page
document.writeGraphicsSave();
document.translate(20, 100);
```

## Krok 3: Utwórz obiekt obrazu
Załaduj plik PNG (nasz krok **convert png to postscript**).

```java
// Create an image from the translucent image file
BufferedImage image = ImageIO.read(new File(dataDir + "mask1.png"));
```

## Krok 4: Dodaj nieprzezroczysty obraz
Narysuj obraz normalnie — to demonstruje **add image to postscript** bez przezroczystości.

```java
// Add the image to the document as an opaque RGB image
document.drawImage(image, new AffineTransform(1, 0, 0, 1, 100, 0), null);
```

## Krok 5: Dodaj przezroczysty obraz (rysuj obraz z przezroczystością)
Teraz używamy `drawTransparentImage`, aby wyrenderować ten sam PNG z pełną nieprzezroczystością (255). Dostosuj wartość, aby kontrolować przezroczystość.

```java
// Add the image to the document as a transparent image
document.drawTransparentImage(image, new AffineTransform(1, 0, 0, 1, 350, 0), 255);
```

## Krok 6: Zapisz i zamknij
Zakończ dokument i zwolnij zasoby.

```java
// Save and close the document
document.writeGraphicsRestore();
document.closePage();
document.save();
```

## Dlaczego to ma znaczenie
Ustawienie koloru tła w Java daje Ci płótno, które może podkreślić nałożone grafiki. Połączenie tego z **draw image with opacity** pozwala tworzyć znaki wodne, loga lub makiety UI bezpośrednio w PostScript, bez potrzeby używania zewnętrznych narzędzi edycyjnych.

## Typowe problemy i wskazówki
- **Obraz nie jest przezroczysty:** Sprawdź, czy PNG faktycznie zawiera kanał alfa.  
- **Nieprawidłowe kolory:** Pamiętaj, że prostokąt tła jest rysowany przed obrazem; zmień wartości `Color`, aby pasowały do Twojego projektu.  
- **Wydajność:** W przypadku dużych dokumentów, ponownie używaj jednej instancji `AffineTransform`, aby zmniejszyć narzut tworzenia obiektów.

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.Page for Java z innymi bibliotekami Java?**  
A: Tak, Aspose.Page for Java może być bezproblemowo zintegrowany z innymi bibliotekami Java, aby zwiększyć możliwości przetwarzania dokumentów.

**Q: Czy dostępna jest darmowa wersja próbna Aspose.Page for Java?**  
A: Tak, możesz uzyskać dostęp do darmowej wersji próbnej Aspose.Page for Java [tutaj](https://releases.aspose.com/).

**Q: Jak mogę uzyskać tymczasową licencję na Aspose.Page for Java?**  
A: Tymczasową licencję możesz uzyskać pod [tym linkiem](https://purchase.aspose.com/temporary-license/).

**Q: Czy istnieją fora wsparcia dla Aspose.Page for Java?**  
A: Tak, odwiedź [forum Aspose.Page for Java](https://forum.aspose.com/c/page/39) w celu uzyskania wsparcia społeczności i dyskusji.

**Q: Gdzie mogę znaleźć dokumentację Aspose.Page for Java?**  
A: Zapoznaj się ze szczegółową [documentation](https://reference.aspose.com/page/java/) aby uzyskać szczegółowe informacje o Aspose.Page for Java.

---

**Ostatnia aktualizacja:** 2026-03-05  
**Testowano z:** Aspose.Page for Java 24.11 (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}