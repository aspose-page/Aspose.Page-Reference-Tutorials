---
date: 2025-12-28
description: Dowiedz się, jak dodać obraz do dokumentów XPS w Javie przy użyciu Aspose.Page.
  Ten przewodnik krok po kroku pokaże Ci, jak łatwo dodawać obrazy i usprawniać przetwarzanie
  dokumentów.
linktitle: Add Image in Java XPS
second_title: Aspose.Page Java API
title: Jak dodać obraz do dokumentów XPS w Javie – prosty przewodnik z Aspose.Page
url: /pl/java/xps-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dodać obraz do dokumentów Java XPS przy użyciu Aspose.Page

Dodawanie obrazów do plików XPS jest powszechnym wymaganiem dla programistów Java, którzy potrzebują wzbogacić raporty, faktury lub dowolny dokument wizualny. W tym samouczku odkryjesz **jak dodać obraz** do dokumentu XPS przy użyciu potężnej biblioteki Aspose.Page for Java. Przejdziemy przez każdy krok, wyjaśnimy, dlaczego każda linia ma znaczenie, i podpowiemy, jak uniknąć typowych pułapek.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebujesz?** Aspose.Page for Java  
- **Czy mogę dodać wiele obrazów?** Tak – powtórz kroki dodawania obrazu dla każdego zdjęcia  
- **Obsługiwane formaty obrazów?** TIFF, JPEG, PNG, GIF (i inne obsługiwane przez .NET)  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa w ocenie; licencja komercyjna jest wymagana w produkcji  
- **Typowy czas implementacji?** Około 10‑15 minut dla podstawowego wstawienia obrazu

## Wprowadzenie
Dodawanie obrazów do dokumentów XPS jest powszechnym wymaganiem w wielu aplikacjach Java, od generowania raportów po przetwarzanie dokumentów. Aspose.Page for Java upraszcza to zadanie, oferując wydajne metody umożliwiające płynne integrowanie obrazów w plikach XPS. W tym samouczku pokażemy, jak dodać obraz do dokumentu XPS przy użyciu Aspose.Page for Java.

## Wymagania wstępne
Zanim zagłębisz się w samouczek, upewnij się, że masz następujące wymagania wstępne:
1. **Aspose.Page for Java Library** – Pobierz i zainstaluj bibliotekę Aspose.Page for Java z [strony internetowej](https://releases.aspose.com/page/java/).  
2. **Java Development Environment** – Upewnij się, że masz skonfigurowane środowisko programistyczne Java na swoim komputerze.

Teraz przejdźmy do kolejnych kroków.

## Importowanie pakietów
W swoim projekcie Java zaimportuj niezbędne pakiety Aspose.Page for Java, aby uzyskać dostęp do wymaganych klas i metod.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.geom.Rectangle2D;
```

## Krok 1: Ustaw katalog dokumentu
Zdefiniuj ścieżkę do katalogu dokumentu, w którym będą przechowywane plik XPS oraz pliki obrazów.

```java
String dataDir = "Your Document Directory";
```

## Krok 2: Utwórz nowy dokument XPS
Zainicjalizuj nowy dokument XPS przy użyciu poniższego fragmentu kodu:

```java
XpsDocument doc = new XpsDocument();
```

## Krok 3: Dodaj obraz do dokumentu XPS
Aby dodać obraz, utwórz ścieżkę w dokumencie XPS i ustaw pędzel obrazu przy użyciu podanego pliku obrazu oraz współrzędnych.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.setRenderTransform(doc.createMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f));
path.setFill(doc.createImageBrush(dataDir + "QL_logo_color.tif", new Rectangle2D.Double(0f, 0f, 258.24f, 56.64f), new Rectangle2D.Double(50f, 20f, 193.68f, 42.48f)));
```

## Krok 4: Zapisz wynikowy dokument XPS
Zapisz zmodyfikowany dokument XPS w określonym katalogu.

```java
doc.save(dataDir + "AddImage_out.xps");
```

Powtórz te kroki, aby dodać więcej obrazów lub dostosować istniejące zgodnie z wymaganiami projektu.

## Zakończenie
Gratulacje! Pomyślnie nauczyłeś się **jak dodać obraz** do dokumentu XPS przy użyciu Aspose.Page for Java. Ta umiejętność jest nieoceniona w podnoszeniu atrakcyjności wizualnej Twoich aplikacji Java i dokumentów.

### Najczęściej zadawane pytania
### Czy mogę dodać wiele obrazów do tego samego dokumentu XPS przy użyciu Aspose.Page for Java?
Tak, możesz dodać wiele obrazów, powtarzając kroki opisane w tym samouczku dla każdego obrazu.

### Jakie formaty obrazów są obsługiwane przez Aspose.Page for Java?
Aspose.Page for Java obsługuje różne formaty obrazów, w tym TIFF, JPEG, PNG i GIF.

### Czy dostępna jest wersja próbna Aspose.Page for Java?
Tak, możesz uzyskać darmową wersję próbną Aspose.Page for Java z [tego linku](https://releases.aspose.com/).

### Jak mogę uzyskać tymczasową licencję na Aspose.Page for Java?
Możesz uzyskać tymczasową licencję pod [tym linkiem](https://purchase.aspose.com/temporary-license/).

### Gdzie mogę znaleźć dodatkowe wsparcie lub dyskutować o problemach związanych z Aspose.Page for Java?
Odwiedź [forum Aspose.Page](https://forum.aspose.com/c/page/39), aby uzyskać pomoc, podzielić się doświadczeniami i połączyć się ze społecznością Aspose.Page.

## Dodatkowe wskazówki i typowe pułapki
- **Dokładność geometrii ścieżki** – Upewnij się, że ciąg ścieżki w stylu SVG odpowiada wymiarom Twojego obrazu; w przeciwnym razie obraz może wyglądać rozciągnięty lub przycięty.  
- **Skalowanie pędzla obrazu** – Metoda `createImageBrush` przyjmuje prostokąty źródłowy i docelowy; dostosowanie tych wartości pozwala precyzyjnie kontrolować pozycjonowanie i skalowanie.  
- **Aktywacja licencji** – Jeśli uruchomisz kod bez ważnej licencji, Aspose doda znak wodny do wygenerowanego pliku XPS.

---

**Last Updated:** 2025-12-28  
**Testowane z:** Aspose.Page for Java 23.12 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}