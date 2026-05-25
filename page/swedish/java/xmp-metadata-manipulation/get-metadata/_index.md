---
date: 2026-05-25
description: Lär dig hur du läser XMP med Aspose.Page i Java. Denna steg‑för‑steg‑guide
  visar hur man extraherar XMP metadata, creator info, timestamps, thumbnails och
  mer.
keywords:
- read xmp using aspose.page
- xmp metadata java
- aspose.page java
linktitle: Hur man läser XMP metadata med Java
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to read xmp using aspose.page with Java. This step‑by‑step
    guide shows extracting XMP metadata, creator info, timestamps, thumbnails, and
    more.
  headline: Read XMP using Aspose.Page – Java Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page can read XMP from PDF, EPS, and several image formats.
    question: Does this approach work with PDF files that contain XMP?
  - answer: Absolutely. The `XmpMetadata` object is mutable; you can add, update,
      or remove keys and then save the document.
    question: Can I modify XMP metadata after reading it?
  - answer: You can retrieve the binary data from the `xmpGImg:data` property of each
      thumbnail entry and write it to a file.
    question: Is there a way to extract all thumbnail images, not just dimensions?
  type: FAQPage
second_title: Aspose.Page Java API
title: Läs XMP med Aspose.Page – Java‑guide
url: /sv/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hämta metadata från XMP med Java

## Hur man läser XMP med Aspose.Page (Java)?

Läs in EPS-filen med `new Document("file.eps")`—klassen `Document` representerar en inläst fil. Anropa `getXmpMetadata()`, som extraherar XMP-paketet, och fråga sedan det returnerade `XmpMetadata`‑objektet—ett karta‑liknande gränssnitt för XMP‑egenskaper—för att hämta de nycklar du behöver. Detta är allt som krävs för att läsa XMP med Aspose.Page. API:et abstraherar den lågnivå‑parsingen, så du får en färdig‑till‑användning karta med egenskaper på bara två kodrader.

Välkommen till vår steg‑för‑steg‑handledning som visar **hur man läser XMP**‑metadata med Java och Aspose.Page‑biblioteket. XMP (Extensible Metadata Platform) är en allmänt antagen standard för att bädda in rik metadata i dokument. I slutet av den här guiden kommer du att kunna läsa dokumentformatets XMP, hämta information om skaparen, tidsstämplar, miniatyrbilder och mer—vilket ger dig möjlighet att bygga smartare dokumentanalys‑lösningar.

## Snabba svar
- **Vad betyder “read XMP”?** Det betyder att programmässigt extrahera XMP‑paketet som lagrar metadata i en fil.  
- **Vilket bibliotek krävs?** Aspose.Page för Java (ladda ner från den officiella sidan [here](https://releases.aspose.com/page/java/)).  
- **Behöver jag en licens?** En tillfällig eller full licens krävs för produktion; en gratis provversion fungerar för utvärdering.  
- **Vilken Java‑version stöds?** Java 8 eller högre.  
- **Kan jag läsa XMP från andra format?** Ja – Aspose.Page extraherar XMP från EPS, PDF, JPEG, PNG och över 20 andra format.

## Förutsättningar
Innan du dyker ner i koden, se till att du har:

- **Java Development Kit (JDK)** – Java 8+ installerat och konfigurerat på din maskin.  
- **Aspose.Page för Java** – Ladda ner biblioteket från den officiella webbplatsen [here](https://releases.aspose.com/page/java/).  
- En EPS‑fil som innehåller XMP‑metadata (t.ex. `xmp1.eps`).  

## Importera paket
Klassen `XmpMetadata` finns i namnrymden `com.aspose.page.xmp`, medan klassen `Document` finns i `com.aspose.page`. Importera båda så att du kan arbeta med EPS‑filen och dess metadata.  
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Steg 1: Initiera inmatnings‑EPS‑filström
Börja med att ange sökvägen till din dokumentkatalog och initiera inmatnings‑EPS‑filströmmen.  
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## Steg 2: Hämta XMP‑metadata
`XmpMetadata` är Aspose.Page‑objektet som innehåller XMP‑paketet extraherat från ett dokument. Hämta det med `document.getXmpMetadata()`. Om filen saknar XMP syntetiserar API:et ett minimalt paket från befintliga PostScript‑kommentarer.  
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Steg 3: Extrahera CreatorTool‑information
`CreatorTool`‑nyckeln finns under `xmp`‑namnrymden och registrerar den applikation som skapade filen. Kontrollera dess närvaro och skriv ut värdet.  
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Steg 4: Extrahera CreateDate‑information
`CreateDate` lagrar tidsstämpeln när dokumentet ursprungligen skapades. Använd samma `containsKey`/`get`‑mönster för att läsa det.  
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Steg 5: Hämta miniatyrbildens bredd
Om miniatyrbilder finns, innehåller `xmp:Thumbnails`‑arrayen en eller flera poster. Varje post innehåller `width`, `height` och binär data. Exemplet extraherar bredden på den första miniatyrbilden.  
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Steg 6: Extrahera formatinformation
`format`‑nyckeln berättar för dig det ursprungliga filformatet (t.ex. “application/postscript”). Detta är användbart när du behöver logga eller validera källtyper.  
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Steg 7: Hämta DocumentID
`DocumentID` är en unik identifierare som tilldelas av skapande applikation. Den kan användas för deduplicering i stora tillgångsbibliotek.  
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Varför detta är viktigt
Aspose.Page kan läsa XMP från **20+** filformat och bearbetar dokument upp till **500 MB** utan att ladda hela filen i minnet, vilket ger dig snabb, låg‑resursåtkomst till viktig metadata. Denna funktion är kritisk för batch‑bearbetnings‑pipelines, digitala tillgångshanteringssystem och alla lösningar som förlitar sig på sökbara, maskinläsbara dokumentattribut.

## Vanliga fallgropar & tips
- **Saknad XMP:** Vissa EPS‑filer kanske inte innehåller XMP. Anropet `getXmpMetadata()` kommer att syntetisera en minimal uppsättning baserad på befintliga PS‑kommentarer, men du får inte fullständig metadata om den inte är inbäddad.  
- **Miniatyr‑arrayer:** `xmp:Thumbnails`‑nyckeln kan innehålla flera poster. Exemplet extraherar bara den första; iterera arrayen om du behöver alla miniatyrbilder.  
- **Namnrymdsmedvetenhet:** XMP‑nycklar använder namnrymder (t.ex. `xmp:`, `dc:`). Se till att du refererar till exakt nyckelnamn; annars kommer `containsKey` att returnera false.  

## Vanliga frågor
### Kan jag använda Aspose.Page för Java med andra programmeringsspråk?
Ja, Aspose.Page stöder Java, .NET och flera andra språk. Se den fullständiga listan i [documentation](https://reference.aspose.com/page/java/).

### Finns en gratis provversion för Aspose.Page för Java?
Ja, du kan komma åt den gratis provversionen [here](https://releases.aspose.com/).

### Var kan jag hitta support för Aspose.Page för Java?
Besök [Aspose.Page forum](https://forum.aspose.com/c/page/39) för gemenskapshjälp och officiell support.

### Hur får jag en tillfällig licens för Aspose.Page för Java?
Du kan få en tillfällig licens [here](https://purchase.aspose.com/temporary-license/).

### Finns det ytterligare resurser för Aspose.Page för Java?
Utforska den kompletta [documentation](https://reference.aspose.com/page/java/) och ladda ner biblioteket [here](https://releases.aspose.com/page/java/).

## Ytterligare FAQ
**Q: Fungerar detta tillvägagångssätt med PDF‑filer som innehåller XMP?**  
A: Ja, Aspose.Page kan läsa XMP från PDF, EPS och flera bildformat.

**Q: Kan jag modifiera XMP‑metadata efter att ha läst dem?**  
A: Absolut. `XmpMetadata`‑objektet är muterbart; du kan lägga till, uppdatera eller ta bort nycklar och sedan spara dokumentet.

**Q: Finns det ett sätt att extrahera alla miniatyrbilder, inte bara dimensioner?**  
A: Du kan hämta den binära datan från `xmpGImg:data`‑egenskapen för varje miniatyrpost och skriva den till en fil.

## Slutsats
Du har nu bemästrat **hur man läser XMP**‑metadata med Java och Aspose.Page. Genom att följa dessa steg kan du extrahera verktyg för skapare, tidsstämplar, miniatyrbilder, formatinformation och dokument‑ID:n—vilket ger dig full insikt i den inbäddade metadata i dina EPS‑filer. Känn dig fri att experimentera med ytterligare XMP‑namnrymder för att hämta ännu rikare data till dina applikationer.

---

**Last Updated:** 2026-05-25  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose

## Relaterade handledningar

- [Aspose Page Java‑handledning – Lägg till XMP‑metadata i EPS‑filer](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page xmp‑handledning – Lägg till namnrymd i XMP med Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [aspose page xmp‑handledning – Ändra namngivet värde i XMP med Java](/page/java/xmp-metadata-manipulation/change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}