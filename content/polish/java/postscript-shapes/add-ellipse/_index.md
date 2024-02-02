---
title: Dodaj elipsę w języku Java PostScript
linktitle: Dodaj elipsę w języku Java PostScript
second_title: Aspose.Page API Java
description: Opanuj tworzenie wspaniałych dokumentów PostScript w Javie dzięki Aspose.Page. Dowiedz się, jak krok po kroku dodawać elipsy, aby uzyskać atrakcyjną wizualnie treść.
type: docs
weight: 10
url: /pl/java/postscript-shapes/add-ellipse/
---
## Wstęp
W dynamicznym świecie programowania w języku Java tworzenie atrakcyjnych wizualnie dokumentów jest powszechnym wymogiem. Aspose.Page dla Java to potężna biblioteka, która umożliwia programistom łatwe manipulowanie plikami PostScript. W tym samouczku omówimy, jak dodawać elipsy do dokumentów PostScript za pomocą Aspose.Page dla Java. Śledź dalej, aby udoskonalić swoje umiejętności tworzenia dokumentów!
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że masz skonfigurowane następujące wymagania wstępne:
1. Środowisko programistyczne Java: Upewnij się, że na komputerze jest zainstalowane funkcjonalne środowisko programistyczne Java.
2.  Biblioteka Aspose.Page dla Java: Pobierz i dołącz bibliotekę Aspose.Page do swojego projektu Java. Możesz znaleźć drogę do biblioteki[Tutaj](https://releases.aspose.com/page/java/).
## Importuj pakiety
kodzie Java zaimportuj niezbędne pakiety, aby móc korzystać z funkcjonalności Aspose.Page. Oto przykład:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Krok 1: Skonfiguruj swój dokument
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz strumień wyjściowy dla dokumentu PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Twórz opcje zapisywania w formacie A4
PsSaveOptions options = new PsSaveOptions();
// Utwórz nowy dokument PS z otwartą stroną
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Krok 2: Wypełnij elipsę kolorem
```java
// Ustaw farbę do wypełnienia elipsy
document.setPaint(Color.ORANGE);
// Wypełnij pierwszą elipsę
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```
## Krok 3: Zarysuj elipsę za pomocą obrysu
```java
// Ustaw farbę do głaskania elipsy
document.setPaint(Color.RED);
// Ustaw skok
document.setStroke(new BasicStroke(3));
// Obrysuj (zarysuj) drugą elipsę
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```
## Krok 4: Zamknij i zapisz dokument
```java
// Zamknij bieżącą stronę
document.closePage();
// Zapisz dokument
document.save();
```
Teraz pomyślnie dodałeś elipsy do swojego dokumentu PostScript za pomocą Aspose.Page dla Java! Eksperymentuj z różnymi współrzędnymi i wymiarami, aby dostosować swoje efekty wizualne.
## Wniosek
 Aspose.Page dla Java upraszcza proces tworzenia i manipulowania dokumentami PostScript. Ten samouczek wyposażył Cię w wiedzę dotyczącą dodawania elips, zapewniając solidną podstawę do tworzenia bardziej złożonych wizualizacji. Zanurz się w[dokumentacja](https://reference.aspose.com/page/java/) aby poznać dalsze szczegóły i możliwości.
## Często zadawane pytania
### P: Czy mogę używać Aspose.Page dla Java z innymi bibliotekami Java?
O: Tak, Aspose.Page dla Java został zaprojektowany tak, aby bezproblemowo integrować się z innymi bibliotekami Java.
### P: Jak mogę uzyskać tymczasową licencję na Aspose.Page dla Java?
 Odp.: Uzyskaj tymczasową licencję[Tutaj](https://purchase.aspose.com/temporary-license/) do celów testowych.
### P: Czy Aspose.Page nadaje się do projektów komercyjnych?
 Odp.: Absolutnie! Odwiedzać[Tutaj](https://purchase.aspose.com/buy) w celu zbadania możliwości licencjonowania do użytku komercyjnego.
### P: Gdzie mogę szukać pomocy lub omówić zapytania związane z Aspose.Page?
 O: Dołącz do społeczności na stronie[Forum Aspose.Page](https://forum.aspose.com/c/page/39) za dyskusję i pomoc.
### P: Czy są jakieś bezpłatne zasoby, dzięki którym można dowiedzieć się więcej o Aspose.Page dla Java?
 Odp.: Skorzystaj z[bezpłatna wersja próbna](https://releases.aspose.com/) i zapoznaj się z przykładami w dokumentacji.