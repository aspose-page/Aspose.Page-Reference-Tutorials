---
date: 2026-02-18
description: Lär dig att rita rektangelformer i Java PostScript med Aspose.Page. Denna
  steg‑för‑steg‑guide visar hur du ställer in färg, anger rektangelns färg i Java
  och skapar livfull grafik samtidigt som den förklarar hur du ritar rektanglar effektivt.
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: Hur man ritar en rektangel i Java PostScript med Aspose.Page
url: /sv/java/postscript-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man ritar rektangel i Java PostScript med Aspose.Page

## Introduction
Om du behöver **how to draw rectangle** former i en Java PostScript-fil, har du kommit till rätt ställe. I den här handledningen går vi igenom hur du använder Aspose.Page för Java för att lägga till färgglada rektanglar, kontrollera deras fyllning och kontur, och spara resultatet som ett PostScript-dokument. Du kommer att se exakt **how to set paint**, hur du definierar rektangelns geometri, och varför detta tillvägagångssätt är idealiskt för att programatiskt generera utskrivbara grafik. I slutet av guiden kommer du också att förstå den bredare kontexten av **draw rectangle java** tekniker och hur de passar in i **java awt rectangle drawing** arbetsflöden.

## Quick Answers
- **What library is required?** Aspose.Page for Java → **Vilket bibliotek krävs?** Aspose.Page for Java  
- **Can I change rectangle colors?** Yes – use `setPaint` with any `java.awt.Color` → **Kan jag ändra rektangelns färger?** Ja – använd `setPaint` med valfri `java.awt.Color`  
- **Do I need a license for development?** A free trial works for testing; a license is required for production → **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en licens krävs för produktion  
- **Which page size is used in the example?** A4 (default `PsSaveOptions`) → **Vilken sidstorlek används i exemplet?** A4 (standard `PsSaveOptions`)  
- **Is the code compatible with Java 8+?** Absolutely – it uses standard AWT classes → **Är koden kompatibel med Java 8+?** Absolut – den använder standard‑AWT‑klasser  

## What Is “How to Draw Rectangle” in PostScript?
Att rita en rektangel i ett PostScript-dokument innebär att definiera ett rektangulärt område och antingen fylla det, rita dess kontur, eller båda. Med Aspose.Page kan du göra detta med hjälp av välbekanta **java awt rectangle drawing** klasser, vilket gör koden lätt att läsa och underhålla.

## Why Use Aspose.Page for Rectangle Graphics?
- **Cross‑platform**: Genererar standard‑PostScript som fungerar på vilken skrivare som helst.  
- **Fine‑grained control**: Du kan ställa in fyllningsfärger, konturfärger och linjebredd oberoende av varandra.  
- **No external dependencies**: Använder endast de inbyggda AWT‑geometri‑klasserna, så du behöver inga extra grafikbibliotek.  

## Prerequisites
Innan du dyker ner i handledningen, se till att du har följande förutsättningar på plats:
- Grundläggande förståelse för Java‑programmering.  
- Aspose.Page för Java‑biblioteket installerat. Om inte, ladda ner det från den [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- En Java‑utvecklingsmiljö konfigurerad på din maskin.

## Import Packages
I ditt Java‑projekt börjar du med att importera de nödvändiga paketen. Dessa importeringar ger dig åtkomst till AWT:s `Color`, `BasicStroke` och `Rectangle2D`‑klasser, samt Aspose.Page:s kärndokumenthanteringsklasser.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step‑by‑Step Guide to Draw Rectangle in Java PostScript

### Step 1: Set Paint for Filling Rectangle  
**How to set paint** – vi väljer en orange fyllningsfärg för den första rektangeln. Detta demonstrerar **set rectangle color java**-kapaciteten.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Set paint for filling rectangle
document.setPaint(Color.ORANGE);        
// Fill the first rectangle
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```

### Step 2: Set Paint for Stroking Rectangle  
**Set rectangle color java** – nu ändrar vi färgen till röd och definierar en konturbredd. Denna del av exemplet visar hur man **draw rectangle java** med en anpassad linjetjocklek.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### Step 3: Close Current Page and Save Document  
Efter ritning stänger vi sidan och sparar filen. Att stänga sidan säkerställer att alla ritkommandon skrivs ut till PostScript‑strömmen.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Common Use Cases for Rectangle Drawing
- **Fakturering eller kvittogenerering** – rektanglar fungerar som ramar eller markerar sektioner.  
- **Etikett‑skapande** – rita färgade rutor för att separera produktinformation.  
- **Enkla diagram** – använd fyllda rektanglar som stapeldiagramselement.  
- **Anpassade utskrivbara formulär** – kombinera rektanglar med text för att bygga formulärfält.  

## Common Issues & Tips
- **Filvägsfel** – se till att `dataDir` slutar med en filseparator (`/` eller `\\`).  
- **Licensundantag** – provversionen lägger till ett vattenmärke; skaffa en full licens för produktionsanvändning.  
- **Färgsynlighet** – vissa skrivare kan tolka vissa RGB‑värden annorlunda; testa först med en enkel svart rektangel.  
- **Minnesanvändning** – för stora dokument, överväg att spola ut strömmen efter varje sida (`document.closePage()`).  

## Frequently Asked Questions

**Q:** *Kan jag använda Aspose.Page för Java med andra programmeringsspråk?*  
A: Aspose.Page stödjer främst Java, men liknande bibliotek finns tillgängliga för andra språk.

**Q:** *Finns det en provversion av Aspose.Page för Java?*  
A: Ja, du kan utforska funktionerna i Aspose.Page för Java med den [free trial version](https://releases.aspose.com/).

**Q:** *Var kan jag hitta ytterligare hjälp och diskussioner?*  
A: Besök [Aspose.Page forum](https://forum.aspose.com/c/page/39) för att engagera dig med communityn och få hjälp.

**Q:** *Hur kan jag skaffa en tillfällig licens för Aspose.Page för Java?*  
A: Skaffa en tillfällig licens [here](https://purchase.aspose.com/temporary-license/).

**Q:** *Var kan jag köpa en licensierad version av Aspose.Page för Java?*  
A: Köp en licensierad version [here](https://purchase.aspose.com/buy).

**Additional Q&A**

**Q:** *Kan jag ändra rektangelns storlek dynamiskt?*  
A: Ja – ändra helt enkelt `Rectangle2D.Float(x, y, width, height)`-parametrarna innan du anropar `fill` eller `draw`.

**Q:** *Är det möjligt att lägga till text i rektangeln?*  
A: Absolut. Efter att ha ritat rektangeln, använd `document.drawString(...)` med önskad teckensnitt och position.

**Q:** *Stöder Aspose.Page andra former som cirklar eller polygoner?*  
A: Ja, API‑et erbjuder metoder som `drawEllipse` och `drawPolygon` för en mängd vektorgrafik.

## Conclusion
I den här guiden demonstrerade vi **how to draw rectangle** former i ett Java PostScript‑dokument, täckte **how to set paint**, och visade hur man **set rectangle color java** med Aspose.Page. Du har nu en solid grund för att skapa livfulla utskrivbara grafik, oavsett om du bygger fakturor, etiketter eller anpassade formulär. Känn dig fri att experimentera med olika färger, linjestilar och ytterligare AWT‑former för att berika ditt resultat.

---

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}