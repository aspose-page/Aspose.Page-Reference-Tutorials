---
date: 2026-03-08
description: Dowiedz się, jak konwertować XPS na BMP w Javie i ustawiać rozdzielczość
  BMP przy użyciu biblioteki konwersji obrazów Aspose.Page dla Javy. Ten przewodnik
  obejmuje wysokiej jakości wyjście oraz wskazówki przyjazne dla pamięci.
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: Konwertuj XPS na BMP w Javie – Ustaw rozdzielczość dla wysokiej jakości wyjścia
url: /pl/java/xps-conversion/to-bmp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konwertuj XPS do BMP w Javie

## Wprowadzenie
Witamy w tym przewodniku krok po kroku, jak **konwertować XPS do BMP** w Javie i ustawić rozdzielczość dla optymalnej jakości obrazu przy użyciu Aspose.Page. Niezależnie od tego, czy budujesz pipeline drukowania, generujesz miniatury, czy potrzebujesz grafiki wysokiej rozdzielczości, kontrolowanie DPI daje Ci elastyczność spełnienia każdego wymagania.

## Szybkie odpowiedzi
- **Jakiej biblioteki powinienem używać?** Aspose.Page for Java jest najpełniejszą **java image conversion library** dla XPS → BMP.  
- **Czy mogę kontrolować jakość obrazu?** Tak – użyj `BmpSaveOptions`, aby **ustawić rozdzielczość BMP** i tryb wygładzania.  
- **Jak uniknąć OutOfMemoryError w Javie przy przetwarzaniu dużych plików XPS?** Renderuj strony w partiach lub zwiększ pamięć sterty JVM (`-Xmx`).  
- **Czy muszę konwertować tylko określone strony?** Oczywiście, `options.setPageNumbers()` pozwala wybrać dokładne strony.  
- **Jakie wersje Javy są wspierane?** Wszystkie nowoczesne wersje Javy (8 i wyższe) działają bezproblemowo.

## Jaki jest cel ustawiania rozdzielczości?
Rozdzielczość określa liczbę punktów na cal (DPI) w wygenerowanym obrazie BMP. Wyższe DPI daje ostrzejsze obrazy, co jest niezbędne przy drukowaniu lub szczegółowej pracy graficznej. Dostosowanie rozdzielczości daje pełną kontrolę nad jakością wyjściową Twojego **convert xps to bmp** workflow.

## Dlaczego używać Aspose.Page do konwersji XPS → BMP?
- **Wysoka wierność** – zachowuje jakość wektorową oryginalnego XPS.  
- **Precyzyjna kontrola** – możesz ustawić DPI, wygładzanie oraz nawet wybrać konkretne strony do konwersji.  
- **Brak zewnętrznych zależności** – czysta Java, nie wymaga natywnych bibliotek.  
- **Skalowalny** – działa zarówno dla dokumentów jednosktronicowych, jak i dużych, wielostronicowych plików XPS.  

## Prerequisites
Zanim zagłębisz się w proces konwersji, upewnij się, że masz następujące wymagania wstępne:
- **Środowisko programistyczne Java** – Java 8 lub nowsza zainstalowana na Twoim komputerze.  
- **Biblioteka Aspose.Page for Java** – Pobierz i dołącz bibliotekę Aspose.Page for Java do swojego projektu. Bibliotekę znajdziesz [tutaj](https://releases.aspose.com/page/java/).  
- **Przykładowy plik XPS** – Przygotuj przykładowy dokument XPS, który chcesz przekonwertować do BMP.

## Importowanie pakietów
Include the necessary Aspose.Page packages in your Java code:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Jak ustawić rozdzielczość dla konwersji XPS do BMP
Poniżej znajduje się zwięzły, numerowany przewodnik, który pokazuje dokładnie, gdzie i jak ustawić rozdzielczość, a także jak **konwertować określone strony**.

### Krok 1: Załaduj dokument XPS
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Krok 2: Zainicjuj opcje (Rozdzielczość i wybór stron)
```java
// Initialize options object with necessary parameters.
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);

// Primary setting – this is the **how to set resolution** part.
options.setResolution(300);               // 300 DPI for high‑quality output

// Optional: convert specific pages only (e.g., pages 1, 2, and 6)
options.setPageNumbers(new int[]{1, 2, 6});
```

### Krok 3: Utwórz urządzenie renderujące
```java
// Create rendering device for BMP format
ImageDevice device = new ImageDevice();
```

### Krok 4: Zapisz dokument przy użyciu opcji
```java
// Save XPS document to BMP using options and device
document.save(device, options);
```

### Krok 5: Iteruj przez wyrenderowane obrazy i zapisz pliki
```java
// Iterate through document partitions
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoBMP" + "_" + (i + 1) + "_" + (j + 1) + ".bmp");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```

Powtórz te kroki dla dowolnych dodatkowych dostosowań lub modyfikacji, które mogą być potrzebne w procesie konwersji.

## Jak uniknąć OutOfMemoryError w Javie przy konwersji dużych plików XPS
- **Przetwarzaj w partiach** – Przykład już renderuje dokument w partiach (`device.getResult()`), co zmniejsza obciążenie pamięci.  
- **Zwiększ stertę JVM** – Użyj flagi `-Xmx` (np. `-Xmx2g`), aby przydzielić więcej pamięci dla dużych dokumentów.  
- **Zwolnij zasoby** – Wywołaj `document.close()`, gdy skończysz, aby zwolnić zasoby natywne.

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|---------|-------------|
| **Niska jakość wyjścia BMP** | Sprawdź, czy `options.setResolution()` jest ustawione na wartość ≥ 300 DPI. |
| **Tylko część dokumentu jest konwertowana** | Upewnij się, że `options.setPageNumbers()` zawiera wszystkie żądane indeksy stron. |
| **OutOfMemoryError przy dużych plikach XPS** | Przetwarzaj dokument w mniejszych partiach lub zwiększ rozmiar sterty JVM (`-Xmx`). |
| **Plik nie znaleziony** | Sprawdź dokładnie ścieżkę `dataDir` oraz czy plik wejściowy XPS istnieje. |

## Najczęściej zadawane pytania
### P: Czy mogę dostosować rozdzielczość obrazów BMP?
O: Tak, możesz dostosować rozdzielczość, modyfikując parametr `options.setResolution()` w kodzie.

### P: Czy Aspose.Page jest kompatybilny z różnymi wersjami Javy?
O: Tak, Aspose.Page obsługuje szeroki zakres wersji Javy. Upewnij się, że masz zainstalowaną kompatybilną wersję.

### P: Jak mogę konwertować pliki XPS z określonego zakresu stron?
O: Użyj metody `options.setPageNumbers()`, aby określić numery stron, które chcesz przekonwertować.

### P: Czy Aspose.Page obsługuje inne formaty wyjściowe?
O: Tak, Aspose.Page obsługuje różne formaty wyjściowe. Zapoznaj się z dokumentacją, aby uzyskać pełną listę.

### P: Gdzie mogę znaleźć dodatkową pomoc lub wsparcie?
O: Odwiedź [Forum Aspose.Page](https://forum.aspose.com/c/page/39), aby uzyskać wsparcie społeczności i dyskusje.

---

**Ostatnia aktualizacja:** 2026-03-08  
**Testowano z:** Aspose.Page for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}