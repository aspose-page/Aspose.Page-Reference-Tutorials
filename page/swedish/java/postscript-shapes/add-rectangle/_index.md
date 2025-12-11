---
date: 2025-12-11
description: Lär dig hur du ritar rektangelformer i Java PostScript med Aspose.Page.
  Denna steg‑för‑steg‑guide visar hur du ställer in färg, anger rektangelns färg i
  Java och skapar livfull grafik.
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

## Introduktion
Om du behöver **hur man ritar rektangel** former i en Java PostScript-fil, har du kommit till rätt ställe. I den här handledningen går vi igenom hur du använder Aspose.Page för Java för att lägga till färgglada rektanglar, kontrollera deras fyllning och linje, och spara resultatet som ett PostScript-dokument. Du kommer att se exakt **hur man ställer in färg**, hur man definierar rektangelns geometri, och varför detta tillvägagångssätt är idealiskt för att programatiskt generera utskrivbara grafik.

## Snabba svar
- **Vilket bibliotek krävs?** Aspose.Page för Java  
- **Kan jag ändra rektangelns färger?** Ja – använd `setPaint` med valfri `java.awt.Color`  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en licens krävs för produktion  
- **Vilken sidstorlek används i exemplet?** A4 (standard `PsSaveOptions`)  
- **Är koden kompatibel med Java 8+?** Absolut – den använder standard‑AWT‑klasser  

## Förutsättningar
Innan du dyker ner i handledningen, se till att du har följande förutsättningar på plats:
- Grundläggande förståelse för Java‑programmering.  
- Aspose.Page för Java‑biblioteket installerat. Om inte, ladda ner det från [Aspose.Page för Java-dokumentationen](https://reference.aspose.com/page/java/).  
- En Java‑utvecklingsmiljö installerad på din maskin.

## Importera paket
I ditt Java‑projekt, börja med att importera de nödvändiga paketen:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Hur man ritar rektangel i Java PostScript
Nedan är hela arbetsflödet uppdelat i tydliga steg. Varje steg innehåller en kort förklaring följt av den ursprungliga kodblocket (oförändrad).

### Steg 1: Ställ in färg för att fylla rektangel  
**Hur man ställer in färg** – vi väljer en orange fyllningsfärg för den första rektangeln.

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

### Steg 2: Ställ in färg för att rita rektangel  
**Ställ in rektangelns färg java** – nu ändrar vi färgen till röd och definierar en linjebredd.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### Steg 3: Stäng aktuell sida och spara dokumentet  
Efter ritning stänger vi sidan och sparar filen.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Varför använda Aspose.Page för rektangelgrafik?
- **Cross‑platform**: Genererar standard‑PostScript som fungerar på vilken skrivare som helst.  
- **Fin‑granulär kontroll**: Du kan sätta fyllningsfärger, linjefärger och linjebredd oberoende av varandra.  
- **Inga externa beroenden**: Använder endast de inbyggda AWT‑geometri‑klasserna.  

## Vanliga problem & tips
- **Filvägsfel** – se till att `dataDir` slutar med en filseparator (`/` eller `\\`).  
- **Licensundantag** – provversionen lägger till ett vattenmärke; skaffa en full licens för produktionsbruk.  
- **Färgvisibilitet** – vissa skrivare kan tolka vissa RGB‑värden annorlunda; testa först med en enkel svart rektangel.

## Slutsats
I den här guiden demonstrerade vi **hur man ritar rektangel** former i ett Java PostScript‑dokument, täckte **hur man ställer in färg**, och visade hur man **ställer in rektangelns färg java** med Aspose.Page. Känn dig fri att experimentera med olika former, färger och linjestilar för att skapa rik utskrivbar grafik för rapporter, fakturor eller anpassade utskrifter.

## Vanliga frågor

### Kan jag använda Aspose.Page för Java med andra programmeringsspråk?
Aspose.Page stödjer främst Java, men liknande bibliotek finns tillgängliga för andra språk.

### Finns en provversion av Aspose.Page för Java tillgänglig?
Ja, du kan utforska funktionerna i Aspose.Page för Java med den [gratis provversionen](https://releases.aspose.com/).

### Var kan jag hitta ytterligare hjälp och diskussioner?
Besök [Aspose.Page forum](https://forum.aspose.com/c/page/39) för att delta i communityn och få hjälp.

### Hur kan jag få en tillfällig licens för Aspose.Page för Java?
Skaffa en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

### Var kan jag köpa en licensierad version av Aspose.Page för Java?
Köp en licensierad version [här](https://purchase.aspose.com/buy).

**Ytterligare Q&A**

**Q:** *Kan jag ändra rektangelns storlek dynamiskt?*  
**A:** Ja – ändra helt enkelt `Rectangle2D.Float(x, y, width, height)`‑parametrarna innan du anropar `fill` eller `draw`.

**Q:** *Är det möjligt att lägga till text i rektangeln?*  
**A:** Absolut. Efter att ha ritat rektangeln, använd `document.drawString(...)` med önskat teckensnitt och position.

**Q:** *Stöder Aspose.Page andra former som cirklar eller polygoner?*  
**A:** Ja, API:et erbjuder metoder som `drawEllipse` och `drawPolygon` för en mängd vektorgrafik.

---

**Senast uppdaterad:** 2025-12-11  
**Testat med:** Aspose.Page för Java 24.12 (senaste)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}