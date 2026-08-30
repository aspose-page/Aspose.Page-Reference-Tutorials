---
date: 2026-04-24
description: Dowiedz się, jak ustawić kolor prostokąta i dodać prostokąt w Java XPS
  przy użyciu Aspose.Page. Ten przewodnik obejmuje dodawanie prostokąta w Javie oraz
  zmianę obrysu prostokąta.
keywords:
- set rectangle color
- add rectangle java
- change rectangle stroke
linktitle: Dodaj prostokąt w Java XPS
second_title: Aspose.Page Java API
title: Ustaw kolor prostokąta i dodaj prostokąt w Java XPS
url: /pl/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw kolor prostokąta i dodaj prostokąt w Java XPS

## Wprowadzenie
W tym przewodniku dowiesz się, jak **ustawić kolor prostokąta** oraz **dodać prostokąt** w Java XPS przy użyciu biblioteki Aspose.Page. Niezależnie od tego, czy potrzebujesz narysować proste kształty do raportu, czy stworzyć złożoną grafikę wektorową, opanowanie stylizacji prostokątów daje precyzyjną kontrolę nad dokumentami XPS.  

## Szybkie odpowiedzi
- **Jakiej biblioteki wymaga?** Aspose.Page for Java  
- **Czy mogę zmienić obrys prostokąta?** Tak, używając `setStroke` i `setStrokeThickness`  
- **Czy obsługiwany jest profil kolorów CMYK?** Absolutnie – możesz wczytać profile ICC, jak pokazano  
- **Czy potrzebna jest licencja do produkcji?** Tak, wymagana jest licencja komercyjna dla użytku nie‑ewaluacyjnego  
- **Jak długo trwa implementacja?** Zazwyczaj poniżej 10 minut dla podstawowego prostokąta

## Czym jest **set rectangle color**?
Ustawienie koloru prostokąta oznacza określenie koloru wypełnienia lub obrysu, którym kształt zostanie wyrenderowany w finalnym dokumencie XPS. Dzięki Aspose.Page możesz używać RGB, CMYK lub nawet własnych profili kolorów ICC, aby uzyskać dokładne dopasowanie kolorów.

## Dlaczego używać Aspose.Page do **add rectangle java** i **change rectangle stroke**?
- **Full‑featured API** – obsługuje zarówno kolory stałe, jak i gradienty.  
- **Cross‑platform** – działa na dowolnym środowisku Java bez zależności natywnych.  
- **Rich geometry support** – twórz złożone ścieżki, stosuj transformacje i zarządzaj grubością obrysu w prosty sposób.  

## Wymagania wstępne
Zanim przejdziesz do kodu, upewnij się, że masz:

- Podstawową znajomość programowania w Javie.  
- Zainstalowaną bibliotekę Aspose.Page. Jeśli nie, pobierz ją z [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).  
- Działające środowisko programistyczne Java (IDE, JDK itp.).  

## Importowanie pakietów
Aby rozpocząć, zaimportuj niezbędne pakiety do swojego projektu Java. Upewnij się, że biblioteka Aspose.Page jest poprawnie dodana do classpath. Oto podstawowy przykład:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Teraz rozbijmy podany przykład na kilka kroków, aby **dodać prostokąt** i **ustawić jego kolor** w Java XPS.

## Krok 1: Ustaw katalog dokumentu
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
Zastąp `"Your Document Directory"` absolutną ścieżką, w której chcesz odczytywać/zapisywać pliki XPS.

## Krok 2: Utwórz nowy dokument XPS
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```
Ta linia inicjalizuje nowy dokument XPS, który będzie przechowywał nasze kształty.

## Krok 3: Dodaj prostokąt z obrysem w kolorze CMYK
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
Ten krok dodaje **prostokąt z obrysem** w stałym kolorze CMYK. Metoda `setStroke` definiuje kolor konturu prostokąta, natomiast `setStrokeThickness` kontroluje szerokość linii — idealne do **zmiany obrysu prostokąta**.

### Porada:
Jeśli wolisz kolor RGB, zamień wywołanie `createColor` na `doc.createColor(0, 0, 255)` dla stałego niebieskiego wypełnienia.

## Krok 4: Zapisz wynikowy dokument XPS
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```
Na koniec zapisz dokument XPS na dysku. Plik `AddRectangle_out.xps` zawiera teraz prostokąt, którego kolor i obrys zostały zdefiniowane.

## Typowe problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|-------|-------|----------|
| **Rectangle not visible** | Nieprawidłowa geometria ścieżki lub grubość obrysu ustawiona na 0 | Zweryfikuj ciąg ścieżki (`"M 20,10 L 220,10 220,100 20,100 Z"`) i upewnij się, że `setStrokeThickness` jest większe niż 0. |
| **Wrong color** | Użycie profilu ICC, który nie pasuje do zamierzonej przestrzeni kolorów | Użyj `doc.createColor(r, g, b)` dla RGB lub dokładnie sprawdź ścieżkę do pliku ICC. |
| **File not saved** | `dataDir` wskazuje na nieistniejący folder lub brak uprawnień do zapisu | Utwórz folder wcześniej lub wybierz lokalizację z prawami zapisu. |

## Najczęściej zadawane pytania

**Q:** *Czy mogę dodać wiele prostokątów w jednym dokumencie XPS?*  
A: Tak. Po prostu powtórz kroki tworzenia geometrii i stylizacji dla każdego potrzebnego prostokąta.

**Q:** *Jak mogę zmienić kolor wypełnienia prostokąta zamiast obrysu?*  
A: Użyj `path.setFill(...)` z pędzlem stałego koloru, podobnie jak przy użyciu `setStroke`.

**Q:** *Czy Aspose.Page nadaje się do skomplikowanych manipulacji dokumentami XPS?*  
A: Absolutnie. Biblioteka obsługuje zaawansowane funkcje, takie jak gradienty, transformacje i osadzone czcionki.

**Q:** *Gdzie mogę znaleźć dodatkowe przykłady i wsparcie społeczności?*  
A: Przeglądaj [Aspose.Page forum](https://forum.aspose.com/c/page/39) po więcej przykładów kodu i pomoc od innych użytkowników.

**Q:** *Czy mogę wypróbować Aspose.Page przed zakupem?*  
A: Tak, możesz skorzystać z [free trial](https://releases.aspose.com/) aby ocenić możliwości API.

**Ostatnia aktualizacja:** 2026-04-24  
**Testowano z:** Aspose.Page for Java 24.12  
**Autor:** Aspose

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}