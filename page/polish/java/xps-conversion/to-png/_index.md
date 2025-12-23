---
date: 2025-12-23
description: Bezproblemowo **konwertuj XPS na PNG** w Javie przy użyciu Aspose.Page.
  Ten przewodnik pokazuje, jak renderować XPS do plików graficznych przy użyciu niezawodnego,
  przyjaznego programistom rozwiązania.
linktitle: Convert XPS to PNG in Java
second_title: Aspose.Page Java API
title: Konwertuj XPS na PNG w Javie
url: /pl/java/xps-conversion/to-png/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konwertowanie XPS do PNG w Javie

## Wstęp
W dynamicznym świecie tworzenia oprogramowania często pojawia się potrzeba **konwersji XPS do PNG** (XML Paper Specification do Portable Network Graphics). Aby wykonać to zadanie płynnie w Javie, Aspose.Page oferuje potężne rozwiązanie. W tym samouczku przeprowadzimy proces konwersji XPS do PNG przy użyciu Aspose.Page dla Javy.

## Szybkie odpowiedzi
- **Jaką bibliotekę obsługuje konwersję?** Aspose.Page dla Javy  
- **Jakie formaty są zaangażowane?** XPS (źródło) → PNG (wyjście)  
- **Czy potrzebuję licencji do produkcji?** Tak, wymagana jest licencja komercyjna  
- **Czy mogę ustawić rozdzielczość obrazu?** Tak, używając `PngSaveOptions.setResolution()`  
- **Czy można wybrać konkretne strony?** Oczywiście – podaj numery stron w obiekcie opcji  

## Dlaczego konwertować XPS do PNG?
Renderowanie XPS do plików graficznych jest przydatne, gdy trzeba wyświetlać dokumenty w sieci, osadzać je w raportach lub generować miniatury podglądu. PNG oferuje bezstratną kompresję i szerokie wsparcie przeglądarek, co czyni go idealnym wyborem dla wysokiej jakości wizualnych reprezentacji treści XPS.

## Wymagania wstępne
Zanim przejdziemy do samouczka, upewnij się, że masz przygotowane następujące elementy:
1. **Java Development Kit (JDK):** Upewnij się, że masz zainstalowany JDK w systemie.  
2. **Aspose.Page dla Javy:** Pobierz i zainstaluj bibliotekę Aspose.Page. Link do pobrania znajdziesz [tutaj](https://releases.aspose.com/page/java/).  
3. **Zintegrowane Środowisko Programistyczne (IDE):** Wybierz IDE kompatybilne z Javą, np. IntelliJ IDEA lub Eclipse.  

## Jak konwertować XPS do PNG w Javie
Poniżej znajduje się przewodnik krok po kroku, który wyjaśnia **jak konwertować** dokumenty XPS na obrazy PNG, wraz z fragmentami kodu, które możesz skopiować bezpośrednio do swojego projektu.

### Importowanie pakietów
W swoim projekcie Java zaimportuj niezbędne pakiety, aby wykorzystać funkcje Aspose.Page. Dodaj następujące instrukcje importu na początku pliku Java:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

### Krok 1: Ustaw katalog dokumentu
Zdefiniuj folder, który zawiera źródłowy plik XPS oraz miejsce, w którym zostaną zapisane pliki PNG.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Krok 2: Załaduj dokument XPS
Utwórz instancję `XpsDocument`, która wczyta źródłowy plik XPS.

```java
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Krok 3: Zainicjalizuj opcje
Skonfiguruj opcje wyjściowe PNG. Tutaj możesz ustawić wygładzanie, rozdzielczość oraz określić, które strony mają zostać wyrenderowane.

```java
// Initialize options object with necessary parameters.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### Krok 4: Utwórz urządzenie renderujące
Utwórz `ImageDevice`, które będzie przechowywać dane wyrenderowanego obrazu.

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

### Krok 5: Zapisz i iteruj
Wyrenderuj dokument XPS, a następnie zapisz każdy wygenerowany bajtowy ciąg PNG do pliku na dysku.

```java
// Save XPS document to PNG using options and device
document.save(device, options);
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Close the Stream
        imageStream.close();
    }
}
```

Postępując zgodnie z tymi krokami, możesz bez trudu **renderować XPS do plików graficznych** w formacie PNG przy użyciu Aspose.Page dla Javy.

## Podsumowanie
Podsumowując, Aspose.Page dla Javy upraszcza proces konwersji XPS do PNG, dostarczając programistom niezawodne i wydajne narzędzie. Włącz tę bibliotekę do swoich projektów Java, aby usprawnić zadania związane z manipulacją dokumentami.

## FAQ
### Czy mogę używać Aspose.Page dla Javy w projektach komercyjnych?
Tak, Aspose.Page jest produktem komercyjnym. Informacje o licencjonowaniu znajdziesz [tutaj](https://purchase.aspose.com/buy).

### Czy dostępna jest darmowa wersja próbna?
Tak, możesz wypróbować darmową wersję próbną [tutaj](https://releases.aspose.com/).

### Gdzie mogę znaleźć dokumentację Aspose.Page dla Javy?
Kompleksowa dokumentacja jest dostępna [tutaj](https://reference.aspose.com/page/java/).

### Jak uzyskać tymczasową licencję do celów testowych?
Tymczasową licencję możesz uzyskać [tutaj](https://purchase.aspose.com/temporary-license/).

### Czy istnieją fora społecznościowe dotyczące dyskusji o Aspose.Page?
Tak, odwiedź fora społecznościowe [tutaj](https://forum.aspose.com/c/page/39).

## Dodatkowe często zadawane pytania

**Q: Czy mogę konwertować tylko wybrane strony pliku XPS?**  
A: Oczywiście. Użyj metody `setPageNumbers` w `PngSaveOptions`, aby określić strony, które chcesz wyrenderować.

**Q: Jaka rozdzielczość obrazu jest zalecana dla wysokiej jakości PNG?**  
A: Rozdzielczość 300 dpi to dobry kompromis między jakością a rozmiarem pliku, ale możesz ją dostosować za pomocą `options.setResolution()`.

**Q: Czy API obsługuje konwersję wielowątkową dla dużych dokumentów?**  
A: Tak, możesz wywoływać logikę konwersji w równoległych wątkach, każdy obsługujący inną stronę lub część dokumentu.

**Q: Jak radzić sobie z zużyciem pamięci przy konwersji bardzo dużych plików XPS?**  
A: Przetwarzaj strony kolejno i zwalniaj `FileOutputStream` po każdym zapisie, jak pokazano w przykładowym kodzie.

**Q: Czy istnieje sposób na dodanie własnych metadanych do wygenerowanych plików PNG?**  
A: Chociaż `PngSaveOptions` nie udostępnia bezpośrednio pól metadanych, możesz po przetworzeniu PNG użyć standardowych bibliotek graficznych do osadzenia metadanych.

---

**Ostatnia aktualizacja:** 2025-12-23  
**Testowano z:** Aspose.Page dla Javy 24.12 (najnowsza)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}