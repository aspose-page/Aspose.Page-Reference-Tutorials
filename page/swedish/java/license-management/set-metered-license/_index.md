---
date: 2025-12-03
description: Lär dig hur du sparar EPS som PNG med Aspose.Page för Java samtidigt
  som du konfigurerar en mätlicens. Steg‑för‑steg‑guide med komplett kodexempel.
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

## Introduction
Om du behöver **spara EPS som PNG** i en Java‑applikation och vill ha ett problemfritt sätt att hantera licensiering, är du på rätt plats. Denna handledning guidar dig genom att konfigurera en mätlicens för Aspose.Page, läsa in en PostScript‑ (EPS)‑fil och konvertera den till en PNG‑bild — med tydliga, steg‑för‑steg‑instruktioner som du kan följa direkt.

## Quick Answers
- **Vad betyder “spara EPS som PNG”?** Det konverterar en vektor‑EPS‑fil till en raster‑PNG‑bild.  
- **Varför använda en mätlicens?** Den låter dig betala endast för de sidor du bearbetar, perfekt för varierande arbetsbelastning.  
- **Behöver jag en internetanslutning?** Nej, de mätade nycklarna valideras lokalt.  
- **Vilken Java‑version krävs?** Java 8 eller högre.  
- **Hur lång tid tar installationen?** Ungefär 10 minuter för en grundläggande implementation.

## What is “save EPS as PNG”?
Att spara EPS som PNG omvandlar ett skalbart Encapsulated PostScript‑dokument till ett allmänt stödformat för bitmapar. PNG behåller transparens och erbjuder förlustfri kompression, vilket gör det idealiskt för webb‑grafik, miniatyrer och utskrifts‑förhandsvisningar.

## Why use Aspose.Page for this task?
- **Ren Java‑API** – inga inhemska beroenden.  
- **Hög noggrannhet** – vektorgrafik renderas exakt.  
- **Mätlicensiering** – du betalar bara för det du konverterar.  
- **Stöd för flera utdataformat** – PNG, JPEG, TIFF osv.

## Prerequisites
Innan du börjar, se till att du har:

- Grundläggande kunskaper i Java‑programmering.  
- Aspose.Page‑biblioteket installerat – ladda ner det från [here](https://releases.aspose.com/page/java/).  
- Mätade offentliga och privata nycklar, som du kan få via ditt Aspose‑konto.

## Import Packages
Först, importera de klasser vi kommer att behöva. Behåll importblocket exakt som det visas så att koden kompilerar utan ändringar.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Step 1: Initialize Document and Image Format
Här sätter vi de mätade nycklarna och definierar utdataformatet (PNG). Detta är grunden för **spara EPS som PNG**‑operationen.

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

## Step 2: Initialize PostScript Input Stream
Öppna EPS‑filen du vill konvertera. Strömmen matar dokumentet till Aspose.Page.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

## Step 3: Check Document License
Verifiera alltid att den mätade licensen har tillämpats korrekt innan bearbetning.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

## Step 4: Initialize Options and Image Device
Skapa options‑objektet som styr konverteringsinställningarna och enheten som kommer att ta emot den renderade bilden.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

## Step 5: Save EPS File as Image
Detta är det centrala **spara EPS som PNG**‑anropet. Dokumentet renderas till bild‑enheten med de konfigurerade alternativen.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

## Step 6: Get and Save Image Bytes
Extrahera PNG‑byten från enheten och skriv dem till en fil på disk.

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

## Common Issues and Solutions
| Problem | Varför det händer | Lösning |
|---------|-------------------|---------|
| **Licensen känns inte igen** | Nycklarna är felaktiga eller placerade i fel ordning. | Dubbelkolla de offentliga/privata nyckelsträngarna och säkerställ att `setMeteredKey` anropas innan någon dokumentbearbetning. |
| **Utdatafil är tom** | `device.getImagesBytes()` returnerade `null`. | Verifiera att EPS‑filen är giltig och att `ImageSaveOptions` inte är inställda på en canvas med nollstorlek. |
| **OutOfMemoryError vid stora EPS** | Rendering av stora vektor‑filer förbrukar mycket minne. | Bearbeta sidor en åt gången eller öka JVM‑heap (`-Xmx2g`). |

## Frequently Asked Questions

**Q: Hur får jag de mätade offentliga och privata nycklarna?**  
A: Du kan få dessa nycklar via ditt Aspose‑konto.

**Q: Är Aspose.Page‑biblioteket gratis?**  
A: Aspose.Page erbjuder både gratis provversion och betalda versioner. Besök [here](https://releases.aspose.com/) för en gratis provversion.

**Q: Kan jag använda Aspose.Page i kommersiella projekt?**  
A: Ja, Aspose.Page erbjuder kommersiella licenser. Du kan köpa dem [here](https://purchase.aspose.com/buy).

**Q: Var kan jag hitta ytterligare dokumentation?**  
A: Se dokumentationen [here](https://reference.aspose.com/page/java/).

**Q: Hur kan jag få tillfälliga licenser?**  
A: Tillfälliga licenser kan erhållas [here](https://purchase.aspose.com/temporary-license/).

---

**Senast uppdaterad:** 2025-12-03  
**Testad med:** Aspose.Page 24.12 för Java  
**Författare:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}