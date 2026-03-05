---
date: 2025-12-28
description: Dowiedz się, jak tworzyć dokument XPS w Javie przy użyciu Aspose.Page
  i bez wysiłku dodać obraz w trybie kafelkowym, korzystając z tego przewodnika krok
  po kroku.
linktitle: Add Tiled Image in Java XPS
second_title: Aspose.Page Java API
title: Jak utworzyć dokument XPS z obrazem kafelkowanym w Javie
url: /pl/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz dokument XPS i dodaj obraz kafelkowy w Javie

## Wprowadzenie
W nowoczesnym rozwoju aplikacji Java umiejętność **utworzenia dokumentu XPS** programowo jest cenną kompetencją, szczególnie gdy trzeba wzbogacić go o grafikę, taką jak obrazy kafelkowe. Aspose.Page for Java upraszcza ten proces, pozwalając skupić się na projekcie wizualnym zamiast na niskopoziomowej obsłudze plików. W tym samouczku dowiesz się dokładnie, jak **utworzyć dokument XPS**, **dodać obraz kafelkowy** i zapisać wynik, korzystając z przejrzystych przykładów kodu krok po kroku.

## Szybkie odpowiedzi
- **Co robi Aspose.Page?** Udostępnia wysokopoziomowe API do generowania i manipulacji dokumentami XPS w Javie.  
- **Czy mogę kafelkować obraz?** Tak – użyj `XpsImageBrush` z `XpsTileMode.Tile`.  
- **Czy potrzebna jest licencja?** Wymagana jest tymczasowa lub komercyjna licencja do użytku produkcyjnego.  
- **Jaką wersję Javy obsługuje?** Każdy JDK 8+ jest kompatybilny.  
- **Jak długo trwa implementacja?** Około 10–15 minut dla podstawowego scenariusza obrazu kafelkowego.

## Co to jest „utworzyć dokument XPS”?
Plik XPS (XML Paper Specification) to format dokumentu o stałym układzie, podobny do PDF. Programowe tworzenie dokumentu XPS pozwala generować pliki gotowe do druku, niezależne od urządzenia, bezpośrednio z kodu Java.

## Dlaczego dodać obraz kafelkowy?
Kafelkowanie obrazu powiela grafikę na określonym obszarze, co jest idealne dla tła, znaków wodnych lub wypełnień wzorem. Dzięki `XpsTileMode.Tile` w Aspose.Page możesz to osiągnąć w kilku linijkach kodu.

## Wymagania wstępne
Przed rozpoczęciem upewnij się, że masz:

1. **Java Development Kit (JDK)** – zainstalowany JDK 8 lub nowszy.  
2. **Aspose.Page for Java** – pobierz ze [strony internetowej](https://releases.aspose.com/page/java/).  
3. **Katalog zapisu** – w którym zostanie zapisany wygenerowany plik XPS.

## Importowanie pakietów
W swoim projekcie Java zaimportuj niezbędne klasy:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Przewodnik krok po kroku

### Krok 1: Konfiguracja projektu
Dodaj pliki JAR Aspose.Page do classpath swojego projektu i zweryfikuj, że instrukcje importu kompilują się bez błędów.

### Krok 2: Utwórz dokument XPS
Zainicjuj nowy obiekt `XpsDocument`. To podstawowy kontener, który będzie przechowywał wszystkie strony, ścieżki i zasoby.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Krok 3: Zdefiniuj ścieżkę obrazu kafelkowego
Umieść obraz, który chcesz kafelkować (np. `R08LN_NN.jpg`) w katalogu wskazywanym przez `dataDir`. Obraz zostanie użyty jako wzorzec pędzla.

### Krok 4: Dodaj obraz kafelkowy
Utwórz prostokątną ścieżkę i wypełnij ją `XpsImageBrush`. Ustawiając tryb kafelkowania na `Tile`, obraz będzie powtarzał się w całym prostokącie.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### Krok 5: Zapisz dokument
Zachowaj plik XPS na dysku. Plik wyjściowy będzie zawierał obraz kafelkowy, który właśnie zdefiniowałeś.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Powtarzaj te kroki, gdy tylko będziesz musiał **dodać obraz kafelkowy** do innych stron lub kształtów w tym samym dokumencie XPS.

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|---------|-------------|
| Obraz się nie wyświetla | Zweryfikuj, czy ścieżka pliku (`dataDir + "R08LN_NN.jpg"`) jest poprawna i czy obraz jest dostępny. |
| Wzór kafelkowy jest rozciągnięty | Dostosuj wartości źródłowego i docelowego `Rectangle2D`, aby kontrolować rozmiar kafelka. |
| Przezroczystość nie działa | Upewnij się, że przezroczystość pędzla jest ustawiona **po** skonfigurowaniu trybu kafelkowania. |

## Najczęściej zadawane pytania

### Czy Aspose.Page jest kompatybilny ze wszystkimi wersjami Javy?
Aspose.Page jest zaprojektowany tak, aby działać z różnymi wersjami Javy. Sprawdź kompatybilność w dokumentacji [tutaj](https://reference.aspose.com/page/java/).

### Czy mogę używać Aspose.Page w projektach komercyjnych?
Tak, Aspose.Page oferuje licencje komercyjne. Kup je [tutaj](https://purchase.aspose.com/buy).

### Czy dostępna jest darmowa wersja próbna?
Tak, wypróbuj funkcje Aspose.Page w darmowej wersji próbnej [tutaj](https://releases.aspose.com/).

### Gdzie mogę znaleźć wsparcie społeczności i dyskusje?
Dołącz do społeczności Aspose.Page na [forum](https://forum.aspose.com/c/page/39).

### Jak mogę uzyskać tymczasową licencję na Aspose.Page?
Uzyskaj tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/).

---

**Ostatnia aktualizacja:** 2025-12-28  
**Testowano z:** Aspose.Page for Java 24.12 (latest)  
**Autor:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
