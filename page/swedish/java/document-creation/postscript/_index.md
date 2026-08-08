---
date: 2026-06-20
description: Lär dig hur du ställer in A4-sidstorlek, skapar PostScript-filer i Java
  och lägger till anpassade teckensnitt med Aspose.Page. Prova den kostnadsfria provversionen
  idag!
keywords:
- set a4 page size
- add custom fonts java
- java create postscript
linktitle: Skapa dokument i Java med PostScript
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to set A4 page size and create PostScript in Java with Aspose.Page
  type: TechArticle
- description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to set A4 page size and create PostScript in Java with Aspose.Page
  steps:
  - name: Set Document Directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define Fonts Folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create Output Stream for PostScript Document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create Save Options with A4 Size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set Page Margins and Add Custom Fonts Folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a Multipaged or Single‑Paged PS Document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close Current Page and Save Document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [here](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [here](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page forum [forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
title: Hur man ställer in A4-sidstorlek och skapar PostScript i Java med Aspose.Page
url: /sv/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så här ställer du in A4‑sidstorlek och skapar PostScript i Java med Aspose.Page

## Introduktion
Om du behöver **ställa in a4‑sidstorlek** när du genererar PostScript‑filer från Java, erbjuder Aspose.Page ett snabbt och pålitligt API som döljer de lågnivå‑detaljerna. I den här handledningen går vi igenom hela arbetsflödet – att skapa ett PostScript‑dokument, konfigurera A4‑sidmåtten och **lägga till anpassade teckensnitt** när det behövs. I slutet har du ett färdigt kodexempel som du kan klistra in i vilket Java‑projekt som helst.

## Snabba svar
- **Vilket bibliotek skapar PostScript i Java?** Aspose.Page för Java.  
- **Vilken sidstorlek riktar sig guiden mot?** A4 (210 mm × 297 mm).  
- **Kan jag bädda in egna teckensnitt?** Ja – ange den extra teckensnittsmappen i sparalternativen.  
- **Behöver jag en licens för produktion?** En kommersiell licens krävs; en gratis provversion finns tillgänglig.  
- **Vilka Java‑versioner stöds?** Java 8 och senare.

## Så här ställer du in a4‑sidstorlek och skapar postscript i Java
Läs in Aspose.Page‑biblioteket, konfigurera `PsSaveOptions` med A4‑konstanterna och skriv dokumentet till en fil – allt på under tio kodrader. Detta direkta tillvägagångssätt garanterar korrekta sidmått och låter dig lägga till anpassade teckensnitt utan extra konfiguration.

## Vad är postscript a4‑storlek?
PostScript A4‑storlek är ISO 216‑standarden (210 mm × 297 mm) uttryckt i PostScript‑sidbeskrivningsspråket. Den definierar det utskrivbara området som skrivare och visningsprogram tolkar, vilket säkerställer en konsekvent layout över plattformar. Eftersom PostScript beskriver sidinnehåll på ett enhetsoberoende sätt, garanterar användning av A4‑storlek att dokumentet visas likadant på alla A4‑kompatibla skrivare eller visningsprogram världen över.

## Varför använda Aspose.Page för att ställa in postscript‑sidstorlek?
Aspose.Page stödjer **30+ PostScript‑operatorer** och kan generera filer upp till **500 MB** utan att ladda hela dokumentet i minnet. Detta ger dig exakt kontroll över sidmått samtidigt som stora arbetsbelastningar hanteras effektivt. Biblioteket abstraherar också komplex PostScript‑syntax, hanterar resurser automatiskt och erbjuder högpresterande streaming, vilket gör det idealiskt för både enkla enkelsidiga flyers och komplexa flersidiga rapporter.

## Hur man lägger till anpassade teckensnitt i Java
Att bädda in egna typsnitt säkerställer att det genererade dokumentet ser exakt ut som designat på alla skrivare eller visningsprogram, och Aspose.Page upptäcker automatiskt teckensnitt som placerats i den angivna mappen. Genom att registrera en extra teckensnittsmapp kan du använda vilket TrueType‑ eller OpenType‑teckensnitt som helst, undvika reservteckensnitt och behålla varumärkeskonsistens över alla utskriftsenheter.

## Förutsättningar
Innan du börjar, se till att du har:

- Grundläggande kunskaper i Java‑programmering.  
- Aspose.Page för Java installerat. Du kan ladda ner det [här](https://releases.aspose.com/page/java/).  
- En mapp som heter `necessary_fonts` (eller ett annat namn du föredrar) som innehåller de anpassade teckensnitt du vill bädda in.

## Importera paket
I ditt Java‑projekt, importera de nödvändiga Aspose.Page‑klasserna:

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Nu delar vi upp exemplet i tydliga, numrerade steg.

### Steg 1: Ange dokumentkatalog
Konstanten `OUTPUT_DIR` talar om för biblioteket var den genererade filen ska skrivas.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Steg 2: Definiera teckensnittsmapp
`FONTS_FOLDER` pekar på katalogen som innehåller dina anpassade TrueType‑ eller OpenType‑teckensnitt.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Steg 3: Skapa OutputStream för PostScript‑dokument
`FileOutputStream` öppnar en ström som kommer att ta emot den slutgiltiga PostScript‑A4‑utmatningen.

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### Steg 4: Skapa sparalternativ med A4‑storlek
`PsSaveOptions` låter dig ange mål‑sidstorlek.  
**Definition:** `PsPageSize` är en uppräkning som innehåller standard‑sidstorlekskonstanter såsom A4, Letter och Legal.  
Genom att anropa `options.setPageSize(PsPageSize.A4)` konfigureras dokumentet för standard‑A4‑dimensioner.

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### Steg 5: Ange sidmarginaler och lägg till anpassad teckensnittsmapp
`options.setMargins(0, 0, 0, 0)` tar bort alla marginaler för en fullbleed‑sida, och `options.setAdditionalFontsFolder(FONTS_FOLDER)` registrerar dina anpassade teckensnitt.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### Steg 6: Skapa ett flersidigt eller enkelsidigt PS‑dokument
`PsDocument document = new PsDocument(outputStream, options)` skapar dokumentet. `PsDocument` representerar ett PostScript‑dokument som kan innehålla en eller flera sidor. Sätt `multiPaged` till `true` för flersidigt utdata.

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### Steg 7: Stäng aktuell sida och spara dokumentet
Genom att anropa `document.close()` slutförs filen och **PostScript A4‑storlek** skrivs till disk.

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Vanliga problem & tips
- **Teckensnitt visas inte?** Kontrollera att teckensnittsfilen är i ett stödformat (TrueType eller OpenType) och att `FONTS_FOLDER` avslutas med ett snedstreck (`/`).  
- **Marginaler syns fortfarande?** Anropa `options.setMargins(...)` **innan** du skapar `PsDocument`.  
- **Flersidigt utdata ser tomt ut?** Kom ihåg att anropa `document.newPage()` för varje extra sida du behöver.

## Vanliga frågor

**Q: Kan jag använda anpassade teckensnitt i mitt PostScript‑dokument?**  
A: Ja, ange den extra teckensnittsmappen i sparalternativen (se Steg 5) så bäddar Aspose.Page in teckensnitten automatiskt.

**Q: Finns det en provversion av Aspose.Page för Java?**  
A: Ja, du kan få en gratis provversion [här](https://releases.aspose.com/).

**Q: Hur får jag åtkomst till den fullständiga API‑referensen?**  
A: Se dokumentationen [här](https://reference.aspose.com/page/java/).

**Q: Var kan jag köpa en licens för Aspose.Page för Java?**  
A: Du kan köpa en licens [här](https://purchase.aspose.com/buy).

**Q: Var kan jag be communityn om hjälp?**  
A: Besök Aspose.Page‑forumet [forum](https://forum.aspose.com/c/page/39).

**Q: Kan jag generera flersidiga PostScript‑filer?**  
A: Absolut – sätt `multiPaged` till `true` i Steg 6 och anropa `document.newPage()` för varje extra sida.

## Slutsats
Genom att följa dessa steg vet du nu **hur du ställer in a4‑sidstorlek** och skapar **PostScript**‑filer i Java med Aspose.Page, samtidigt som du kan **lägga till anpassade teckensnitt java** och kontrollera sidstorleksalternativ. Aspose.Page sköter det tunga arbetet, så att du kan fokusera på innehållet i dina dokument.

---

**Senast uppdaterad:** 2026-06-20  
**Testat med:** Aspose.Page för Java 24.11  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Aspose.Page Java‑handledning – ställ in anpassad sidstorlek medan du lägger till sidor i PostScript](/page/java/postscript-page-manipulation/add-pages2/)
- [Hur man lägger till text i PostScript med Aspose.Page för Java](/page/java/postscript-text-manipulation/)
- [Aspose Page Java‑handledning – konvertera PostScript till PDF](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
document.closePage();
document.save();
```