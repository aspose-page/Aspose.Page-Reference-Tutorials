---
date: 2026-05-20
description: Dowiedz się, jak dodać tekst Unicode w Java PostScript przy użyciu Aspose.Page
  – krok po kroku przewodnik, jak łatwo dodawać ciągi Unicode.
keywords:
- how to add unicode
- java add arabic text
- java add chinese text
linktitle: Dodaj tekst przy użyciu ciągu Unicode w Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add Unicode text in Java PostScript using Aspose.Page
    – a step‑by‑step guide on how to add unicode strings effortlessly.
  headline: How to Add Unicode Text in Java PostScript with Aspose.Page
  type: TechArticle
- description: Learn how to add Unicode text in Java PostScript using Aspose.Page
    – a step‑by‑step guide on how to add unicode strings effortlessly.
  name: How to Add Unicode Text in Java PostScript with Aspose.Page
  steps:
  - name: '**Java Development Kit (JDK)** – Any recent version (8 or newer).'
    text: '**Java Development Kit (JDK)** – Any recent version (8 or newer).'
  - name: '**Aspose.Page for Java** – Download and install the library from the [download
      link](https://releases.aspose.com/page/java/). You can also browse all releases
      [here](https://releases.aspose.com/).'
    text: '**Aspose.Page for Java** – Download and install the library from the [download
      link](https://releases.aspose.com/page/java/). You can also browse all releases
      [here](https://releases.aspose.com/).'
  - name: '**IDE of your choice** – IntelliJ IDEA, Eclipse, or any other Java IDE
      you prefer.'
    text: '**IDE of your choice** – IntelliJ IDEA, Eclipse, or any other Java IDE
      you prefer.'
  type: HowTo
- questions:
  - answer: Aspose.Page is built specifically for Java, but Aspose offers equivalent
      libraries for .NET, C++, and Python if you need cross‑language support.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can access a free trial of Aspose.Page [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      help, samples, and troubleshooting tips.
    question: Where can I find support and community discussions?
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for testing?
  - answer: The API supports Regular, Bold, Italic, and BoldItalic styles for any
      TrueType or OpenType font you load.
    question: What font styles does Aspose.Page support?
  type: FAQPage
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
Jeśli zastanawiasz się **jak dodać Unicode** do przepływu pracy opartego na Java‑based PostScript (lub XPS), trafiłeś we właściwe miejsce. W tym samouczku przeprowadzimy Cię krok po kroku przez dokładne czynności potrzebne do osadzenia ciągów Unicode przy użyciu biblioteki Aspose.Page dla Javy. Po zakończeniu przewodnika będziesz mógł wstawiać dowolny tekst specyficzny dla języka — arabski, chiński, emotikony, cokolwiek — bezpośrednio do wyjścia PostScript.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebujesz?** Aspose.Page for Java  
- **Czy mogę dodać skrypty od prawej do lewej?** Tak, ustaw poziom Bidi jak pokazano w kodzie  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna wystarczy do testów; licencja komercyjna jest wymagana w produkcji  
- **Które IDE jest najlepsze?** Dowolne IDE Java (IntelliJ IDEA, Eclipse, NetBeans)  
- **Czy kod jest wieloplatformowy?** Zdecydowanie — działa na Windows, macOS i Linux  

## Co oznacza „jak dodać Unicode” w kontekście PostScript?
Dodawanie tekstu Unicode oznacza osadzanie znaków, których punkty kodowe znajdują się poza podstawowym zakresem ASCII — takich jak arabski, chiński czy emoji — w dokumencie PostScript (lub XPS) przy użyciu Aspose.Page. Biblioteka automatycznie mapuje te punkty kodowe na odpowiednie glify w wybranej czcionce, obsługując złożone kształtowanie, ligatury i kolejność od prawej do lewej bez ręcznego kodowania.

## Dlaczego używać Aspose.Page do tekstu Unicode?
Aspose.Page zapewnia niezawodne, w 100 % czysto‑Java rozwiązanie, które obsługuje **ponad 50 formatów wejścia i wyjścia** oraz może renderować tekst wielojęzyczny w dokumentach do 1 000 stron bez ładowania całego pliku do pamięci. Eliminuje potrzebę zewnętrznych narzędzi do obsługi czcionek, skraca czas programowania o 70 %, i gwarantuje spójny wygląd wizualny w środowiskach Windows, macOS i Linux.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz przygotowane następujące elementy:

1. **Java Development Kit (JDK)** – dowolna aktualna wersja (8 lub nowsza).  
2. **Aspose.Page for Java** – pobierz i zainstaluj bibliotekę z [download link](https://releases.aspose.com/page/java/). Możesz także przeglądać wszystkie wydania [tutaj](https://releases.aspose.com/).  
3. **IDE według własnego wyboru** – IntelliJ IDEA, Eclipse lub dowolne inne IDE Java, które preferujesz.

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
Klasa `XpsDocument` reprezentuje plik XPS w pamięci i zapewnia płótno dla wszystkich operacji rysowania.

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Krok 3: Dodanie tekstu Unicode
Teraz faktycznie dodamy ciąg Unicode. Poniższy przykład zapisuje odwrócone zdanie „AVAJ rof SPX.esopsA”, które zawiera wyłącznie znaki ASCII, ale możesz je zastąpić dowolnym tekstem Unicode (np. arabskim „مرحبا” lub chińskim „你好”). Tak wygląda **java add arabic text** lub **java add chinese text** w Twoim dokumencie.

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

> **Wskazówka:** Aby poprawnie renderować języki od prawej do lewej, ustaw `glyphs.setBidiLevel(1);`. Dla skryptów od lewej do prawej możesz pominąć tę linię.

## Krok 4: Zapisz dokument
Zapisz plik XPS na dysku:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

Po uruchomieniu programu otwórz wygenerowany `AddEncodingText_out.xps` w dowolnej przeglądarce XPS, aby zobaczyć renderowany tekst Unicode w określonych współrzędnych.

## Typowe problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| Tekst wyświetla się jako kwadraty | Czcionka nie znaleziona lub nie obsługuje znaków | Użyj czcionki zawierającej wymagane glify (np. „Arial Unicode MS”) |
| Tekst od prawej do lewej wyświetla się od lewej do prawej | Nie ustawiono poziomu Bidi | Wywołaj `glyphs.setBidiLevel(1);` |
| Plik nie został zapisany | Ścieżka `dataDir` nieprawidłowa lub brak uprawnień do zapisu | Upewnij się, że katalog istnieje i aplikacja ma dostęp do zapisu |

## Najczęściej zadawane pytania
**Q: Czy mogę używać Aspose.Page for Java z innymi językami programowania?**  
A: Aspose.Page jest zbudowane specjalnie dla Javy, ale Aspose oferuje równoważne biblioteki dla .NET, C++ i Pythona, jeśli potrzebujesz wsparcia wielojęzykowego.

**Q: Czy dostępna jest darmowa wersja próbna?**  
A: Tak, możesz uzyskać darmową wersję próbną Aspose.Page [tutaj](https://releases.aspose.com/).

**Q: Gdzie mogę znaleźć wsparcie i dyskusje społeczności?**  
A: Odwiedź [forum Aspose.Page](https://forum.aspose.com/c/page/39) w celu uzyskania pomocy, przykładów i wskazówek rozwiązywania problemów.

**Q: Jak uzyskać tymczasową licencję do testów?**  
A: Możesz uzyskać tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/).

**Q: Jakie style czcionek obsługuje Aspose.Page?**  
A: API obsługuje style Regular, Bold, Italic i BoldItalic dla dowolnej czcionki TrueType lub OpenType, którą załadujesz.

## Podsumowanie
Teraz opanowałeś **jak dodać Unicode** do dokumentu Java PostScript (XPS) przy użyciu Aspose.Page. Ta możliwość otwiera drzwi do wielojęzycznych raportów, międzynarodowych faktur i wszelkich scenariuszy, w których wymagane są znaki spoza zestawu ASCII. Śmiało eksploruj dodatkowe **funkcje**, takie jak obracanie tekstu, ścieżki przycinania czy osadzanie własnych czcionek — szczegóły dostępne są w oficjalnej [dokumentacji](https://reference.aspose.com/page/java/).

---

**Ostatnia aktualizacja:** 2026-05-20  
**Testowano z:** Aspose.Page for Java 23.12 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Jak dodać tekst w PostScript przy użyciu Aspose.Page dla Java](/page/java/postscript-text-manipulation/)
- [Ustaw kolor tekstu Java z Aspose.Page – Przewodnik manipulacji tekstem](/page/java/postscript-text-manipulation/add-text/)
- [Dodaj strony PostScript Java – Bezproblemowy przewodnik z Aspose.Page](/page/java/postscript-page-manipulation/add-pages1/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}