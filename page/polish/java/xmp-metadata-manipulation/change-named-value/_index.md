---
date: 2026-05-15
description: Dowiedz się, jak edytować metadane XMP oraz jak zmienić wartości XMP
  w plikach EPS przy użyciu Aspose.Page for Java – jasny przewodnik krok po kroku.
keywords:
- how to edit xmp
- how to change xmp
- Aspose.Page XMP Java
- edit EPS metadata
- XMP manipulation Java
linktitle: Zmiana nazwanej wartości w XMP przy użyciu Java
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  headline: how to edit xmp – Change Named Value in XMP using Java
  type: TechArticle
- description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  name: how to edit xmp – Change Named Value in XMP using Java
  steps:
  - name: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
    text: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
  - name: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
    text: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
  - name: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
    text: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
  type: HowTo
- questions:
  - answer: Aspose.Page primarily supports Java, but Aspose offers equivalent libraries
      for .NET, C++, and Python that expose similar XMP manipulation capabilities.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore a free trial of Aspose.Page for Java [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support and discussions.
    question: Where can I find additional support and discussions about Aspose.Page
      for Java?
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: To buy Aspose.Page for Java, visit the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: jak edytować XMP – Zmiana nazwanej wartości w XMP przy użyciu Java
url: /pl/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak edytować XMP – Zmiana nazwanej wartości w XMP przy użyciu Javy

W nowoczesnych przepływach dokumentów **Aspose.Page for Java** ułatwia odczyt, edycję i zapis metadanych XMP wewnątrz plików EPS. **Ten samouczek pokazuje, jak edytować metadane XMP** w dokumentach EPS przy użyciu API Aspose.Page, aby utrzymać informacje o dokumencie dokładne, przeszukiwalne i zgodne ze standardami branżowymi. Niezależnie od tego, czy aktualizujesz wymiary strony, informacje o autorze, czy własne znaczniki, poniższe kroki przeprowadzą Cię przez proces w Javie.

## Szybkie odpowiedzi
- **Co obejmuje ten samouczek?** Zmiana nazwanej wartości XMP w pliku EPS przy użyciu Aspose.Page for Java.  
- **Jakiej wersji biblioteki potrzebuję?** Dowolna nowsza wersja Aspose.Page for Java (API jest stabilne od kilku lat).  
- **Czy potrzebna jest licencja?** Do produkcji wymagana jest tymczasowa lub pełna licencja; darmowa wersja próbna wystarcza do testów.  
- **Jak długo trwa implementacja?** Około 10‑15 minut dla programisty zaznajomionego z Java I/O.  
- **Czy mogę używać tego z innymi formatami plików?** API XMP jest również dostępne dla PDF, SVG i innych formatów obsługiwanych przez Aspose.Page.

## Co to są metadane XMP?
XMP (Extensible Metadata Platform) to ustandaryzowany format oparty na XML, umożliwiający osadzanie bogatych metadanych — takich jak twórca, tytuł i własne właściwości — bezpośrednio w plikach. W dokumentach EPS XMP współistnieje z tradycyjnymi komentarzami PostScript, umożliwiając aplikacjom odczyt i modyfikację metadanych bez zmiany treści wizualnej.

## Dlaczego używać Aspose.Page for Java do edycji XMP?
Aspose.Page zapewnia **pełną kontrolę nad ponad 150 właściwościami schematu XMP** i działa konsekwentnie w formatach EPS, PDF i SVG. Przetwarza pliki do **500 MB** bez ładowania całego dokumentu do pamięci oraz zawiera wbudowaną walidację, która gwarantuje, że wynikowy EPS pozostaje zgodny ze standardami. Nie są wymagane zewnętrzne parsery XML ani biblioteki natywne.

## Wprowadzenie
Aspose.Page for Java to solidna biblioteka ułatwiająca manipulację i przetwarzanie plików EPS. Jeśli chodzi o obsługę metadanych XMP w tych plikach, Aspose.Page daje programistom kompleksowy zestaw funkcji. W tym samouczku skupimy się na zmianie nazwanej wartości w XMP, oferując jasny i zwięzły przewodnik dla programistów chcących rozszerzyć możliwości przetwarzania dokumentów.

## Wymagania wstępne
Przed przystąpieniem do samouczka upewnij się, że spełniasz następujące wymagania:
1. **Środowisko programistyczne Java** – JDK (8 lub wyższy) oraz IDE lub narzędzie budujące (Maven/Gradle).  
2. **Biblioteka Aspose.Page for Java** – Pobierz i zintegrować bibliotekę Aspose.Page for Java w swoim projekcie. Bibliotekę i szczegółową dokumentację znajdziesz [tutaj](https://reference.aspose.com/page/java/).  
3. **Przykładowy plik EPS** – Przygotuj przykładowy plik EPS do eksperymentów. Jeśli go nie masz, użyj dostarczonego pliku przykładowego o nazwie **"xmp4.eps."**

## Importowanie pakietów
Instrukcje `import` wprowadzają niezbędne klasy Aspose.Page do zakresu.

Klasa `PsDocument` jest podstawowym obiektem Aspose.Page reprezentującym dokument EPS w pamięci.  
Klasa `XmpMetadata` zapewnia dostęp do pakietu XMP osadzonego w pliku EPS.  

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Jak edytować metadane XMP?
Wczytaj plik EPS, pobierz jego pakiet XMP, zmodyfikuj żądaną właściwość i zapisz dokument — wszystko w kilku prostych linijkach. To podejście działa dla dowolnej nazwanej wartości XMP, niezależnie od tego, czy jest to standardowe pole Dublin Core, czy własna przestrzeń nazw, którą zdefiniowałeś.

## Krok 1: Zainicjalizuj strumień wejściowy pliku EPS
`FileInputStream` otwiera strumień tylko do odczytu do źródłowego pliku EPS, pozwalając Aspose.Page na pobranie dokumentu bez blokowania systemu plików.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## Krok 2: Zainicjalizuj PsDocument
`PsDocument` jest głównym obiektem, który enkapsuluje zawartość EPS i zapewnia dostęp do jego metadanych, stron i zasobów.

```java
PsDocument document = new PsDocument(psStream);
```

## Krok 3: Pobierz metadane XMP
`XmpMetadata` reprezentuje pakiet XMP wewnątrz pliku EPS i oferuje metody do odczytu, modyfikacji lub usuwania poszczególnych właściwości.

```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Krok 4: Ustaw nową wartość w XMP
`setProperty` ustawia wartość określonej właściwości XMP w pakiecie metadanych.

```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## Krok 5: Zainicjalizuj strumień wyjściowy pliku EPS
`FileOutputStream` tworzy strumień zapisu do zapisania zmodyfikowanego pliku EPS.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## Krok 6: Zapisz dokument ze zmienionymi metadanymi XMP
`save` zapisuje w‑pamięci obiekt PsDocument, w tym zaktualizowane XMP, do strumienia wyjściowego.

```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Krok 7: Zamknij strumień wejściowy EPS
`close` zwalnia uchwyt pliku i zwalnia zasoby powiązane ze strumieniem wejściowym.

```java
// Close input EPS stream
psStream.close();
```

## Typowe problemy i rozwiązania
- **FileNotFoundException** – Sprawdź, czy `dataDir` wskazuje poprawny folder i czy plik `xmp4.eps` istnieje.  
- **LicenseException** – Jeśli pojawiają się błędy licencyjne, upewnij się, że przed utworzeniem `PsDocument` załadowano prawidłowy plik licencji Aspose.Page.  
- **Metadane nie zostały zaktualizowane** – Po zapisaniu otwórz wynikowy EPS w przeglądarce metadanych (np. Adobe Bridge), aby potwierdzić, że nowa wartość się pojawiła.

## Najczęściej zadawane pytania
**P: Czy mogę używać Aspose.Page for Java z innymi językami programowania?**  
O: Aspose.Page głównie obsługuje Javę, ale Aspose oferuje równoważne biblioteki dla .NET, C++ i Pythona, które udostępniają podobne możliwości manipulacji XMP.

**P: Czy dostępna jest darmowa wersja próbna Aspose.Page for Java?**  
O: Tak, darmową wersję próbną Aspose.Page for Java znajdziesz [tutaj](https://releases.aspose.com/).

**P: Gdzie mogę znaleźć dodatkowe wsparcie i dyskusje na temat Aspose.Page for Java?**  
O: Odwiedź [forum Aspose.Page](https://forum.aspose.com/c/page/39) w celu uzyskania wsparcia społeczności i dyskusji.

**P: Jak uzyskać tymczasową licencję dla Aspose.Page for Java?**  
O: Tymczasową licencję możesz nabyć [tutaj](https://purchase.aspose.com/temporary-license/).

**P: Gdzie mogę kupić Aspose.Page for Java?**  
O: Aby zakupić Aspose.Page for Java, przejdź na [stronę zakupu](https://purchase.aspose.com/buy).

---

**Ostatnia aktualizacja:** 2026-05-15  
**Testowane z:** Aspose.Page for Java (najnowsze wydanie)  
**Autor:** Aspose

## Powiązane samouczki

- [Jak odczytać metadane XMP przy użyciu Javy – Przewodnik Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)
- [Samouczek Aspose Page Java – Dodawanie metadanych XMP do plików EPS](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page modify xmp – Zmiana wartości w XMP przy użyciu Javy](/page/java/xmp-metadata-manipulation/change-values/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}