---
date: 2025-12-21
description: Lär dig hur du med Aspose.Page kan ändra XMP i EPS‑dokument med Java.
  Förbättra metadata snabbt med Aspose.Page för Java.
linktitle: Change Values in XMP using Java
second_title: Aspose.Page Java API
title: aspose.page modifiera xmp – Ändra värden i XMP med Java
url: /sv/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ändra värden i XMP med Java

## Introduktion
Om du behöver **aspose.page modify xmp** data i en EPS‑fil, har du kommit till rätt ställe. I den här handledningen går vi igenom de exakta stegen som krävs för att läsa, uppdatera och spara XMP‑värden (Extensible Metadata Platform) med Aspose.Page‑biblioteket för Java. När du är klar kan du anpassa dokumentmetadata — såsom skapare, titel och ändringsdatum — så att de matchar ditt projekts krav.

## Snabba svar
- **Vad gör “aspose.page modify xmp”?** Det låter dig läsa och skriva XMP‑metadata i EPS‑filer via Aspose.Page Java‑API.  
- **Vilken biblioteksversion krävs?** Vilken som helst nyare Aspose.Page för Java‑utgåva (API‑et är stabilt mellan versioner).  
- **Behöver jag en licens för att köra exemplet?** En gratis provversion fungerar för utvärdering; en kommersiell licens krävs för produktion.  
- **Kan jag ändra flera XMP‑fält samtidigt?** Ja — anropa `put` för varje fält innan du sparar dokumentet.  
- **Behövs tidszons‑hantering?** Att sätta standardtidszonen (t.ex. UTC) säkerställer konsekventa datumvärden.

## Vad är XMP och varför ändra det?
XMP (Extensible Metadata Platform) är ett standardiserat sätt att bädda in rik metadata direkt i filer som EPS, PDF och bilder. Att uppdatera XMP låter dig kontrollera hur dokument indexeras, visas och söks — avgörande för varumärkesbyggande, efterlevnad och arbetsflödesautomatisering.

## Varför använda Aspose.Page för Java?
- **Fullt utrustat API** – Ingen extern verktyg behövs; allt hanteras i‑process.  
- **Plattformsoberoende** – Fungerar på alla operativsystem som stödjer Java.  
- **Inga inhemska beroenden** – Ren Java‑implementation förenklar distribution.  
- **Robust stöd** – Hanterar både befintliga XMP‑block och skapar nya från PS‑kommentarer när de saknas.

## Förutsättningar
Innan vi påbörjar den här handledningen, se till att du har följande förutsättningar på plats:
1. **Java‑utvecklingsmiljö** – En JDK (8 eller senare) samt en IDE eller byggverktyg du föredrar.  
2. **Aspose.Page för Java‑bibliotek** – Ladda ner och installera Aspose.Page för Java‑biblioteket. Du hittar det nödvändiga paketet [här](https://releases.aspose.com/page/java/).

## Importera paket
Börja med att importera de nödvändiga paketen i ditt Java‑projekt. Dessa paket är avgörande för att interagera med och manipulera EPS‑dokument.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Steg 1: Hämta XMP‑metadata
Hämta XMP‑metadata från EPS‑dokumentet. Om EPS‑filen inte innehåller XMP‑metadata skapas en ny med värden från PS‑metadata‑kommentarer såsom %%Creator, %%CreateDate och %%Title.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## Steg 2: Ändra värdet för "ModifyDate"
```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## Steg 3: Ändra värdet för "Creator"
```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## Steg 4: Ändra värdet för "Title"
```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## Steg 5: Spara dokumentet med ändrad XMP‑metadata
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Vanliga problem och lösningar
- **Saknat XMP‑block** – API‑et skapar automatiskt ett från PS‑kommentarer, men du kan också manuellt instansiera `XmpMetadata` om så behövs.  
- **Tidszons‑mismatch** – Sätt alltid `TimeZone.setDefault` innan du skapar `Date`‑objektet för att undvika oväntade förskjutningar.  
- **Filåtkomstfel** – Kontrollera att in‑ och utdata‑sökvägarna är korrekta och att ditt program har läs‑/skrivrättigheter.

## Vanliga frågor

**Q: Hur kan jag hantera tidszonsaspekter när jag ändrar XMP‑värden?**  
A: Använd `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` för att säkerställa konsekventa tidszonsinställningar.

**Q: Kan jag ändra flera XMP‑värden i en enda operation?**  
A: Ja, genom att använda `put`‑metoden för varje önskat värde kan du modifiera flera XMP‑värden samtidigt.

**Q: Var kan jag hitta ytterligare dokumentation för Aspose.Page för Java?**  
A: Utforska den omfattande dokumentationen [här](https://reference.aspose.com/page/java/).

**Q: Finns det en gratis provversion av Aspose.Page för Java?**  
A: Ja, du kan komma åt den gratis provversionen [här](https://releases.aspose.com/).

**Q: Hur kan jag skaffa en tillfällig licens för Aspose.Page för Java?**  
A: Skaffa en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

**Q: Påverkar ändring av XMP det visuella innehållet i EPS?**  
A: Nej. XMP‑ändringar är endast metadata och ändrar inte de grafiska elementen i EPS‑filen.

**Q: Kan jag programatiskt läsa tillbaka de uppdaterade värdena för att verifiera ändringen?**  
A: Absolut — anropa bara `xmp.get("dc:creator")` (eller den relevanta nyckeln) efter att ha sparat och innan du stänger dokumentet.

## Slutsats
Grattis! Du har framgångsrikt gått igenom processen för att **aspose.page modify xmp** värden i EPS‑dokument med Aspose.Page för Java. Denna handledning har gett dig kunskapen att ändra metadata, så att dina dokument sömlöst matchar dina specifika krav.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Page for Java (latest release)  
**Author:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
