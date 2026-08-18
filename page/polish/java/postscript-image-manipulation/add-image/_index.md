---
date: 2026-02-15
description: Dowiedz się, jak tworzyć dokumenty PostScript w Javie i generować pliki
  dokumentów PostScript z przesunięciem i obrotem obrazu przy użyciu Aspose.Page dla
  Javy.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: Tworzenie PostScript w Javie – Dodawanie obrazu w PostScript Java
url: /pl/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz PostScript Java – Dodaj obraz w Java PostScript

## Wprowadzenie
W tym samouczku dowiesz się, jak **create postscript java** dokumenty i osadzać obrazy przy użyciu biblioteki Aspose.Page for Java. Przejdziemy krok po kroku, od inicjalizacji nowego pliku PostScript po zastosowanie transformacji **translate and rotate image**. Na końcu będziesz w stanie programowo generować pliki PostScript i kontrolować położenie obrazu z precyzją do pojedynczego piksela — idealne do automatycznych raportów, procesów drukowania lub każdego scenariusza, w którym potrzebujesz wygenerować wyjście **generate postscript document** z Javy.

## Szybkie odpowiedzi
- **Jakiej biblioteki wymaga?** Aspose.Page for Java  
- **Czy mogę dodać wiele obrazów?** Yes – repeat the transform and draw steps  
- **Czy potrzebna jest licencja do rozwoju?** A free trial works for testing; a license is required for production  
- **Jaką wersję Javy obsługuje?** Java 8 and later  
- **Czy obsługiwana jest rotacja obrazu?** Absolutely – use `AffineTransform.rotate()`

## Czym jest create postscript java?
Operacja **create postscript java** tworzy plik opisujący stronę PostScript, który koduje tekst, grafikę wektorową i obrazy rastrowe. Dzięki Aspose.Page możesz budować te pliki bezpośrednio w kodzie Java, uzyskując pełną kontrolę programistyczną nad układem, skalowaniem i rotacją bez potrzeby używania osobnego interpretera PostScript.

## Dlaczego warto używać Aspose.Page do manipulacji obrazami?
- **High‑level API:** Abstrahuje niskopoziomowe polecenia PostScript do prostych metod Java.  
- **Cross‑platform:** Działa na każdym systemie operacyjnym obsługującym Javę.  
- **Full graphics‑state control:** Umożliwia zapisywanie, przywracanie, przesuwanie, skalowanie i obracanie grafiki wedle potrzeb.  
- **No external dependencies:** Obsługuje ładowanie obrazów, konwersję formatów i osadzanie wewnętrznie.

## Wymagania wstępne
Zanim przejdziemy do kodu, upewnij się, że masz:

- Zainstalowany Java Development Kit (JDK) na swoim systemie.  
- Bibliotekę Aspose.Page for Java. Możesz ją pobrać [tutaj](https://releases.aspose.com/page/java/).  
- Podstawową znajomość programowania w Javie.

## Importowanie pakietów
Aby rozpocząć, zaimportuj niezbędne pakiety w swoim projekcie Java. Skorzystaj z poniższego fragmentu kodu jako odniesienia:

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Krok 1: Zapisz stan grafiki
Pierwszy krok polega na zapisaniu stanu grafiki w dokumencie. Zapewnia to możliwość cofnięcia wszelkich transformacji lub modyfikacji wykonanych później, jeśli będzie to potrzebne.

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

## Krok 2: Translacja i transformacja (translate and rotate image)
Następnie przesuń dokument i utwórz obiekt `BufferedImage` z pliku obrazu. Zastosuj serię transformacji, takich jak skalowanie i rotacja, używając `AffineTransform`. To właśnie miejsce, w którym odbywa się operacja **translate and rotate image**.

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

## Krok 3: Dodaj obraz do dokumentu
Teraz dodaj przekształcony obraz do dokumentu.

```java
document.drawImage(image, transform, null);
```

## Krok 4: Przywróć stan grafiki
Po dodaniu obrazu zapisz przywrócenie stanu grafiki, aby sfinalizować wprowadzone zmiany.

```java
document.writeGraphicsRestore();
```

## Krok 5: Zamknij bieżącą stronę i zapisz
Zamknij bieżącą stronę i zapisz dokument.

```java
document.closePage();
document.save();
```

Możesz powtarzać te kroki, aby dodać wiele obrazów lub dostosować transformacje zgodnie z własnymi wymaganiami.

## Typowe problemy i rozwiązania
- **FileNotFoundException:** Upewnij się, że ścieżka `dataDir` kończy się separatorem plików (`/` lub `\\`) oraz że nazwa pliku obrazu jest dokładnie taka sama.  
- **ImageIO.read returns null:** Sprawdź, czy format obrazu jest obsługiwany (np. JPEG, PNG).  
- **Incorrect rotation angle:** `AffineTransform.rotate` oczekuje radianów. Jeśli potrzeba, przelicz stopnie na radiany (`Math.toRadians(degrees)`).

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.Page for Java z innymi językami programowania?**  
A: Aspose.Page głównie obsługuje Javę, ale dostępne są wersje dla innych języków programowania.

**Q: Czy dostępna jest darmowa wersja próbna Aspose.Page for Java?**  
A: Tak, darmową wersję próbną możesz uzyskać [tutaj](https://releases.aspose.com/).

**Q: Jak mogę uzyskać tymczasową licencję na Aspose.Page for Java?**  
A: Tymczasową licencję możesz otrzymać [tutaj](https://purchase.aspose.com/temporary-license/).

**Q: Gdzie mogę znaleźć wsparcie społeczności i dyskusje związane z Aspose.Page for Java?**  
A: Odwiedź [Forum Aspose.Page](https://forum.aspose.com/c/page/39), aby uzyskać wsparcie społeczności.

**Q: Czy istnieją dodatkowe zasoby dotyczące zakupu Aspose.Page for Java?**  
A: Bibliotekę możesz kupić [tutaj](https://purchase.aspose.com/buy).

## Podsumowanie
Gratulacje! Pomyślnie nauczyłeś się, jak **create postscript java** dokumenty i osadzać obrazy przy użyciu Aspose.Page for Java. Zapoznaj się z [dokumentacją](https://reference.aspose.com/page/java/), aby poznać bardziej zaawansowane funkcje i możliwości, takie jak grafika wektorowa, renderowanie tekstu oraz niestandardowe rozmiary stron.

---

**Ostatnia aktualizacja:** 2026-02-15  
**Testowano z:** Aspose.Page for Java 23.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}