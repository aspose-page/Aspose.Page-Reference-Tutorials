---
date: 2025-12-18
description: Lär dig hur du lägger till metadata genom att infoga array‑element i
  XMP‑metadata för EPS‑filer med Aspose.Page för Java. Följ vår steg‑för‑steg‑guide.
linktitle: Add Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Hur man lägger till metadata – Lägg till arrayelement i XMP (Java)
url: /sv/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till array‑element i XMP‑metadata med Java

## Hur man lägger till metadata
Välkommen till vår steg‑för‑steg‑guide om **hur man lägger till metadata** i EPS‑filer med Aspose.Page för Java. I den här handledningen går vi igenom hur du lägger till array‑element i XMP‑metadata – ett vanligt krav när du behöver berika dokumentinformation såsom titlar eller skapare. I slutet kommer du att förstå varför XMP är värdefullt, hur du manipulerar det programatiskt och hur du sparar den uppdaterade EPS‑filen.

## Snabba svar
- **Vilket bibliotek används?** Aspose.Page for Java  
- **Vilket filformat är målet?** EPS (Encapsulated PostScript)  
- **Kan jag lägga till flera titlar?** Ja, använd `xmp.addArrayItem("dc:title", ...)` upprepade gånger  
- **Behöver jag en licens för produktion?** Ja, en giltig Aspose.Page‑licens krävs  
- **Är koden kompatibel med Java 8+?** Absolut, den fungerar med alla moderna Java‑versioner  

## Förutsättningar
Innan vi dyker in i handledningen, se till att du har följande förutsättningar:
- Aspose.Page for Java‑biblioteket installerat.  
- Grundläggande förståelse för Java‑programmering.  
- En giltig EPS‑fil med befintlig XMP‑metadata eller PS‑metadata‑kommentarer.  

## Importera paket
För att komma igång måste du importera de nödvändiga paketen för att arbeta med Aspose.Page. Inkludera följande rader i början av din Java‑fil:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Steg 1: Hämta XMP‑metadata
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
I det här steget hämtar vi den befintliga XMP‑metadata från EPS‑filen. Om EPS‑filen ännu inte innehåller XMP‑metadata genererar Aspose.Page en ny och fyller den med värden från PS‑metadata‑kommentarer.

## Steg 2: Lägg till array‑elementet "dc:title"
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Nu lägger vi till ett nytt array‑element i egenskapen **dc:title** i XMP‑metadata. Ersätt `"NewTitle"` med den önskade titeln.

## Steg 3: Lägg till array‑elementet "dc:creator"
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
På samma sätt lägger vi till ett nytt array‑element i egenskapen **dc:creator** i XMP‑metadata. Ersätt `"NewCreator"` med den önskade skaparinformationen.

## Steg 4: Initiera utdata‑EPS‑filström
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Förbered utdata‑EPS‑filströmmen där det modifierade dokumentet med uppdaterad XMP‑metadata kommer att sparas.

## Steg 5: Spara dokumentet med ändrad XMP‑metadata
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Spara dokumentet med den uppdaterade XMP‑metadata till utdata‑EPS‑filen.

## Slutsats
Grattis! Du har nu framgångsrikt lärt dig **hur man lägger till metadata** genom att infoga array‑element i XMP‑metadata med Aspose.Page för Java. Detta kraftfulla bibliotek förenklar processen att manipulera EPS‑filer och erbjuder omfattande funktionalitet för dokumentbehandling.

## Vanliga frågor

### Kan jag använda Aspose.Page för Java med andra dokumentformat?
Ja, Aspose.Page stödjer olika dokumentformat, inklusive EPS, PDF och XPS.

### Finns det en gratis provversion av Aspose.Page för Java?
Ja, du kan komma åt den gratis provversionen [här](https://releases.aspose.com/).

### Var kan jag hitta dokumentationen för Aspose.Page för Java?
Dokumentationen finns tillgänglig [här](https://reference.aspose.com/page/java/).

### Hur kan jag köpa Aspose.Page för Java?
Du kan köpa produkten [här](https://purchase.aspose.com/buy).

### Finns tillfälliga licenser för Aspose.Page för Java?
Ja, du kan skaffa en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

## Ytterligare vanliga frågor

**Q: Kan jag lägga till mer än ett array‑element till samma egenskap?**  
A: Absolut. Anropa `xmp.addArrayItem` flera gånger för samma egenskap för att bygga en lista med värden.

**Q: Fungerar detta tillvägagångssätt med befintliga XMP‑scheman förutom Dublin Core?**  
A: Ja, du kan lägga till array‑element till vilken XMP‑egenskap som helst så länge namnrymden refereras korrekt.

**Q: Hur kan jag verifiera att metadata har lagts till korrekt?**  
A: Öppna den resulterande EPS‑filen i en visare som stödjer XMP (t.ex. Adobe Bridge) eller extrahera metadata programatiskt med `XmpMetadata`‑metoder.

---

**Senast uppdaterad:** 2025-12-18  
**Testat med:** Aspose.Page for Java 24.11  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}