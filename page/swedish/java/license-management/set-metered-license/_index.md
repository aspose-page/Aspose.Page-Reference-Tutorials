---
date: 2026-09-24
description: Lär dig hur du använder Aspose.Page för att konvertera EPS till PNG i
  Java, konfigurera en metered license och skriva PNG‑fil Java‑kod effektivt.
keywords:
- aspose page convert eps
- write png file java
- metered license java
- eps to png conversion
lastmod: 2026-09-24
linktitle: Ställ in metered license i Java
og_description: Aspose.Page konverterar EPS till PNG i Java med en metered license.
  Denna guide visar steg‑för‑steg hur du konfigurerar licensiering, renderar EPS och
  skriver PNG‑fil Java‑kod.
og_image_alt: Guide showing Aspose.Page Java converting EPS to PNG with metered license
og_title: Aspose.Page konverterar EPS till PNG i Java (metered license)
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  headline: Aspose.Page convert EPS to PNG in Java (metered license)
  type: TechArticle
- description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  name: Aspose.Page convert EPS to PNG in Java (metered license)
  steps:
  - name: initialize document and image format
    text: First, set the metered keys and define the output format (PNG). This establishes
      the foundation for the conversion. The `MeteredLicense` class stores your public
      and private keys, while `ImageSaveOptions` tells Aspose.Page to produce PNG
      output.
  - name: initialize PostScript input stream
    text: Open the EPS file you want to convert. The stream feeds the document into
      Aspose.Page. The `FileInputStream` reads the EPS file from disk, allowing the
      `Document` constructor to parse the PostScript data.
  - name: check document license
    text: Always verify that the metered license was applied correctly before processing.
      The `isLicensed()` method returns `true` only when the supplied keys are valid,
      preventing accidental usage of an unlicensed library.
  - name: initialize options and image device
    text: Create the options object that controls conversion settings and the device
      that will receive the rendered image. `ImageDevice` captures the rasterized
      output in memory, while `ImageSaveOptions` lets you tweak DPI, compression level,
      and color depth.
  - name: save EPS file as image
    text: This is the core **save EPS as PNG** call. The document is rendered into
      the image device using the options we configured. The `document.save(device,
      options)` method performs the rasterization in a single step.
  - name: get and save image bytes
    text: Extract the PNG bytes from the device and write them to a file on disk.
      This step demonstrates how to **write PNG file Java** safely. `Files.write(Paths.get("output.png"),
      device.getImagesBytes()[0])` persists the image without additional libraries.
  type: HowTo
- questions:
  - answer: Log into your Aspose account, navigate to the **Metered License** section,
      and copy the generated public and private keys.
    question: How do I obtain metered public and private keys?
  - answer: Aspose.Page offers a free trial with full functionality; production use
      requires a paid license. Download the trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is the Aspose.Page library free?
  - answer: Yes, a commercial license permits deployment in production environments.
      Purchase a license [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for commercial projects?
  - answer: The full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: Temporary licenses are provided through the Aspose portal [Aspose temporary
      license page](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image conversion
- metered licensing
title: Aspose.Page konverterar EPS till PNG i Java (metered license)
url: /sv/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page konvertera EPS till PNG i Java (metered license)

## Introduktion
Om du behöver **spara EPS som PNG** i en Java‑applikation samtidigt som licensieringen hålls enkel, är du på rätt plats. Den här handledningen guidar dig genom att konfigurera en **metered license** för Aspose.Page, ladda en EPS‑fil (Encapsulated PostScript) och konvertera den till en PNG‑bild. I slutet kommer du att förstå hur du **renderar EPS till PNG effektivt** och hur du **skriver PNG‑fil Java**‑kod som fungerar pålitligt i produktion.

## Snabba svar
- **Vad betyder “save EPS as PNG”?** Det konverterar en vektor‑EPS‑fil till en raster‑PNG‑bild, bevarar transparens och förlustfri komprimering.  
- **Varför använda en metered license?** Du betalar bara för de sidor du bearbetar, vilket är idealiskt för varierande arbetsbelastningar.  
- **Behöver jag en internetanslutning?** Nej, de metered‑nycklarna valideras lokalt på JVM.  
- **Vilken Java‑version krävs?** Java 8 eller högre stöds fullt ut.  
- **Hur lång tid tar installationen?** Ungefär 10 minuter för en grundläggande implementation.

## Vad är “save EPS to PNG”?
Att spara EPS som PNG konverterar ett vektor‑Encapsulated PostScript‑dokument till en raster‑PNG‑bild, bevarar transparens och erbjuder förlustfri komprimering. Denna transformation är användbar när du behöver webbklara grafik, miniatyrbilder eller utskrivbara förhandsgranskningar som kan visas i vilken webbläsare som helst utan att kräva en PostScript‑tolk.

## Varför rendera EPS till PNG med Aspose.Page?
Aspose.Page tillhandahåller ett rent Java‑API som rasteriserar EPS‑filer med hög noggrannhet, stöder över 50 utdataformat och erbjuder metered‑licensiering så att du bara betalar för det du konverterar. Biblioteket kan bearbeta dokument med flera hundra sidor utan att ladda hela filen i minnet, vilket ger snabb, exakt rendering på alla plattformar som stöder JVM.

## Förutsättningar
- Grundläggande erfarenhet av Java‑utveckling.  
- Aspose.Page‑biblioteket hämtat från [Aspose.Page Java download page](https://releases.aspose.com/page/java/).  
- Ett par metered offentliga och privata nycklar från ditt Aspose‑konto.  

## Importera paket
`import`‑satserna importerar de nödvändiga klasserna. Behåll detta block exakt som det visas så att koden kompilerar utan ändringar.

`java.io`‑klasserna hanterar filströmmar, medan Aspose.Page‑klasserna hanterar licensiering, dokumentladdning och bildrendering.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Hur man sparar EPS som PNG med Aspose.Page Java
Nedan följer en steg‑för‑steg‑guide som kombinerar licensiering, laddning, rendering och skrivning av den slutliga PNG‑filen.

### Direkt svar
Läs in din EPS‑fil, tillämpa en metered license, konfigurera `ImageSaveOptions` för PNG, rendera dokumentet till en `ImageDevice` och skriv slutligen den resulterande byte‑arrayen till disk. Denna sekvens slutför **save EPS as PNG**‑arbetsflödet med bara några rader Java‑kod.

### Steg 1: initiera dokument och bildformat
Först, ange de metered‑nycklarna och definiera utdataformatet (PNG). Detta etablerar grunden för konverteringen.

`MeteredLicense`‑klassen lagrar dina offentliga och privata nycklar, medan `ImageSaveOptions` instruerar Aspose.Page att producera PNG‑utdata.

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

### Steg 2: initiera PostScript‑indataström
Öppna EPS‑filen du vill konvertera. Strömmen matar dokumentet till Aspose.Page.

`FileInputStream` läser EPS‑filen från disk, vilket möjliggör för `Document`‑konstruktorn att tolka PostScript‑data.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### Steg 3: kontrollera dokumentlicens
Verifiera alltid att den metered‑licensen har tillämpats korrekt innan bearbetning.

`isLicensed()`‑metoden returnerar `true` endast när de angivna nycklarna är giltiga, vilket förhindrar oavsiktlig användning av ett olicensierat bibliotek.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### Steg 4: initiera alternativ och bildenhet
Skapa alternativobjektet som styr konverteringsinställningarna och enheten som kommer att ta emot den renderade bilden.

`ImageDevice` fångar den rasteriserade utdata i minnet, medan `ImageSaveOptions` låter dig justera DPI, komprimeringsnivå och färgdjup.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### Steg 5: spara EPS‑fil som bild
Detta är det centrala **save EPS as PNG**‑anropet. Dokumentet renderas till bild‑enheten med de alternativ vi konfigurerat.

`document.save(device, options)`‑metoden utför rasteriseringen i ett enda steg.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### Steg 6: hämta och spara bild‑byte
Extrahera PNG‑byten från enheten och skriv dem till en fil på disk. Detta steg visar hur man **write PNG file Java** säkert.

`Files.write(Paths.get("output.png"), device.getImagesBytes()[0])` sparar bilden utan ytterligare bibliotek.

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
| Problem | Varför det händer | Lösning |
|-------|----------------|-----|
| **Licens ej erkänd** | Nycklarna är felaktiga eller `setMeteredKey` anropas efter dokumentbehandling. | Dubbelkolla de offentliga/privata nyckelsträngarna och se till att `setMeteredKey` körs innan några Aspose.Page‑anrop. |
| **Utdatafilen är tom** | `device.getImagesBytes()` returnerade `null` eftersom EPS‑filen inte kunde parsas. | Verifiera att EPS‑filen är giltig och att `ImageSaveOptions` specificerar en canvas‑storlek som inte är noll. |
| **OutOfMemoryError på stora EPS** | Rendering av stora vektor‑filer förbrukar mycket heap‑minne. | Bearbeta sidor en åt gången eller öka JVM‑heapen (`-Xmx2g`). |

## Vanliga frågor

**Q: How do I obtain metered public and private keys?**  
Logga in på ditt Aspose‑konto, gå till avsnittet **Metered License** och kopiera de genererade offentliga och privata nycklarna.

**Q: Is the Aspose.Page library free?**  
Aspose.Page erbjuder en gratis provversion med full funktionalitet; produktionsanvändning kräver en betald licens. Ladda ner provversionen [Aspose trial download page](https://releases.aspose.com/).

**Q: Can I use Aspose.Page for commercial projects?**  
Ja, en kommersiell licens tillåter distribution i produktionsmiljöer. Köp en licens [Aspose purchase page](https://purchase.aspose.com/buy).

**Q: Where can I find additional documentation?**  
Den fullständiga API‑referensen finns på [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: How can I get a temporary license for evaluation?**  
Tillfälliga licenser tillhandahålls via Aspose‑portalen [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: What if I need to convert multi‑page EPS files?**  
Loopa igenom varje sida med `device.getImagesBytes()` och skriv varje byte‑array till en separat PNG‑fil.

**Q: Can I change the PNG quality or color depth?**  
Ja, konfigurera `ImageSaveOptions` (t.ex. `options.setCompressionLevel(9)`) innan du anropar `document.save(...)`.

---

**Senast uppdaterad:** 2026-09-24  
**Testad med:** Aspose.Page 24.12 för Java (senaste)  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man ställer in licens för Aspose.Page Java API – Licenshantering](/page/java/license-management/)
- [Konvertera PS till PNG med Aspose.Page Java API](/page/java/postscript-conversion/to-image/)
- [Ändra storlek på EPS med Aspose.Page – Java EPS-manipulation](/page/java/manipulation-eps/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}