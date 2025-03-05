---
title: Dodaj prostokąt w Java XPS
linktitle: Dodaj prostokąt w Java XPS
second_title: Aspose.Page API Java
description: Dowiedz się, jak dodawać prostokąty w Java XPS przy użyciu Aspose.Page. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby bezproblemowo manipulować dokumentami. #JavaXPS #AsposePage
type: docs
weight: 11
url: /pl/java/xps-shapes/add-rectangle/
---
## Wstęp
Witamy w tym obszernym przewodniku na temat dodawania prostokątów w Java XPS przy użyciu Aspose.Page! Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz przygodę z Java XPS, ten samouczek przeprowadzi Cię przez proces za pomocą instrukcji krok po kroku, zapewniając głębokie zrozumienie tematu.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Podstawowa znajomość języka programowania Java.
-  Zainstalowana biblioteka Aspose.Page. Jeśli nie, możesz pobrać go ze strony[Dokumentacja Java Aspose.Page](https://reference.aspose.com/page/java/).
- Działające środowisko programistyczne Java.
## Importuj pakiety
Aby rozpocząć, zaimportuj niezbędne pakiety do swojego projektu Java. Upewnij się, że biblioteka Aspose.Page została poprawnie dodana do ścieżki klas. Oto podstawowy przykład:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```
Podzielmy teraz podany przykład na wiele kroków, aby dodać prostokąt w Java XPS.
## Krok 1: Ustaw katalog dokumentów
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
```
Zastąp „Twój katalog dokumentów” ścieżką do żądanego katalogu.
## Krok 2: Utwórz nowy dokument XPS
```java
// Utwórz nowy dokument XPS
XpsDocument doc = new XpsDocument();
```
Spowoduje to inicjowanie nowego dokumentu XPS.
## Krok 3: Dodaj obrysowany prostokąt w jednolitym kolorze CMYK
```java
// Obrysowany prostokąt w jednolitym kolorze CMYK (niebieski) w lewym dolnym rogu
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
tym kroku dodawany jest obrysowany prostokąt z jednolitym kolorem CMYK.
## Krok 4: Zapisz wynikowy dokument XPS
```java
// Zapisz wynikowy dokument XPS
doc.save(dataDir + "AddRectangle_out.xps");
```
Na koniec zapisz zmodyfikowany dokument XPS z dodanym prostokątem.
Powtórz te kroki, dostosowując parametry w razie potrzeby, aby jeszcze bardziej dostosować prostokąty.
## Wniosek
Gratulacje! Pomyślnie nauczyłeś się dodawać prostokąty w Java XPS przy użyciu Aspose.Page. Ten samouczek zapewnia solidną podstawę do manipulacji dokumentami XPS.
## Często zadawane pytania
### Czy mogę dodać wiele prostokątów w jednym dokumencie XPS?
Tak, możesz dodać dowolną liczbę prostokątów, powtarzając kroki opisane w samouczku.
### Jak zmienić kolor prostokąta?
 Zmodyfikuj wartości kolorów w pliku`createColor` sposób na uzyskanie pożądanego koloru.
### Czy Aspose.Page nadaje się do obsługi złożonych manipulacji dokumentami XPS?
Absolutnie! Aspose.Page zapewnia solidny zestaw funkcji do obsługi różnych zadań związanych z dokumentami XPS.
### Gdzie mogę znaleźć dodatkowe przykłady i wsparcie?
 Poznaj[Forum Aspose.Page](https://forum.aspose.com/c/page/39)aby uzyskać więcej przykładów, i zwróć się o pomoc do społeczności.
### Czy mogę wypróbować Aspose.Page przed zakupem?
 Tak, możesz poznać m.in[bezpłatna wersja próbna](https://releases.aspose.com/) aby poznać możliwości Aspose.Page.