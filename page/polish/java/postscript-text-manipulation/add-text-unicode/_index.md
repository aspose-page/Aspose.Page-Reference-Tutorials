---
date: 2025-12-17
description: Dowiedz się, jak dodać tekst Unicode w Java PostScript przy użyciu Aspose.Page
  – krok po kroku przewodnik, jak łatwo dodawać ciągi Unicode.
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: Jak dodać tekst Unicode w Java PostScript przy użyciu Aspose.Page
url: /pl/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dodać tekst Unicode w Java PostScript przy użyciu Aspose.Page

## Wprowadzenie
Jeśli zastanawiasz się **how to add Unicode** znaki w przepływie pracy opartym na Java‑based PostScript (lub XPS), trafiłeś we właściwe miejsce. W tym samouczku przeprowadzimy Cię krok po kroku przez dokładne czynności potrzebne do osadzenia ciągów Unicode przy użyciu biblioteki Aspose.Page dla Javy. Po zakończeniu przewodnika będziesz mógł wstawić dowolny tekst specyficzny dla języka — arabski, chiński, emotikony, cokolwiek — bezpośrednio do swojego wyjścia PostScript.

## Szybkie odpowiedzi
- **What library is needed?** Aspose.Page for Java  
- **Can I add right‑to‑left scripts?** Tak, ustaw poziom Bidi jak pokazano w kodzie  
- **Do I need a license for development?** Darmowa wersja próbna działa do testów; licencja komercyjna jest wymagana w produkcji  
- **Which IDE works best?** Dowolne środowisko Java (IntelliJ IDEA, Eclipse, NetBeans)  
- **Is the code cross‑platform?** Absolutnie — uruchom je na Windows, macOS lub Linux

## Co oznacza „how to add Unicode” w kontekście PostScript?
Dodawanie Unicode oznacza wstawianie znaków reprezentowanych przez punkty kodowe wykraczające poza podstawowy zakres ASCII. Aspose.Page abstrahuje szczegóły niskopoziomowego kodowania, pozwalając Ci skupić się na treści tekstu i jego wizualnym rozmieszczeniu.

## Dlaczego używać Aspose.Page do tekstu Unicode?
- **Full Unicode support** – Obsługuje złożone skrypty, ligatury i języki od prawej do lewej.  
- **No external dependencies** – Nie musisz ręcznie zarządzać plikami czcionek; API współpracuje z czcionkami systemowymi.  
- **Straight‑forward API** – Kilka wywołań metod wystarczy, aby wyrenderować tekst wielojęzyczny.

## Prerequisites
Zanim przejdziemy dalej, upewnij się, że masz przygotowane następujące elementy:

1. **Java Development Kit (JDK)** – Dowolna aktualna wersja (8 lub nowsza).  
2. **Aspose.Page for Java** – Pobierz i zainstaluj bibliotekę z [download link](https://releases.aspose.com/page/java/).  
3. **IDE of your choice** – IntelliJ IDEA, Eclipse lub dowolne inne środowisko Java, którego preferujesz.

## Importowanie pakietów
Dodaj wymagane klasy Aspose.Page do swojego pliku źródłowego Java:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Krok 1: Konfiguracja projektu
Utwórz nowy projekt Java, dodaj plik JAR Aspose.Page do ścieżki kompilacji projektu i utwórz folder, w którym zostanie zapisany wygenerowany plik XPS. Ten folder jest później odwoływany jako `dataDir`.

## Krok 2: Inicjalizacja dokumentu XPS
Utwórz pusty dokument XPS, który będzie przechowywał zawartość:

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Krok 3: Dodawanie tekstu Unicode
Teraz faktycznie dodamy ciąg Unicode. Poniższy przykład zapisuje odwróconą frazę „AVAJ rof SPX.esopsA”, która zawiera wyłącznie znaki ASCII, ale możesz ją zastąpić dowolnym tekstem Unicode (np. arabskim „مرحبا” lub chińskim „你好”).

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

> **Pro tip:** Aby poprawnie renderować języki od prawej do lewej, ustaw `glyphs.setBidiLevel(1);`. Dla skryptów od lewej do prawej możesz pominąć tę linię.

## Krok 4: Zapis dokumentu
Zapisz plik XPS na dysku:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

Po uruchomieniu programu otwórz wygenerowany `AddEncodingText_out.xps` w dowolnym przeglądarce XPS, aby zobaczyć wyrenderowany tekst Unicode w określonych współrzędnych.

## Typowe problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|-------|--------|-----|
| Tekst wyświetla się jako kwadraty | Czcionka nie znaleziona lub nie obsługuje znaków | Użyj czcionki zawierającej wymagane glify (np. “Arial Unicode MS”) |
| Tekst od prawej do lewej wyświetla się od lewej do prawej | Poziom Bidi nie ustawiony | Wywołaj `glyphs.setBidiLevel(1);` |
| Plik nie został zapisany | Ścieżka `dataDir` jest nieprawidłowa lub brakuje uprawnień do zapisu | Upewnij się, że katalog istnieje i aplikacja ma dostęp do zapisu |

## Najczęściej zadawane pytania
### Czy mogę używać Aspose.Page dla Javy z innymi językami programowania?
Aspose.Page jest przede wszystkim przeznaczony dla Javy, ale Aspose udostępnia biblioteki dla różnych języków programowania.

### Czy dostępna jest darmowa wersja próbna?
Tak, możesz uzyskać darmową wersję próbną Aspose.Page [tutaj](https://releases.aspose.com/).

### Gdzie mogę znaleźć wsparcie i dyskusje na temat Aspose.Page?
Odwiedź [Aspose.Page forum](https://forum.aspose.com/c/page/39) w celu uzyskania wsparcia i dyskusji.

### Jak mogę uzyskać tymczasową licencję na Aspose.Page?
Możesz nabyć tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/).

### Jakie style czcionek są dostępne w Aspose.Page?
Aspose.Page obsługuje style czcionek takie jak Regular, Bold, Italic i BoldItalic.

## Zakończenie
Opanowałeś teraz **how to add Unicode** tekst do dokumentu Java PostScript (XPS) przy użyciu Aspose.Page. Ta możliwość otwiera drzwi do wielojęzycznych raportów, zinternacjonalizowanych faktur i wszelkich scenariuszy, w których wymagane są znaki spoza ASCII. Śmiało eksploruj dodatkowe funkcje, takie jak rotacja tekstu, ścieżki przycinania czy osadzanie własnych czcionek — szczegóły dostępne są w oficjalnej [documentation](https://reference.aspose.com/page/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2025-12-17  
**Testowano z:** Aspose.Page for Java 23.12 (latest at time of writing)  
**Autor:** Aspose  

---