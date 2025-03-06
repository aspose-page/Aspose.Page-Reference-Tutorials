---
title: Uzyskaj metadane z XMP przy użyciu języka Java
linktitle: Uzyskaj metadane z XMP przy użyciu języka Java
second_title: Aspose.Page API Java
description: Odblokuj moc Aspose.Page dla Java, aby bez wysiłku wyodrębnić metadane XMP. Ulepsz analizę dokumentów dzięki naszemu przewodnikowi krok po kroku!
weight: 18
url: /pl/java/xmp-metadata-manipulation/get-metadata/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Uzyskaj metadane z XMP przy użyciu języka Java

## Wstęp
Witamy w naszym przewodniku krok po kroku dotyczącym wykorzystania Aspose.Page dla Java do wyodrębniania metadanych z plików XMP. XMP (Extensible Metadata Platform) zapewnia ustandaryzowany sposób przechowywania metadanych w plikach. Ten samouczek koncentruje się na pobieraniu niezbędnych informacji z XMP przy użyciu Java, oferując wgląd w szczegóły dokumentu.
## Warunki wstępne
Przed przystąpieniem do samouczka upewnij się, że spełniasz następujące wymagania wstępne:
- Zestaw Java Development Kit (JDK): Upewnij się, że na komputerze jest zainstalowana Java.
-  Aspose.Page dla Java: Pobierz i zainstaluj bibliotekę Aspose.Page, którą możesz znaleźć[Tutaj](https://releases.aspose.com/page/java/).
## Importuj pakiety
W swoim projekcie Java zaimportuj niezbędne pakiety:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## Krok 1: Zainicjuj wejściowy strumień pliku EPS
Rozpocznij od ustawienia ścieżki do katalogu dokumentów i zainicjowania wejściowego strumienia pliku EPS.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```
## Krok 2: Uzyskaj metadane XMP
Pobierz metadane XMP z pliku EPS. Jeżeli w pliku brakuje metadanych XMP, zostanie wygenerowany nowy z wartościami z komentarzy do metadanych PS.
```java
XmpMetadata xmp = document.getXmpMetadata();
```
## Krok 3: Wyodrębnij informacje z narzędzia CreatorTool
Sprawdź i wydrukuj wartość „CreatorTool” z metadanych XMP.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## Krok 4: Wyodrębnij informacje o CreateDate
Sprawdź i wydrukuj wartość „CreateDate” z metadanych XMP.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Krok 5: Pobierz szerokość miniatury
Jeśli istnieją miniatury, wyodrębnij i wydrukuj szerokość pierwszej miniatury.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```
## Krok 6: Wyodrębnij informacje o formacie
Sprawdź i wydrukuj wartość „format” z metadanych XMP.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## Krok 7: Uzyskaj identyfikator dokumentu
Sprawdź i wydrukuj wartość „DocumentID” z metadanych XMP.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```
## Wniosek
Gratulacje! Pomyślnie nauczyłeś się wyodrębniać metadane XMP za pomocą Aspose.Page dla Java. Ten przewodnik zawiera kompleksowy przegląd procesu, dzięki czemu możesz skutecznie wydobywać istotne informacje z dokumentów.
## Często Zadawane Pytania
### Czy mogę używać Aspose.Page dla Java z innymi językami programowania?
 Tak, Aspose.Page obsługuje wiele języków, w tym Java, .NET i inne. Sprawdź[dokumentacja](https://reference.aspose.com/page/java/) dla szczegółów.
### Czy dostępna jest bezpłatna wersja próbna Aspose.Page dla Java?
 Tak, możesz uzyskać dostęp do bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć wsparcie dla Aspose.Page dla Java?
 Odwiedzić[Forum Aspose.Page](https://forum.aspose.com/c/page/39) za wsparcie społeczności.
### Jak uzyskać tymczasową licencję na Aspose.Page dla Java?
 Możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
### Czy istnieją dodatkowe zasoby dla Aspose.Page dla Java?
 Poznaj całość[dokumentacja](https://reference.aspose.com/page/java/) i pobierz bibliotekę[Tutaj](https://releases.aspose.com/page/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
