---
title: Dodaj obraz kafelkowy w Java XPS
linktitle: Dodaj obraz kafelkowy w Java XPS
second_title: Aspose.Page API Java
description: Poznaj bezproblemową manipulację dokumentami Java XPS za pomocą Aspose.Page. Dzięki temu przewodnikowi krok po kroku nauczysz się bezproblemowo dodawać obrazy sąsiadująco.
type: docs
weight: 11
url: /pl/java/xps-image-manipulation/add-tiled-image/
---
## Wstęp
dynamicznym świecie programowania w języku Java stale rośnie potrzeba wydajnego manipulowania i tworzenia dokumentów. Aspose.Page dla Java jawi się jako potężne narzędzie, zapewniające programistom możliwość płynnej pracy z dokumentami XPS. Ten samouczek koncentruje się na konkretnym zadaniu — dodaniu obrazu sąsiadującego do dokumentu Java XPS.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
1. Zestaw Java Development Kit (JDK): Upewnij się, że masz zainstalowany pakiet JDK w swoim systemie.
2.  Aspose.Page dla Java: Pobierz i zainstaluj Aspose.Page dla Java z[strona internetowa](https://releases.aspose.com/page/java/).
3. Twój katalog dokumentów: wybierz lub utwórz katalog, w którym chcesz zapisać dokument XPS.
## Importuj pakiety
W swoim projekcie Java zaimportuj niezbędne pakiety, aby móc korzystać z funkcjonalności Aspose.Page:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
Podzielmy teraz proces dodawania obrazu sąsiadującego do dokumentu Java XPS na jasne i łatwe do wykonania kroki.
## Krok 1: Skonfiguruj swój projekt
Zacznij od skonfigurowania projektu Java i upewnij się, że Aspose.Page for Java jest prawidłowo zintegrowany.
## Krok 2: Utwórz dokument XPS
Zainicjuj nowy dokument XPS, używając następującego kodu:
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz nowy dokument XPS
XpsDocument doc = new XpsDocument();
```
## Krok 3: Zdefiniuj ścieżkę obrazu sąsiadującą z obrazem
Określ ścieżkę do obrazu sąsiadującego, który chcesz dodać do dokumentu XPS.
## Krok 4: Dodaj obraz kafelkowy
Skorzystaj z poniższego fragmentu kodu, aby dodać obraz sąsiadujący z dokumentem XPS:
```java
// Obraz kafelkowy
// Prostokąt wypełniony ImageBrush w prawym górnym rogu poniżej
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```
## Krok 5: Zapisz dokument
Na koniec zapisz powstały dokument XPS, korzystając z poniższego kodu:
```java
// Zapisz wynikowy dokument XPS
doc.save(dataDir + "AddTiledImage_out.xps"); 
```
Powtórz te kroki, aby bez wysiłku włączyć obraz kafelkowy do dokumentu Java XPS za pomocą Aspose.Page.
## Wniosek
Aspose.Page dla Java usprawnia proces pracy z dokumentami XPS, oferując programistom wydajne rozwiązanie do manipulacji dokumentami. Postępując zgodnie z tym przewodnikiem krok po kroku, możesz bez trudu dodać obraz sąsiadujący do dokumentu Java XPS.

## Często zadawane pytania
### Czy Aspose.Page jest kompatybilny ze wszystkimi wersjami Java?
 Aspose.Page jest zaprojektowany do pracy z różnymi wersjami Java. Zapewnij kompatybilność, sprawdzając dokumentację[Tutaj](https://reference.aspose.com/page/java/).
### Czy mogę używać Aspose.Page do projektów komercyjnych?
Tak, Aspose.Page oferuje licencje komercyjne. Kup je[Tutaj](https://purchase.aspose.com/buy).
### Czy dostępny jest bezpłatny okres próbny?
 Tak, poznaj funkcje Aspose.Page w ramach bezpłatnej wersji próbnej[Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć wsparcie i dyskusje społeczności?
 Nawiąż kontakt ze społecznością Aspose.Page na stronie[forum](https://forum.aspose.com/c/page/39).
### Jak mogę uzyskać tymczasową licencję na Aspose.Page?
 Zdobądź licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).