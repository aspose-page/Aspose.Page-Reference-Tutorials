---
date: 2026-01-02
description: Dowiedz się, jak dodać maskę przezroczystości do dokumentów XPS przy
  użyciu Aspose.Page Java. Przewodnik krok po kroku, jak utworzyć prostokąt maski
  przezroczystości i poprawić jakość wizualną.
linktitle: Set Opacity Mask in Java XPS
second_title: Aspose.Page Java API
title: Ustaw maskę przezroczystości w Java XPS przy użyciu Aspose.Page Java
url: /pl/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw maskę przezroczystości w Java XPS przy użyciu Aspose.Page Java

## Wprowadzenie
Witamy w naszym kompleksowym przewodniku po **aspose page java** opacity masks. W tym tutorialu nauczysz się, jak stworzyć dokument XPS, dodać canvas i zastosować maskę przezroczystości do prostokąta — wszystko przy użyciu potężnego API Aspose.Page Java. Po zakończeniu będziesz w stanie dodawać prostokąty z maską przezroczystości, które nadadzą Twoim plikom XPS wykończenie o półprzezroczystym wyglądzie.

## Szybkie odpowiedzi
- **Co robi opacity mask?** Definiuje różne poziomy przezroczystości dla kształtu, pozwalając na prześwitywanie zawartości pod spodem.
- **Jakiej biblioteki potrzebuję?** Aspose.Page for Java (aspose page java).
- **Czy potrzebna jest licencja?** Tymczasowa licencja działa w trybie testowym; pełna licencja jest wymagana w produkcji.
- **Ile linii kodu?** Około 20 linii Java plus kilka instrukcji konfiguracyjnych.
- **Czy mogę ponownie używać maski na wielu kształtach?** Tak, możesz przypisać ten sam ImageBrush do kilku ścieżek.

## Czym jest opacity mask w XPS?
Opacity mask to bitmapa lub wektor, który kontroluje alfa (przezroczystość) każdego piksela w kształcie. Po zastosowaniu do prostokąta, jego części stają się w pełni nieprzezroczyste, częściowo przezroczyste lub całkowicie przezroczyste, tworząc zaawansowane efekty wizualne.

## Dlaczego używać Aspose.Page Java do opacity mask?
- **Pełne API w stylu .NET w Javie** – intuicyjny model obiektowy.
- **Brak zewnętrznych zależności** – działa w czystej Javie.
- **Renderowanie wysokiej wierności** – maski renderują się dokładnie zgodnie ze specyfikacją XPS.
- **Cross‑platform** – działa na Windows, Linux i macOS bez zmian.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:
- Podstawową znajomość programowania w języku Java.  
- Zainstalowaną bibliotekę Aspose.Page for Java. Możesz ją pobrać **[tutaj](https://releases.aspose.com/page/java/)**.  
- Ważną licencję na Aspose.Page. Jeśli jej nie masz, uzyskaj tymczasową licencję **[tutaj](https://purchase.aspose.com/temporary-license/)**.  
- Środowisko programistyczne umożliwiające kompilację i uruchamianie aplikacji Java (np. IntelliJ IDEA, Eclipse lub VS Code).

## Importowanie pakietów
Rozpocznij od zaimportowania niezbędnych klas z biblioteki Aspose.Page. Zapewni to dostępność API w Twoim projekcie.

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
Najpierw zainicjuj nowy dokument XPS, który będzie przechowywał wszystkie nasze elementy graficzne.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### Krok 2: Dodaj Canvas
Canvas pełni rolę powierzchni rysunkowej wewnątrz strony XPS.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### Krok 3: Dodaj prostokąt i zastosuj jednolite wypełnienie
Tutaj tworzymy ścieżkę prostokąta i nadajemy mu jednolite, czerwone wypełnienie. Ten prostokąt później otrzyma maskę przezroczystości.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### Krok 4: Dodaj opacity mask przy użyciu ImageBrush
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

Postępuj zgodnie z tymi krokami, aby wprowadzić funkcjonalność **add opacity mask** do swojego dokumentu Java XPS przy użyciu Aspose.Page.

## Częste problemy i rozwiązywanie
- **Obraz nie został znaleziony** – Sprawdź, czy `dataDir` wskazuje na właściwy folder i czy plik `R08SY_NN.tif` istnieje.
- **Maska wygląda na jednolitą** – Upewnij się, że obraz źródłowy rzeczywiście zawiera różne wartości alfa; w pełni nieprzezroczysty obraz nie pokaże przezroczystości.
- **Tryb kafelkowania nie działa** – Prostokąt docelowy musi być mniejszy od prostokąta źródłowego, aby efekt kafelkowania był widoczny.

## Najczęściej zadawane pytania

**P: Czy Aspose.Page jest kompatybilny ze wszystkimi środowiskami programistycznymi Javy?**  
O: Tak, Aspose.Page został zaprojektowany tak, aby bezproblemowo współpracować z różnymi IDE i narzędziami budowania Javy.

**P: Czy mogę używać Aspose.Page bez licencji?**  
O: Bibliotekę można ocenić przy użyciu tymczasowej licencji, ale pełna licencja jest wymagana w środowisku produkcyjnym.

**P: Czy wersja próbna ma jakieś ograniczenia?**  
O: Wersja trial może nakładać ograniczenia dotyczące rozmiaru lub funkcji; zapoznaj się z oficjalną dokumentacją po szczegóły.

**P: Jak mogę uzyskać wsparcie dla Aspose.Page?**  
O: Odwiedź **[forum Aspose.Page](https://forum.aspose.com/c/page/39)**, aby uzyskać pomoc od społeczności lub zakup licencję dla wsparcia premium.

**P: Czy istnieje gwarancja zwrotu pieniędzy dla Aspose.Page?**  
O: Szczegóły dotyczące polityki zwrotów znajdziesz na **[stronie zakupu](https://purchase.aspose.com/buy)**.

---

**Ostatnia aktualizacja:** 2026-01-02  
**Testowano z:** Aspose.Page Java 24.11 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}