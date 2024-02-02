---
title: Dodaj gradient ukośny w Java XPS
linktitle: Dodaj gradient ukośny w Java XPS
second_title: Aspose.Page API Java
description: Dowiedz się, jak dodać oszałamiający gradient ukośny do dokumentów XPS w Javie za pomocą Aspose.Page. Podnieś poziom swojej prezentacji wizualnej bez wysiłku.
type: docs
weight: 10
url: /pl/java/xps-gradient-addition/diagonal/
---
## Wstęp
stale rozwijającym się świecie programowania w języku Java kluczowe znaczenie ma poprawa atrakcyjności wizualnej dokumentów XPS. Jednym ze skutecznych sposobów osiągnięcia tego jest zastosowanie gradientów ukośnych. Ten samouczek poprowadzi Cię przez proces korzystania z Aspose.Page dla Java, dostarczając instrukcje krok po kroku i fragmenty kodu.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Podstawowa znajomość programowania w języku Java.
- Zainstalowano zestaw Java Development Kit (JDK) w systemie.
-  Aspose.Page dla biblioteki Java. Możesz go pobrać[Tutaj](https://releases.aspose.com/page/java/).
- Edytor kodu, taki jak IntelliJ IDEA lub Eclipse.
## Importuj pakiety
Rozpocznij od zaimportowania niezbędnych pakietów dla projektu Java. W swoim kodzie możesz dodać następujące importy:
```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```
## Krok 1: Skonfiguruj swój projekt
Utwórz nowy projekt Java w preferowanym zintegrowanym środowisku programistycznym (IDE) i dołącz bibliotekę Aspose.Page do zależności projektu.
## Krok 2: Zdefiniuj katalog dokumentów
Ustaw ścieżkę do katalogu dokumentów, w którym zostanie zapisany plik XPS:
```java
String dataDir = "Your Document Directory";
```
## Krok 3: Utwórz dokument XPS
Zainicjuj nowy obiekt XpsDocument:
```java
XpsDocument doc = new XpsDocument();
```
## Krok 4: Dodaj ukośną ścieżkę gradientu
Dodaj ścieżkę do dokumentu XPS z gradientem ukośnym:
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```
## Krok 5: Zdefiniuj liniowe punkty gradientu
Skonfiguruj przystanki gradientu liniowego z określonymi kolorami i pozycjami:
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... powtórz dla innych kolorów i pozycji
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```
## Krok 6: Zastosuj gradient liniowy do ścieżki
Zastosuj gradient liniowy do wcześniej zdefiniowanej ścieżki:
```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## Krok 7: Zapisz dokument
Zapisz dokument XPS z dodanym gradientem ukośnym:
```java
doc.save(dataDir + "LinearGradient.xps");
```
## Wniosek
Gratulacje! Pomyślnie dodałeś gradient ukośny do dokumentu XPS przy użyciu Aspose.Page dla Java. Ta atrakcyjna wizualnie funkcja może poprawić ogólną prezentację dokumentów.
## Często Zadawane Pytania
### P: Czy mogę używać Aspose.Page dla Java z innymi frameworkami Java?
Aspose.Page został zaprojektowany tak, aby bezproblemowo integrować się z różnymi frameworkami Java, co czyni go wszechstronnym wyborem dla Twoich projektów.
### P: Czy istnieją jakieś uwagi dotyczące licencji na Aspose.Page?
 Tak, pamiętaj o sprawdzeniu szczegółów licencji na stronie[Strona zakupu Aspose.Page](https://purchase.aspose.com/buy).
### P: Czy mogę wypróbować Aspose.Page dla Java przed zakupem?
 Absolutnie! Możesz zwiedzić m.in[bezpłatna wersja próbna tutaj](https://releases.aspose.com/).
### P: Jak mogę uzyskać wsparcie lub połączyć się ze społecznością Aspose?
 Odwiedzić[Forum Aspose.Page](https://forum.aspose.com/c/page/39) nawiązać kontakt ze społecznością i poprosić o pomoc.
### P: Czy istnieje przepis dotyczący licencji tymczasowych?
 Tak, możesz uzyskać[licencja tymczasowa tutaj](https://purchase.aspose.com/temporary-license/).