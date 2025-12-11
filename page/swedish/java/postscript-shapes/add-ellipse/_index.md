---
date: 2025-12-11
description: Lär dig hur du skapar en PostScript‑ellips i Java med Aspose.Page. Denna
  steg‑för‑steg‑guide visar hur du fyller ellipsen med färg och ritar ellipsen med
  Java.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Hur man skapar en PostScript-ellips i Java med Aspose.Page
url: /sv/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar PostScript-ellips i Java med Aspose.Page

## Introduktion
Att programatiskt skapa en **PostScript ellipse** ger dig finjusterad kontroll över vektorgrafik i rapporter, fakturor eller vilket utskriftsbart dokument som helst. I den här handledningen kommer du att lära dig hur du **skapar PostScript ellipse**-former med Aspose.Page för Java-biblioteket, fyller en ellips med färg och ritar en ellipskontur. I slutet är du redo att bädda in anpassad grafik direkt i ditt PostScript‑utdata.

## Snabba svar
- **Vilket bibliotek är bäst för att rita PostScript‑grafik i Java?** Aspose.Page for Java.  
- **Kan jag fylla en ellips med en solid färg?** Ja – använd `document.setPaint(Color.YOUR_COLOR)` innan `fill`.  
- **Hur ritar jag bara konturen av en ellips?** Ställ in färg och pensel, och anropa sedan `document.draw(...)`.  
- **Behöver jag en licens för produktionsanvändning?** En kommersiell licens krävs; en tillfällig licens finns tillgänglig för testning.  
- **Vilken Java‑version stöds?** Alla Java 8+ runtime‑miljöer fungerar med den aktuella Aspose.Page‑utgåvan.

## Vad är en PostScript ellipse?
En PostScript ellipse är en vektorform definierad av en omgivande rektangel. Till skillnad från rasterbilder skalas den utan kvalitetsförlust, vilket gör den idealisk för högupplöst utskrift och PDF‑konvertering.

## Varför använda Aspose.Page för att skapa en PostScript ellipse?
- **Full kontroll** över ritningsprimitiver (linjer, kurvor, ellipser).  
- **Plattformsoberoende** – fungerar på Windows, Linux och macOS.  
- **Inga externa beroenden** – ren Java‑API, ingen native kod.  
- **Enkel integration** med befintliga Java‑applikationer och byggverktyg.

## Förutsättningar
Innan du börjar, se till att du har:

1. En fungerande Java‑utvecklingsmiljö (JDK 8 eller senare).  
2. Aspose.Page för Java‑biblioteket tillagt i ditt projekt. Du kan ladda ner det **[här](https://releases.aspose.com/page/java/)**.  

## Importera paket
I din Java‑källfil importerar du de klasser som krävs för att rita och spara PostScript‑innehåll.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Steg‑för‑steg‑guide

### Steg 1: Ställ in PostScript‑dokumentet
Skapa ett utdataflöde, konfigurera sidstorlek och skapa en `PsDocument`.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Steg 2: Fyll ellips med färg
Ställ in färgen till önskad fyllningsfärg och anropa `fill` med en `Ellipse2D`‑instans.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Steg 3: Konturera ellips med pensel
Byt färg till konturfärgen, definiera en `BasicStroke` för linjetjocklek och rita ellipsens kontur.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Steg 4: Stäng och spara dokumentet
Avsluta sidan och skriv PostScript‑filen till disk.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Du har nu en PostScript‑fil som innehåller två ellipser—en fylld med orange och en annan konturerad i rött. Känn dig fri att experimentera med olika koordinater, storlekar och färger för att matcha dina designbehov.

## Vanliga fallgropar och felsökning
- **Felaktig filsökväg** – Se till att `dataDir` slutar med en separator (`/` eller `\\`) som passar ditt OS.  
- **Saknad licens** – Utan en giltig licens körs biblioteket i evalueringsläge och kan lägga till vattenmärken.  
- **Färg inte tillämpad** – Kom ihåg att sätta `document.setPaint(...)` *innan* varje `fill`‑ eller `draw`‑anrop; färginställningen kvarstår inte automatiskt mellan separata operationer.

## Vanliga frågor

**Q: Kan jag använda Aspose.Page för Java med andra Java‑bibliotek?**  
A: Ja, Aspose.Page för Java är designat för att sömlöst integreras med andra Java‑bibliotek.

**Q: Hur kan jag få en tillfällig licens för Aspose.Page för Java?**  
A: Skaffa en tillfällig licens **[här](https://purchase.aspose.com/temporary-license/)** för teständamål.

**Q: Är Aspose.Page lämplig för kommersiella projekt?**  
A: Absolut! Besök **[här](https://purchase.aspose.com/buy)** för att utforska licensalternativ för kommersiell användning.

**Q: Var kan jag få hjälp eller diskutera frågor relaterade till Aspose.Page?**  
A: Gå med i communityn på **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** för diskussioner och hjälp.

**Q: Finns det några gratisresurser för att lära sig mer om Aspose.Page för Java?**  
A: Använd **[gratis provversion](https://releases.aspose.com/)** och utforska exempel i dokumentationen.

## Slutsats
Aspose.Page för Java gör det enkelt att **skapa PostScript ellipse**‑grafik, oavsett om du behöver en enkel fylld form eller en komplex konturerad linje. Med stegen ovan kan du snabbt lägga till professionell vektorgrafik i vilket utskriftsbart dokument som helst. För djupare utforskning—såsom att kombinera flera former, applicera gradienter eller konvertera till PDF—se den officiella **[dokumentationen](https://reference.aspose.com/page/java/)**.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose