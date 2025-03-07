---
title: Ustaw maskę krycia w Java XPS
linktitle: Ustaw maskę krycia w Java XPS
second_title: Aspose.Page API Java
description: Odkryj moc ustawiania masek kryjących w Java XPS za pomocą Aspose.Page. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby uzyskać lepszą wizualnie obsługę dokumentów.
weight: 11
url: /pl/java/xps-transparency/set-opacity-mask/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw maskę krycia w Java XPS

## Wstęp
Witamy w naszym obszernym przewodniku na temat ustawiania masek kryjących w Java XPS przy użyciu Aspose.Page. W tym samouczku przeprowadzimy Cię przez proces tworzenia dokumentu XPS, dodawania płótna i stosowania maski kryjącej do prostokąta przy użyciu zaawansowanych funkcji Aspose.Page dla Java.
## Warunki wstępne
Zanim zagłębisz się w ten samouczek, upewnij się, że posiadasz następujące elementy:
- Podstawowa znajomość programowania w języku Java.
-  Zainstalowana biblioteka Aspose.Page dla Java. Możesz go pobrać[Tutaj](https://releases.aspose.com/page/java/).
-  Ważna licencja na Aspose.Page. Jeśli go nie posiadasz, możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
- Środowisko programistyczne skonfigurowane do uruchamiania aplikacji Java.
## Importuj pakiety
Zacznij od zaimportowania niezbędnych pakietów do projektu Java. Upewnij się, że masz prawidłowo zintegrowaną bibliotekę Aspose.Page. Poniżej znajduje się fragment, który Cię poprowadzi:
```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
Podzielmy teraz przykładowy kod na kilka kroków:
## Krok 1: Utwórz nowy dokument XPS
```java
// Utwórz nowy dokument XPS
XpsDocument doc = new XpsDocument();
```
## Krok 2: Dodaj płótno
```java
// Nowe płótno
XpsCanvas canvas = doc.addCanvas();
```
## Krok 3: Dodaj prostokąt z maską krycia
```java
// Prostokąt pośrodku po lewej stronie z nieprzezroczystością maskowaną przez ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```
## Krok 4: Ustaw maskę krycia za pomocą ImageBrush
```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```
## Krok 5: Zapisz wynikowy dokument XPS
```java
// Zapisz wynikowy dokument XPS
doc.save(dataDir + "OpacityMask_out.xps"); 
```
Wykonaj uważnie poniższe kroki, aby włączyć maski kryjące do dokumentu Java XPS za pomocą Aspose.Page.
## Wniosek
Gratulacje! Pomyślnie nauczyłeś się ustawiać maski kryjące w Java XPS za pomocą Aspose.Page. Ta funkcja dodaje warstwę bogactwa wizualnego do Twoich dokumentów, czyniąc je bardziej wciągającymi i dynamicznymi.
## Często zadawane pytania
### Czy Aspose.Page jest kompatybilny ze wszystkimi środowiskami programistycznymi Java?
Tak, Aspose.Page został zaprojektowany do bezproblemowej współpracy z różnymi środowiskami programistycznymi Java.
### Czy mogę używać Aspose.Page bez licencji?
Chociaż możesz używać Aspose.Page bez licencji, zaleca się uzyskanie takiej, aby uzyskać pełny zakres funkcji i wsparcia.
### Czy są jakieś ograniczenia wersji próbnej?
Wersja próbna może mieć pewne ograniczenia funkcji. Zaleca się sprawdzenie dokumentacji w celu uzyskania szczegółowych informacji.
### Jak mogę uzyskać pomoc dotyczącą Aspose.Page?
 Możesz odwiedzić[Forum Aspose.Page](https://forum.aspose.com/c/page/39) uzyskać wsparcie społeczności lub kupić licencję na pomoc premium.
### Czy Aspose.Page gwarantuje zwrot pieniędzy?
 Patrz[strona zakupu](https://purchase.aspose.com/buy) aby uzyskać informacje na temat zasad zwrotów.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
