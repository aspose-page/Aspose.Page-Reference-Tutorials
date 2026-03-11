---
date: 2025-12-30
description: Dowiedz się, jak tworzyć dokumenty XPS w Javie, dodając prostokąty przy
  użyciu Aspose.Page. Skorzystaj z tego przewodnika krok po kroku, aby płynnie manipulować
  dokumentami XPS.
linktitle: Create XPS Document Java – Add Rectangle
second_title: Aspose.Page Java API
title: Utwórz dokument XPS w Javie – Dodaj prostokąt za pomocą Aspose.Page
url: /pl/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz dokument XPS w Javie – Dodaj prostokąt

## Wprowadzenie
W tym kompleksowym samouczku **utworzysz dokumenty XPS w Javie** i nauczysz się, jak dodawać prostokąty przy użyciu biblioteki Aspose.Page. Niezależnie od tego, czy tworzysz raporty, faktury, czy własne grafiki, opanowanie tworzenia prostokątów daje precyzyjną kontrolę nad układem XPS. Przeprowadzimy Cię przez każdy krok, wyjaśnimy, dlaczego używamy poszczególnych linii kodu, oraz pokażemy, jak dostosować kolory i obramowania, aby uzyskać profesjonalny efekt.

## Szybkie odpowiedzi
- **Jakiej biblioteki używać?** Aspose.Page for Java  
- **Jak długo trwa implementacja?** Około 10 minut dla podstawowego prostokąta  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna wystarczy do rozwoju; licencja komercyjna jest wymagana w produkcji  
- **Jaką wersję Javy obsługuje?** Java 8 i nowsze  
- **Czy mogę dodać wiele kształtów?** Tak – powtórz kroki dla każdego kształtu

## Wymagania wstępne
Zanim przejdziesz dalej, upewnij się, że masz:

- Podstawową znajomość języka programowania Java.  
- Zainstalowaną bibliotekę Aspose.Page. Jeśli jej nie masz, możesz pobrać ją z [dokumentacji Aspose.Page Java](https://reference.aspose.com/page/java/).  
- Działające środowisko programistyczne Java (IDE, JDK oraz Maven/Gradle, jeśli wolisz).

## Importowanie pakietów
Aby rozpocząć, zaimportuj niezbędne pakiety do swojego projektu Java. Upewnij się, że biblioteka Aspose.Page została poprawnie dodana do classpath. Oto podstawowy przykład:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Teraz rozbijmy podany przykład na kilka kroków, aby dodać prostokąt w XPS przy użyciu Javy.

## Krok 1: Ustaw katalog dokumentu
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

Zastąp `"Your Document Directory"` ścieżką do folderu, w którym chcesz przechowywać pliki XPS.

## Krok 2: Utwórz nowy dokument XPS
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Ta linia **tworzy** nowy dokument XPS, który później możesz wypełnić kształtami, tekstem lub obrazami.

## Krok 3: Dodaj prostokąt z obramowaniem w kolorze CMYK
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```

Ten krok dodaje prostokąt z obramowaniem w jednolitym kolorze CMYK. Możesz zmienić ciąg geometryczny (`"M 20,10 L 220,10 220,100 20,100 Z"`), aby zmodyfikować rozmiar lub położenie, oraz dostosować wartości kolorów w `createColor`, aby pasowały do Twojego projektu.

## Krok 4: Zapisz powstały dokument XPS
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```

Na koniec zapisz zmodyfikowany dokument XPS z dodanym prostokątem w katalogu określonym wcześniej.

## Typowe przypadki użycia
- **Nagłówki raportów** – używaj prostokątów jako tła dla tytułów.  
- **Tabele faktur** – podkreślaj komórki lub sekcje kolorowymi obramowaniami.  
- **Grafiki własne** – łącz wiele prostokątów, aby tworzyć złożone kształty.

## Wskazówki rozwiązywania problemów
- **Błąd pliku nie znaleziono:** Sprawdź, czy `dataDir` wskazuje istniejący folder oraz czy profil ICC (`uswebuncoated.icc`) jest dostępny.  
- **Nieprawidłowe kolory:** Upewnij się, że profil ICC odpowiada przestrzeni kolorów, której używasz (CMYK vs. RGB).  
- **Nieoczekiwane wymiary:** Dostosuj ciąg geometryczny, aby odzwierciedlał prawidłowe współrzędne.

## Zakończenie
Gratulacje! Pomyślnie nauczyłeś się, jak **tworzyć dokumenty XPS w Javie** i dodawać prostokąty przy użyciu Aspose.Page. Ta podstawa pozwala budować bardziej rozbudowane dokumenty XPS, personalizować grafikę i integrować kształty w większych przepływach pracy.

## Najczęściej zadawane pytania
### Czy mogę dodać wiele prostokątów w jednym dokumencie XPS?
Tak, możesz dodać dowolną liczbę prostokątów, powtarzając kroki opisane w samouczku.

### Jak mogę zmienić kolor prostokąta?
Zmodyfikuj wartości kolorów w metodzie `createColor`, aby uzyskać pożądany odcień.

### Czy Aspose.Page nadaje się do obsługi skomplikowanych manipulacji dokumentami XPS?
Zdecydowanie! Aspose.Page oferuje bogaty zestaw funkcji do obsługi różnorodnych zadań związanych z dokumentami XPS.

### Gdzie mogę znaleźć dodatkowe przykłady i wsparcie?
Odwiedź [forum Aspose.Page](https://forum.aspose.com/c/page/39), aby znaleźć więcej przykładów i uzyskać pomoc od społeczności.

### Czy mogę wypróbować Aspose.Page przed zakupem?
Tak, możesz wypróbować [bezpłatną wersję próbną](https://releases.aspose.com/), aby zapoznać się z możliwościami Aspose.Page.

## Frequently Asked Questions

**Q: Czy to podejście działa z Java 11 lub nowszą?**  
A: Tak, biblioteka Aspose.Page jest kompatybilna z Java 8 i późniejszymi wersjami, w tym Java 11, 17 i wyższymi.

**Q: Czy mogę osadzić obrazy wewnątrz obszaru prostokąta?**  
A: Możesz dodać element `XpsImage` i umieścić go nad lub wewnątrz prostokąta, używając tych samych współrzędnych geometrycznych.

**Q: Jak ustawić kolor wypełnienia zamiast samego obramowania?**  
A: Wywołaj `path.setFill(...)` z pędzlem jednolitego koloru utworzonym przez `doc.createSolidColorBrush(...)`.

**Q: Czy można obrócić prostokąt?**  
A: Zastosuj macierz transformacji do ścieżki przy użyciu `path.setTransform(...)`, aby uzyskać obrót lub skalowanie.

**Q: Jakiej licencji potrzebuję do użytku produkcyjnego?**  
A: Do wdrożenia wymagana jest komercyjna licencja Aspose.Page; wersja próbna jest ograniczona do oceny i rozwoju.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2025-12-30  
**Testowano z:** Aspose.Page for Java 24.12 (latest)  
**Autor:** Aspose  

---