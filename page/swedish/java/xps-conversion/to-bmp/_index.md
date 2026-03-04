---
date: 2025-12-21
description: Lär dig hur du ställer in upplösning när du konverterar XPS till BMP
  i Java med Aspose.Page. Denna Java‑bildkonverteringsguide säkerställer högkvalitativa
  resultat.
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: Hur man ställer in upplösning vid konvertering av XPS till BMP i Java
url: /sv/java/xps-conversion/to-bmp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konvertera XPS till BMP i Java

## Introduktion
Välkommen till denna steg‑för‑steg‑guide om **hur man ställer in upplösning** när man konverterar XPS (XML Paper Specification)-filer till BMP (Bitmap)-format i Java med Aspose.Page. Aspose.Page för Java är ett kraftfullt bibliotek som erbjuder omfattande funktioner för att arbeta med XPS-dokument. I den här handledningen kommer vi att gå igenom processen för att enkelt konvertera XPS-filer till BMP-bilder.

## Snabba svar
- **Vilket bibliotek bör jag använda?** Aspose.Page för Java tillhandahåller de mest kompletta XPS → BMP-konverteringsfunktionerna.  
- **Kan jag kontrollera bildkvaliteten?** Ja – använd `BmpSaveOptions` för att ställa in upplösning och utjämningsläge.  
- **Behöver jag bara konvertera specifika sidor?** Absolut, `options.setPageNumbers()` låter dig välja exakt vilka sidor.  
- **Är detta en riktig java-bildkonvertering?** API:et renderar XPS-sidor direkt till bitmapdata, så inga mellanformat behövs.  
- **Vilken Java-version stöds?** Alla moderna Java-versioner (8 och senare) är kompatibla.

## Vad är syftet med att ställa in upplösning?
Upplösning bestämmer antalet punkter per tum (DPI) i den genererade BMP-bilden. En högre DPI ger skarpare bilder, vilket är avgörande för utskrift eller detaljerat grafiskt arbete. Genom att justera upplösning får du full kontroll över utdata kvaliteten i ditt **java convert xps**‑arbetsflöde.

## Varför använda Aspose.Page för XPS → BMP-konvertering?
- **Hög trohet** – bevarar vektor kvaliteten i den ursprungliga XPS.  
- **Fin‑granulär kontroll** – du kan ställa in DPI, utjämning och till och med välja specifika sidor att konvertera.  
- **Inga externa beroenden** – ren Java, inga inhemska bibliotek krävs.  
- **Skalbar** – fungerar för enkelsidiga dokument såväl som stora flersidiga XPS-filer.

## Förutsättningar
Innan du dyker ner i konverteringsprocessen, se till att du har följande förutsättningar:
- **Java-utvecklingsmiljö** – Java 8 eller nyare installerat på din maskin.  
- **Aspose.Page för Java-bibliotek** – Ladda ner och inkludera Aspose.Page för Java-biblioteket i ditt projekt. Du kan hitta biblioteket [här](https://releases.aspose.com/page/java/).  
- **Exempel XPS-fil** – Förbered ett exempel XPS-dokument som du vill konvertera till BMP.

## Importera paket
Inkludera de nödvändiga Aspose.Page-paketen i din Java-kod:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Hur man ställer in upplösning för XPS till BMP-konvertering
Nedan följer en kortfattad, numrerad genomgång som visar exakt var och hur man ställer in upplösning, samt hur man **konverterar specifika sidor**.

### Steg 1: Ladda XPS-dokument
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

Upprepa dessa steg för eventuella ytterligare anpassningar eller ändringar du kan behöva i konverteringsprocessen.

## Vanliga problem och lösningar
| Issue | Solution |
|-------|----------|
| **Lågkvalitativ BMP-utdata** | Verifiera att `options.setResolution()` är inställd på ett värde ≥ 300 DPI. |
| **Endast en del av dokumentet konverteras** | Se till att `options.setPageNumbers()` inkluderar alla önskade sidindex. |
| **OutOfMemoryError på stora XPS-filer** | Bearbeta dokumentet i mindre partitioner eller öka JVM:s heap-storlek (`-Xmx`). |
| **Fil ej hittad** | Dubbelkolla `dataDir`-sökvägen och att den angivna XPS-filen finns. |

## Vanliga frågor
### Q: Kan jag anpassa upplösningen på BMP-bilderna?
A: Ja, du kan justera upplösningen genom att ändra parametern `options.setResolution()` i koden.

### Q: Är Aspose.Page kompatibel med olika Java-versioner?
A: Ja, Aspose.Page stödjer ett brett spektrum av Java-versioner. Se till att du har en kompatibel version installerad.

### Q: Hur kan jag konvertera XPS-filer från ett specifikt sidintervall?
A: Använd metoden `options.setPageNumbers()` för att ange de sidnummer du vill konvertera.

### Q: Finns det andra utdataformat som stöds av Aspose.Page?
A: Ja, Aspose.Page stödjer olika utdataformat. Se dokumentationen för en komplett lista.

### Q: Var kan jag hitta ytterligare hjälp eller support?
A: Besök [Aspose.Page Forum](https://forum.aspose.com/c/page/39) för community-support och diskussioner.

---

**Senast uppdaterad:** 2025-12-21  
**Testad med:** Aspose.Page for Java 24.12  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}