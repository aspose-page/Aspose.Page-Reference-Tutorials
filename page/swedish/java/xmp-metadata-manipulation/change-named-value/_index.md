---
date: 2026-05-15
description: Lär dig hur du redigerar XMP metadata och hur du ändrar XMP värden i
  EPS filer med Aspose.Page for Java – en tydlig steg‑för‑steg‑guide.
keywords:
- how to edit xmp
- how to change xmp
- Aspose.Page XMP Java
- edit EPS metadata
- XMP manipulation Java
linktitle: Ändra namngivet värde i XMP med Java
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  headline: how to edit xmp – Change Named Value in XMP using Java
  type: TechArticle
- description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  name: how to edit xmp – Change Named Value in XMP using Java
  steps:
  - name: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
    text: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
  - name: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
    text: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
  - name: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
    text: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
  type: HowTo
- questions:
  - answer: Aspose.Page primarily supports Java, but Aspose offers equivalent libraries
      for .NET, C++, and Python that expose similar XMP manipulation capabilities.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore a free trial of Aspose.Page for Java [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support and discussions.
    question: Where can I find additional support and discussions about Aspose.Page
      for Java?
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: To buy Aspose.Page for Java, visit the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: hur man redigerar xmp – Ändra namngivet värde i XMP med Java
url: /sv/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# hur man redigerar xmp – Ändra namngivet värde i XMP med Java

I moderna dokumentarbetsflöden gör **Aspose.Page for Java** det enkelt att läsa, redigera och skriva XMP-metadata i EPS-filer. **Denna handledning visar hur man redigerar xmp**-metadata i EPS-dokument med hjälp av Aspose.Page API, så att du kan hålla din dokumentinformation korrekt, sökbar och i enlighet med branschstandarder. Oavsett om du uppdaterar sidmått, författarinformation eller anpassade taggar, guidar stegen nedan dig genom processen i Java.

## Snabba svar
- **Vad täcker den här handledningen?** Ändra ett namngivet XMP‑värde i en EPS‑fil med Aspose.Page for Java.  
- **Vilken biblioteksversion krävs?** Vilken som helst nyare Aspose.Page for Java‑utgåva (API:et har varit stabilt i flera år).  
- **Behöver jag en licens?** En tillfällig eller full licens krävs för produktion; en gratis provversion fungerar för testning.  
- **Hur lång tid tar implementeringen?** Ungefär 10‑15 minuter för en utvecklare som är bekant med Java I/O.  
- **Kan jag använda detta med andra filformat?** XMP‑API:et är också tillgängligt för PDF, SVG och andra format som stöds av Aspose.Page.

## Vad är XMP-metadata?
XMP (Extensible Metadata Platform) är ett standardiserat XML‑baserat format för att bädda in rik metadata—såsom skapare, titel och anpassade egenskaper—direkt i filer. I EPS‑dokument lever XMP bredvid traditionella PostScript‑kommentarer, vilket gör det möjligt för applikationer att läsa och ändra metadata utan att förändra det visuella innehållet.

## Varför använda Aspose.Page for Java för att redigera XMP?
Aspose.Page ger dig **full kontroll över mer än 150 XMP‑schemapropertys** och fungerar konsekvent över EPS-, PDF- och SVG-format. Det bearbetar filer upp till **500 MB** utan att ladda hela dokumentet i minnet, och det innehåller inbyggd validering som garanterar att den resulterande EPS‑filen förblir standard‑kompatibel. Inga externa XML‑parsers eller inhemska bibliotek krävs.

## Introduktion
Aspose.Page for Java är ett robust bibliotek som underlättar manipulation och bearbetning av EPS‑filer. När det gäller hantering av XMP‑metadata i dessa filer ger Aspose.Page utvecklare ett omfattande verktygssätt. I den här handledningen kommer vi att fokusera på att ändra ett namngivet värde i XMP, och erbjuda en tydlig och koncis guide för utvecklare som vill förbättra sina dokumentbearbetningsmöjligheter.

## Förutsättningar
Innan du dyker ner i handledningen, se till att du har följande förutsättningar på plats:
1. **Java Development Environment** – En JDK (8 eller högre) och en IDE eller byggverktyg (Maven/Gradle).  
2. **Aspose.Page for Java Library** – Ladda ner och integrera Aspose.Page for Java‑biblioteket i ditt projekt. Du kan hitta biblioteket och detaljerad dokumentation [here](https://reference.aspose.com/page/java/).  
3. **Sample EPS File** – Ha en exempel‑EPS‑fil redo för experimentering. Om du inte har en, använd den medföljande exempelfilen med namnet **"xmp4.eps."**

## Importera paket
`import`‑satserna importerar de väsentliga Aspose.Page‑klasserna i scopet.

Klassen `PsDocument` är Aspose.Page:s kärnobjekt som representerar ett EPS‑dokument i minnet.  
Klassen `XmpMetadata` ger åtkomst till XMP‑paketet som är inbäddat i EPS‑filen.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Hur man redigerar XMP-metadata?
Läs in EPS‑filen, hämta dess XMP‑paket, ändra den önskade egenskapen och spara dokumentet—allt i några enkla rader. Detta tillvägagångssätt fungerar för vilket namngivet XMP‑värde som helst, oavsett om det är ett standard‑Dublin‑Core‑fält eller ett anpassat namnrymd du har definierat.

## Steg 1: Initiera inmatnings‑EPS‑filström
`FileInputStream` öppnar en skrivskyddad ström till käll‑EPS‑filen, vilket gör att Aspose.Page kan läsa in dokumentet utan att låsa filsystemet.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## Steg 2: Initiera PsDocument
`PsDocument` är det primära objektet som kapslar EPS‑innehållet och ger åtkomst till dess metadata, sidor och resurser.

```java
PsDocument document = new PsDocument(psStream);
```

## Steg 3: Hämta XMP-metadata
`XmpMetadata` representerar XMP‑paketet i EPS‑filen och erbjuder metoder för att läsa, ändra eller ta bort enskilda egenskaper.

```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Steg 4: Sätt nytt värde i XMP
`setProperty` sätter värdet för en specificerad XMP‑egenskap i metadata‑paketet.

```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## Steg 5: Initiera utmatnings‑EPS‑filström
`FileOutputStream` skapar en skrivbar ström för att spara den modifierade EPS‑filen.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## Steg 6: Spara dokument med ändrad XMP-metadata
`save` skriver det in‑minnet‑PsDocument, inklusive uppdaterad XMP, till utmatningsströmmen.

```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Steg 7: Stäng inmatnings‑EPS‑ström
`close` frigör filhandtaget och resurserna som är kopplade till inmatningsströmmen.

```java
// Close input EPS stream
psStream.close();
```

## Vanliga problem och lösningar
- **FileNotFoundException** – Verifiera att `dataDir` pekar på rätt mapp och att `xmp4.eps` finns.  
- **LicenseException** – Om du får licensfel, se till att en giltig Aspose.Page‑licensfil laddas innan du skapar `PsDocument`.  
- **Metadata Not Updated** – Efter sparning, öppna den resulterande EPS‑filen i en metadata‑visare (t.ex. Adobe Bridge) för att bekräfta att det nya värdet visas.

## Vanliga frågor
**Q: Kan jag använda Aspose.Page for Java med andra programmeringsspråk?**  
A: Aspose.Page stödjer främst Java, men Aspose erbjuder motsvarande bibliotek för .NET, C++ och Python som ger liknande XMP‑manipuleringsfunktioner.

**Q: Finns det en gratis provversion av Aspose.Page for Java?**  
A: Ja, du kan prova en gratis provversion av Aspose.Page for Java [here](https://releases.aspose.com/).

**Q: Var kan jag hitta ytterligare support och diskussioner om Aspose.Page for Java?**  
A: Besök [Aspose.Page forum](https://forum.aspose.com/c/page/39) för gemenskapsstöd och diskussioner.

**Q: Hur kan jag skaffa en tillfällig licens för Aspose.Page for Java?**  
A: Du kan skaffa en tillfällig licens [here](https://purchase.aspose.com/temporary-license/).

**Q: Var kan jag köpa Aspose.Page for Java?**  
A: För att köpa Aspose.Page for Java, besök [purchase page](https://purchase.aspose.com/buy).

**Senast uppdaterad:** 2026-05-15  
**Testad med:** Aspose.Page for Java (senaste version)  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man läser XMP-metadata med Java – Aspose.Page Guide](/page/java/xmp-metadata-manipulation/get-metadata/)
- [Aspose Page Java-handledning – Lägg till XMP-metadata i EPS-filer](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page modify xmp – Ändra värden i XMP med Java](/page/java/xmp-metadata-manipulation/change-values/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}