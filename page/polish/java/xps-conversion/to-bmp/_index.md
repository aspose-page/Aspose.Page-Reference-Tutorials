---
date: 2025-12-21
description: Dowiedz się, jak ustawić rozdzielczość przy konwertowaniu XPS na BMP
  w Javie przy użyciu Aspose.Page. Ten przewodnik po konwersji obrazów w Javie zapewnia
  wysoką jakość wyników.
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: Jak ustawić rozdzielczość przy konwertowaniu XPS na BMP w Javie
url: /pl/java/xps-conversion/to-bmp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konwertuj XPS do BMP w Javie

## Wprowadzenie
Witamy w tym przewodniku krok po kroku dotyczącym **ustawiania rozdzielczości** podczas konwertowania plików XPS (XML Paper Specification) do formatu BMP (Bitmap) w Javie przy użyciu Aspose.Page. Aspose.Page dla Javy to potężna biblioteka oferująca kompleksowe funkcje pracy z dokumentami XPS. W tym tutorialu przeprowadzimy Cię przez proces konwersji plików XPS do obrazów BMP bez wysiłku.

## Szybkie odpowiedzi
- **Jakiej biblioteki powinienem używać?** Aspose.Page dla Javy zapewnia najpełniejsze funkcje konwersji XPS → BMP.  
- **Czy mogę kontrolować jakość obrazu?** Tak – użyj `BmpSaveOptions`, aby ustawić rozdzielczość i tryb wygładzania.  
- **Czy muszę konwertować tylko wybrane strony?** Oczywiście, `options.setPageNumbers()` pozwala wybrać dokładne strony.  
- **Czy to prawdziwa konwersja obrazu w Javie?** API renderuje strony XPS bezpośrednio do danych bitmapy, więc nie są wymagane formaty pośrednie.  
- **Jaką wersję Javy obsługuje?** Wszystkie współczesne wersje Javy (8 i wyżej) są kompatybilne.

## Jaki jest cel ustawiania rozdzielczości?
Rozdzielczość określa liczbę punktów na cal (DPI) w generowanym obrazie BMP. Wyższe DPI daje ostrzejsze obrazy, co jest niezbędne przy drukowaniu lub szczegółowej pracy graficznej. Dostosowanie rozdzielczości daje pełną kontrolę nad jakością wyjściową Twojego **java convert xps** workflow.

## Dlaczego warto używać Aspose.Page do konwersji XPS → BMP?
- **Wysoka wierność** – zachowuje wektorową jakość oryginalnego XPS.  
- **Precyzyjna kontrola** – możesz ustawić DPI, wygładzanie oraz wybrać konkretne strony do konwersji.  
- **Brak zewnętrznych zależności** – czysta Java, bez wymogu natywnych bibliotek.  
- **Skalowalność** – działa zarówno dla dokumentów jednosktronicowych, jak i dużych, wielostronicowych plików XPS.

## Wymagania wstępne
Zanim przejdziesz do procesu konwersji, upewnij się, że spełniasz następujące wymagania:
- **Środowisko programistyczne Javy** – zainstalowany Java 8 lub nowsza wersja.  
- **Biblioteka Aspose.Page dla Javy** – pobierz i dołącz bibliotekę Aspose.Page do swojego projektu. Bibliotekę znajdziesz [tutaj](https://releases.aspose.com/page/java/).  
- **Przykładowy plik XPS** – przygotuj przykładowy dokument XPS, który chcesz skonwertować do BMP.

## Importowanie pakietów
Dołącz niezbędne pakiety Aspose.Page w swoim kodzie Javy:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Jak ustawić rozdzielczość przy konwersji XPS do BMP
Poniżej znajduje się zwięzły, numerowany przewodnik, który pokazuje dokładnie, gdzie i jak ustawić rozdzielczość, a także jak **konwertować wybrane strony**.

### Krok 1: Załaduj dokument XPS
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Krok 2: Zainicjuj opcje (rozdzielczość i wybór stron)
```java
// Initialize options object with necessary parameters.
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);

// Primary setting – this is the **how to set resolution** part.
options.setResolution(300);               // 300 DPI for high‑quality output

// Optional: convert specific pages only (e.g., pages 1, 2, and 6)
options.setPageNumbers(new int[]{1, 2, 6});
```

### Krok 3: Utwórz urządzenie renderujące
```java
// Create rendering device for BMP format
ImageDevice device = new ImageDevice();
```

### Krok 4: Zapisz dokument przy użyciu opcji
```java
// Save XPS document to BMP using options and device
document.save(device, options);
```

### Krok 5: Przejdź przez wyrenderowane obrazy i zapisz pliki
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

Powtórz te kroki dla każdej dodatkowej personalizacji lub modyfikacji, której potrzebujesz w procesie konwersji.

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|----------|
| **Niska jakość wyjściowego BMP** | Sprawdź, czy `options.setResolution()` jest ustawione na wartość ≥ 300 DPI. |
| **Konwertuje się tylko część dokumentu** | Upewnij się, że `options.setPageNumbers()` obejmuje wszystkie żądane indeksy stron. |
| **OutOfMemoryError przy dużych plikach XPS** | Przetwarzaj dokument w mniejszych partiach lub zwiększ rozmiar sterty JVM (`-Xmx`). |
| **Plik nie został znaleziony** | Podwójnie sprawdź ścieżkę `dataDir` oraz istnienie wejściowego pliku XPS. |

## Najczęściej zadawane pytania
### P: Czy mogę dostosować rozdzielczość obrazów BMP?
O: Tak, możesz zmienić rozdzielczość, modyfikując parametr `options.setResolution()` w kodzie.

### P: Czy Aspose.Page jest kompatybilny z różnymi wersjami Javy?
O: Tak, Aspose.Page obsługuje szeroki zakres wersji Javy. Upewnij się, że masz zainstalowaną kompatybilną wersję.

### P: Jak mogę konwertować pliki XPS z określonego zakresu stron?
O: Użyj metody `options.setPageNumbers()`, aby określić numery stron, które chcesz konwertować.

### P: Czy Aspose.Page obsługuje inne formaty wyjściowe?
O: Tak, Aspose.Page wspiera różne formaty wyjściowe. Zapoznaj się z dokumentacją, aby uzyskać pełną listę.

### P: Gdzie mogę znaleźć dodatkową pomoc lub wsparcie?
O: Odwiedź [Forum Aspose.Page](https://forum.aspose.com/c/page/39) w celu uzyskania wsparcia społeczności i dyskusji.

---

**Ostatnia aktualizacja:** 2025-12-21  
**Testowano z:** Aspose.Page dla Javy 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}