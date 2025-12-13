---
date: 2025-12-13
description: Dowiedz się, jak dodać tekst do strony ASP w Javie, ustawić styl czcionki
  w Javie oraz jak dodać tekst Unicode przy użyciu Aspose.Page. Postępuj zgodnie z
  naszym przewodnikiem krok po kroku.
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: strona asp dodaj tekst – Unicode w Java PostScript
url: /pl/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# asp page add text – Unicode w Java PostScript

## Wprowadzenie
Jeśli potrzebujesz **asp page add text** w przepływie pracy Java PostScript, zachowując znaki Unicode, trafiłeś we właściwe miejsce. W tym samouczku przeprowadzimy Cię przez dodawanie tekstu Unicode, ustawianie stylu czcionki oraz zapisywanie wyniku przy użyciu **Aspose.Page for Java**. Po zakończeniu zrozumiesz, jak ustawić font style java i jak efektywnie dodawać tekst unicode w swoich projektach.

## Szybkie odpowiedzi
- **Jaka biblioteka może dodawać tekst Unicode w Java PostScript?** Aspose.Page for Java.  
- **Która podstawowa metoda dodaje tekst?** `doc.addGlyphs(...)` z obiektem `XpsGlyphs`.  
- **Czy potrzebuję specjalnej czcionki dla Unicode?** Dowolna czcionka TrueType/OpenType, która obsługuje wymagane punkty kodowe (np. Arial).  
- **Czy mogę zmienić styl czcionki?** Tak, używając `XpsFontStyle` (Regular, Bold, Italic, itp.).  
- **Czy wymagana jest licencja do produkcji?** Tak, ważna licencja Aspose.Page jest potrzebna do użytku nie‑testowego.

## Co to jest asp page add text?
`asp page add text` odnosi się do procesu wstawiania ciągów tekstowych do dokumentu PostScript lub XPS przy użyciu API Aspose.Page. API abstrahuje niskopoziomowe polecenia PostScript, umożliwiając pracę z obiektami wysokiego poziomu, takimi jak `XpsGlyphs`.

## Dlaczego używać Aspose.Page do set font style java i dodawania tekstu Unicode?
- **Pełne wsparcie Unicode** – Obsługuje skrypty od prawej do lewej i złożone glify.  
- **Proste API** – Jednowierszowe wywołania do dodawania tekstu i stosowania stylów.  
- **Wieloplatformowe** – Działa w każdym środowisku kompatybilnym z Java.  
- **Brak zewnętrznych zależności** – Nie wymaga dodatkowych silników renderujących.

## Wymagania wstępne
Zanim przejdziemy do samouczka, upewnij się, że masz spełnione następujące wymagania:

1. **Java Development Kit (JDK)** – Upewnij się, że Java jest zainstalowana na Twoim komputerze.  
2. **Aspose.Page for Java** – Pobierz i zainstaluj bibliotekę Aspose.Page z [download link](https://releases.aspose.com/page/java/).  
3. **Integrated Development Environment (IDE)** – Wybierz preferowane środowisko Java IDE, takie jak IntelliJ IDEA lub Eclipse.

## Importowanie pakietów
W swoim projekcie Java zaimportuj niezbędne pakiety dla Aspose.Page. Dodaj następujące linie do swojego kodu:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Krok 1: Konfiguracja projektu
Utwórz nowy projekt Java w swoim IDE i skonfiguruj strukturę projektu. Upewnij się, że biblioteka Aspose.Page jest uwzględniona w zależnościach projektu.

## Krok 2: Inicjalizacja dokumentu XPS
Rozpocznij od zainicjowania nowego dokumentu XPS w swoim projekcie:

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Krok 3: Dodawanie tekstu Unicode
Teraz dodajmy tekst Unicode do Twojego dokumentu XPS przy użyciu biblioteki Aspose.Page. Użyj poniższego fragmentu kodu:

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

Ten fragment kodu dodaje tekst Unicode **"AVAJ rof SPX.esopsA"** do dokumentu XPS w współrzędnych (400, 200) z określoną czcionką i stylem. Zauważ, że wywołanie `setBidiLevel(1)` włącza renderowanie od prawej do lewej dla prawidłowego wyświetlania Unicode.

## Krok 4: Zapis dokumentu
Zapisz powstały dokument XPS przy użyciu poniższego kodu:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

## Zakończenie
Gratulacje! Pomyślnie **asp page add text** oraz ustawiłeś styl czcionki w scenariuszu Java PostScript przy użyciu Aspose.Page. Ta metoda zapewnia precyzyjną kontrolę nad renderowaniem i stylizacją Unicode, co czyni ją idealną do międzynarodowych raportów, faktur i grafiki.

Śmiało eksploruj więcej funkcji i możliwości Aspose.Page w [dokumentacji](https://reference.aspose.com/page/java/).

## Najczęściej zadawane pytania

**Q:** Czy mogę używać Aspose.Page for Java z innymi językami programowania?  
**A:** Aspose.Page jest głównie przeznaczony dla Java, ale Aspose udostępnia biblioteki dla różnych języków programowania.

**Q:** Czy dostępna jest darmowa wersja próbna?  
**A:** Tak, możesz uzyskać dostęp do darmowej wersji próbnej Aspose.Page [tutaj](https://releases.aspose.com/).

**Q:** Gdzie mogę znaleźć wsparcie i dyskusje na temat Aspose.Page?  
**A:** Odwiedź [forum Aspose.Page](https://forum.aspose.com/c/page/39), aby uzyskać wsparcie i dyskusje.

**Q:** Jak mogę uzyskać tymczasową licencję dla Aspose.Page?  
**A:** Możesz nabyć tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/).

**Q:** Jakie style czcionek są dostępne w Aspose.Page?  
**A:** Aspose.Page obsługuje style czcionek takie jak Regular, Bold, Italic oraz BoldItalic.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2025-12-13  
**Testowano z:** Aspose.Page for Java (latest)  
**Autor:** Aspose  

---