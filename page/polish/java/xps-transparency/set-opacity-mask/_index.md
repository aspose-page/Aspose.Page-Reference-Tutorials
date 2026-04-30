---
date: 2026-04-30
description: Dowiedz się, jak tworzyć dokumenty XPS w Javie i dodawać maskę przezroczystości
  przy użyciu Aspose.Page Java. Przewodnik krok po kroku z przykładami kodu.
keywords:
- create xps document java
- opacity mask java
- aspose.page java
linktitle: Ustaw maskę przezroczystości w Java XPS
second_title: Aspose.Page Java API
title: Tworzenie dokumentu XPS w Javie – ustaw maskę przezroczystości za pomocą Aspose.Page
url: /pl/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw maskę przezroczystości w Java XPS przy użyciu Aspose.Page Java

## Wprowadzenie
W tym samouczku **utworzysz pliki dokumentu XPS w Javie** i nauczysz się, jak zastosować maskę przezroczystości, która nada Twojej grafice wykończenie, półprzezroczysty wygląd. Przejdziemy przez cały proces — od inicjalizacji dokumentu XPS, dodania płótna, narysowania prostokąta, po dołączenie maski przezroczystości opartej na obrazie — używając intuicyjnego API Aspose.Page Java. Po zakończeniu będziesz w stanie programowo generować profesjonalne pliki XPS i ponownie używać maski na dowolnym kształcie, którego potrzebujesz.

## Szybkie odpowiedzi
- **Co robi maska przezroczystości?** Definiuje różne poziomy przezroczystości dla kształtu, pozwalając na prześwitywanie zawartości pod spodem.  
- **Jakiej biblioteki wymaga?** Aspose.Page for Java (aspose page java).  
- **Czy potrzebna jest licencja?** Tymczasowa licencja działa w testach; pełna licencja jest wymagana w produkcji.  
- **Ile linii kodu?** Około 20 linii Javy plus kilka instrukcji konfiguracyjnych.  
- **Czy mogę ponownie używać maski na wielu kształtach?** Tak, możesz przypisać ten sam `ImageBrush` do kilku ścieżek.

## Czym jest maska przezroczystości w XPS?
Maska przezroczystości to bitmapa lub wektor, który kontroluje alfa (przezroczystość) każdego piksela w kształcie. Po zastosowaniu do prostokąta, części prostokąta stają się całkowicie nieprzezroczyste, częściowo przezroczyste lub całkowicie przezroczyste, tworząc zaawansowane efekty wizualne bez dodatkowych warstw rysunkowych.

## Dlaczego używać Aspose.Page Java do **tworzenia dokumentu XPS w Javie**?
- **Czyste API Java** – Brak zależności natywnych, więc ten sam kod działa na Windows, Linux i macOS.  
- **Pełna zgodność ze specyfikacją XPS** – Maski renderują dokładnie tak, jak określa standard XPS.  
- **Projekt obiektowy** – Podobny do .NET, co ułatwia naukę, jeśli używałeś Aspose w innych językach.  
- **Wysoka wydajność** – Optymalizowane pod kątem dużych dokumentów i przetwarzania wsadowego.

## Typowe przypadki użycia
- **Znakowanie wodne** – Zastosuj półprzezroczyste logo na stronach.  
- **Dynamiczne tematy** – Zmieniaj styl wizualny elementów UI w generowanych raportach.  
- **Podglądy gotowe do druku** – Pokaż, jak projekt będzie wyglądał przy różnej przezroczystości przed wysłaniem do drukarki.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:
- Podstawową znajomość programowania w Javie.  
- Zainstalowaną bibliotekę Aspose.Page for Java. Możesz ją pobrać **[tutaj](https://releases.aspose.com/page/java/)**.  
- Ważną licencję na Aspose.Page. Jeśli jej nie masz, uzyskaj tymczasową licencję **[tutaj](https://purchase.aspose.com/temporary-license/)**.  
- Środowisko programistyczne umożliwiające kompilację i uruchamianie aplikacji Java (np. IntelliJ IDEA, Eclipse lub VS Code).

## Importowanie pakietów
Zacznij od zaimportowania niezbędnych klas z biblioteki Aspose.Page. Zapewni to dostępność API w Twoim projekcie.

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Przewodnik krok po kroku

### Krok 1: Utwórz nowy dokument XPS
Najpierw utwórz nowy dokument XPS, który będzie przechowywał całą naszą grafikę.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### Krok 2: Dodaj płótno
Płótno pełni rolę powierzchni rysunkowej wewnątrz strony XPS.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### Krok 3: Dodaj prostokąt i zastosuj jednolite wypełnienie
Tutaj tworzymy ścieżkę prostokąta i nadajemy mu jednolite czerwone wypełnienie. Ten prostokąt później otrzyma maskę przezroczystości.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### Krok 4: Dodaj maskę przezroczystości przy użyciu ImageBrush
Ładujemy obraz TIFF, definiujemy prostokąty źródłowy i docelowy oraz ustawiamy pędzel w tryb kafelkowania, aby maska powtarzała się w razie potrzeby.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### Krok 5: Zapisz powstały dokument XPS
Na koniec zapisujemy dokument na dysku. Plik wyjściowy będzie zawierał prostokąt z zastosowaną maską przezroczystości.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

Postępuj zgodnie z tymi krokami, aby wprowadzić funkcję **add opacity mask** do swojego dokumentu XPS w Javie przy użyciu Aspose.Page.

## Typowe problemy i rozwiązywanie
- **Obraz nie znaleziony** – Sprawdź, czy `dataDir` wskazuje na właściwy folder i czy plik `R08SY_NN.tif` istnieje.  
- **Maska wygląda na jednolitą** – Upewnij się, że obraz źródłowy rzeczywiście zawiera różne wartości alfa; w pełni nieprzezroczysty obraz nie pokaże przezroczystości.  
- **Tryb kafelkowania nie działa** – Prostokąt docelowy musi być mniejszy niż prostokąt źródłowy, aby efekt kafelkowania był widoczny.

## Najczęściej zadawane pytania

**Q: Czy Aspose.Page jest kompatybilny ze wszystkimi środowiskami programistycznymi Java?**  
A: Tak, Aspose.Page został zaprojektowany tak, aby działał płynnie z różnymi IDE i narzędziami budowania w Javie.

**Q: Czy mogę używać Aspose.Page bez licencji?**  
A: Możesz ocenić bibliotekę przy użyciu tymczasowej licencji, ale pełna licencja jest wymagana w środowisku produkcyjnym.

**Q: Czy istnieją jakiekolwiek ograniczenia wersji próbnej?**  
A: Wersja próbna może nakładać ograniczenia dotyczące rozmiaru lub funkcji; zapoznaj się z oficjalną dokumentacją po szczegóły.

**Q: Jak mogę uzyskać wsparcie dla Aspose.Page?**  
A: Odwiedź **[forum Aspose.Page](https://forum.aspose.com/c/page/39)**, aby uzyskać pomoc społeczności lub zakup licencję, aby otrzymać wsparcie premium.

**Q: Czy istnieje gwarancja zwrotu pieniędzy dla Aspose.Page?**  
A: Sprawdź **[stronę zakupu](https://purchase.aspose.com/buy)**, aby uzyskać informacje o polityce zwrotów.

**Ostatnia aktualizacja:** 2026-04-30  
**Testowano z:** Aspose.Page Java 24.11 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}