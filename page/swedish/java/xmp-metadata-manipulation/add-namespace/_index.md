---
title: Lägg till namnutrymme i XMP med Java
linktitle: Lägg till namnutrymme i XMP med Java
second_title: Aspose.Page Java API
description: Lås upp kraften i dokumentmanipulation med Aspose.Page för Java. Lär dig att lägga till XMP-namnområden utan ansträngning i den här omfattande guiden.
weight: 13
url: /sv/java/xmp-metadata-manipulation/add-namespace/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till namnutrymme i XMP med Java


## Introduktion

När det gäller dokumentmanipulation framstår Aspose.Page för Java som ett robust verktyg som erbjuder ett brett utbud av funktioner. En kraftfull funktion är möjligheten att lägga till namnområden i XMP (Extensible Metadata Platform) med hjälp av Java. Denna handledning guidar dig genom processen och delar upp den i enkla steg att följa.

## Förutsättningar

Innan du fördjupar dig i handledningen, se till att du har följande förutsättningar på plats:

-  Aspose.Page för Java: Se till att du har biblioteket installerat. Du kan ladda ner den[här](https://releases.aspose.com/page/java/).

- Java Development Environment: Konfigurera en Java-miljö på ditt system.

- Dokumentfil: Ha en EPS-fil med XMP-metadata. Om det inte innehåller XMP-metadata kommer biblioteket att skapa en baserad på PS-metadatakommentarer.

## Importera paket

För att börja, importera de nödvändiga paketen till ditt Java-projekt:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;

import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Steg 1: Hämta XMP-metadata

```java

// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";

// Initiera indata EPS-filström
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");

PsDocument document = new PsDocument(psStream);
// Skaffa XMP-metadata. Om EPS-filen inte innehåller XMP-metadata, skapa en ny fylld med värden från PS-metadatakommentarer (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Steg 2: Registrera nytt namnområde

```java
// Lägg till nytt XML-namnområde "http://www.some.org/schema/tmp#" med prefixet "tmp"
xmp.registerNamespaceURI("tmp", "http://www.some.org/schema/tmp#");
```

## Steg 3: Lägg till ny egendom

```java
// Lägg till den nya egenskapen "tmp:newKey" i det nya XML-namnområdet
xmp.put("tmp:newKey", new XmpValue("NewValue"));
```

## Steg 4: Spara dokument

```java
// Initiera utdata EPS-filström
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");

//Spara dokument med ändrade XMP-metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Steg 5: Stäng strömmar

```java
// Stäng ingångs EPS-ström
psStream.close();
```

Nu har du framgångsrikt lagt till ett namnområde i XMP med Aspose.Page för Java. Utforska gärna fler funktioner och frigör det här bibliotekets fulla potential.

## Slutsats

Aspose.Page för Java förenklar den komplexa uppgiften att manipulera XMP-metadata i EPS-filer. Genom att följa den här steg-för-steg-guiden har du skaffat dig en värdefull färdighet för att förbättra dina dokumentbehandlingsmöjligheter.

## Vanliga frågor

### Kan jag använda Aspose.Page för Java med andra programmeringsspråk?
Aspose.Page stöder i första hand Java, men det finns versioner tillgängliga för andra språk som .NET.

### Finns det en gratis provperiod?
 Ja, du kan utforska en gratis provperiod[här](https://releases.aspose.com/).

### Var kan jag hitta omfattande dokumentation?
 Se dokumentationen[här](https://reference.aspose.com/page/java/).

### Hur kan jag få en tillfällig licens?
 Du kan skaffa en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).

### Finns det gemenskapsforum för Aspose.Page?
 Ja, du kan engagera dig i samhället på[Aspose.Page forum](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
