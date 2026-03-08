---
date: 2026-03-08
description: Lär dig hur du konverterar XPS till BMP i Java och ställer in BMP‑upplösning
  med Aspose.Page java‑bildkonverteringsbiblioteket. Denna guide täcker högkvalitativ
  utdata och minnesvänliga tips.
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: Konvertera XPS till BMP i Java – Ställ in upplösning för högkvalitativ utdata
url: /sv/java/xps-conversion/to-bmp/
weight: 10
---

 unchanged.

Make sure to keep all markdown formatting.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konvertera XPS till BMP i Java

## Introduktion
Välkommen till den här steg‑för‑steg‑guiden om hur du **konverterar XPS till BMP** i Java och ställer in upplösningen för optimal bildkvalitet med Aspose.Page. Oavsett om du bygger en utskriftspipeline, genererar miniatyrbilder eller behöver högupplösta grafik, ger kontroll av DPI dig flexibiliteten att möta alla krav.

## Snabba svar
- **Vilket bibliotek ska jag använda?** Aspose.Page for Java är det mest kompletta **java image conversion library** för XPS → BMP.  
- **Kan jag kontrollera bildkvaliteten?** Ja – använd `BmpSaveOptions` för att **set BMP resolution** och smoothing mode.  
- **Hur undviker jag OutOfMemoryError Java när jag bearbetar stora XPS‑filer?** Rendera sidor i partitioner eller öka JVM‑heapen (`-Xmx`).  
- **Behöver jag bara konvertera specifika sidor?** Absolut, `options.setPageNumbers()` låter dig välja exakta sidor.  
- **Vilka Java‑versioner stöds?** Alla moderna Java‑versioner (8 och senare) fungerar sömlöst.

## Vad är syftet med att ställa in upplösning?
Upplösning bestämmer antalet punkter per tum (DPI) i den genererade BMP‑bilden. En högre DPI ger skarpare bilder, vilket är avgörande för utskrift eller detaljerat grafiskt arbete. Genom att justera upplösningen får du full kontroll över utdata­kvaliteten i ditt **convert xps to bmp**‑arbetsflöde.

## Varför använda Aspose.Page för XPS → BMP‑konvertering?
- **High fidelity** – behåller vektor­kvaliteten i den ursprungliga XPS.  
- **Fine‑grained control** – du kan ställa in DPI, smoothing och till och med välja specifika sidor att konvertera.  
- **No external dependencies** – ren Java, inga inhemska bibliotek krävs.  
- **Scalable** – fungerar för enkelsidiga dokument såväl som stora flersidiga XPS‑filer.  

## Förutsättningar
Innan du dyker ner i konverteringsprocessen, se till att du har följande förutsättningar:
- **Java Development Environment** – Java 8 eller nyare installerat på din maskin.  
- **Aspose.Page for Java Library** – Ladda ner och inkludera Aspose.Page for Java‑biblioteket i ditt projekt. Du kan hitta biblioteket [here](https://releases.aspose.com/page/java/).  
- **Sample XPS File** – Förbered ett exempel‑XPS‑dokument som du vill konvertera till BMP.

## Importera paket
Inkludera de nödvändiga Aspose.Page‑paketen i din Java‑kod:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Hur man ställer in upplösning för XPS till BMP‑konvertering
Nedan är en kortfattad, numrerad genomgång som visar exakt var och hur du ställer in upplösningen, samt hur du **konverterar specifika sidor**.

### Steg 1: Ladda XPS‑dokument
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Steg 2: Initiera alternativ (upplösning & sidval)
```java
// Initialize options object with necessary parameters.
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);

// Primary setting – this is the **how to set resolution** part.
options.setResolution(300);               // 300 DPI for high‑quality output

// Optional: convert specific pages only (e.g., pages 1, 2, and 6)
options.setPageNumbers(new int[]{1, 2, 6});
```

### Steg 3: Skapa renderingsenhet
```java
// Create rendering device for BMP format
ImageDevice device = new ImageDevice();
```

### Steg 4: Spara dokument med alternativ
```java
// Save XPS document to BMP using options and device
document.save(device, options);
```

### Steg 5: Iterera genom renderade bilder och skriv filer
```java
// Iterate through document partitions
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoBMP" + "_" + (i + 1) + "_" + (j + 1) + ".bmp");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```

Upprepa dessa steg för eventuell ytterligare anpassning eller modifiering du kan behöva i konverteringsprocessen.

## Hur man undviker OutOfMemoryError Java vid konvertering av stora XPS‑filer
- **Process in partitions** – Exemplet renderar redan dokumentet i partitioner (`device.getResult()`), vilket minskar minnesbelastningen.  
- **Increase JVM heap** – Använd flaggan `-Xmx` (t.ex. `-Xmx2g`) för att tilldela mer minne för stora dokument.  
- **Dispose of resources** – Anropa `document.close()` när du är klar för att frigöra inhemska resurser.

## Vanliga problem och lösningar
| Issue | Solution |
|-------|----------|
| **Lågkvalitativ BMP‑utdata** | Verifiera att `options.setResolution()` är inställd på ett värde ≥ 300 DPI. |
| **Endast en del av dokumentet konverteras** | Se till att `options.setPageNumbers()` inkluderar alla önskade sidindex. |
| **OutOfMemoryError på stora XPS‑filer** | Processa dokumentet i mindre partitioner eller öka JVM‑heap‑storleken (`-Xmx`). |
| **Filen hittades inte** | Dubbelkolla `dataDir`‑sökvägen och att den inmatade XPS‑filen finns. |

## Vanliga frågor
### Q: Kan jag anpassa upplösningen på BMP‑bilderna?
A: Ja, du kan justera upplösningen genom att ändra parametern `options.setResolution()` i koden.

### Q: Är Aspose.Page kompatibel med olika Java‑versioner?
A: Ja, Aspose.Page stödjer ett brett spektrum av Java‑versioner. Se till att du har en kompatibel version installerad.

### Q: Hur kan jag konvertera XPS‑filer från ett specifikt sidintervall?
A: Använd metoden `options.setPageNumbers()` för att ange de sidnummer du vill konvertera.

### Q: Finns det andra utdataformat som stöds av Aspose.Page?
A: Ja, Aspose.Page stödjer olika utdataformat. Se dokumentationen för en fullständig lista.

### Q: Var kan jag hitta ytterligare hjälp eller support?
A: Besök [Aspose.Page Forum](https://forum.aspose.com/c/page/39) för community‑support och diskussioner.

---

**Senast uppdaterad:** 2026-03-08  
**Testat med:** Aspose.Page for Java 24.12  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}