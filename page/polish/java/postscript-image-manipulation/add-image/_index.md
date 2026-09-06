---
date: 2026-08-23
description: Dowiedz się, jak używać aspose.page image manipulation java do osadzania
  i obracania obrazów w plikach PostScript przy użyciu przejrzystych przykładów w
  języku Java.
keywords:
- aspose.page image manipulation java
- add image postscript java
- java postscript image rotation
- aspose.page java tutorial
- image embedding java
lastmod: 2026-08-23
linktitle: Dodaj obraz w Java PostScript
og_description: Dowiedz się, jak używać aspose.page image manipulation java do osadzania
  i obracania obrazów w plikach PostScript, z krok‑po‑kroku przykładami kodu w języku
  Java.
og_image_alt: Guide showing Java code to add and rotate images in PostScript using
  Aspose.Page
og_title: Jak używać aspose.page image manipulation java, aby dodać obraz
schemas:
- author: Aspose
  dateModified: '2026-08-23'
  description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  headline: How to use aspose.page image manipulation java to add image
  type: TechArticle
- description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  name: How to use aspose.page image manipulation java to add image
  steps:
  - name: write graphics save
    text: Saving the graphics state isolates your transformations so you can revert
      later. This is equivalent to the `gsave` operator in raw PostScript.
  - name: translate and transform (translate and rotate image)
    text: First, create a `BufferedImage` from the source file, then build an `AffineTransform`
      that translates the image to the desired coordinates and rotates it around its
      centre. `AffineTransform.rotate` expects an angle in radians, so convert degrees
      with `Math.toRadians(degrees)`. **AffineTransform** is
  - name: add image to document
    text: After configuring the transform, draw the image onto the current page. The
      library automatically converts the `BufferedImage` into an appropriate PostScript
      image stream.
  - name: write graphics restore
    text: Calling restore (`grestore`) returns the graphics state to what it was before
      the save, ensuring subsequent drawing commands are not affected by the previous
      transformation.
  - name: close current page and save
    text: Finish the page, close the document, and write the output file to disk.
      You can repeat the above sequence to embed additional images, adjusting the
      translation coordinates and rotation angle each time.
  type: HowTo
- questions:
  - answer: The core library is Java‑only, but Aspose provides equivalent APIs for
      .NET, C++, and Python, each tailored to its platform.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can access the free trial **[Aspose.Page free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for community assistance.
    question: Where can I find community support and discussions related to Aspose.Page
      for Java?
  - answer: You can buy the library **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.
    question: Are there any additional resources for purchasing Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image manipulation
- postscript
- image rotation
- java tutorial
title: Jak używać aspose.page image manipulation java, aby dodać obraz
url: /pl/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak używać aspose.page image manipulation java do dodawania obrazu

## Wprowadzenie
W tym samouczku dowiesz się, jak **używać aspose.page image manipulation java** do tworzenia plików PostScript, osadzania obrazów rastrowych oraz stosowania transformacji translacji i rotacji. Po zakończeniu przewodnika będziesz w stanie generować pikselowo‑idealny output PostScript z Javy — idealny do automatycznego raportowania, potoków drukowania lub dowolnego przepływu pracy, który wymaga precyzyjnego rozmieszczenia obrazu w dokumencie PostScript.

## Szybkie odpowiedzi
- **Jakiej biblioteki wymaga?** Aspose.Page for Java  
- **Czy mogę dodać wiele obrazów?** Tak – powtórz kroki transformacji i rysowania dla każdego obrazu  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna działa do testów; licencja jest wymagana w produkcji  
- **Która wersja Javy jest wspierana?** Java 8 and later  
- **Czy obsługiwana jest rotacja obrazu?** Zdecydowanie – użyj `AffineTransform.rotate()`  

## Czym jest aspose.page image manipulation java?
`aspose.page image manipulation java` to API Aspose.Page, które pozwala programowo budować, edytować i renderować dokumenty PostScript z kodu Java, w tym pełną kontrolę nad rozmieszczeniem obrazu, skalowaniem i rotacją. Dzięki temu API unikasz niskopoziomowej składni PostScript i pozwalasz bibliotece obsługiwać konwersję formatu oraz osadzanie wewnętrznie.

## Dlaczego używać aspose.page do manipulacji obrazem?
Aspose.Page udostępnia **ponad 50 formatów obrazów** (w tym JPEG, PNG, BMP, TIFF) i może je osadzać w PostScript bez ładowania całego dokumentu do pamięci, co umożliwia przetwarzanie plików ze setkami stron przy zużyciu pamięci poniżej 100 MB na typowym serwerze. API wysokiego poziomu abstrahuje złożone polecenia PostScript, dzięki czemu piszesz zwięzły kod Java zamiast surowych operatorów PS.

## Wymagania wstępne
- Zainstalowany Java Development Kit (JDK) 8 lub nowszy.  
- Biblioteka Aspose.Page for Java – pobierz ją **[Strona pobierania Aspose.Page for Java](https://releases.aspose.com/page/java/)**.  
- Podstawowa znajomość składni Java i programowania obiektowego.

## Czym jest create postscript java?
Tworzenie pliku PostScript z Javy oznacza programowe generowanie dokumentu `.ps`, który opisuje układ strony, grafikę wektorową i obrazy rastrowe przy użyciu języka PostScript. Aspose.Page tłumaczy wywołania Java na prawidłowe instrukcje PostScript, umożliwiając tworzenie gotowych do druku plików bez osobnego interpretera PostScript.

## Jak dodać obraz z translacją i rotacją krok po kroku

Wczytaj obraz, zastosuj `AffineTransform` i narysuj go na stronie. Poniższe kroki przedstawiają dokładną kolejność, którą należy wykonać.

### Krok 1: zapis stanu graficznego
Zapisanie stanu graficznego izoluje twoje transformacje, dzięki czemu możesz je później przywrócić. Jest to równoważne operatorowi `gsave` w surowym PostScript.

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Krok 2: translacja i transformacja (przesunięcie i obrót obrazu)
Najpierw utwórz `BufferedImage` z pliku źródłowego, a następnie zbuduj `AffineTransform`, który przesuwa obraz do żądanych współrzędnych i obraca go wokół jego środka. `AffineTransform.rotate` oczekuje kąta w radianach, więc przelicz stopnie przy pomocy `Math.toRadians(degrees)`.

**AffineTransform** to klasa Java reprezentująca dwuwymiarową transformację afiniczną, taką jak translacja, rotacja, skalowanie lub ścinanie.  
**BufferedImage** to klasa Java przechowująca obraz w pamięci jako raster pikseli.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

### Krok 3: dodaj obraz do dokumentu
Po skonfigurowaniu transformacji narysuj obraz na bieżącej stronie. Biblioteka automatycznie konwertuje `BufferedImage` na odpowiedni strumień obrazu PostScript.

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

### Krok 4: przywrócenie stanu graficznego
Wywołanie przywrócenia (`grestore`) przywraca stan graficzny do tego, jaki był przed zapisem, zapewniając, że kolejne polecenia rysowania nie będą wpływać na poprzednią transformację.

```java
document.drawImage(image, transform, null);
```

### Krok 5: zamknij bieżącą stronę i zapisz
Zakończ stronę, zamknij dokument i zapisz plik wyjściowy na dysku.

```java
document.writeGraphicsRestore();
```

Możesz powtórzyć powyższą sekwencję, aby osadzić dodatkowe obrazy, dostosowując przy każdym razie współrzędne translacji i kąt rotacji.

## Typowe problemy i rozwiązania
- **FileNotFoundException:** Upewnij się, że `dataDir` kończy się separatorem plików (`/` lub `\\`) oraz że nazwa pliku obrazu jest dokładnie zgodna.  
- **ImageIO.read returns null:** Upewnij się, że format obrazu znajduje się na liście obsługiwanych (JPEG, PNG, BMP, GIF, TIFF).  
- **Incorrect rotation angle:** `AffineTransform.rotate` działa w radianach; użyj `Math.toRadians(degrees)` do konwersji ze stopni.  
- **Memory spikes on large pages:** Użyj `Document.save` z `saveOptions.setCompress(true)`, aby zmniejszyć zużycie pamięci.

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.Page for Java z innymi językami programowania?**  
A: Główna biblioteka jest wyłącznie w Javie, ale Aspose udostępnia równoważne API dla .NET, C++ i Pythona, każde dostosowane do swojej platformy.

**Q: Czy dostępna jest darmowa wersja próbna Aspose.Page for Java?**  
A: Tak, możesz uzyskać dostęp do darmowej wersji próbnej **[Strona darmowej wersji próbnej Aspose.Page](https://releases.aspose.com/)**.

**Q: Jak mogę uzyskać tymczasową licencję dla Aspose.Page for Java?**  
A: Możesz uzyskać tymczasową licencję **[strona żądania tymczasowej licencji](https://purchase.aspose.com/temporary-license/)**.

**Q: Gdzie mogę znaleźć wsparcie społeczności i dyskusje związane z Aspose.Page for Java?**  
A: Odwiedź **[Forum Aspose.Page](https://forum.aspose.com/c/page/39)**, aby uzyskać pomoc od społeczności.

**Q: Czy są dodatkowe zasoby dotyczące zakupu Aspose.Page for Java?**  
A: Możesz kupić bibliotekę **[Strona zakupu Aspose.Page](https://purchase.aspose.com/buy)**.

## Podsumowanie
Masz teraz kompletny, kompleksowy przykład **aspose.page image manipulation java**, który tworzy plik PostScript, przesuwa i obraca obraz oraz zapisuje wynik. Przeglądaj pełną **[dokumentację](https://reference.aspose.com/page/java/)**, aby odkryć zaawansowane funkcje, takie jak grafika wektorowa, niestandardowe rozmiary stron i renderowanie tekstu.

---

**Ostatnia aktualizacja:** 2026-08-23  
**Testowano z:** Aspose.Page for Java 23.11  
**Autor:** Aspose  








```java
document.closePage();
document.save();
```

## Powiązane samouczki

- [Jak przekonwertować PostScript na PDF przy użyciu Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [Jak dodać gradient: gradient diagonalny w Java PostScript przy użyciu Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Jak dodać wzór kreskowania w Java PostScript z Aspose.Page](/page/java/postscript-hatch-patterns/add-hatch-pattern/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}