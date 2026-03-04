---
date: 2025-12-21
description: Lär dig hur du läser XMP‑metadata med Java och Aspose.Page. Denna steg‑för‑steg‑guide
  visar hur du läser XMP i dokumentformat och extraherar viktiga egenskaper.
linktitle: How to Read XMP Metadata using Java
second_title: Aspose.Page Java API
title: Hur man läser XMP-metadata med Java – Aspose.Page-guide
url: /sv/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hämta metadata från XMP med Java

## Så läser du XMP‑metadata med Java

Välkommen till vår steg‑för‑steg‑handledning som visar **hur man läser XMP**‑metadata med Java och Aspose.Page‑biblioteket. XMP (Extensible Metadata Platform) är en allmänt antagen standard för att bädda in rik metadata i dokument. I slutet av den här guiden kan du läsa dokumentformatets XMP, hämta skaparinformation, tidsstämplar, miniatyrbilder och mer – vilket ger dig möjlighet att bygga smartare dokumentanalys‑lösningar.

## Snabba svar
- **Vad betyder “how to read xmp”?** Det avser att programatiskt extrahera XMP‑metadata från filer.  
- **Vilket bibliotek krävs?** Aspose.Page för Java (tillgängligt från Aspose‑nedladdningssidan).  
- **Behöver jag en licens?** En temporär eller fullständig licens krävs för produktionsbruk; en gratis provversion finns tillgänglig.  
- **Vilken Java‑version stöds?** Java 8 eller högre.  
- **Kan jag läsa XMP från andra format?** Ja, Aspose.Page kan hantera EPS, PDF och flera bildtyper som bäddar in XMP.

## Förutsättningar
Innan du dyker ner i koden, se till att du har:

- **Java Development Kit (JDK)** – Java 8+ installerat och konfigurerat på din maskin.  
- **Aspose.Page för Java** – Ladda ner biblioteket från den officiella webbplatsen [here](https://releases.aspose.com/page/java/).  
- En EPS‑fil som innehåller XMP‑metadata (t.ex. `xmp1.eps`).  

## Importera paket
I ditt Java‑projekt importerar du de nödvändiga paketen:
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
Hämta XMP‑metadata från EPS‑filen. Om filen saknar XMP‑metadata genereras en ny med värden från PS‑metadata‑kommentarer.
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Steg 3: Extrahera CreatorTool‑information
Kontrollera och skriv ut värdet för ”CreatorTool” från XMP‑metadata.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Steg 4: Extrahera CreateDate‑information
Kontrollera och skriv ut värdet för ”CreateDate” från XMP‑metadata.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Steg 5: Hämta miniatyrbildens bredd
Om miniatyrbilder finns, extrahera och skriv ut bredden på den första miniatyrbilden.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Steg 6: Extrahera formatinformation
Kontrollera och skriv ut värdet för ”format” från XMP‑metadata.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Steg 7: Hämta DocumentID
Kontrollera och skriv ut värdet för ”DocumentID” från XMP‑metadata.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Varför detta är viktigt
Att läsa XMP‑metadata låter dig programatiskt upptäcka ursprung, skapelsedatum och andra väsentliga attribut för ett dokument utan att öppna det i en visare. Detta är särskilt användbart för batch‑behandling, innehållshanteringssystem och digitala tillgångspipelines där metadata driver indexering och sökning.

## Vanliga fallgropar & tips
- **Saknad XMP:** Vissa EPS‑filer kan sakna XMP. Anropet `getXmpMetadata()` kommer att syntetisera en minimal uppsättning baserat på befintliga PS‑kommentarer, men du får inte fullständig metadata om den inte är inbäddad.  
- **Miniatyr‑arrayer:** Nyckeln `xmp:Thumbnails` kan innehålla flera poster. Exemplet extraherar bara den första; iterera genom arrayen om du behöver alla miniatyrbilder.  
- **Namnrymdsmedvetenhet:** XMP‑nycklar använder namnrymder (t.ex. `xmp:`, `dc:`). Se till att referera till exakt nyckelnamn; annars returnerar `containsKey` falskt.

## Vanliga frågor
### Kan jag använda Aspose.Page för Java med andra programmeringsspråk?
Ja, Aspose.Page stöder flera språk, inklusive Java, .NET och fler. Se [documentation](https://reference.aspose.com/page/java/) för detaljer.

### Finns en gratis provversion av Aspose.Page för Java?
Ja, du kan komma åt den kostnadsfria provversionen [here](https://releases.aspose.com/).

### Var kan jag få support för Aspose.Page för Java?
Besök [Aspose.Page forum](https://forum.aspose.com/c/page/39) för community‑support.

### Hur får jag en temporär licens för Aspose.Page för Java?
Du kan skaffa en temporär licens [here](https://purchase.aspose.com/temporary-license/).

### Finns ytterligare resurser för Aspose.Page för Java?
Utforska den kompletta [documentation](https://reference.aspose.com/page/java/) och ladda ner biblioteket [here](https://releases.aspose.com/page/java/).

## Ytterligare vanliga frågor
**Q: Fungerar detta tillvägagångssätt med PDF‑filer som innehåller XMP?**  
A: Ja, Aspose.Page kan läsa XMP från PDF, EPS och flera bildformat.

**Q: Kan jag modifiera XMP‑metadata efter att ha läst den?**  
A: Absolut. `XmpMetadata`‑objektet är muterbart; du kan lägga till, uppdatera eller ta bort nycklar och sedan spara dokumentet.

**Q: Finns det ett sätt att extrahera alla miniatyrbilder, inte bara dimensionerna?**  
A: Du kan hämta den binära datan från `xmpGImg:data`‑egenskapen för varje miniatyrpost och skriva den till en fil.

## Slutsats
Du har nu bemästrat **hur man läser XMP**‑metadata med Java och Aspose.Page. Genom att följa dessa steg kan du extrahera verktyg för skapare, tidsstämplar, miniatyrbilder, formatinformation och dokument‑ID:n – vilket ger dig full insikt i den inbäddade metadata i dina EPS‑filer. Känn dig fri att experimentera med ytterligare XMP‑namnrymder för att hämta ännu rikare data till dina applikationer.

---

**Senast uppdaterad:** 2025-12-21  
**Testat med:** Aspose.Page för Java 24.12 (senaste)  
**Författare:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
