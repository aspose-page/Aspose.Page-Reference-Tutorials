---
date: 2025-12-09
description: Dowiedz się, jak tworzyć dokumenty PostScript w Javie oraz przesuwać
  i obracać obrazy przy użyciu Aspose.Page, aby uzyskać płynną manipulację obrazami.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: Utwórz dokument PostScript w Javie – Dodaj obraz w PostScript w Javie
url: /pl/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz dokument PostScript w Javie – Dodaj obraz w Java PostScript

## Wprowadzenie
W tym samouczku dowiesz się, jak **utworzyć dokument PostScript w Javie** i osadzać obrazy przy użyciu biblioteki Aspose.Page for Java. Przejdziemy krok po kroku od konfiguracji dokumentu po zastosowanie transformacji, takich jak **przesunięcie i obrót obrazu**. Po zakończeniu będziesz w stanie programowo generować bogate pliki PostScript i dostosowywać położenie obrazów do dokładnych potrzeb układu.

## Szybkie odpowiedzi
- **Jakiej biblioteki wymagana jest?** Aspose.Page for Java  
- **Czy mogę dodać wiele obrazów?** Tak – powtórz kroki transformacji i rysowania  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna działa do testów; licencja jest wymagana w produkcji  
- **Jaką wersję Javy obsługuje?** Java 8 i nowsze  
- **Czy obsługa rotacji obrazu jest dostępna?** Zdecydowanie – użyj `AffineTransform.rotate()`  

## Czym jest tworzenie dokumentu PostScript w Javie?
Dokument PostScript jest plikiem języka opisu strony, który opisuje tekst, grafikę i obrazy. Korzystając z Aspose.Page, możesz programowo generować te pliki w Javie, uzyskując pełną kontrolę nad układem, stanem grafiki i obsługą obrazów, bez potrzeby interpreteru PostScript.

## Dlaczego używać Aspose.Page do manipulacji obrazami?
- **API wysokiego poziomu:** Upraszcza złożone polecenia PostScript.  
- **Wieloplatformowy:** Działa na każdym systemie operacyjnym obsługującym Javę.  
- **Pełna kontrola stanu grafiki:** Łatwo zapisuj, przywracaj, przesuwaj, skaluj i obracaj grafikę.  
- **Brak zewnętrznych zależności:** Obsługuje ładowanie i konwersję obrazów wewnętrznie.  

## Wymagania wstępne
Zanim przejdziemy do kodu, upewnij się, że masz:

- Zainstalowany Java Development Kit (JDK) na swoim systemie.  
- Bibliotekę Aspose.Page for Java. Możesz ją pobrać [tutaj](https://releases.aspose.com/page/java/).  
- Podstawową znajomość programowania w Javie.  

## Importowanie pakietów
Aby rozpocząć, zaimportuj niezbędne pakiety w swoim projekcie Java. Użyj poniższego fragmentu kodu jako odniesienia:

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
Pierwszy krok polega na zapisaniu stanu grafiki w dokumencie. Zapewnia to, że wszelkie późniejsze transformacje lub modyfikacje mogą zostać przywrócone w razie potrzeby.

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

## Krok 2: Translacja i transformacja (przesunięcie i obrót obrazu)
Następnie przesuń dokument i utwórz obiekt `BufferedImage` z pliku obrazu. Zastosuj serię transformacji, takich jak skalowanie i obrót, używając `AffineTransform`. To jest miejsce, w którym odbywa się operacja **przesunięcia i obrotu obrazu**.

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

Możesz powtórzyć te kroki, aby dodać wiele obrazów lub dostosować transformacje zgodnie z wymaganiami.

## Typowe problemy i rozwiązania
- **FileNotFoundException:** Upewnij się, że ścieżka `dataDir` kończy się separatorem plików (`/` lub `\\`) oraz że nazwa pliku obrazu jest dokładnie taka sama.  
- **ImageIO.read zwraca null:** Sprawdź, czy format obrazu jest obsługiwany (np. JPEG, PNG).  
- **Nieprawidłowy kąt obrotu:** `AffineTransform.rotate` oczekuje radianów. W razie potrzeby przelicz stopnie na radiany (`Math.toRadians(degrees)`).  

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.Page for Java z innymi językami programowania?**  
**A:** Aspose.Page głównie obsługuje Javę, ale dostępne są wersje dla innych języków programowania.  

**Q: Czy dostępna jest darmowa wersja próbna Aspose.Page for Java?**  
**A:** Tak, możesz uzyskać dostęp do darmowej wersji próbnej [tutaj](https://releases.aspose.com/).  

**Q: Jak mogę uzyskać tymczasową licencję na Aspose.Page for Java?**  
**A:** Tymczasową licencję możesz uzyskać [tutaj](https://purchase.aspose.com/temporary-license/).  

**Q: Gdzie mogę znaleźć wsparcie społeczności i dyskusje związane z Aspose.Page for Java?**  
**A:** Odwiedź [forum Aspose.Page](https://forum.aspose.com/c/page/39), aby uzyskać wsparcie społeczności.  

**Q: Czy są dodatkowe zasoby dotyczące zakupu Aspose.Page for Java?**  
**A:** Bibliotekę możesz kupić [tutaj](https://purchase.aspose.com/buy).  

## Podsumowanie
Gratulacje! Pomyślnie nauczyłeś się, jak **utworzyć dokument PostScript w Javie** i osadzać obrazy przy użyciu Aspose.Page for Java. Zapoznaj się z [dokumentacją](https://reference.aspose.com/page/java/), aby poznać bardziej zaawansowane funkcje i możliwości, takie jak grafika wektorowa, renderowanie tekstu oraz niestandardowe rozmiary stron.

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.Page for Java 23.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}