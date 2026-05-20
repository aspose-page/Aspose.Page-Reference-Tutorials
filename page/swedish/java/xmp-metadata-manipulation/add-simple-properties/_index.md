---
date: 2026-05-20
description: Lär dig hur du lägger till XMP-metadata i EPS-filer med Aspose.Page för
  Java. Step‑by‑step guide för att programatiskt bädda in enkla XMP-egenskaper.
keywords:
- add xmp metadata
- how to add xmp
- Aspose.Page Java XMP
linktitle: Lägg till enkla egenskaper i XMP med Java
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add XMP metadata to EPS files with Aspose.Page for Java.
    Step‑by‑step guide to embed simple XMP properties programmatically.
  headline: Add XMP Metadata to EPS Files Using Java
  type: TechArticle
- questions:
  - answer: Aspose.Page primarily supports Java, but equivalent libraries are available
      for .NET, C++, and Python.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore the features of Aspose.Page by obtaining a free trial
      **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Page for Java?
  - answer: The documentation is available **[here](https://reference.aspose.com/page/java/)**.
    question: Where can I find detailed documentation for Aspose.Page for Java?
  - answer: A temporary license can be acquired **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: You can purchase the product **[here](https://purchase.aspose.com/buy)**.
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: Lägg till XMP-metadata i EPS-filer med Java
url: /sv/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till XMP-metadata i EPS-filer med Java

## Introduktion
I moderna grafik‑pipelines ger möjligheten att **lägga till XMP‑metadata** i EPS‑filer programatiskt dig full kontroll över hur dina illustrationer beskrivs, söks och arkiveras. Med Aspose.Page för Java kan du läsa, modifiera och skriva XMP‑paket i EPS‑dokument utan att lämna Java‑ekosystemet. I den här handledningen går vi igenom de exakta stegen för att lägga till enkla XMP‑egenskaper i en EPS‑fil, så att du snabbt och pålitligt kan berika dina grafik med anpassad metadata.

## Snabba svar
- **Vad betyder “lägga till XMP‑metadata i EPS”?** Inbäddning av ett XMP‑paket (XML‑baserad metadata) i en EPS‑fil.  
- **Vilket bibliotek krävs?** Aspose.Page för Java (nedladdningsbart från Aspose‑sajten).  
- **Behöver jag en licens för testning?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Hur många kodrader?** Mindre än 30 rader Java plus några import‑satser.  
- **Kan jag lägga till andra datatyper?** Ja – datum, heltal, dubbelvärden, strängar och till och med arrayer stöds.

## Hur man lägger till XMP‑metadata i EPS‑filer med Java?
Läs in EPS‑filen med `new PsDocument("input.eps")`, hämta eller skapa dess XMP‑paket, infoga de önskade egenskaperna och spara sedan dokumentet tillbaka till disk – allt på under tio rader Java‑kod. Detta tillvägagångssätt låter dig bädda in sökbar, standard‑kompatibel metadata utan manuell redigering av EPS‑källan.

## Vad är XMP‑metadata i EPS?
XMP‑metadata i EPS är ett XML‑paket som lever inuti EPS‑filen och lagrar information såsom författare, skapelsedatum och anpassade taggar. Inbäddning av detta paket låter efterföljande verktyg läsa och agera på data utan att behöva separata sidofiler.

## Varför lägga till XMP‑metadata i EPS‑filer?
Inbäddning av XMP‑metadata gör EPS‑tillgångar omedelbart sökbara, säkerställer efterlevnad genom att lagra licensinformation i filen, möjliggör automatiserade pipelines att fatta beslut baserade på inbäddade taggar och garanterar att metadata följer med grafiken över alla plattformar. Aspose.Page kan bearbeta filer upp till 500 MB utan att ladda hela dokumentet i minnet, vilket ger snabb prestanda för storskaliga arbetsbelastningar.

## Förutsättningar
Innan du börjar, se till att du har:

- Grundläggande kunskaper i Java‑programmering.  
- Aspose.Page för Java‑biblioteket installerat. Du kan ladda ner det **[here](https://releases.aspose.com/page/java/)**.  
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

## Steg 1: Ladda EPS‑dokumentet och hämta XMP‑metadata
Klassen `PsDocument` representerar en EPS‑fil och tillhandahåller metoder för att komma åt dess innehåll och metadata.  
Objektet `XmpMetadata` innehåller XMP‑paketet som är associerat med dokumentet.

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
Klassen `Date` representerar ett specifikt ögonblick i tiden, med millisekundprecision.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Steg 3: Lägg till en heltals‑egenskap
Klassen `Integer` omsluter ett primitivt `int`‑värde som ett objekt.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Steg 4: Lägg till en dubbel‑egenskap
Klassen `Double` omsluter ett primitivt `double`‑värde som ett objekt.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Steg 5: Lägg till en sträng‑egenskap
Klassen `String` representerar en sekvens av tecken.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Steg 6: Spara den uppdaterade EPS‑filen
Metoden `save` skriver det modifierade dokumentet tillbaka till disk och bevarar EPS‑strukturen.

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
Stäng alltid strömmar för att undvika filhandtagsläckor och säkerställ att alla buffertar töms.

```java
// Close input EPS stream
psStream.close();
```

## Vanliga problem och lösningar
| Problem | Orsak | Lösning |
|---------|-------|---------|
| **Null XMP‑metadata** | EPS‑filen hade inget XMP‑paket och biblioteket kunde inte härleda PS‑kommentarer. | Se till att käll‑EPS‑filen innehåller minst en PS‑kommentar (t.ex. `%%Creator`). Biblioteket kommer automatiskt att generera ett minimalt XMP‑paket. |
| **Tidszonsfel** | Datum visas förskjutna när de öppnas i ett annat program. | Ange `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` innan du skapar `Date`‑objektet, som visas i Steg 2. |
| **Licens‑undantag** | Körningstid kastar `LicenseException`. | Applicera en giltig Aspose.Page‑licens innan du använder API‑et, eller kör i provläge för utvärdering. |

## Vanliga frågor
**F: Kan jag använda Aspose.Page för Java med andra programmeringsspråk?**  
A: Aspose.Page stöder främst Java, men motsvarande bibliotek finns tillgängliga för .NET, C++ och Python.

**F: Finns en gratis provversion för Aspose.Page för Java?**  
A: Ja, du kan utforska funktionerna i Aspose.Page genom att skaffa en gratis provversion **[here](https://releases.aspose.com/)**.

**F: Var kan jag hitta detaljerad dokumentation för Aspose.Page för Java?**  
A: Dokumentationen finns **[here](https://reference.aspose.com/page/java/)**.

**F: Hur kan jag få en tillfällig licens för Aspose.Page för Java?**  
A: En tillfällig licens kan erhållas **[here](https://purchase.aspose.com/temporary-license/)**.

**F: Var kan jag köpa Aspose.Page för Java?**  
A: Du kan köpa produkten **[here](https://purchase.aspose.com/buy)**.

**Senast uppdaterad:** 2026-05-20  
**Testad med:** Aspose.Page för Java 24.12 (senaste vid skrivande)  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Hur man läser XMP‑metadata med Java – Aspose.Page Guide](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page xmp‑handledning – Lägg till namnrymd i XMP med Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Lägg till array‑element i XMP‑metadata med Java](/page/java/xmp-metadata-manipulation/add-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}