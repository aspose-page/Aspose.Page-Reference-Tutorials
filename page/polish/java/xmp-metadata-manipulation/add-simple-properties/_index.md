---
date: 2026-05-20
description: Dowiedz się, jak dodać metadane XMP do plików EPS za pomocą Aspose.Page
  for Java. Przewodnik krok po kroku, jak programowo osadzić proste właściwości XMP.
keywords:
- add xmp metadata
- how to add xmp
- Aspose.Page Java XMP
linktitle: Dodaj proste właściwości XMP przy użyciu Javy
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add XMP metadata to EPS files with Aspose.Page for Java.
    Step‑by‑step guide to embed simple XMP properties programmatically.
  headline: Add XMP Metadata to EPS Files Using Java
  type: TechArticle
- questions:
  - answer: Aspose.Page primarily supports Java, but equivalent libraries are available
      for .NET, C++, and Python.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore the features of Aspose.Page by obtaining a free trial
      **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Page for Java?
  - answer: The documentation is available **[here](https://reference.aspose.com/page/java/)**.
    question: Where can I find detailed documentation for Aspose.Page for Java?
  - answer: A temporary license can be acquired **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: You can purchase the product **[here](https://purchase.aspose.com/buy)**.
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: Dodaj metadane XMP do plików EPS przy użyciu Javy
url: /pl/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj metadane XMP do plików EPS przy użyciu Javy

## Wprowadzenie
W nowoczesnych potokach graficznych możliwość **dodawania metadanych XMP** do plików EPS programowo daje pełną kontrolę nad tym, jak Twoje ilustracje są opisywane, wyszukiwane i archiwizowane. Dzięki Aspose.Page for Java możesz odczytywać, modyfikować i zapisywać pakiety XMP wewnątrz dokumentów EPS, nie opuszczając ekosystemu Javy. W tym samouczku przeprowadzimy Cię krok po kroku przez dokładne czynności dodawania prostych właściwości XMP do pliku EPS, abyś mógł szybko i niezawodnie wzbogacić swoje grafiki o niestandardowe metadane.

## Szybkie odpowiedzi
- **Co oznacza „dodawanie metadanych XMP do EPS”?** Osadzanie pakietu XMP (metadane oparte na XML) wewnątrz pliku EPS.  
- **Jakiej biblioteki wymaga się?** Aspose.Page for Java (do pobrania ze strony Aspose).  
- **Czy potrzebna jest licencja do testów?** Darmowa wersja próbna działa w trakcie rozwoju; licencja komercyjna jest wymagana w produkcji.  
- **Ile linii kodu?** Mniej niż 30 linii Javy plus kilka instrukcji importu.  
- **Czy mogę dodać inne typy danych?** Tak – obsługiwane są daty, liczby całkowite, liczby zmiennoprzecinkowe, ciągi znaków oraz nawet tablice.

## Jak dodać metadane XMP do plików EPS przy użyciu Javy?
Wczytaj plik EPS za pomocą `new PsDocument("input.eps")`, pobierz lub utwórz jego pakiet XMP, wstaw żądane właściwości, a następnie zapisz dokument z powrotem na dysk – wszystko w mniej niż dziesięciu liniach kodu Javy. Takie podejście pozwala osadzić przeszukiwalne, zgodne ze standardami metadane bez ręcznej edycji źródła EPS.

## Czym są metadane XMP w EPS?
Metadane XMP w EPS to pakiet XML znajdujący się wewnątrz pliku EPS i przechowujący informacje takie jak autor, data utworzenia i własne tagi. Osadzenie tego pakietu pozwala narzędziom downstream odczytywać i wykorzystywać dane bez potrzeby oddzielnych plików pomocniczych.

## Dlaczego warto dodawać metadane XMP do plików EPS?
Osadzanie metadanych XMP sprawia, że zasoby EPS są od razu przeszukiwalne, zapewnia zgodność poprzez przechowywanie informacji o licencji w pliku, umożliwia automatycznym potokom podejmowanie decyzji na podstawie osadzonych tagów oraz gwarantuje, że metadane podróżują wraz z grafiką na wszystkich platformach. Aspose.Page może przetwarzać pliki do 500 MB bez wczytywania całego dokumentu do pamięci, zapewniając wysoką wydajność przy dużych obciążeniach.

## Wymagania wstępne
- Podstawowa znajomość programowania w Javie.  
- Zainstalowana biblioteka Aspose.Page for Java. Możesz ją pobrać **[tutaj](https://releases.aspose.com/page/java/)**.  
- Przykładowy plik EPS zawierający metadane. Jeśli go nie masz, możesz użyć dostarczonego pliku **`xmp3.eps`**.

## Importowanie pakietów
Najpierw zaimportuj klasy, które będą potrzebne. Importy pozostają dokładnie takie same jak w oryginalnym przykładzie:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Krok 1: Wczytaj dokument EPS i pobierz metadane XMP
Klasa `PsDocument` reprezentuje plik EPS i udostępnia metody do dostępu do jego zawartości i metadanych.  
Obiekt `XmpMetadata` przechowuje pakiet XMP powiązany z dokumentem.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Krok 2: Dodaj właściwość Date
Klasa `Date` reprezentuje konkretny moment w czasie, z precyzją milisekund.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Krok 3: Dodaj właściwość Integer
Klasa `Integer` opakowuje prymitywną wartość `int` jako obiekt.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Krok 4: Dodaj właściwość Double
Klasa `Double` opakowuje prymitywną wartość `double` jako obiekt.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Krok 5: Dodaj właściwość String
Klasa `String` reprezentuje sekwencję znaków.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Krok 6: Zapisz zaktualizowany plik EPS
Metoda `save` zapisuje zmodyfikowany dokument z powrotem na dysk, zachowując strukturę EPS.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Krok 7: Oczyść zasoby
Zawsze zamykaj strumienie, aby uniknąć wycieków uchwytów plików i zapewnić opróżnienie wszystkich buforów.

```java
// Close input EPS stream
psStream.close();
```

## Typowe problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| **Brak metadanych XMP** | Plik EPS nie zawierał pakietu XMP, a biblioteka nie mogła wywnioskować komentarzy PS. | Upewnij się, że źródłowy plik EPS zawiera przynajmniej jeden komentarz PS (np. `%%Creator`). Biblioteka automatycznie wygeneruje minimalny pakiet XMP. |
| **Niezgodność strefy czasowej** | Daty wydają się przesunięte po otwarciu w innym programie. | Ustaw `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` przed utworzeniem obiektu `Date`, jak pokazano w Kroku 2. |
| **Wyjątek licencyjny** | W czasie wykonywania zgłaszany jest `LicenseException`. | Zastosuj ważną licencję Aspose.Page przed użyciem API lub uruchom w trybie próbnym w celu oceny. |

## Najczęściej zadawane pytania
**Q: Czy mogę używać Aspose.Page for Java z innymi językami programowania?**  
**A:** Aspose.Page głównie obsługuje Javę, ale dostępne są równoważne biblioteki dla .NET, C++ i Pythona.

**Q: Czy dostępna jest darmowa wersja próbna Aspose.Page for Java?**  
**A:** Tak, możesz zapoznać się z funkcjami Aspose.Page, uzyskując darmową wersję próbną **[tutaj](https://releases.aspose.com/)**.

**Q: Gdzie mogę znaleźć szczegółową dokumentację Aspose.Page for Java?**  
**A:** Dokumentacja jest dostępna **[tutaj](https://reference.aspose.com/page/java/)**.

**Q: Jak mogę uzyskać tymczasową licencję dla Aspose.Page for Java?**  
**A:** Tymczasową licencję można nabyć **[tutaj](https://purchase.aspose.com/temporary-license/)**.

**Q: Gdzie mogę kupić Aspose.Page for Java?**  
**A:** Produkt można zakupić **[tutaj](https://purchase.aspose.com/buy)**.

---

**Ostatnia aktualizacja:** 2026-05-20  
**Testowano z:** Aspose.Page for Java 24.12 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Jak odczytać metadane XMP przy użyciu Javy – przewodnik Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)
- [samouczek aspose.page xmp – Dodaj przestrzeń nazw w XMP przy użyciu Javy](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Dodaj elementy tablicy w metadanych XMP przy użyciu Javy](/page/java/xmp-metadata-manipulation/add-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}