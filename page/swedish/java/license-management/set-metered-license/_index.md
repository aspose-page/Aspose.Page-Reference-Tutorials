---
title: Enkel integrering av mätlicens med Aspose.Page Java
linktitle: Ställ in mätlicens i Java
second_title: Aspose.Page Java API
description: Utforska den sömlösa integrationen av Aspose.Page med Java. Konfigurera mätlicenser utan ansträngning och förbättra dina dokumentbehandlingsmöjligheter.
weight: 10
url: /sv/java/license-management/set-metered-license/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Enkel integrering av mätlicens med Aspose.Page Java

## Introduktion
Välkommen till vår omfattande guide om hur du ställer in en mätlicens i Java med Aspose.Page. Om du vill förbättra dina dokumentbehandlingsmöjligheter och säkerställa sömlös integration med Aspose.Page, är du på rätt plats. I den här handledningen går vi igenom processen och delar upp varje steg i lättsmälta bitar.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
- Grundläggande kunskaper i Java-programmering.
-  Aspose.Page-biblioteket installerat. Du kan ladda ner den från[här](https://releases.aspose.com/page/java/).
- Uppmätta offentliga och privata nycklar, som du kan få via ditt Aspose-konto.
## Importera paket
Låt oss börja med att importera de nödvändiga paketen för vårt Java-program. Se till att du har Aspose.Page-biblioteket integrerat i ditt projekt.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;

```
## Steg 1: Initiera dokument- och bildformat
Det första steget är att ställa in dokumentet och definiera önskat bildformat.
```java
// ställ in mätta offentliga och privata nycklar
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Gå till egenskapen setMeteredKey och skicka offentliga och privata nycklar som parametrar
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```
## Steg 2: Initiera PostScript Input Stream
I det här steget initierar vi PostScript-indataströmmen för bearbetning.
```java
// Initiera PostScript-indataström
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```
## Steg 3: Kontrollera dokumentlicens
Innan du fortsätter är det viktigt att kontrollera om dokumentet är korrekt licensierat.
```java
// Kontrollera om dokumentet är licensierat
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```
## Steg 4: Initiera alternativ och bildenhet
Låt oss nu initiera alternativ och bildenheten med standardparametrar.
```java
// Initiera alternativobjekt med standardparametrar.
ImageSaveOptions options = new ImageSaveOptions();
// Initiera ImageDevice-objekt med standardparametrar.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```
## Steg 5: Spara EPS-fil som bild
Spara EPS-filen som en bild med de definierade alternativen och enheten.
```java
// Spara EPS-fil som bild
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```
## Steg 6: Hämta och spara bildbytes
Hämta bildbytes och spara dem i en fil.
```java
// Få bilder bytes. En byte array för en sida. I vårt fall har vi en sida.
byte[][] imagesBytes = device.getImagesBytes();
// Spara bildbytes till fil
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```
## Slutsats
Grattis! Du har framgångsrikt konfigurerat en uppmätt licens i Java med Aspose.Page. Denna handledning gav en steg-för-steg-guide för att säkerställa en smidig integrationsprocess.
## Vanliga frågor
### F: Hur får jag uppmätt offentliga och privata nycklar?
Du kan få dessa nycklar via ditt Aspose-konto.
### F: Är Aspose.Page-biblioteket gratis?
 Aspose.Page erbjuder både gratis provversioner och betalversioner. Besök[här](https://releases.aspose.com/) för en gratis provperiod.
### F: Kan jag använda Aspose.Page för kommersiella projekt?
 Ja, Aspose.Page erbjuder kommersiella licenser. Du kan köpa dem[här](https://purchase.aspose.com/buy).
### F: Var kan jag hitta ytterligare dokumentation?
 Se dokumentationen[här](https://reference.aspose.com/page/java/).
### F: Hur kan jag få tillfälliga licenser?
 Tillfälliga licenser kan erhållas[här](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
