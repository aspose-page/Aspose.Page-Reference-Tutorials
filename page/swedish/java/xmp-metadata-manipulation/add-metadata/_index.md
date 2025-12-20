---
date: 2025-12-20
description: Lär dig hur du lägger till XMP-metadata i EPS-filer med Aspose Page Java‑handledningen.
  Följ den här steg‑för‑steg‑guiden för att förbättra din dokumenthantering.
linktitle: Add Metadata in XMP using Java
second_title: Aspose.Page Java API
title: Aspose Page Java‑handledning – Lägg till XMP‑metadata i EPS‑filer
url: /sv/java/xmp-metadata-manipulation/add-metadata/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till metadata i XMP med Java

## Introduction
I denna **aspose page java tutorial**, du kommer att lära dig hur du förbättrar ditt dokuments metadata genom att lägga till XMP‑information med Java. Denna steg‑för‑steg‑guide visar dig hur du läser en befintlig EPS‑fil, extraherar dess XMP‑metadata och sparar ändringarna tillbaka till disk med Aspose.Page for Java‑biblioteket. I slutet av handledningen har du ett solid, återanvändbart mönster för att arbeta med XMP i alla EPS‑arbetsflöden.

## Quick Answers
- **What library is required?** Aspose.Page for Java  
- **Can I add XMP to any EPS file?** Ja – API‑et skapar ett nytt XMP‑block om ett sådant inte redan finns.  
- **Do I need a license for development?** En gratis provversion fungerar för utvärdering; en kommersiell licens krävs för produktion.  
- **Which Java version is supported?** Java 8 and later.  
- **How long does the implementation take?** Vanligtvis under 10 minutes for a basic metadata update.

## Aspose Page Java Tutorial Overview
Denna handledning demonstrerar de grundläggande stegen du behöver för att manipulera XMP‑metadata i EPS‑filer. Att förstå dessa steg hjälper dig att integrera metadatahantering i större dokument‑bearbetningspipelines, förbättra sökbarheten och följa branschstandarder för digital tillgångshantering.

## Prerequisites
Innan vi dyker in i handledningen, se till att du har följande förutsättningar:
- Grundläggande kunskaper i Java‑programmering.  
- Aspose.Page for Java library installed. You can download it [here](https://releases.aspose.com/page/java/).  
- En EPS‑fil som du vill modifiera.

## Import Packages
Först, importera de nödvändiga paketen till ditt Java‑program:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```

## Step 1: Get XMP Metadata
Steg 1: Hämta XMP‑metadata

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created using values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

Ersätt `"Your Document Directory"` med den faktiska sökvägen där dina dokument lagras.

## Step 2: Retrieve CreatorTool Value
Steg 2: Hämta CreatorTool‑värde

```java
// Get "CreatorTool" value
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Step 3: Retrieve CreateDate Value
Steg 3: Hämta CreateDate‑värde

```java
// Get "CreateDate" value
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Step 4: Retrieve Title Value
Steg 4: Hämta Title‑värde

```java
// Get "Title" value
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```

## Step 5: Retrieve Format Value
Steg 5: Hämta Format‑värde

```java
// Get "format" value
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Step 6: Retrieve Creator Value
Steg 6: Hämta Creator‑värde

```java
// Get "creator" value
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```

## Step 7: Retrieve MetadataDate Value
Steg 7: Hämta MetadataDate‑värde

```java
// Get "MetadataDate" value
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```

## Step 8: Save Document with New XMP Metadata
Steg 8: Spara dokumentet med ny XMP‑metadata

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

Till sist, glöm inte att stänga inmatnings‑EPS‑strömmen:

```java
// Close input EPS stream
psStream.close();
```

Nu har du framgångsrikt lagt till metadata till din EPS‑fil med Aspose.Page for Java!

## Conclusion
I denna **aspose page java tutorial**, utforskade vi hur man lägger till XMP‑metadata till en EPS‑fil med Aspose.Page for Java‑biblioteket. Detta kraftfulla API låter dig manipulera dokumentmetadata programatiskt, vilket hjälper dig att hålla tillgångar organiserade och sökbara.

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