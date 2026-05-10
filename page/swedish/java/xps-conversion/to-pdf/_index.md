---
date: 2026-03-13
description: Lär dig hur du utför Aspose Page‑konvertering från XPS till PDF i Java.
  Denna steg‑för‑steg‑guide visar hur du renderar PDF från XPS, ställer in PDF‑sidnummer
  och optimerar utdata.
linktitle: How to Convert XPS to PDF in Java
second_title: Aspose.Page Java API
title: Aspose Page‑konvertering – Hur man konverterar XPS till PDF i Java
url: /sv/java/xps-conversion/to-pdf/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Page Conversion – Så konverterar du XPS till PDF i Java

Att konvertera XPS-filer till PDF är ett vanligt behov när du behöver ett universellt visningsbart dokumentformat. I den här handledningen kommer du att upptäcka **aspose page conversion** i praktiken, med Aspose.Page för Java för att **render PDF from XPS** med bara några rader kod. Oavsett om du bygger ett dokumenthanteringssystem, genererar utskrivbara rapporter eller arkiverar filer, guidar den här guiden dig genom hela processen, från förutsättningar till felsökning.

## Snabba svar
- **Vilket bibliotek hanterar konverteringen?** Aspose.Page för Java.  
- **Hur lång tid tar implementeringen?** Ungefär 10‑15 minuter för en grundläggande installation.  
- **Behöver jag en licens?** En gratis provversion fungerar för utvärdering; en licens krävs för produktion.  
- **Kan jag konvertera endast utvalda sidor?** Ja – använd alternativet *specify PDF page numbers*.  
- **Är konverteringen förlustfri?** Biblioteket bevarar vektorgrafik och textens noggrannhet.  

## Vad är Aspose Page Conversion från XPS till PDF?
Aspose Page conversion omvandlar XPS (XML Paper Specification)-dokument—Microsofts fast layout-format—till PDF, den de‑facto standarden för delning och utskrift. Konverteringen behåller layout, typsnitt och vektorgrafik, vilket säkerställer att den resulterande PDF-filen ser exakt ut som den ursprungliga XPS-filen.

## Varför använda Aspose.Page för Java för att rendera PDF från XPS?
- **High fidelity** – behåller vektorgrafik, typsnitt och layout.  
- **Fine‑grained control** – du kan ställa in bildkvalitet, komprimering och även välja specifika sidor.  
- **No external dependencies** – ren Java, fungerar på alla plattformar som stödjer JDK.  
- **Built‑in page selection** – enkelt **specify PDF page numbers** för att minska filstorleken.

## Förutsättningar
Innan du börjar, se till att du har:

- **Java Development Kit (JDK)** – någon nyare version (8+ rekommenderas).  
- **Aspose.Page for Java** – ladda ner biblioteket från den officiella [dokumentation](https://reference.aspose.com/page/java/).  
- En XPS-fil som du vill konvertera.

## Importera paket
I ditt Java‑projekt importerar du de paket som krävs för att arbeta med Aspose.Page för Java. Detta steg är avgörande för att få åtkomst till de funktioner som behövs för XPS‑till‑PDF‑konvertering.

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Steg‑för‑steg‑guide

### Steg 1: Ange dokumentkatalog
Definiera sökvägen till mappen som innehåller din käll‑XPS‑fil.

```java
String dataDir = "Your Document Directory";
```

### Steg 2: Initiera PDF‑utmatningsström
Skapa en `FileOutputStream` som kommer att ta emot den genererade PDF‑filen.

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

### Steg 3: Ladda XPS‑dokument
Ladda XPS‑filen med Aspose.Page.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Steg 4: Initiera PDF‑spara‑alternativ  
Skapa alternativ för konverteringen. Här kan du **specify PDF page numbers**, justera bildkvalitet och ställa in komprimering.

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);
options.setImageCompression(PdfImageCompression.Jpeg);
options.setTextCompression(PdfTextCompression.Flate);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### Steg 5: Skapa PDF‑renderingsenhet  
Ställ in en renderingsenhet som kommer att skriva PDF‑utdata.

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### Steg 6: Spara dokumentet  
Spara slutligen XPS‑dokumentet som en PDF med de alternativ och den enhet du konfigurerat.

```java
document.save(device, options);
```

Upprepa dessa steg, justera filsökvägar och alternativ enligt ditt specifika scenario.

## Hur du specificerar PDF‑sidnummer när du konverterar XPS
Om du bara behöver ett delmängd av sidor från den ursprungliga XPS‑filen, fyll i `setPageNumbers`‑arrayen med de önskade sidindexen (börjar på 1). Detta hjälper till att minska filstorleken och bearbetningstiden.

## Vanliga problem & felsökning
- **FileNotFoundException** – Verifiera att `dataDir` pekar på rätt mapp och att XPS‑filnamnet stämmer.  
- **LicenseException** – En giltig Aspose.Page‑licens krävs för produktionsanvändning; annars körs biblioteket i utvärderingsläge med vattenstämpel.  
- **Low image quality** – Öka `setJpegQualityLevel` eller byt till förlustfri komprimering om det behövs.

## Vanliga frågor
### Kan jag konvertera XPS‑filer med flera sidor med Aspose.Page för Java?
Ja, du kan **specify PDF page numbers** i `PdfSaveOptions` (se Steg 4) för att inkludera de sidor du behöver.

### Var kan jag hitta ytterligare support eller diskutera frågor relaterade till Aspose.Page?
Besök [Aspose.Page forum](https://forum.aspose.com/c/page/39) för community‑support och diskussioner.

### Finns det en gratis provversion av Aspose.Page för Java?
Ja, du kan utforska funktionerna med en [gratis provversion](https://releases.aspose.com/).

### Hur kan jag skaffa en tillfällig licens för Aspose.Page för Java?
Besök [denna länk](https://purchase.aspose.com/temporary-license/) för detaljer om tillfällig licens.

### Var kan jag köpa licensen för Aspose.Page för Java?
Du kan köpa licensen [här](https://purchase.aspose.com/buy).

---

**Senast uppdaterad:** 2026-03-13  
**Testad med:** Aspose.Page for Java 24.11  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}