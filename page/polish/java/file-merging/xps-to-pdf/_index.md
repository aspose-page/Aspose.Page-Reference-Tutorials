---
date: 2025-11-29
description: Dowiedz się, jak zapisać XPS jako PDF w Javie przy użyciu Aspose.Page
  Java. Skorzystaj z naszego przewodnika krok po kroku, aby efektywnie konwertować
  XPS na PDF oraz ustawiać kompresję PDF.
linktitle: Convert XPS to PDF in Java using Aspose.Page Java
second_title: Aspose.Page Java API
title: Konwertuj XPS na PDF w Javie przy użyciu Aspose.Page Java
url: /pl/java/file-merging/xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konwertowanie XPS do PDF w Javie przy użyciu Aspose.Page Java

## Wstęp
W tym samouczku dowiesz się **jak konwertować XPS do PDF w Javie przy użyciu Aspose.Page Java**, solidnej biblioteki przeznaczonej do konwersji dokumentów w Javie. Niezależnie od tego, czy musisz przetwarzać faktury wsadowo, generować raporty do druku, czy po prostu migrować starsze pliki XPS, Aspose.Page Java wykona zadanie szybko, niezawodnie i w pełni konfigurowalnie.

## Szybkie odpowiedzi
- **Jaką bibliotekę używać do konwersji XPS na PDF?** Aspose.Page Java  
- **Jak długo trwa podstawowa konwersja?** Zazwyczaj poniżej sekundy dla jednopostaciowego pliku XPS.  
- **Czy potrzebna jest licencja do programowania?** Darmowa wersja próbna wystarczy do oceny; licencja jest wymagana w środowisku produkcyjnym.  
- **Czy mogę kontrolować kompresję PDF?** Tak – użyj `PdfSaveOptions`, aby ustawić kompresję obrazów i tekstu.  
- **Jakiej wersji Javy wymaga biblioteka?** Java 8 lub nowsza (zalecany JDK 11+).

## Co to jest Aspose.Page Java?
Aspose.Page Java to **wydajny interfejs API**, który umożliwia programistom tworzenie, edytowanie i konwertowanie dokumentów XPS w sposób programowy. Obsługuje renderowanie XPS do PDF, PNG, JPEG i innych formatów, dając jednocześnie precyzyjną kontrolę nad ustawieniami wyjściowymi, takimi jak **ustawienie kompresji PDF**.

## Dlaczego warto używać Aspose.Page Java do konwersji XPS‑do‑PDF?
- **Renderowanie bez zależności** – bez bibliotek natywnych i zewnętrznych narzędzi.  
- **Dokładne zachowanie układu** – wyjściowy PDF odzwierciedla oryginalny wygląd XPS.  
- **Pełna kontrola nad wyjściem PDF** – możesz regulować jakość obrazów, wybierać algorytmy kompresji i określać konkretne strony do renderowania.  
- **Wieloplatformowość** – działa na Windows, Linux i macOS z dowolnym standardowym JDK.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

1. **Java Development Kit (JDK) 8+** – zalecany najnowszy JDK ze względu na wydajność i bezpieczeństwo.  
2. **Bibliotekę Aspose.Page for Java** – pobierz plik JAR z oficjalnej [dokumentacji Aspose.Page Java](https://reference.aspose.com/page/java/).  
3. **IDE** (IntelliJ IDEA, Eclipse, VS Code) lub prosty edytor tekstu wraz z narzędziami budowania wiersza poleceń (Maven/Gradle).  

## Importowanie pakietów
Dodaj niezbędne importy do swojej klasy Java, aby móc pracować z dokumentami XPS i wyjściem PDF.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.rendering.pdf.PdfDevice;
import com.aspose.xps.rendering.pdf.PdfSaveOptions;
import com.aspose.xps.rendering.pdf.PdfImageCompression;
import com.aspose.xps.rendering.pdf.PdfTextCompression;
import java.io.FileOutputStream;
```

## Przewodnik krok po kroku

### Krok 1: Ustaw ścieżkę katalogu dokumentu
Zdefiniuj folder zawierający plik źródłowy XPS oraz miejsce, w którym zostanie zapisany PDF.

```java
String dataDir = "C:/MyDocuments/XpsFiles/";   // <-- replace with your actual path
```

### Krok 2: Zainicjuj strumień wyjściowy PDF
Utwórz `FileOutputStream`, który wskaże na docelowy plik PDF.

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

> **Wskazówka:** Użyj `try‑with‑resources`, aby automatycznie zamykać strumień i uniknąć wycieków zasobów.

### Krok 3: Załaduj dokument XPS
Zainicjuj obiekt `XpsDocument`, ładując plik źródłowy XPS.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Krok 4: Zainicjuj opcje zapisu PDF (Ustaw kompresję PDF)
Skonfiguruj, w jaki sposób PDF ma być kompresowany. Ten krok pozwala **ustawić kompresję PDF** dla obrazów i tekstu, co zmniejsza rozmiar pliku bez utraty jakości.

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);                         // maximum JPEG quality
options.setImageCompression(PdfImageCompression.Jpeg);   // compress images as JPEG
options.setTextCompression(PdfTextCompression.Flate);    // compress text streams
options.setPageNumbers(new int[] { 1, 2, 6 });            // optional: export only selected pages
```

> **Dlaczego to ważne:** Dostosowanie jakości JPEG i typów kompresji może zmniejszyć 10 MB PDF do poniżej 2 MB, zachowując wymaganą wierność wizualną.

### Krok 5: Utwórz urządzenie renderujące dla formatu PDF
`PdfDevice` przesyła wyrenderowane strony do strumienia wyjściowego PDF.

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### Krok 6: Zapisz dokument
Na koniec wyrenderuj zawartość XPS do PDF przy użyciu skonfigurowanych opcji.

```java
document.save(device, options);
```

> **Rezultat:** Po wykonaniu, plik `XPStoPDF.pdf` pojawi się w folderze `dataDir`, zawierając skonwertowane strony z ustawieniami kompresji, które określiłeś.

## Typowe problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|-------|-------|----------|
| **`FileNotFoundException`** | Nieprawidłowa ścieżka `dataDir` | Sprawdź, czy katalog istnieje oraz czy aplikacja ma uprawnienia odczytu/zapisu. |
| **Puste strony PDF** | Brak inicjalizacji `PdfDevice` | Upewnij się, że `PdfDevice` został utworzony z tym samym `FileOutputStream`, który jest używany do wyjścia. |
| **Duży rozmiar PDF** | Domyślna kompresja jest niska | Zwiększ `setJpegQualityLevel` lub przełącz na `PdfImageCompression.Jpeg` z niższą jakością. |
| **Wyświetlane tylko niektóre strony** | Filtr `setPageNumbers` wyklucza strony | Zmodyfikuj tablicę, aby zawierała wszystkie potrzebne numery stron lub usuń wywołanie, aby wyeksportować wszystkie strony. |

## Najczęściej zadawane pytania

**P: Czy Aspose.Page Java jest kompatybilny z różnymi wersjami Javy?**  
O: Tak, Aspose.Page Java obsługuje Java 8 aż do Java 21, w tym dystrybucje Oracle i OpenJDK.

**P: Czy mogę dostosować ustawienia kompresji dla konwertowanego PDF?**  
O: Oczywiście. Użyj `PdfSaveOptions`, aby ustawić jakość JPEG, typ kompresji obrazu i kompresję tekstu, jak pokazano w Kroku 4.

**P: Gdzie mogę znaleźć dodatkowe wsparcie lub dyskusje społeczności?**  
O: Odwiedź [forum Aspose.Page](https://forum.aspose.com/c/page/39), aby uzyskać pomoc społeczności, przykłady kodu i wskazówki rozwiązywania problemów.

**P: Czy dostępna jest darmowa wersja próbna Aspose.Page?**  
O: Tak, możesz pobrać w pełni funkcjonalną wersję próbną ze [strony pobierania Aspose](https://releases.aspose.com/).

**P: Jak mogę uzyskać tymczasową licencję na Aspose.Page?**  
O: Tymczasową licencję można zamówić [tutaj](https://purchase.aspose.com/temporary-license/).

## Podsumowanie
Korzystając z **Aspose.Page Java**, możesz bez wysiłku **zapisać XPS jako PDF** i kontrolować każdy aspekt wyjścia, od wyboru stron po kompresję. Ten samouczek przedstawił wszystko, co potrzebne, aby zintegrować konwersję XPS‑do‑PDF w aplikacjach Java, niezależnie od tego, czy tworzysz jednorazowe narzędzie, czy rozbudowaną linię przetwarzania dokumentów.

---

**Ostatnia aktualizacja:** 2025-11-29  
**Testowano z:** Aspose.Page for Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}