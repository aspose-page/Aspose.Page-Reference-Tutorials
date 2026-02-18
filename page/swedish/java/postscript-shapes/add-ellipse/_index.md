---
date: 2026-02-18
description: Lär dig hur du ställer in färg och skapar en PostScript-ellips i Java
  med Aspose.Page. Den här guiden visar hur du fyller en ellips i Java, ritar ellipsens
  kontur och anger linjetjocklek.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Ställ in färg för att rita PostScript-ellips i Java
url: /sv/java/postscript-shapes/add-ellipse/
weight: 10
---

 -> "**Författare:** Aspose"

Then closing shortcodes.

Make sure to keep blank lines and formatting.

Let's assemble final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Set paint color to draw PostScript ellipse in Java

## Introduktion
Om du behöver **set paint color** när du ritar vektorgrafik ger Aspose.Page for Java‑biblioteket dig full kontroll över varje linje och fyllning. I den här handledningen kommer du att upptäcka hur du **set paint color**, **fill ellipse Java** och **draw ellipse outline** med ett enkelt steg‑för‑steg‑förfarande. I slutet kommer du att kunna lägga till högkvalitativa PostScript‑ellipser i fakturor, rapporter eller vilket utskriftsbart dokument som helst.

## Snabba svar
- **Vilket bibliotek är bäst för att rita PostScript‑grafik i Java?** Aspose.Page for Java.  
- **Kan jag fylla en ellips med en solid färg?** Ja – använd `document.setPaint(Color.YOUR_COLOR)` innan `fill`.  
- **Hur ritar jag bara konturen av en ellips?** Ställ in färg och pensel, och anropa sedan `document.draw(...)`.  
- **Behöver jag en licens för produktionsanvändning?** En kommersiell licens krävs; en tillfällig licens finns tillgänglig för testning.  
- **Vilken Java‑version stöds?** Alla Java 8+‑runtime‑miljöer fungerar med den aktuella Aspose.Page‑utgåvan.

## Vad är en PostScript‑ellips?
En PostScript‑ellips är en vektorgestalt som definieras av en avgränsande rektangel. Till skillnad från rasterbilder skalas den utan kvalitetsförlust, vilket gör den idealisk för högupplöst utskrift och PDF‑konvertering.

## Varför använda Aspose.Page för att skapa en PostScript‑ellips?
- **Full kontroll** över ritningsprimitiver (linjer, kurvor, ellipser).  
- **Cross‑platform** – fungerar på Windows, Linux och macOS.  
- **Inga externa beroenden** – ren Java‑API, ingen native‑kod.  
- **Enkel integration** med befintliga Java‑applikationer och byggverktyg.

## Förutsättningar
Innan du börjar, se till att du har:

1. En fungerande Java‑utvecklingsmiljö (JDK 8 eller senare).  
2. Aspose.Page for Java‑biblioteket tillagt i ditt projekt. Du kan ladda ner det **[här](https://releases.aspose.com/page/java/)**.  

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

## Hur man ställer in färg för en ellips
Att ställa in färgen är det första steget innan någon fyllnings‑ eller linjeoperation. Metoden `setPaint` bestämmer färgen som kommer att användas för nästa ritningskommando.

### Steg 1: Skapa PostScript‑dokumentet
Skapa ett output‑ström, konfigurera sidstorlek och instansiera ett `PsDocument`.

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

### Steg 2: Så fyller du en ellips – använd set paint color
För att **fill ellipse** måste du först anropa `setPaint` med önskad fyllningsfärg, och sedan anropa `fill` med en `Ellipse2D`‑instans.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Steg 3: Rita ellipsens kontur och ställ in linjetjocklek
Efter fyllning kan du ändra färgen till en annan, definiera en `BasicStroke` för att kontrollera linjebredden och rita ellipsens kontur.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Steg 4: Stäng och spara dokumentet
Slutför sidan och skriv PostScript‑filen till disk.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Du har nu en PostScript‑fil som innehåller två ellipser—en fylld med orange och en konturerad i rött. Känn dig fri att experimentera med olika koordinater, storlekar och färger för att matcha dina designbehov.

## Vanliga fallgropar och felsökning
- **Felaktig filsökväg** – Se till att `dataDir` slutar med en separator (`/` eller `\\`) som passar ditt OS.  
- **Saknad licens** – Utan en giltig licens körs biblioteket i utvärderingsläge och kan lägga till vattenstämplar.  
- **Färgen appliceras inte** – Kom ihåg att sätta `document.setPaint(...)` *före* varje `fill`‑ eller `draw`‑anrop; färginställningen kvarstår inte automatiskt mellan separata operationer.

## Vanliga frågor

**Q: Kan jag använda Aspose.Page for Java med andra Java‑bibliotek?**  
A: Ja, Aspose.Page for Java är utformat för att sömlöst integreras med andra Java‑bibliotek.

**Q: Hur kan jag få en tillfällig licens för Aspose.Page for Java?**  
A: Skaffa en tillfällig licens **[här](https://purchase.aspose.com/temporary-license/)** för teständamål.

**Q: Är Aspose.Page lämplig för kommersiella projekt?**  
A: Absolut! Besök **[här](https://purchase.aspose.com/buy)** för att utforska licensalternativ för kommersiell användning.

**Q: Var kan jag söka hjälp eller diskutera frågor relaterade till Aspose.Page?**  
A: Gå med i gemenskapen på **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** för diskussioner och hjälp.

**Q: Finns det några gratisresurser för att lära sig mer om Aspose.Page for Java?**  
A: Använd **[free trial](https://releases.aspose.com/)** och utforska exempel i dokumentationen.

## Slutsats
Aspose.Page for Java gör det enkelt att **set paint color**, **fill ellipse** och **draw ellipse outline**—oavsett om du behöver en enkel fylld form eller en komplex linjegrafik. Med stegen ovan kan du snabbt lägga till professionella vektorgrafik i vilket utskriftsbart dokument som helst. För djupare utforskning—såsom att kombinera flera former, applicera gradienter eller konvertera till PDF—se den officiella **[documentation](https://reference.aspose.com/page/java/)**.

---

**Senast uppdaterad:** 2026-02-18  
**Testad med:** Aspose.Page for Java 24.11  
**Författare:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}