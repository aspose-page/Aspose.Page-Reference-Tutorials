---
date: 2025-12-21
description: Dowiedz się, jak odczytywać metadane XMP przy użyciu Javy i Aspose.Page.
  Ten przewodnik krok po kroku pokazuje, jak odczytać XMP w formacie dokumentu i wyodrębnić
  kluczowe właściwości.
linktitle: How to Read XMP Metadata using Java
second_title: Aspose.Page Java API
title: Jak odczytać metadane XMP w Javie – Przewodnik Aspose.Page
url: /pl/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pobieranie metadanych XMP przy użyciu Javy

## Jak odczytać metadane XMP przy użyciu Javy

Witamy w naszym samouczku krok po kroku, który pokazuje **jak odczytać XMP** przy użyciu Javy i biblioteki Aspose.Page. XMP (Extensible Metadata Platform) jest szeroko przyjętym standardem umożliwiającym osadzanie bogatych metadanych w dokumentach. Po zakończeniu tego przewodnika będziesz w stanie odczytać XMP formatu dokumentu, wyciągnąć informacje o twórcy, znaczniki czasu, miniatury i wiele więcej — co pozwoli Ci budować inteligentniejsze rozwiązania analizy dokumentów.

## Szybkie odpowiedzi
- **Co oznacza „jak odczytać xmp”?** Odnosi się do programowego wyodrębniania metadanych XMP z plików.  
- **Jakiej biblioteki potrzebuję?** Aspose.Page for Java (dostępna na stronie pobierania Aspose).  
- **Czy potrzebna jest licencja?** Do użytku produkcyjnego wymagana jest tymczasowa lub pełna licencja; dostępna jest wersja próbna.  
- **Jaką wersję Javy obsługuje?** Java 8 lub nowsza.  
- **Czy mogę odczytać XMP z innych formatów?** Tak, Aspose.Page obsługuje EPS, PDF oraz kilka typów obrazów, które zawierają XMP.

## Wymagania wstępne
Zanim przejdziesz do kodu, upewnij się, że masz:

- **Java Development Kit (JDK)** – Java 8+ zainstalowaną i skonfigurowaną na Twoim komputerze.  
- **Aspose.Page for Java** – Pobierz bibliotekę z oficjalnej strony [here](https://releases.aspose.com/page/java/).  
- Plik EPS zawierający metadane XMP (np. `xmp1.eps`).  

## Importowanie pakietów
W swoim projekcie Java zaimportuj niezbędne pakiety:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Krok 1: Inicjalizacja strumienia wejściowego pliku EPS
Ustaw ścieżkę do katalogu dokumentów i zainicjalizuj strumień wejściowy pliku EPS.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## Krok 2: Pobranie metadanych XMP
Pobierz metadane XMP z pliku EPS. Jeśli plik nie zawiera metadanych XMP, zostaną wygenerowane nowe na podstawie komentarzy PS.
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Krok 3: Wyodrębnienie informacji o CreatorTool
Sprawdź i wypisz wartość „CreatorTool” z metadanych XMP.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Krok 4: Wyodrębnienie informacji o CreateDate
Sprawdź i wypisz wartość „CreateDate” z metadanych XMP.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Krok 5: Pobranie szerokości miniatury
Jeśli istnieją miniatury, wyodrębnij i wypisz szerokość pierwszej miniatury.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Krok 6: Wyodrębnienie informacji o formacie
Sprawdź i wypisz wartość „format” z metadanych XMP.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Krok 7: Pobranie DocumentID
Sprawdź i wypisz wartość „DocumentID” z metadanych XMP.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Dlaczego to ważne
Odczytywanie metadanych XMP pozwala programowo odkrywać pochodzenie, datę utworzenia i inne kluczowe atrybuty dokumentu bez otwierania go w przeglądarce. Jest to szczególnie przydatne przy przetwarzaniu wsadowym, systemach zarządzania treścią oraz w cyfrowych pipeline’ach zasobów, gdzie metadane napędzają indeksowanie i wyszukiwanie.

## Typowe pułapki i wskazówki
- **Brak XMP:** Niektóre pliki EPS mogą nie zawierać XMP. Wywołanie `getXmpMetadata()` wygeneruje minimalny zestaw na podstawie istniejących komentarzy PS, ale nie uzyskasz pełnych metadanych, jeśli nie są osadzone.  
- **Tablice miniatur:** Klucz `xmp:Thumbnails` może zawierać wiele wpisów. Przykład wyodrębnia tylko pierwszy; iteruj tablicę, jeśli potrzebujesz wszystkich miniatur.  
- **Świadomość przestrzeni nazw:** Klucze XMP używają przestrzeni nazw (np. `xmp:`, `dc:`). Upewnij się, że odwołujesz się do dokładnej nazwy klucza; w przeciwnym razie `containsKey` zwróci false.

## Najczęściej zadawane pytania
### Czy mogę używać Aspose.Page for Java z innymi językami programowania?
Tak, Aspose.Page obsługuje wiele języków, w tym Java, .NET i inne. Sprawdź [documentation](https://reference.aspose.com/page/java/) po szczegóły.

### Czy dostępna jest darmowa wersja próbna Aspose.Page for Java?
Tak, darmową wersję próbną znajdziesz [here](https://releases.aspose.com/).

### Gdzie mogę uzyskać wsparcie dla Aspose.Page for Java?
Odwiedź forum [Aspose.Page](https://forum.aspose.com/c/page/39) dla wsparcia społeczności.

### Jak uzyskać tymczasową licencję dla Aspose.Page for Java?
Tymczasową licencję możesz pobrać [here](https://purchase.aspose.com/temporary-license/).

### Czy istnieją dodatkowe zasoby dla Aspose.Page for Java?
Przeglądaj pełną [documentation](https://reference.aspose.com/page/java/) i pobierz bibliotekę [here](https://releases.aspose.com/page/java/).

## Dodatkowe FAQ
**P: Czy to podejście działa z plikami PDF zawierającymi XMP?**  
O: Tak, Aspose.Page może odczytywać XMP z PDF, EPS oraz kilku formatów obrazów.

**P: Czy mogę modyfikować metadane XMP po ich odczytaniu?**  
O: Oczywiście. Obiekt `XmpMetadata` jest mutowalny; możesz dodawać, aktualizować lub usuwać klucze, a następnie zapisać dokument.

**P: Czy istnieje sposób na wyodrębnienie wszystkich obrazów miniatur, a nie tylko ich wymiarów?**  
O: Możesz pobrać dane binarne z właściwości `xmpGImg:data` każdego wpisu miniatury i zapisać je do pliku.

## Zakończenie
Teraz opanowałeś **jak odczytać XMP** przy użyciu Javy i Aspose.Page. Postępując zgodnie z tymi krokami, możesz wyodrębnić narzędzia twórcy, znaczniki czasu, miniatury, informacje o formacie oraz identyfikatory dokumentów — uzyskując pełny wgląd w osadzone metadane swoich plików EPS. Zachęcamy do eksperymentowania z dodatkowymi przestrzeniami nazw XMP, aby wydobywać jeszcze bogatsze dane dla swoich aplikacji.

---

**Ostatnia aktualizacja:** 2025-12-21  
**Testowane z:** Aspose.Page for Java 24.12 (latest)  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
