---
title: Zmień wartości w XMP przy użyciu Java
linktitle: Zmień wartości w XMP przy użyciu Java
second_title: Aspose.Page API Java
description: Ulepsz dokumenty EPS za pomocą Aspose.Page dla Java. Bez wysiłku modyfikuj metadane XMP w celu uzyskania dostosowanych i profesjonalnych treści. #Rozwój Java
weight: 17
url: /pl/java/xmp-metadata-manipulation/change-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zmień wartości w XMP przy użyciu Java

## Wstęp
W dziedzinie przetwarzania i manipulacji dokumentami Aspose.Page for Java wyróżnia się jako potężne narzędzie. W tym samouczku opisano proces zmiany wartości XMP (Extensible Metadata Platform) w dokumentach EPS (Encapsulated PostScript) przy użyciu języka Java z biblioteką Aspose.Page. Postępując zgodnie z dostarczonym przewodnikiem, dowiesz się, jak bez wysiłku modyfikować metadane, dzięki czemu Twoje dokumenty będą dostosowane do Twoich konkretnych wymagań.
## Warunki wstępne
Zanim przejdziemy do tego samouczka, upewnij się, że spełnione są następujące wymagania wstępne:
1. Środowisko programistyczne Java: Upewnij się, że masz działające środowisko programistyczne Java na swoim komputerze.
2.  Biblioteka Aspose.Page dla Java: Pobierz i zainstaluj bibliotekę Aspose.Page dla Java. Możesz znaleźć niezbędny pakiet[Tutaj](https://releases.aspose.com/page/java/).
## Importuj pakiety
Rozpocznij od zaimportowania wymaganych pakietów do projektu Java. Pakiety te są niezbędne do interakcji z dokumentami EPS i manipulowania nimi.
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
## Krok 1: Uzyskaj metadane XMP
Pobierz metadane XMP z dokumentu EPS. Jeśli plik EPS nie zawiera metadanych XMP, zostanie utworzony nowy z wartościami z komentarzy do metadanych PS, takimi jak %%Creator, %%CreateDate i %%Title.
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Zainicjuj wejściowy strumień pliku EPS
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Pobierz metadane XMP. Jeśli plik EPS nie zawiera metadanych XMP, tworzony jest nowy z wartościami z komentarzy metadanych PS
XmpMetadata xmp = document.getXmpMetadata();
```
## Krok 2: Zmień wartość „ModifyDate”.
Zmodyfikuj wartość „ModifyDate” w metadanych XMP, aby odzwierciedlała żądaną datę.
```java
// Zmień wartość „ModifyDate”.
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```
## Krok 3: Zmień wartość „Twórcy”.
Zaktualizuj wartość „Twórca” w metadanych XMP, aby określić twórcę dokumentu.
```java
// Zmień wartość „twórcy”.
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```
## Krok 4: Zmień wartość „Tytułu”.
Zmodyfikuj wartość „Tytuł” w metadanych XMP, aby ustawić odpowiedni tytuł dokumentu.
```java
//Zmień wartość „tytułu”.
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```
## Krok 5: Zapisz dokument ze zmienionymi metadanymi XMP
Zapisz dokument ze zaktualizowanymi metadanymi XMP w nowym pliku EPS.
```java
// Zainicjuj wyjściowy strumień pliku EPS
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
//Zapisz dokument ze zmienionymi metadanymi XMP
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Wniosek
Gratulacje! Pomyślnie przeszedłeś proces zmiany wartości XMP w dokumentach EPS przy użyciu Aspose.Page dla Java. Ten samouczek wyposażył Cię w wiedzę niezbędną do modyfikowania metadanych, dzięki czemu Twoje dokumenty będą bezproblemowo dostosowywane do Twoich konkretnych wymagań.
## Często zadawane pytania
### P: Jak mogę uwzględnić kwestie strefy czasowej podczas modyfikowania wartości XMP?
 Spożytkować`TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` aby zapewnić spójność ustawień stref czasowych.
### P: Czy mogę zmienić wiele wartości XMP w jednej operacji?
 Tak, za pomocą`put` dla każdej żądanej wartości, można jednocześnie modyfikować wiele wartości XMP.
### P: Gdzie mogę znaleźć dodatkową dokumentację dla Aspose.Page dla Java?
 Zapoznaj się z obszerną dokumentacją[Tutaj](https://reference.aspose.com/page/java/).
### P: Czy dostępna jest bezpłatna wersja próbna Aspose.Page dla Java?
 Tak, możesz uzyskać dostęp do bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
### P: Jak mogę uzyskać tymczasową licencję na Aspose.Page dla Java?
 Uzyskaj tymczasową licencję[Tutaj](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
