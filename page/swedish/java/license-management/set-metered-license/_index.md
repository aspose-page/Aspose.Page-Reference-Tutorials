---
date: 2026-02-05
description: Lär dig hur du sparar EPS som PNG med Aspose.Page för Java samtidigt
  som du konfigurerar en mätlicens. Steg‑för‑steg‑guide med fullständigt kodexempel.
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: Spara EPS som PNG med Aspose.Page Java (Mätlicens)
url: /sv/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Spara EPS som PNG med Aspose.Page Java (Mätlicens)

## Introduktion
Om du behöver **save EPS as PNG** i en Java‑applikation och vill ha ett problemfritt sätt att hantera licensiering, är du på rätt plats. Denna handledning guidar dig genom att konfigurera en mätlicens för Aspose.Page, läsa in en PostScript‑ (EPS)‑fil och konvertera den till en PNG‑bild — med tydliga, lättförståeliga steg som du kan följa direkt. I slutet kommer du också att förstå hur du **render EPS to PNG** effektivt och **write PNG file Java**‑kod som fungerar i produktionsmiljöer.

## Snabba svar
- **Vad betyder “save EPS as PNG”?** Det konverterar en vektor‑EPS‑fil till en raster‑PNG‑bild.  
- **Varför använda en mätlicens?** Den låter dig betala endast för de sidor du bearbetar, perfekt för varierande arbetsbelastningar.  
- **Behöver jag en internetanslutning?** Nej, de mätlicensnycklarna valideras lokalt.  
- **Vilken Java‑version krävs?** Java 8 eller högre.  
- **Hur lång tid tar installationen?** Ungefär 10 minuter för en grundläggande implementation.  

## Vad är “save EPS as PNG”?
Att spara EPS som PNG omvandlar ett skalbart Encapsulated PostScript‑dokument till ett allmänt stödformat för bitmapar. PNG behåller transparens och erbjuder förlustfri komprimering, vilket gör det idealiskt för webb‑grafik, miniatyrbilder och utskrifts‑förhandsvisningar.

## Varför rendera EPS till PNG med Aspose.Page?
- **Pure Java API** – inga inhemska beroenden, så du kan köra det var som helst JVM‑stöd finns.  
- **High fidelity rendering** – vektorgrafik rasteriseras exakt, vilket bevarar linjekvaliteten.  
- **Metered licensing** – du betalar bara för det du konverterar, vilket gör kostnaderna förutsägbara.  
- **Multiple output options** – förutom PNG kan du även generera JPEG, TIFF och mer, vilket ger dig flexibilitet för olika projekt.

## Förutsättningar
Innan du börjar, säkerställ att du har:

- Grundläggande kunskap i Java‑programmering.  
- Aspose.Page‑biblioteket installerat – ladda ner det från [here](https://releases.aspose.com/page/java/).  
- Mätlicensens offentliga och privata nycklar, som du kan få via ditt Aspose‑konto.

## Importera paket
Först importerar du de klasser vi behöver. Behåll importblocket exakt som det visas så att koden kompilerar utan ändringar.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Så sparar du EPS som PNG med Aspose.Page Java
Nedan följer en steg‑för‑steg‑guide som kombinerar licensiering, inläsning, rendering och skrivning av den slutgiltiga PNG‑filen.

### Steg 1: Initiera dokument och bildformat
Här sätter vi de mätlicensnycklarna och definierar utdataformatet (PNG). Detta är grunden för **save EPS as PNG**‑operationen.

```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```

### Steg 2: Initiera PostScript‑inmatningsström
Öppna EPS‑filen du vill konvertera. Strömmen matar dokumentet till Aspose.Page.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### Steg 3: Kontrollera dokumentlicens
Verifiera alltid att den mätlicensen har tillämpats korrekt innan bearbetning.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### Steg 4: Initiera alternativ och bildenhet
Skapa alternativ‑objektet som styr konverteringsinställningarna och enheten som kommer att ta emot den renderade bilden.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### Steg 5: Spara EPS‑fil som bild
Detta är det centrala **save EPS as PNG**‑anropet. Dokumentet renderas till bild‑enheten med de alternativ vi konfigurerat.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### Steg 6: Hämta och spara bild‑bytes
Extrahera PNG‑byten från enheten och skriv dem till en fil på disk. Detta steg visar hur du **write PNG file Java** på ett säkert sätt.

```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```

## Vanliga problem och lösningar
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **Licens ej erkänd** | Keys are incorrect or placed in the wrong order. | Double‑check the public/private key strings and ensure `setMeteredKey` is called before any document processing. |
| **Utdatfilen är tom** | `device.getImagesBytes()` returned `null`. | Verify that the EPS file is valid and that the `ImageSaveOptions` are not set to a zero‑size canvas. |
| **OutOfMemoryError vid stor EPS** | Rendering large vector files consumes a lot of memory. | Process pages one‑at‑a‑time or increase JVM heap (`-Xmx2g`). |

## Vanliga frågor

**Q: Hur får jag de offentliga och privata mätlicensnycklarna?**  
A: Du kan få dessa nycklar via ditt Aspose‑konto.

**Q: Är Aspose.Page‑biblioteket gratis?**  
A: Aspose.Page erbjuder både gratis provversion och betalda versioner. Besök [here](https://releases.aspose.com/) för en gratis provversion.

**Q: Kan jag använda Aspose.Page för kommersiella projekt?**  
A: Ja, Aspose.Page erbjuder kommersiella licenser. Du kan köpa dem [here](https://purchase.aspose.com/buy).

**Q: Var kan jag hitta ytterligare dokumentation?**  
A: Se dokumentationen [here](https://reference.aspose.com/page/java/).

**Q: Hur kan jag få tillfälliga licenser?**  
A: Tillfälliga licenser kan erhållas [here](https://purchase.aspose.com/temporary-license/).

**Q: Vad händer om jag behöver konvertera fler‑sidiga EPS‑filer?**  
A: Loopa igenom varje sida med `device.getImagesBytes()` och skriv varje byte‑array till en separat PNG‑fil.

**Q: Kan jag ändra PNG‑kvaliteten eller färgdjupet?**  
A: Ja, konfigurera `ImageSaveOptions` (t.ex. `options.setCompressionLevel(...)`) innan du anropar `document.save(...)`.

---

**Senast uppdaterad:** 2025-12-03  
**Testat med:** Aspose.Page 24.12 for Java  
**Författare:** Aspose  

**Senast uppdaterad:** 2026-02-05  
**Testat med:** Aspose.Page 24.12 for Java (latest)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}