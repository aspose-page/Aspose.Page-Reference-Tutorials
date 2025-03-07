---
title: Zmień rozmiar plików EPS w Javie za pomocą Aspose.Page
linktitle: Zmień rozmiar pliku EPS w Javie
second_title: Aspose.Page API Java
description: Dowiedz się, jak łatwo zmieniać rozmiar plików EPS w Javie dzięki Aspose.Page dla Java. Postępuj zgodnie z naszym obszernym przewodnikiem, aby uzyskać instrukcje krok po kroku.
weight: 11
url: /pl/java/manipulation-eps/resize/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zmień rozmiar plików EPS w Javie za pomocą Aspose.Page

## Wstęp
Witamy w naszym przewodniku krok po kroku dotyczącym zmiany rozmiaru plików EPS w Javie przy użyciu potężnej biblioteki Aspose.Page. Jeśli kiedykolwiek potrzebowałeś programowo dostosować wymiary obrazów EPS, jesteś we właściwym miejscu. W tym samouczku omówimy różne opcje zmiany rozmiaru, w tym punkty, cale, milimetry i wartości procentowe, zapewniając elastyczność potrzebną do konkretnych wymagań.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że posiadasz następujące elementy:
- Zestaw Java Development Kit (JDK) zainstalowany na komputerze.
-  Aspose.Page dla biblioteki Java. Możesz go pobrać[Tutaj](https://releases.aspose.com/page/java/).
- Podstawowa znajomość programowania w języku Java.
## Importuj pakiety
W swoim projekcie Java upewnij się, że masz niezbędne importy, aby móc korzystać z funkcjonalności Aspose.Page. Oto przykład:
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;

```
Podzielmy teraz samouczek na kilka kroków dla każdej opcji zmiany rozmiaru:
## Zmień rozmiar EPS za pomocą punktów
### Krok 1: Skonfiguruj strumień wejściowy
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
### Krok 2: Zainicjuj obiekt PsDocument
```java
PsDocument doc = new PsDocument(inputEpsStream);
```
### Krok 3: Wyodrębnij bieżący rozmiar obrazu EPS
```java
Dimension oldSize = doc.extractEpsSize();
```
### Krok 4: Utwórz strumień wyjściowy
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```
### Krok 5: Zmień rozmiar i zapisz w punktach
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```
## Zmień rozmiar EPS za pomocą cali
Wykonaj podobne kroki jak w przykładzie 1, zastępując „Punkty” „Calami” i odpowiednio dostosowując nowy rozmiar.
## Zmień rozmiar EPS za pomocą milimetrów
Wykonaj podobne kroki jak w przykładzie 1, zastępując „Punkty” „Milimetrami” i odpowiednio dostosowując nowy rozmiar.
## Zmień rozmiar EPS za pomocą procentów
Wykonaj podobne kroki jak w przykładzie 1, zastępując „Punkty” „Procentami” i odpowiednio dostosowując nowy rozmiar.
## Wniosek
Gratulacje! Pomyślnie nauczyłeś się zmieniać rozmiar plików EPS w Javie za pomocą Aspose.Page. W tym przewodniku znajdziesz wszechstronne opcje, dzięki którym możesz dostosować proces zmiany rozmiaru do swoich konkretnych potrzeb.

## Często zadawane pytania
### Czy mogę używać tej biblioteki do innych formatów obrazów?
Nie, Aspose.Page jest specjalnie zaprojektowany do obsługi plików PostScript i EPS.
### Czy dostępna jest bezpłatna wersja próbna Aspose.Page dla Java?
Tak, możesz skorzystać z bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć dodatkową pomoc i dyskusje?
 Odwiedzić[Forum Aspose.Page](https://forum.aspose.com/c/page/39) za wsparcie społeczności.
### Jak mogę uzyskać licencję tymczasową?
 Możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
### Czy są dostępne jakieś przykładowe projekty?
 Tak, sprawdź dokumentację[Tutaj](https://reference.aspose.com/page/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
