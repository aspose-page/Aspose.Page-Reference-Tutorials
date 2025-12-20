---
date: 2025-12-20
description: Lär dig hur du skapar XMP‑metadata EPS i EPS‑filer med Aspose.Page för
  Java. Steg‑för‑steg‑guide för att lägga till enkla XMP‑egenskaper programmässigt.
linktitle: Add Simple Properties in XMP using Java
second_title: Aspose.Page Java API
title: Hur man skapar XMP-metadata EPS med Java
url: /sv/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till enkla egenskaper i XMP med Java

## Introduktion
I moderna dokumentarbetsflöden ger möjligheten att **create XMP metadata EPS** filer programatiskt dig full kontroll över hur dina grafikbeskrivningar hanteras, söks och arkiveras. Med Aspose.Page for Java kan du läsa, modifiera och skriva XMP‑paket i EPS‑dokument utan att lämna Java‑ekosystemet. I den här handledningen går vi igenom de exakta stegen för att lägga till enkla XMP‑egenskaper i en EPS‑fil, så att du snabbt och pålitligt kan berika din grafik med anpassad metadata.

## Snabba svar
- **Vad betyder “create xmp metadata eps”?** Att lägga till ett XMP‑paket (XML‑baserad metadata) i en EPS‑fil.  
- **Vilket bibliotek krävs?** Aspose.Page for Java (nedladdningsbart från Aspose‑sidan).  
- **Behöver jag en licens för testning?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Hur många rader kod?** Mindre än 30 rader Java plus några import‑satser.  
- **Kan jag lägga till andra datatyper?** Ja – datum, heltal, dubbla, strängar och till och med arrayer stöds.

## Vad är create xmp metadata eps?
XMP (Extensible Metadata Platform) är en standard för att bädda in rik metadata i filer. När du **create XMP metadata EPS** så bäddar du in ett XML‑paket i ett EPS‑dokument (Encapsulated PostScript), vilket gör att efterföljande applikationer kan läsa författare, skapelsedatum, anpassade taggar och mer.

## Varför lägga till XMP‑metadata i EPS‑filer?
- **Sökbarhet:** Möjliggör automatisk indexering av DAM‑system.  
- **Efterlevnad:** Lagrar juridisk eller licensinformation direkt i filen.  
- **Automation:** Låter efterföljande pipelines fatta beslut baserat på inbäddad data.  
- **Portabilitet:** Metadatan följer med EPS‑filen och säkerställer konsistens över plattformar.

## Förutsättningar
Innan du börjar, se till att du har:

- Grundläggande kunskap i Java‑programmering.  
- Aspose.Page for Java‑biblioteket installerat. Du kan ladda ner det **[here](https://releases.aspose.com/page/java/)**.  
- En exempel‑EPS‑fil som innehåller metadata. Om du inte har en, kan du använda den medföljande **`xmp3.eps`**‑filen.

## Importera paket
Först importerar du de klasser du behöver. Importerna förblir exakt desamma som i originalexemplet:

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

## Steg 1: Läs in EPS‑dokumentet och hämta XMP‑metadata
Vi öppnar EPS‑filen, skapar en `PsDocument`‑instans och hämtar (eller skapar) XMP‑paketet.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Steg 2: Lägg till en datum‑egenskap
Att lägga till ett datum är så enkelt som att skapa ett `Date`‑objekt och lägga in det i XMP‑kartan.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Steg 3: Lägg till en heltals‑egenskap
Du kan lagra numeriska identifierare eller versionsnummer med ett heltal.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Steg 4: Lägg till en dubbel‑egenskap
Flyttal är användbara för mätningar eller betyg.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Steg 5: Lägg till en sträng‑egenskap
Anpassade texttaggar (t.ex. projektkoder) lagras som strängar.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Steg 6: Spara den uppdaterade EPS‑filen
När alla egenskaper har lagts till, skriv dokumentet tillbaka till disk.

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

## Steg 7: Rensa resurser
Stäng alltid inmatningsströmmen för att undvika läckage av filhandtag.

```java
// Close input EPS stream
psStream.close();
```

## Vanliga problem och lösningar
| Problem | Orsak | Lösning |
|---------|-------|---------|
| **Null XMP metadata** | EPS‑filen hade inget XMP‑paket och biblioteket kunde inte härleda PS‑kommentarer. | Se till att käll‑EPS‑filen innehåller minst en PS‑kommentar (t.ex. `%%Creator`). Biblioteket kommer automatiskt att generera ett minimalt XMP‑paket. |
| **Time zone mismatch** | Datum visas förskjutna när de öppnas i en annan applikation. | Ställ in `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` innan du skapar `Date`‑objektet, som visas i Steg 2. |
| **License exception** | Körning kastar `LicenseException`. | Applicera en giltig Aspose.Page‑licens innan du använder API‑et, eller kör i provläge för utvärdering. |

## Slutsats
Genom att följa dessa steg vet du nu hur du **create XMP metadata EPS** filer med Aspose.Page for Java. Att lägga till enkla egenskaper som datum, heltal, dubbla och strängar är enkelt, och de resulterande EPS‑filerna innehåller rik, sökbar metadata som gynnar alla efterföljande arbetsflöden.

## Vanliga frågor
### Kan jag använda Aspose.Page for Java med andra programmeringsspråk?
Aspose.Page stödjer främst Java, men det finns versioner tillgängliga för andra språk som .NET.

### Finns en gratis provversion tillgänglig för Aspose.Page for Java?
Ja, du kan utforska funktionerna i Aspose.Page genom att skaffa en gratis provversion **[here](https://releases.aspose.com/)**.

### Var kan jag hitta detaljerad dokumentation för Aspose.Page for Java?
Dokumentationen finns **[here](https://reference.aspose.com/page/java/)**.

### Hur kan jag skaffa en tillfällig licens för Aspose.Page for Java?
En tillfällig licens kan erhållas **[here](https://purchase.aspose.com/temporary-license/)**.

### Var kan jag köpa Aspose.Page for Java?
Du kan köpa produkten **[here](https://purchase.aspose.com/buy)**.

---

**Senast uppdaterad:** 2025-12-20  
**Testad med:** Aspose.Page for Java 24.11 (senaste vid skrivande)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}