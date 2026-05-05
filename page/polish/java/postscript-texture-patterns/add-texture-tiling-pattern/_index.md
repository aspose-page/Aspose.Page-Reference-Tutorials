---
date: 2026-05-05
description: Dowiedz się, jak dodawać wzory tekstur kafelkowych do dokumentów PostScript
  przy użyciu Aspose.Page dla Javy. Ten przewodnik pokazuje, jak efektywnie dodawać
  teksturę i odkrywać kreatywne możliwości.
keywords:
- how to add texture
- fill shape with texture
- fill rectangle with texture
linktitle: Dodaj wzór kafelkowania tekstury w Java PostScript
second_title: Aspose.Page Java API
title: Jak dodać wzór kafelkowania tekstury w Java PostScript
url: /pl/java/postscript-texture-patterns/add-texture-tiling-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dodać wzorzec kafelkowania tekstury w Java PostScript

## Wprowadzenie
W świecie programowania w Javie, nauka **jak dodać teksturę** do dokumentów PostScript jest częstym wymaganiem. Aspose.Page for Java upraszcza to zadanie, pozwalając skupić się na projekcie, a nie na niskopoziomowej składni PostScript. W tym samouczku przeprowadzimy Cię przez każdy krok potrzebny do dodania wzorca kafelkowania tekstury, wypełniania kształtów oraz tekstu teksturą w dokumencie Java PostScript.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebujesz?** Aspose.Page for Java  
- **Które główne słowo kluczowe jest celem tego przewodnika?** *how to add texture*  
- **Czy potrzebuję licencji do testowania?** Dostępna jest bezpłatna wersja próbna; licencja jest wymagana w produkcji.  
- **Jaką wersję Javy obsługuje?** Java 8 lub wyższą.  
- **Czy mogę ponownie używać pędzla tekstury dla wielu kształtów?** Tak – utwórz `TexturePaint` raz i zastosuj go do dowolnego kształtu.  
- **Jak wypełnić prostokąt teksturą?** Użyj `document.fill(shape)` po ustawieniu `TexturePaint` jako bieżącego pędzla.

## Czym jest wzorzec kafelkowania tekstury?
Wzorzec kafelkowania tekstury powtarza mały obraz (kafelek) na większym obszarze, umożliwiając **wypełnianie kształtu teksturą** bez ręcznego rysowania każdego kafelka. Technika ta jest idealna dla tła, wypełnień i dekoracyjnych efektów tekstowych w PostScript.

## Dlaczego warto używać Aspose.Page for Java?
- **Renderowanie bez zależności** – nie wymaga zewnętrznych interpreterów PostScript.  
- **Pełna kontrola nad grafiką** – łącz wektory, tekst i bitmapowe tekstury.  
- **Cross‑platform** – działa na każdym systemie operacyjnym obsługującym Javę.  

## Wymagania wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania:
- Podstawowa znajomość języka programowania Java.  
- Znajomość struktury dokumentu PostScript.  
- Zainstalowana biblioteka Aspose.Page for Java. Możesz ją pobrać [tutaj](https://releases.aspose.com/page/java/).

## Importowanie pakietów
Rozpocznij od zaimportowania niezbędnych pakietów do swojego projektu Java:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Jak dodać wzorzec kafelkowania tekstury w Java PostScript
Poniżej znajduje się przewodnik krok po kroku. Każdy krok zawiera krótkie wyjaśnienie oraz dokładny kod, który należy skopiować.

### Krok 1: Utwórz dokument PostScript
Rozpocznij od utworzenia nowego dokumentu PostScript, określając strumień wyjściowy i opcje zapisu. Upewnij się, że masz skonfigurowane niezbędne ścieżki.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTextureTilingPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Krok 2: Skonfiguruj środowisko graficzne
Przesuń początek układu do wygodnej lokalizacji i załaduj bitmapę, która będzie służyć jako kafelek tekstury.

```java
document.writeGraphicsSave();
document.translate(200, 100);
// Create a BufferedImage object from image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestTexture.bmp"));
```

### Krok 3: Utwórz pędzel tekstury
Zdefiniuj `TexturePaint`, który powtarza bitmapę na obszarze kształtu. Dostosuj rozmiar prostokąta, jeśli chcesz, aby kafelek był większy lub mniejszy.

```java
// Create image area doubled in width
Rectangle2D.Float imageArea = new Rectangle2D.Float(0, 0, image.getWidth() * 2, image.getHeight());
// Create texture brush from the image
TexturePaint paint = new TexturePaint(image, imageArea);
```

### Krok 4: Rysuj i wypełniaj kształty
Utwórz prostokąt i **wypełnij prostokąt teksturą** przy użyciu pędzla. Następnie obrysuj kształt, aby wynik był wizualnie wyraźny.

```java
// Create rectangle
Rectangle2D.Float shape = new Rectangle2D.Float(0, 0, 200, 100);
// Set this texture brush as current paint
document.setPaint(paint);
// Fill rectangle
document.fill(shape);
document.setPaint(Color.RED);
document.setStroke(new BasicStroke(2));
document.draw(shape);
```

### Krok 5: Dodaj tekst ze wzorcem tekstury
Możesz również zastosować tę samą teksturę do glifów tekstu. To pokazuje **jak wypełnić teksturą** znaki, jednocześnie umożliwiając ich obrysowanie.

```java
// Fill the text with the texture pattern
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
// Outline the text with the texture pattern
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

### Krok 6: Zapisz i zamknij
Na koniec zamknij stronę, zapisz dokument i zwolnij zasoby.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Częste problemy i wskazówki
- **Brakujący plik tekstury** – Sprawdź, czy ścieżka do `TestTexture.bmp` jest poprawna i plik jest dostępny.  
- **Nieprawidłowe wymiary obrazu** – Jeśli tekstura jest rozciągnięta, dostosuj `imageArea` do rozmiaru oryginalnego obrazu.  
- **Wydajność** – Ponownie używaj tej samej instancji `TexturePaint` dla wielu kształtów, aby uniknąć niepotrzebnego tworzenia obiektów.  
- **Porada:** Użyj bitmapy wysokiej rozdzielczości jako kafelka, aby tekstura pozostała wyraźna po skalowaniu.

## Najczęściej zadawane pytania

**Q: Czy Aspose.Page for Java jest odpowiedni dla początkujących?**  
A: Zdecydowanie tak!

**Q: Czy mogę zintegrować Aspose.Page for Java z istniejącym projektem Java?**  
A: Tak, możesz łatwo zintegrować Aspose.Page for Java ze swoim projektem, postępując zgodnie z dokumentacją udostępnioną [tutaj](https://reference.aspose.com/page/java/).

**Q: Gdzie mogę znaleźć wsparcie lub dyskutować o zapytaniach związanych z Aspose.Page?**  
A: Odwiedź [forum Aspose.Page](https://forum.aspose.com/c/page/39), aby skontaktować się ze społecznością i uzyskać pomoc.

**Q: Czy dostępna jest bezpłatna wersja próbna Aspose.Page for Java?**  
A: Tak, możesz wypróbować bezpłatną wersję próbną [tutaj](https://releases.aspose.com/).

**Q: Jak mogę uzyskać tymczasową licencję na Aspose.Page for Java?**  
A: Odwiedź [ten link](https://purchase.aspose.com/temporary-license/), aby uzyskać tymczasową licencję.

## Zakończenie
Gratulacje! Pomyślnie nauczyłeś się **jak dodać teksturę** w postaci wzorców kafelkowania do dokumentu Java PostScript przy użyciu Aspose.Page for Java. Śmiało eksperymentuj z różnymi bitmapowymi kafelkami, współczynnikami skali i operacjami kompozycji, aby w pełni wykorzystać kreatywny potencjał wypełnień teksturą.

---

**Last Updated:** 2026-05-05  
**Testowano z:** Aspose.Page for Java 24.12 (latest)  
**Autor:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}