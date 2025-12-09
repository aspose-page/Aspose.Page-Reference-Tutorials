---
date: 2025-11-29
description: Lär dig hur du sparar XPS som PDF i Java med Aspose.Page Java. Följ vår
  steg‑för‑steg‑guide för effektiv XPS‑till‑PDF‑konvertering och PDF‑komprimeringsinställningar.
linktitle: Convert XPS to PDF in Java using Aspose.Page Java
second_title: Aspose.Page Java API
title: Konvertera XPS till PDF i Java med Aspose.Page Java
url: /sv/java/file-merging/xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konvertera XPS till PDF i Java med Aspose.Page Java

## Introduktion
I den här handledningen lär du dig **hur du konverterar XPS till PDF i Java med Aspose.Page Java**, ett robust bibliotek designat för Java-dokumentkonvertering. Oavsett om du behöver batch‑processa fakturor, generera utskrivbara rapporter eller helt enkelt migrera äldre XPS‑filer, gör Aspose.Page Java jobbet snabbt, pålitligt och fullt konfigurerbart.

## Snabba svar
- **Vilket bibliotek hanterar XPS till PDF-konvertering?** Aspose.Page Java  
- **Hur lång tid tar en grundläggande konvertering?** Vanligtvis under en sekund för en enkelsidig XPS‑fil.  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för utvärdering; en licens krävs för produktion.  
- **Kan jag styra PDF-komprimering?** Ja – använd `PdfSaveOptions` för att ange bild- och textkomprimering.  
- **Vilken Java‑version krävs?** Java 8 eller senare (JDK 11+ rekommenderas).

## Vad är Aspose.Page Java?
Aspose.Page Java är ett **högeffektivt API** som gör det möjligt för utvecklare att programatiskt skapa, redigera och konvertera XPS‑dokument. Det stödjer rendering av XPS till PDF, PNG, JPEG och andra format samtidigt som det ger fin‑granulär kontroll över utdata‑inställningar såsom **set PDF compression**.

## Varför använda Aspose.Page Java för XPS‑till‑PDF‑konvertering?
- **Zero‑dependency rendering** – inga inhemska bibliotek eller externa verktyg.  
- **Noggrann layoutbevarande** – PDF‑utdata speglar den ursprungliga XPS‑utseendet.  
- **Full kontroll över PDF‑utdata** – du kan justera bildkvalitet, välja komprimeringsalgoritmer och välja specifika sidor att rendera.  
- **Cross‑platform** – fungerar på Windows, Linux och macOS med vilken standard‑JDK som helst.

## Förutsättningar
Innan du börjar, se till att du har:

1. **Java Development Kit (JDK) 8+** – den senaste JDK:n rekommenderas för prestanda och säkerhet.  
2. **Aspose.Page for Java library** – ladda ner JAR‑filen från den officiella [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).  
3. En **IDE** (IntelliJ IDEA, Eclipse, VS Code) eller en enkel textredigerare plus kommandorads‑byggverktyg (Maven/Gradle).  

## Importera paket
Lägg till de nödvändiga importerna i din Java‑klass så att du kan arbeta med XPS‑dokument och PDF‑utdata.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.rendering.pdf.PdfDevice;
import com.aspose.xps.rendering.pdf.PdfSaveOptions;
import com.aspose.xps.rendering.pdf.PdfImageCompression;
import com.aspose.xps.rendering.pdf.PdfTextCompression;
import java.io.FileOutputStream;
```

## Steg‑för‑steg‑guide

### Steg 1: Ange dokumentkatalogens sökväg
Definiera mappen som innehåller din käll‑XPS‑fil och där PDF‑filen ska sparas.

```java
String dataDir = "C:/MyDocuments/XpsFiles/";   // <-- replace with your actual path
```

### Steg 2: Initiera PDF‑utdata‑ström
Skapa ett `FileOutputStream` som pekar på destinations‑PDF‑filen.

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

> **Pro tip:** Använd `try‑with‑resources` för att automatiskt stänga strömmen och undvika resurssläpp.

### Steg 3: Ladda XPS‑dokument
Instansiera ett `XpsDocument`‑objekt genom att läsa in käll‑XPS‑filen.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Steg 4: Initiera PDF‑spara‑alternativ (Set PDF Compression)
Konfigurera hur PDF‑filen ska komprimeras. Detta steg låter dig **set PDF compression** för bilder och text, vilket minskar filstorleken utan att kompromissa med kvaliteten.

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);                         // maximum JPEG quality
options.setImageCompression(PdfImageCompression.Jpeg);   // compress images as JPEG
options.setTextCompression(PdfTextCompression.Flate);    // compress text streams
options.setPageNumbers(new int[] { 1, 2, 6 });            // optional: export only selected pages
```

> **Varför detta är viktigt:** Justering av JPEG‑kvalitet och komprimeringstyper kan minska en 10 MB PDF till under 2 MB samtidigt som den visuella kvaliteten du behöver behålls.

### Steg 5: Skapa renderingsenhet för PDF‑format
`PdfDevice` strömmar de renderade sidorna in i PDF‑utdata‑strömmen.

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### Steg 6: Spara dokumentet
Rendera slutligen XPS‑innehållet till PDF med de konfigurerade alternativen.

```java
document.save(device, options);
```

> **Resultat:** Efter körning kommer `XPStoPDF.pdf` att visas i `dataDir`‑mappen och innehålla de konverterade sidorna med de komprimeringsinställningar du angav.

## Vanliga problem & lösningar
| Problem | Orsak | Lösning |
|---------|-------|----------|
| **`FileNotFoundException`** | Felaktig `dataDir`‑sökväg | Verifiera att katalogen finns och att applikationen har läs‑/skrivrättigheter. |
| **Blank PDF pages** | Saknad `PdfDevice`‑initialisering | Se till att `PdfDevice` skapas med samma `FileOutputStream` som används för utdata. |
| **Large PDF size** | Standardkomprimeringen är låg | Öka `setJpegQualityLevel` eller byt till `PdfImageCompression.Jpeg` med en lägre kvalitetsnivå. |
| **Only some pages appear** | `setPageNumbers`‑filter utesluter sidor | Justera arrayen för att inkludera alla behövda sidnummer eller ta bort anropet för att exportera alla sidor. |

## Vanliga frågor

**Q: Är Aspose.Page Java kompatibel med olika Java‑versioner?**  
A: Ja, Aspose.Page Java stödjer Java 8 till Java 21, inklusive både Oracle‑ och OpenJDK‑distributioner.

**Q: Kan jag anpassa komprimeringsinställningarna för den konverterade PDF‑filen?**  
A: Absolut. Använd `PdfSaveOptions` för att sätta JPEG‑kvalitet, bildkomprimeringstyp och textkomprimering som visas i Steg 4.

**Q: Var kan jag hitta ytterligare support eller community‑diskussioner?**  
A: Besök [Aspose.Page Forum](https://forum.aspose.com/c/page/39) för gemenskapsstöd, kodexempel och felsökningstips.

**Q: Finns det en gratis provversion av Aspose.Page?**  
A: Ja, du kan ladda ner en fullt funktionell provversion från [Aspose download page](https://releases.aspose.com/).

**Q: Hur kan jag få en tillfällig licens för Aspose.Page?**  
A: En tillfällig licens kan begäras [here](https://purchase.aspose.com/temporary-license/).

## Slutsats
Genom att utnyttja **Aspose.Page Java** kan du enkelt **spara XPS som PDF** och kontrollera varje aspekt av utdata, från sidval till komprimering. Denna handledning täckte allt du behöver för att integrera XPS‑till‑PDF‑konvertering i dina Java‑applikationer, oavsett om du bygger ett engångsverktyg eller en storskalig dokumenthanteringspipeline.

---

**Senast uppdaterad:** 2025-11-29  
**Testad med:** Aspose.Page for Java 24.10  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}