---
date: 2025-12-23
description: Lär dig hur du konverterar XPS till PDF i Java med Aspose.Page. Denna
  guide visar steg‑för‑steg konvertering, hur du renderar PDF från XPS och anger PDF‑sidnummer.
linktitle: How to Convert XPS to PDF in Java
second_title: Aspose.Page Java API
title: Hur man konverterar XPS till PDF i Java
url: /sv/java/xps-conversion/to-pdf/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man konverterar XPS till PDF i Java

## Hur man konverterar XPS till PDF i Java
I Java‑utvecklingens värld är **hur man konverterar XPS till PDF** en vanlig fråga. Oavsett om du bygger ett dokumenthanteringssystem eller behöver generera utskrivbara rapporter, kan pålitlig konvertering av XPS‑filer vara en spelväxlare. Lyckligtvis gör Aspose.Page för Java det enkelt att **rendera PDF från XPS** med bara några rader kod.

## Snabba svar
- **Vilket bibliotek hanterar konverteringen?** Aspose.Page för Java.  
- **Hur lång tid tar implementeringen?** Ungefär 10‑15 minuter för en grundläggande installation.  
- **Behöver jag en licens?** En gratis provversion fungerar för utvärdering; en licens krävs för produktion.  
- **Kan jag bara konvertera utvalda sidor?** Ja – använd alternativet *specificera PDF‑sidnummer*.  
- **Är konverteringen förlustfri?** Biblioteket bevarar vektorgrafik och textens integritet.

## Vad är XPS till PDF‑konvertering?
XPS (XML Paper Specification) är Microsofts fast‑layout‑dokumentformat. Att konvertera det till PDF låter dig dela, skriva ut eller arkivera dokument med den universellt accepterade PDF‑standarden.

## Varför använda Aspose.Page för Java för att rendera PDF från XPS?
- **Hög noggrannhet** – behåller vektorgrafik, typsnitt och layout.  
- **Fin‑granulär kontroll** – du kan ställa in bildkvalitet, komprimering och även välja specifika sidor.  
- **Inga externa beroenden** – ren Java, fungerar på alla plattformar som stödjer JDK.

## Förutsättningar
Innan du börjar, se till att du har:

- **Java Development Kit (JDK)** – någon nyare version (8+ rekommenderas).  
- **Aspose.Page för Java** – ladda ner biblioteket från den officiella [dokumentationen](https://reference.aspose.com/page/java/).  
- En XPS‑fil som du vill konvertera.

## Importera paket
I ditt Java‑projekt importerar du de paket som behövs för att arbeta med Aspose.Page för Java. Detta steg är avgörande för att få åtkomst till de funktioner som krävs för XPS‑till‑PDF‑konvertering.

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Steg‑för‑steg‑guide

### Steg 1: Ange dokumentkatalogen
Definiera sökvägen till mappen som innehåller din käll‑XPS‑fil.

```java
String dataDir = "Your Document Directory";
```

### Steg 2: Initiera PDF‑utmatningsström
Skapa ett `FileOutputStream` som kommer att ta emot den genererade PDF‑filen.

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

### Steg 3: Läs in XPS‑dokument
Läs in XPS‑filen med Aspose.Page.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Steg 4: Initiera PDF‑spara‑alternativ  
Skapa alternativ för konverteringen. Här kan du **specificera PDF‑sidnummer**, justera bildkvalitet och ange komprimering.

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

Upprepa dessa steg och anpassa sökvägar och alternativ efter ditt specifika scenario.

## Hur man specificerar PDF‑sidnummer vid konvertering av XPS
Om du bara behöver ett delmängd av sidorna från den ursprungliga XPS‑filen, fyll i `setPageNumbers`‑arrayen med de önskade sidindexen (börjar på 1). Detta hjälper till att minska filstorlek och bearbetningstid.

## Vanliga problem & felsökning
- **FileNotFoundException** – Verifiera att `dataDir` pekar på rätt mapp och att XPS‑filnamnet stämmer.  
- **LicenseException** – En giltig Aspose.Page‑licens krävs för produktionsanvändning; annars körs biblioteket i utvärderingsläge med vattenstämpel.  
- **Låg bildkvalitet** – Öka `setJpegQualityLevel` eller byt till förlustfri komprimering om det behövs.

## Vanliga frågor

### Kan jag konvertera XPS‑filer med flera sidor med Aspose.Page för Java?
Ja, du kan **specificera PDF‑sidnummer** i `PdfSaveOptions` (se Steg 4) för att inkludera de sidor du behöver.

### Var kan jag hitta ytterligare support eller diskutera frågor relaterade till Aspose.Page?
Besök [Aspose.Page‑forumet](https://forum.aspose.com/c/page/39) för community‑support och diskussioner.

### Finns det en gratis provversion av Aspose.Page för Java?
Ja, du kan utforska funktionerna med en [gratis provversion](https://releases.aspose.com/).

### Hur kan jag skaffa en tillfällig licens för Aspose.Page för Java?
Besök [denna länk](https://purchase.aspose.com/temporary-license/) för information om tillfälliga licenser.

### Var kan jag köpa licensen för Aspose.Page för Java?
Du kan köpa licensen [här](https://purchase.aspose.com/buy).

---

**Senast uppdaterad:** 2025-12-23  
**Testad med:** Aspose.Page för Java 24.11  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}