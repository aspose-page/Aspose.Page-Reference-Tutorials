---
date: 2025-12-20
description: Dowiedz się, jak dodać metadane XMP do plików EPS za pomocą samouczka
  Aspose Page Java. Postępuj zgodnie z tym przewodnikiem krok po kroku, aby usprawnić
  zarządzanie dokumentami.
linktitle: Add Metadata in XMP using Java
second_title: Aspose.Page Java API
title: Samouczek Aspose Page Java – Dodaj metadane XMP do plików EPS
url: /pl/java/xmp-metadata-manipulation/add-metadata/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodawanie metadanych XMP przy użyciu Javy

## Introduction
W tym **aspose page java tutorial**, nauczysz się, jak ulepszyć metadane swojego dokumentu, dodając informacje XMP przy użyciu Javy. Ten przewodnik krok po kroku prowadzi Cię przez odczyt istniejącego pliku EPS, wyodrębnienie jego metadanych XMP i zapisanie zmian na dysku przy użyciu biblioteki Aspose.Page for Java. Po zakończeniu tutorialu będziesz mieć solidny, wielokrotnego użytku wzorzec pracy z XMP w dowolnym przepływie pracy EPS.

## Quick Answers
- **What library is required?** Aspose.Page for Java  
- **Can I add XMP to any EPS file?** Tak – API tworzy nowy blok XMP, jeśli nie istnieje.  
- **Do I need a license for development?** Darmowa wersja próbna działa do oceny; licencja komercyjna jest wymagana w produkcji.  
- **Which Java version is supported?** Java 8 i nowsze.  
- **How long does the implementation take?** Zazwyczaj poniżej 10 minut dla podstawowej aktualizacji metadanych.

## Aspose Page Java Tutorial Overview
Ten tutorial demonstruje podstawowe kroki potrzebne do manipulacji metadanymi XMP w plikach EPS. Zrozumienie tych kroków pomoże Ci zintegrować obsługę metadanych z większymi pipeline'ami przetwarzania dokumentów, poprawić możliwość wyszukiwania oraz spełnić standardy branżowe w zakresie zarządzania zasobami cyfrowymi.

## Prerequisites
Zanim przejdziesz do tutorialu, upewnij się, że spełniasz następujące wymagania:
- Podstawowa znajomość programowania w Javie.  
- Zainstalowana biblioteka Aspose.Page for Java. Możesz ją pobrać [here](https://releases.aspose.com/page/java/).  
- Plik EPS, który chcesz zmodyfikować.

## Import Packages
Najpierw zaimportuj niezbędne pakiety do swojego programu w Javie:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```

## Step 1: Get XMP Metadata
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created using values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

Zastąp `"Your Document Directory"` rzeczywistą ścieżką, w której przechowywane są Twoje dokumenty.

## Step 2: Retrieve CreatorTool Value
```java
// Get "CreatorTool" value
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Step 3: Retrieve CreateDate Value
```java
// Get "CreateDate" value
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Step 4: Retrieve Title Value
```java
// Get "Title" value
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```

## Step 5: Retrieve Format Value
```java
// Get "format" value
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Step 6: Retrieve Creator Value
```java
// Get "creator" value
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```

## Step 7: Retrieve MetadataDate Value
```java
// Get "MetadataDate" value
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```

## Step 8: Save Document with New XMP Metadata
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Save document with new XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

Na koniec, nie zapomnij zamknąć strumienia wejściowego EPS:

```java
// Close input EPS stream
psStream.close();
```

Teraz pomyślnie dodałeś metadane do pliku EPS przy użyciu Aspose.Page for Java!

## Conclusion
W tym **aspose page java tutorial**, omówiliśmy, jak dodać metadane XMP do pliku EPS przy użyciu biblioteki Aspose.Page for Java. To potężne API pozwala programowo manipulować metadanymi dokumentu, pomagając utrzymać zasoby w porządku i ułatwiając ich wyszukiwanie.

## Frequently Asked Questions

**Q: Is Aspose.Page for Java free to use?**  
A: Aspose.Page for Java is a commercial product. You can explore its features through a free trial [here](https://releases.aspose.com/).

**Q: Where can I find the documentation for Aspose.Page for Java?**  
A: The documentation is available [here](https://reference.aspose.com/page/java/).

**Q: How can I obtain a temporary license for Aspose.Page for Java?**  
A: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).

**Q: What file formats does Aspose.Page for Java support?**  
A: Aspose.Page for Java supports various formats, including EPS, PDF, and XPS.

**Q: Can I purchase Aspose.Page for Java?**  
A: Yes, you can purchase Aspose.Page for Java [here](https://purchase.aspose.com/buy).

**Q: How do I handle large EPS files when adding metadata?**  
A: Process the file in a streaming fashion (as shown) to keep memory usage low, and close streams promptly.

**Q: Can I modify existing XMP fields instead of just reading them?**  
A: Absolutely – you can use `xmp.put(key, value)` to update or add new entries before saving.

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}