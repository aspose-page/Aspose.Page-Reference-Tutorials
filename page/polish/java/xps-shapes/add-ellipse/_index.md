---
date: 2026-04-24
description: Dowiedz się, jak stworzyć dokument XPS w Javie z elipsą o gradientzie
  promieniowym. Ten przewodnik krok po kroku pokazuje, jak ustawić grubość obrysu
  i zdefiniować geometrię ścieżki przy użyciu Aspose.Page.
keywords:
- create xps document java
- set stroke thickness
- define path geometry
linktitle: Dodaj elipsę w Java XPS
second_title: Aspose.Page Java API
title: Tworzenie dokumentu XPS w Javie – Dodaj elipsę z gradientem promieniowym
url: /pl/java/xps-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj elipsę z gradientem radialnym przy użyciu Aspose.Page

## Wprowadzenie
W tym samouczku dowiesz się, jak **create XPS document Java** z piękną elipsą obrysowaną gradientem radialnym przy użyciu Aspose.Page dla Javy. Aspose.Page to solidna biblioteka, która abstrahuje szczegóły niskiego poziomu XPS, pozwalając skupić się na projektowaniu, a nie na zawiłościach formatu pliku. Po zakończeniu tego przewodnika będziesz mieć gotowy plik XPS, który możesz osadzić w raportach, fakturach lub w dowolnym procesie generowania dokumentów.

## Szybkie odpowiedzi
- **Co generuje ten kod?** Jednostronicowy plik XPS zawierający elipsę obrysowaną wielokolorowym gradientem radialnym.  
- **Które główne API jest używane?** `Aspose.Page` for Java (`XpsDocument`, `XpsCanvas`, `XpsPath`, etc.).  
- **Czy potrzebuję licencji, aby uruchomić przykład?** Tymczasowa licencja działa w trybie ewaluacji; pełna licencja jest wymagana w produkcji.  
- **Jakie kluczowe właściwości ustawiamy?** Pędzel obrysu (gradient radialny), metoda rozprzestrzeniania, przystanki gradientu i grubość obrysu.  
- **Czy mogę zmienić rozmiar elipsy?** Tak – zmodyfikuj ciąg geometrii ścieżki lub współrzędne pędzla gradientu.

## Co to jest „create XPS document Java”?
Tworzenie dokumentu XPS w Javie oznacza programowe generowanie pliku XML Paper Specification (XPS) — formatu dokumentu o stałym układzie, podobnego do PDF — bezpośrednio z kodu Java. Aspose.Page udostępnia wysokopoziomowy model obiektowy (`XpsDocument`, `XpsCanvas`, itp.), który abstrahuje znacznik XML, czyniąc proces tak prostym, jak praca ze standardowymi obiektami Java.

## Dlaczego używać elipsy z gradientem radialnym?
Gradient radialny nadaje trójwymiarowy efekt, idealny do podkreśleń wizualnych, logotypów lub elementów dekoracyjnych w raportach. W porównaniu z obrysem jednolitego koloru, gradient dodaje głębi bez znaczącego zwiększania rozmiaru pliku, a format XPS zachowuje jakość wektorową przy dowolnym skalowaniu.

## Wymagania wstępne
- Zainstalowany Java Development Kit (JDK) na Twoim komputerze.
- Pobraną bibliotekę Aspose.Page for Java. Możesz ją pobrać [tutaj](https://releases.aspose.com/page/java/).
- Edytor kodu według własnego wyboru (Eclipse, IntelliJ, itp.) do pisania i uruchamiania kodu Java.

## Importowanie pakietów
Upewnij się, że w swoim projekcie Java zaimportowano niezbędne pakiety, aby używać Aspose.Page. Dodaj następujące instrukcje importu na początku pliku Java:

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```

## Krok 1: Konfiguracja katalogu dokumentu
Zdefiniuj ścieżkę do katalogu dokumentu, w którym zostanie zapisany plik XPS:

```java
String dataDir = "Your Document Directory";
```

## Krok 2: Utworzenie dokumentu XPS
Zainicjalizuj nowy dokument XPS przy użyciu poniższego kodu:

```java
XpsDocument doc = new XpsDocument();
```

## Krok 3: Definicja przystanków gradientu radialnego
Utwórz listę przystanków gradientu dla elipsy obrysowanej gradientem radialnym:

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```

## Krok 4: Utworzenie geometrii ścieżki
Zdefiniuj elipsę obrysowaną gradientem radialnym przy użyciu geometrii ścieżki:

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```

## Krok 5: Dodanie płótna i ścieżki
Dodaj nowe płótno do dokumentu i dołącz ścieżkę z zdefiniowaną geometrią:

```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```

## Krok 6: Ustawienie obrysu i gradientu
Skonfiguruj obrys ścieżki przy użyciu pędzla gradientu radialnego:

```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```

## Krok 7: Ustawienie grubości obrysu
Określ **set stroke thickness** ścieżki:

```java
path.setStrokeThickness(12f);
```

## Krok 8: Zapisanie dokumentu
Zapisz powstały dokument XPS:

```java
doc.save(dataDir + "AddEllipse_out.xps");
```

Gratulacje! Pomyślnie dodałeś elipsę obrysowaną gradientem radialnym podczas **creating an XPS document Java** z Aspose.Page.

## Częste problemy i rozwiązania
| Problem | Dlaczego się pojawia | Rozwiązanie |
|-------|----------------|-----|
| **Elipsa wygląda płasko** | Użycie `XpsSpreadMethod.Pad` zamiast `Reflect` | Zmień metodę rozprzestrzeniania na `XpsSpreadMethod.Reflect` jak pokazano w Kroku 6. |
| **Brak pliku wyjściowego** | `dataDir` wskazuje na nieistniejący folder | Upewnij się, że katalog istnieje lub użyj ścieżki bezwzględnej. |
| **Kolory gradientu wyglądają niepoprawnie** | Nieprawidłowa kolejność przystanków gradientu | Sprawdź, czy wartości `offset` (0 → 1) rosną monotonicznie. |
| **Błędy kompilacji** | Brak plików JAR Aspose.Page w ścieżce klas | Dodaj `aspose-page-xx.jar` do zależności projektu. |

## Najczęściej zadawane pytania

**Q:** Czy mogę używać Aspose.Page for Java z innymi bibliotekami Java?  
**A:** Tak, Aspose.Page for Java może być bezproblemowo integrowany z innymi bibliotekami Java.

**Q:** Czy Aspose.Page jest odpowiedni do przetwarzania dokumentów na dużą skalę?  
**A:** Zdecydowanie! Aspose.Page jest zaprojektowany do efektywnego przetwarzania dokumentów na dużą skalę.

**Q:** Gdzie mogę znaleźć więcej samouczków i przykładów dla Aspose.Page for Java?  
**A:** Odwiedź [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) aby uzyskać kompleksowe samouczki i przykłady.

**Q:** Jak mogę uzyskać tymczasową licencję dla Aspose.Page for Java?  
**A:** Możesz uzyskać tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/).

**Q:** Czy istnieją fora społecznościowe dotyczące dyskusji o Aspose.Page?  
**A:** Tak, dołącz do [Aspose.Page community forum](https://forum.aspose.com/c/page/39), aby wymieniać się doświadczeniami z innymi programistami i uzyskać pomoc.

---

**Ostatnia aktualizacja:** 2026-04-24  
**Testowano z:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}