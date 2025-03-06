---
title: Dodaj obraz w języku Java PostScript
linktitle: Dodaj obraz w języku Java PostScript
second_title: Aspose.Page API Java
description: Poznaj bezproblemową integrację Aspose.Page Java w tym samouczku na temat dodawania obrazów do dokumentów PostScript. Zwiększ swoje możliwości manipulowania dokumentami.
weight: 10
url: /pl/java/postscript-image-manipulation/add-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj obraz w języku Java PostScript

## Wstęp
W tym samouczku omówimy, jak dodawać obrazy do dokumentu Java PostScript przy użyciu biblioteki Aspose.Page for Java. Aspose.Page to potężna biblioteka zapewniająca różne funkcje do pracy z plikami PostScript, umożliwiając programistom płynne manipulowanie i ulepszanie dokumentów.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Zestaw Java Development Kit (JDK) zainstalowany w systemie.
-  Aspose.Page dla biblioteki Java. Możesz go pobrać[Tutaj](https://releases.aspose.com/page/java/).
- Podstawowa znajomość programowania w języku Java.
## Importuj pakiety
Aby rozpocząć, zaimportuj niezbędne pakiety do swojego projektu Java. Użyj poniższego fragmentu kodu jako odniesienia:
```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Krok 1: Zapisz zapisaną grafikę
Pierwszy krok polega na zapisaniu grafiki zapisanej w dokumencie. Dzięki temu wszelkie późniejsze przekształcenia i modyfikacje można w razie potrzeby wycofać.
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz strumień wyjściowy dla dokumentu PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Twórz opcje zapisywania w formacie A4
PsSaveOptions options = new PsSaveOptions();
// Utwórz nowy dokument PS z otwartą stroną
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```
## Krok 2: Przetłumacz i przekształć
Następnie przetłumacz dokument i utwórz obiekt BufferedImage z pliku obrazu. Zastosuj serię przekształceń, takich jak skalowanie i obrót, za pomocą AffineTransform.
```java
document.translate(100, 100);
// Utwórz obiekt BufferedImage z pliku obrazu
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Utwórz transformację obrazu
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
## Krok 4: Zapisz przywracanie grafiki
Po dodaniu obrazu zapisz przywracanie grafiki, aby sfinalizować wprowadzone zmiany.
```java
document.writeGraphicsRestore();
```
## Krok 5: Zamknij bieżącą stronę i zapisz
Zamknij bieżącą stronę i zapisz dokument.
```java
document.closePage();
document.save();
```
Powtórz te kroki, aby dodać wiele obrazów lub dostosuj przekształcenia w zależności od wymagań.
## Wniosek
 Gratulacje! Pomyślnie nauczyłeś się dodawać obrazy do dokumentu Java PostScript przy użyciu Aspose.Page dla Java. Poznaj[dokumentacja](https://reference.aspose.com/page/java/) dla bardziej zaawansowanych funkcji i funkcjonalności.
## Często zadawane pytania
### Czy mogę używać Aspose.Page dla Java z innymi językami programowania?
Aspose.Page obsługuje przede wszystkim Javę, ale dostępne są również wersje dla innych języków programowania.
### Czy dostępna jest bezpłatna wersja próbna Aspose.Page dla Java?
 Tak, możesz uzyskać dostęp do bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
### Jak mogę uzyskać tymczasową licencję na Aspose.Page dla Java?
 Możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
### Gdzie mogę znaleźć wsparcie społeczności i dyskusje dotyczące Aspose.Page dla Java?
 Odwiedzić[Forum Aspose.Page](https://forum.aspose.com/c/page/39) za wsparcie społeczności.
### Czy są jakieś dodatkowe zasoby potrzebne do zakupu Aspose.Page dla Java?
 Można kupić bibliotekę[Tutaj](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
