---
date: 2026-03-05
description: Lär dig hur du lägger till dc:title‑arrayobjekt i XMP‑metadata för EPS‑filer
  med Aspose.Page för Java. Följ den här steg‑för‑steg‑guiden för snabba resultat.
linktitle: How to Add dc:title Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Hur man lägger till dc:title-arrayobjekt i XMP-metadata med Java
url: /sv/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till array‑element i XMP‑metadata med Java

## Introduktion
I den här handledningen kommer du att upptäcka **hur du lägger till dc:title** (och andra array‑element) till XMP‑metadata i en EPS‑fil med Aspose.Page för Java. Att uppdatera XMP‑metadata är användbart när du behöver bädda in sökbar information—såsom titlar, skapare eller nyckelord—direkt i dina grafikfiler. Vi går igenom varje steg, förklarar varför varje rad är viktig och visar hur du verifierar ändringarna.

## Snabba svar
- **Vad representerar “dc:title”?** Det är Dublin Core‑titel‑egenskapen lagrad som en XMP‑array.  
- **Varför modifiera XMP‑metadata?** Det möjliggör bättre tillgångshantering, sökbarhet och efterlevnad av standarder.  
- **Behöver jag ett befintligt XMP‑block?** Nej—Aspose.Page genererar ett från PS‑kommentarer om det saknas.  
- **Vilken biblioteks­version krävs?** Vilken som helst recent Aspose.Page för Java‑utgåva (testad med den senaste 2026‑byggnaden).  
- **Kan jag lägga till andra array‑egenskaper?** Ja—använd samma `addArrayItem`‑metod för egenskaper som `dc:creator`.

## Förutsättningar
Innan vi dyker ner, se till att du har:

- Aspose.Page för Java‑biblioteket installerat (lägg till JAR‑filen i ditt projekts classpath).  
- Grundläggande Java‑utvecklingserfarenhet (JDK 8+ rekommenderas).  
- En EPS‑fil som redan innehåller XMP‑metadata eller åtminstone PS‑metadata‑kommentarer (t.ex. `%%Title`, `%%Creator`).  

## Importera paket
För att börja, importera klasserna som krävs för att läsa, manipulera och spara EPS‑filer:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Steg 1: Ladda EPS‑dokumentet och hämta XMP‑metadata
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

Här öppnar vi EPS‑filen och ber Aspose.Page om dess XMP‑block. Om filen saknar XMP skapar biblioteket automatiskt ett med hjälp av befintliga PS‑kommentarer, vilket säkerställer att du alltid har en metadata‑behållare att arbeta med.

## Steg 2: Lägg till ett nytt **dc:title**‑array‑element  
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```

Denna rad visar **hur du lägger till dc:title**. Ersätt `"NewTitle"` med den faktiska titel du vill bädda in. Metoden lägger till värdet i den befintliga titel‑arrayen och bevarar eventuella tidigare titlar.

## Steg 3: Lägg till ett nytt **dc:creator**‑array‑element  
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```

På samma sätt kan du berika `dc:creator`‑egenskapen. Flera skapare kan lagras; varje anrop lägger till ett nytt element.

## Steg 4: Förbered utdata‑strömmen  
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

Vi skapar en ström för den modifierade EPS‑filen. Genom att använda ett annat filnamn (`xmp3_changed.eps`) lämnas den ursprungliga filen orörd.

## Steg 5: Spara dokumentet med uppdaterad XMP‑metadata  
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

`save`‑anropet skriver EPS‑data tillsammans med det uppdaterade XMP‑blocket. `finally`‑blocket garanterar att filhandtaget frigörs även om ett undantag inträffar.

## Varför detta är viktigt
Att bädda in korrekta `dc:title`‑ och `dc:creator`‑värden förbättrar:

- **Sökbarhet** i digitala tillgångshanteringssystem (DAM).  
- **Efterlevnad** av publiceringsstandarder som kräver metadata.  
- **Samarbete**, eftersom teammedlemmar snabbt kan identifiera filinnehåll utan att öppna EPS‑filen.

## Vanliga fallgropar och tips
- **Fallgrop:** Oavsiktligt skriva över befintliga array‑element.  
  **Tips:** Använd `xmp.getArrayItems("dc:title")` för att inspektera aktuella värden innan du lägger till nya.  
- **Fallgrop:** Glömma att stänga strömmar, vilket leder till låsta filer.  
  **Tips:** Omslut alltid I/O i try‑with‑resources eller ett `finally`‑block som visas.  
- **Tips:** Du kan kedja flera `addArrayItem`‑anrop för att lägga till flera titlar eller skapare i ett och samma pass.

## Vanliga frågor

### Kan jag använda Aspose.Page för Java med andra dokumentformat?
Ja, Aspose.Page stöder olika dokumentformat, inklusive EPS, PDF och XPS.

### Finns det en gratis provversion av Aspose.Page för Java?
Ja, du kan komma åt den gratis provversionen [här](https://releases.aspose.com/).

### Var kan jag hitta dokumentationen för Aspose.Page för Java?
Dokumentationen finns tillgänglig [här](https://reference.aspose.com/page/java/).

### Hur kan jag köpa Aspose.Page för Java?
Du kan köpa produkten [här](https://purchase.aspose.com/buy).

### Finns tillfälliga licenser för Aspose.Page för Java?
Ja, du kan skaffa en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

---

**Senast uppdaterad:** 2026-03-05  
**Testad med:** Aspose.Page för Java (latest 2026 release)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}