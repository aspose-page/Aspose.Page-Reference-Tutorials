---
date: 2026-10-20
description: Lär dig hur du scale rectangle med Aspose.Page for Java, hur du translate
  shape, och applicerar affine transform för att skapa PostScript-dokument.
keywords:
- how to scale rectangle
- how to translate shape
- save postscript file
- apply affine transform
- java graphics scaling
lastmod: 2026-10-20
linktitle: Transformationer i Java sidhantering
og_description: Lär dig hur du scale rectangle, translate shape, och applicerar affine
  transform med Aspose.Page for Java för att effektivt generera PostScript-filer.
og_image_alt: Screenshot of Java code scaling a rectangle with Aspose.Page
og_title: Hur man skalar rektangel med Aspose.Page for Java – steg-för-steg guide
schemas:
- author: Aspose
  dateModified: '2026-10-20'
  description: Learn how to scale rectangle with Aspose.Page for Java, how to translate
    shape, and apply affine transform to create PostScript documents.
  headline: How to Scale Rectangle with Aspose.Page for Java
  type: TechArticle
- questions:
  - answer: '`translate` moves the origin of the coordinate system, while `scale`
      changes the size of drawn objects along the X and/or Y axes.'
    question: What is the difference between `translate` and `scale`?
  - answer: Yes—by calling `translate`, `scale`, `rotate`, or `shear` sequentially
      before drawing, you create a combined affine transformation.
    question: Can I combine multiple transformations in a single graphics state?
  - answer: Use `writeGraphicsRestore()` to revert to the previously saved graphics
      state.
    question: How do I reset transformations after drawing a shape?
  - answer: Absolutely. Translate the rectangle to the origin, apply `rotate(angle)`,
      then translate it back before drawing.
    question: Is it possible to rotate a rectangle around its center?
  - answer: Yes—set the appropriate rendering options in `PsSaveOptions` to enable
      anti‑aliasing.
    question: Does Aspose.Page support anti‑aliasing for smoother graphics?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript generation
- affine transformation
- rectangle scaling
title: Hur man skalar rektangel med Aspose.Page for Java
url: /sv/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så här skalar du rektangel med Aspose.Page för Java

## Introduktion
I den här guiden kommer du att upptäcka **how to scale rectangle**-objekt med Aspose.Page för Java, samtidigt som du lär dig hur du förflyttar formpositioner, roterar grafik och tillämpar affina transformoperationer för att producera högkvalitativ PostScript-utdata. Dessa tekniker låter dig bygga sofistikerad, enhetsoberoende grafik utan att skriva låg‑nivå renderingskod, vilket gör dina Java‑applikationer kraftfullare och mer underhållbara.

## Snabba svar
`scale(sx, sy)` skalar grafikkontexten med de angivna horisontella och vertikala faktorerna.  

- **How do I scale a rectangle in Java with Aspose.Page?** Anropa `scale(sx, sy)`‑metoden på grafikkontexten innan du ritar rektangeln.  
- **Can I move (translate) a shape without affecting other graphics?** Ja—omge förflyttningen mellan anropen `writeGraphicsSave()` och `writeGraphicsRestore()`.  
- **What class creates a PostScript file?** Använd `PsDocument` tillsammans med `PsSaveOptions`.  
- **Do I need a license for production use?** En giltig Aspose.Page‑licens krävs för kommersiella distributioner.  
- **Which Java version is supported?** Aspose.Page fungerar med Java 8 och senare.

## Förutsättningar
Innan du börjar, verifiera att du har:

- En solid förståelse för grundläggande Java‑syntax och objekt‑orienterade koncept.  
- Aspose.Page för Java‑biblioteket installerat. Du kan ladda ner det från [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- En Java‑IDE (IntelliJ IDEA, Eclipse eller VS Code) konfigurerad med bibliotekets JAR‑filer på klassökvägen.

## Importera paket
`PsDocument` är huvudklassen som används för att skapa ett PostScript‑dokument, och `PsSaveOptions` konfigurerar hur dokumentet sparas.  

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Vad betyder “how to scale rectangle” i Aspose.Page?
Metoden `scale(float sx, float sy)` tillämpar en affinsk skalningstransform på det aktuella grafikläget, vilket ändrar storleken på efterföljande ritningar med faktorerna `sx` (horisontell) och `sy` (vertikal). Detta är kärnoperationen bakom nyckelordet **how to scale rectangle**. Genom att applicera denna transform innan ritning kommer alla efterföljande former, såsom rektanglar, att renderas med de nya dimensionerna samtidigt som deras proportioner bevaras.

## Hur man översätter form med Aspose.Page
`writeGraphicsSave()` sparar det aktuella grafikläget och `writeGraphicsRestore()` återställer det, vilket säkerställer att transformationer endast påverkar den avsedda formen. Översättning (translation) flyttar koordinatsystemets ursprung utan att ändra objektets dimensioner. Genom att omge `translate(dx, dy)` med `writeGraphicsSave()` / `writeGraphicsRestore()` säkerställer du att endast den avsedda formen flyttas medan annan grafik förblir oförändrad, vilket ger exakt kontroll över enskilda element.

## Exempel 1: inga transformationer
Det första exemplet ritar en rektangel utan någon transformation, vilket skapar en grundlinje för visuell jämförelse med senare exempel.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## Exempel 2: förflyttning
I detta exempel flyttar vi grafikkontexten 250 enheter åt höger innan vi ritar en andra rektangel, vilket illustrerar **how to translate shape**.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Exempel 3: skalning
Här besvarar vi huvudfrågan **how to scale rectangle**. Rektangeln minskas till 50 % av sin ursprungliga bredd och 75 % av sin ursprungliga höjd med anropet `scale(0.5f, 0.75f)`.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Hur man roterar form java (rotate shape java)
`rotate(angle)` roterar koordinatsystemet med den angivna vinkeln i grader. Ladda ditt `PsDocument`, anropa `rotate(angle)` på grafikläget, rita formen och återställ sedan det tidigare läget. Detta mönster implementerar **rotate shape java** och **how to rotate rectangle** i ett enda återanvändbart block, vilket låter dig pivåra grafik kring vilken punkt du än väljer.

## Varför detta är viktigt – verkliga fördelar
- **Device‑independent output** – Aspose.Page kan generera PostScript‑ och XPS‑filer som renderas identiskt på vilken skrivare eller visare som helst, vilket eliminerar plattforms‑specifika justeringar.  
- **Fine‑grained control** – Kombinera förflyttning, skalning, skevning och rotation för att uppfylla exakta layout‑specifikationer; API‑et stödjer över 20 transformationskombinationer per sida.  
- **Performance‑oriented processing** – Biblioteket bearbetar dokument med ett minnesavtryck under 10 MB för typiska 100‑sidiga rapporter, vilket gör batch‑jobb snabba och skalbara.

## Vanliga användningsområden
- **Printable invoices** – Placera logotyper, streckkoder och tabeller exakt med hjälp av skalning och förflyttning för att följa företagets varumärkesriktlinjer.  
- **Technical diagrams** – Generera scheman där varje komponent måste skalas proportionellt och placeras.  
- **Automated multi‑page reports** – Skapa PostScript‑rapporter som kräver konsekvent skalning över sidor, såsom tekniska specifikationer.

## Vanliga problem och lösningar
- **Transformation not resetting** – Para alltid `writeGraphicsSave()` med `writeGraphicsRestore()`; annars ärver efterföljande ritningar oönskade transformationer.  
- **Unexpected colors** – Ställ in färgen (paint) efter varje transformation eftersom grafikläget inte bevarar färginformation efter en återställning.  
- **File size too large** – Aktivera kompression i `PsSaveOptions` och begränsa upplösningen på inbäddade rasterbilder för att hålla den slutliga filen under 5 MB för typiska 50‑sidiga dokument.

## Vanliga frågor
### Kan jag använda Aspose.Page för Java för andra dokumentformat?
Aspose.Page fokuserar främst på sidhantering för PostScript‑ och XPS‑format, men erbjuder även begränsade PDF‑exportmöjligheter.

### Var kan jag hitta fler exempel och dokumentation för Aspose.Page för Java?
Besök [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) för omfattande guider, API‑referenser och exempelprojekt.

### Finns det en gratis provversion av Aspose.Page för Java?
Ja, du kan få en gratis provversion via **Aspose free trial download**‑sidan: [Aspose free trial download](https://releases.aspose.com/).

### Hur kan jag få en tillfällig licens för Aspose.Page för Java?
Skaffa en tillfällig licens via **temporary license request page**: [temporary license request page](https://purchase.aspose.com/temporary-license/).

### Var kan jag få community‑stöd eller ställa frågor om Aspose.Page för Java?
Besök [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) för community‑diskussioner, kodsnuttar och felsökningstips.

## Vanligt ställda frågor

**Q: What is the difference between `translate` and `scale`?**  
A: `translate` flyttar koordinatsystemets ursprung, medan `scale` ändrar storleken på ritade objekt längs X‑ och/eller Y‑axeln.

**Q: Can I combine multiple transformations in a single graphics state?**  
A: Ja—genom att anropa `translate`, `scale`, `rotate` eller `shear` sekventiellt innan ritning skapar du en kombinerad affinsk transformation.

**Q: How do I reset transformations after drawing a shape?**  
A: Använd `writeGraphicsRestore()` för att återgå till det tidigare sparade grafikläget.

**Q: Is it possible to rotate a rectangle around its center?**  
A: Absolut. Förflytta rektangeln till origo, applicera `rotate(angle)`, och förflytta sedan tillbaka innan du ritar.

**Q: Does Aspose.Page support anti‑aliasing for smoother graphics?**  
A: Ja—ställ in lämpliga renderingsalternativ i `PsSaveOptions` för att aktivera anti‑aliasing.

**Senast uppdaterad:** 2026-10-20  
**Testad med:** Aspose.Page for Java 24.12  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man ritar rektangel i Java PostScript med Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [Skapa radialgradient i PostScript med Aspose.Page för Java](/page/java/postscript-gradient-addition/)
- [PostScript‑sidmanipulation](/page/java/postscript-page-manipulation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}