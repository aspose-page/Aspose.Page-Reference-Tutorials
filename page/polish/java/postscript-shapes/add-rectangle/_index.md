---
date: 2026-02-18
description: Naucz się rysować kształty prostokątów w Java PostScript przy użyciu
  Aspose.Page. Ten przewodnik krok po kroku pokazuje, jak ustawić farbę, ustawić kolor
  prostokąta w Javie oraz tworzyć żywe grafiki, jednocześnie wyjaśniając, jak efektywnie
  rysować prostokąty.
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: Jak narysować prostokąt w Java PostScript przy użyciu Aspose.Page
url: /pl/java/postscript-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak rysować prostokąt w Java PostScript przy użyciu Aspose.Page

## Wprowadzenie
Jeśli potrzebujesz **how to draw rectangle** kształtów wewnątrz pliku Java PostScript, trafiłeś we właściwe miejsce. W tym samouczku przeprowadzimy Cię przez użycie Aspose.Page dla Javy do dodawania kolorowych prostokątów, kontrolowania ich wypełnienia i obrysu oraz zapisywania wyniku jako dokumentu PostScript. Zobaczysz dokładnie **how to set paint**, jak zdefiniować geometrię prostokąta i dlaczego takie podejście jest idealne do programowego generowania grafiki do druku. Pod koniec przewodnika zrozumiesz także szerszy kontekst technik **draw rectangle java** oraz ich miejsce w przepływach **java awt rectangle drawing**.

## Szybkie odpowiedzi
- **Jakiej biblioteki wymaga?** Aspose.Page for Java  
- **Czy mogę zmienić kolory prostokąta?** Tak – użyj `setPaint` z dowolnym `java.awt.Color`  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna działa do testów; licencja jest wymagana w produkcji  
- **Jaki rozmiar strony jest użyty w przykładzie?** A4 (domyślny `PsSaveOptions`)  
- **Czy kod jest kompatybilny z Java 8+?** Absolutnie – używa standardowych klas AWT  

## Co to jest „How to Draw Rectangle” w PostScript?
Rysowanie prostokąta w dokumencie PostScript oznacza zdefiniowanie prostokątnego obszaru i jego wypełnienie, obrysowanie lub oba te działania. Dzięki Aspose.Page możesz to zrobić, używając znanych klas **java awt rectangle drawing**, co sprawia, że kod jest łatwy do odczytania i utrzymania.

## Dlaczego używać Aspose.Page do grafiki prostokątnej?
- **Cross‑platform**: Generuje standardowy PostScript działający na każdej drukarce.  
- **Fine‑grained control**: Możesz niezależnie ustawiać kolory wypełnienia, kolory obrysu i szerokości linii.  
- **No external dependencies**: Używa tylko wbudowanych klas geometrii AWT, więc nie potrzebujesz dodatkowych bibliotek graficznych.  

## Prerequisites
Zanim zanurzysz się w samouczek, upewnij się, że spełniasz następujące wymagania:
- Podstawowa znajomość programowania w Javie.  
- Biblioteka Aspose.Page for Java zainstalowana. Jeśli nie, pobierz ją z [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- Środowisko programistyczne Java skonfigurowane na Twoim komputerze.

## Importowanie pakietów
W swoim projekcie Java rozpocznij od zaimportowania niezbędnych pakietów. Te importy dają dostęp do klas AWT `Color`, `BasicStroke` i `Rectangle2D`, a także do podstawowych klas obsługi dokumentów Aspose.Page.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Przewodnik krok po kroku: rysowanie prostokąta w Java PostScript

### Krok 1: Ustawienie koloru wypełnienia prostokąta  
**How to set paint** – wybieramy pomarańczowy kolor wypełnienia dla pierwszego prostokąta. To demonstruje możliwość **set rectangle color java**.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Set paint for filling rectangle
document.setPaint(Color.ORANGE);        
// Fill the first rectangle
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```

### Krok 2: Ustawienie koloru obrysu prostokąta  
**Set rectangle color java** – teraz zmieniamy kolor na czerwony i definiujemy szerokość linii. Ta część przykładu pokazuje, jak **draw rectangle java** z niestandardową grubością linii.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### Krok 3: Zamknięcie bieżącej strony i zapisanie dokumentu  
Po narysowaniu zamykamy stronę i zapisujemy plik. Zamknięcie strony zapewnia, że wszystkie polecenia rysowania zostaną wypchnięte do strumienia PostScript.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Typowe zastosowania rysowania prostokątów
- **Invoice or receipt generation** – prostokąty pełnią rolę ramek lub podkreślają sekcje.  
- **Label creation** – rysuj kolorowe pola, aby oddzielić informacje o produkcie.  
- **Simple charts** – używaj wypełnionych prostokątów jako elementów wykresów słupkowych.  
- **Custom printable forms** – łącz prostokąty z tekstem, aby tworzyć pola formularzy.

## Częste problemy i wskazówki
- **File path errors** – upewnij się, że `dataDir` kończy się separatorem plików (`/` lub `\\`).  
- **License exceptions** – wersja próbna dodaje znak wodny; uzyskaj pełną licencję do użytku produkcyjnego.  
- **Color visibility** – niektóre drukarki mogą inaczej interpretować niektóre wartości RGB; najpierw przetestuj prosty czarny prostokąt.  
- **Memory usage** – przy dużych dokumentach rozważ opróżnianie strumienia po każdej stronie (`document.closePage()`).

## Najczęściej zadawane pytania

**Q:** *Czy mogę używać Aspose.Page dla Javy z innymi językami programowania?*  
A: Aspose.Page głównie obsługuje Javę, ale dostępne są podobne biblioteki dla innych języków.

**Q:** *Czy dostępna jest wersja próbna Aspose.Page dla Javy?*  
A: Tak, możesz zapoznać się z funkcjami Aspose.Page dla Javy korzystając z [free trial version](https://releases.aspose.com/).

**Q:** *Gdzie mogę znaleźć dodatkową pomoc i dyskusje?*  
A: Odwiedź [Aspose.Page forum](https://forum.aspose.com/c/page/39), aby skontaktować się ze społecznością i uzyskać pomoc.

**Q:** *Jak mogę uzyskać tymczasową licencję na Aspose.Page dla Javy?*  
A: Uzyskaj tymczasową licencję [here](https://purchase.aspose.com/temporary-license/).

**Q:** *Gdzie mogę kupić licencjonowaną wersję Aspose.Page dla Javy?*  
A: Kup licencjonowaną wersję [here](https://purchase.aspose.com/buy).

**Additional Q&A**

**Q:** *Czy mogę dynamicznie zmieniać rozmiar prostokąta?*  
A: Tak – po prostu zmodyfikuj parametry `Rectangle2D.Float(x, y, width, height)` przed wywołaniem `fill` lub `draw`.

**Q:** *Czy można dodać tekst wewnątrz prostokąta?*  
A: Oczywiście. Po narysowaniu prostokąta użyj `document.drawString(...)` z wybraną czcionką i pozycją.

**Q:** *Czy Aspose.Page obsługuje inne kształty, takie jak koła lub wielokąty?*  
A: Tak, API udostępnia metody takie jak `drawEllipse` i `drawPolygon` dla różnych grafik wektorowych.

## Podsumowanie
W tym przewodniku pokazaliśmy, jak **how to draw rectangle** kształty w dokumencie Java PostScript, omówiliśmy **how to set paint** oraz przedstawiliśmy, jak **set rectangle color java** przy użyciu Aspose.Page. Masz teraz solidne podstawy do tworzenia żywych grafik do druku, niezależnie od tego, czy tworzysz faktury, etykiety, czy niestandardowe formularze. Śmiało eksperymentuj z różnymi kolorami, stylami linii i dodatkowymi kształtami AWT, aby wzbogacić swój wynik.

---

**Ostatnia aktualizacja:** 2026-02-18  
**Testowano z:** Aspose.Page for Java 24.12 (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}