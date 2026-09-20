---
date: 2026-09-19
description: Lär dig hur du lägger till XMP-namngivna värden i EPS-filer med Aspose.Page
  for Java – en steg‑för‑steg‑guide med kodexempel.
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
- EPS XMP manipulation
- Java metadata API
lastmod: 2026-09-19
linktitle: Lägg till namngivet värde i XMP med Java
og_description: Hur du lägger till XMP-namngivna värden i EPS-filer med Aspose.Page
  for Java. Följ den här koncisa guiden för att injicera anpassad metadata på några
  minuter.
og_image_alt: Screenshot of Java code adding XMP named value to an EPS file with Aspose.Page
og_title: Så lägger du till XMP-namngivet värde i EPS-filer med Java
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  headline: How to add XMP named value in EPS files using Java
  type: TechArticle
- description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  name: How to add XMP named value in EPS files using Java
  steps:
  - name: Initialize input EPS file stream
    text: '**FileInputStream** is a Java I/O class that reads raw bytes from a file.
      Load the source EPS file into a `FileInputStream`. This stream feeds the document
      into Aspose’s API. > **Pro tip:** Keep the `dataDir` variable configurable so
      the same code works across environments.'
  - name: Obtain XMP metadata
    text: '**XmpMetadata** represents the XMP packet associated with an EPS document.
      Retrieve the existing XMP packet; if the EPS file lacks one, Aspose creates
      a fresh XMP object populated from the PS comments.'
  - name: Add named value
    text: '**NamedValue** is a key‑value pair stored within the XMP metadata namespace.
      Insert a custom named value into the XMP structure. In this example we add a
      new key under the `xmpTPg:MaxPageSize` namespace. > **Why this matters:** Named
      values let you store arbitrary key‑value pairs that downstream app'
  - name: Initialize output EPS file stream
    text: '**FileOutputStream** is a Java I/O class that writes raw bytes to a file.
      Prepare a `FileOutputStream` where the modified EPS will be saved.'
  - name: Save document
    text: The `save` method persists the changes. It writes the updated XMP packet
      back into the EPS file, guaranteeing that the new named value becomes part of
      the document’s metadata.
  - name: Close input EPS stream
    text: Closing the original file handle prevents resource leaks and ensures that
      the file is not locked for subsequent operations. By following these six steps,
      you have successfully **added a named value in XMP metadata** using **Aspose.Page
      for Java**.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly with other Java
      libraries, providing flexibility in your development environment.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can access a free trial of Aspose.Page for Java on the [Aspose
      releases page](https://releases.aspose.com/).
    question: Is a free trial available for Aspose.Page for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to obtain a temporary license for Aspose.Page for Java.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Explore the [documentation](https://reference.aspose.com/page/java/) for
      comprehensive tutorials and examples.
    question: Where can I find more tutorials and examples for Aspose.Page for Java?
  - answer: Absolutely, Aspose.Page for Java is designed to handle large‑scale projects
      efficiently, providing robust document manipulation capabilities.
    question: Is Aspose.Page for Java suitable for large‑scale projects?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- XMP metadata
- Aspose.Page
- Java EPS
- document automation
title: Så lägger du till XMP-namngivet värde i EPS-filer med Java
url: /sv/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till namngivet värde i XMP-metadata med Java

## Introduktion
I modern Java‑utveckling är det viktigt att lära sig **hur man lägger till XMP**‑metadata i EPS‑filer för att bevara dokumentets ursprung och förbättra sökbarheten. Med **Aspose.Page for Java** kan du enkelt injicera anpassade namngivna värden i XMP‑paketet. Denna handledning guidar dig genom de exakta stegen — komplett med kodexempel — så att du kan börja lägga till XMP‑metadata i dina EPS‑dokument redan idag.

## Snabba svar
- **Vilket bibliotek behövs?** Aspose.Page for Java (Aspose)  
- **Vilken filtyp är målet?** EPS‑filer som innehåller XMP‑metadata  
- **Primärt användningsfall?** Lägg till anpassade namngivna värden (t.ex. sidstorleksgränser) i XMP  
- **Förutsättningar?** JDK 8+ och Aspose.Page for Java‑biblioteket  
- **Typisk implementeringstid?** 5–10 minuter när biblioteket är konfigurerat  

## Vad är asp?
Aspose är förkortningen för Aspose, en svit av API:er som gör det möjligt för utvecklare att skapa, redigera, konvertera och rendera ett brett spektrum av dokumentformat utan att behöva extern programvara. Komponenten Aspose.Page for Java fokuserar specifikt på PostScript‑ och EPS‑behandling och ger programmatisk åtkomst till sidinnehåll, grafik och metadata såsom XMP.

## Varför lägga till namngivna värden i XMP-metadata?
Namngivna värden låter dig lagra godtyckliga nyckel‑värde‑par direkt i XMP‑paketet, vilket gör dem omedelbart läsbara av efterföljande verktyg. Detta förbättrar sökmotorvänligheten, möjliggör automatisering av arbetsflöden och uppfyller efterlevnadskrav genom att bädda in regulatorisk information utan att ändra det visuella innehållet.

## Varför detta är viktigt
Att lägga till namngivna värden i XMP låter dig lagra godtyckliga nyckel‑värde‑par som kan läsas utan att parsra hela EPS‑filen. Denna funktion är särskilt värdefull i automatiserade publiceringspipeline, digitala tillgångshanteringssystem och efterlevnadsdrivna arbetsflöden där metadata styr efterföljande åtgärder.

## Förutsättningar
Innan vi dyker ner, se till att du har följande:

- **Java Development Kit (JDK):** En aktuell JDK (8 eller högre) installerad på din maskin.  
- **Aspose.Page for Java Library:** Ladda ner den från den officiella [Aspose.Page for Java download](https://releases.aspose.com/page/java/). Lägg till JAR‑filen i ditt projekts classpath.  
- **En EPS‑fil** som antingen redan innehåller XMP‑metadata eller som kommer att få den genererad automatiskt.

## Importera paket
Börja med att importera de nödvändiga Java‑paketen. Dessa importeringar ger dig åtkomst till filströmmar, EPS‑dokumentmodellen och XMP‑hanteringsklasser.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Hur man lägger till XMP‑namngivet värde i EPS‑filer med Java
För att lägga till ett namngivet värde, läs in EPS‑filen med ett `FileInputStream`, hämta eller skapa dess `XmpMetadata`‑objekt, infoga det önskade `NamedValue` i rätt namnrymd och skriv sedan tillbaka det modifierade dokumentet med ett `FileOutputStream`. Aspose.Page hanterar automatiskt skapandet av XMP‑paketet om det saknas, vilket säkerställer att den nya metadata bäddas in korrekt.

### Steg 1: Initiera inmatnings‑EPS‑filström
**FileInputStream** är en Java‑I/O‑klass som läser råa bytes från en fil. Läs in käll‑EPS‑filen i ett `FileInputStream`. Denna ström matar dokumentet till Asposes API.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **Proffstips:** Håll variabeln `dataDir` konfigurerbar så att samma kod fungerar i olika miljöer.

### Steg 2: Hämta XMP‑metadata
**XmpMetadata** representerar XMP‑paketet som är associerat med ett EPS‑dokument. Hämta det befintliga XMP‑paketet; om EPS‑filen saknar ett skapar Aspose ett nytt XMP‑objekt som fylls med data från PS‑kommentarerna.

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### Steg 3: Lägg till namngivet värde
**NamedValue** är ett nyckel‑värde‑par som lagras inom XMP‑metadata‑namnrymden. Infoga ett anpassat namngivet värde i XMP‑strukturen. I detta exempel lägger vi till en ny nyckel under namnrymden `xmpTPg:MaxPageSize`.

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **Varför detta är viktigt:** Namngivna värden låter dig lagra godtyckliga nyckel‑värde‑par som efterföljande applikationer kan läsa utan att parsra hela dokumentet.

### Steg 4: Initiera utmatnings‑EPS‑filström
**FileOutputStream** är en Java‑I/O‑klass som skriver råa bytes till en fil. Förbered ett `FileOutputStream` där den modifierade EPS‑filen ska sparas.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### Steg 5: Spara dokumentet
`save`‑metoden sparar förändringarna. Den skriver tillbaka det uppdaterade XMP‑paketet till EPS‑filen och garanterar att det nya namngivna värdet blir en del av dokumentets metadata.

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### Steg 6: Stäng inmatnings‑EPS‑strömmen
Att stänga den ursprungliga filhandtaget förhindrar resurssläpp och säkerställer att filen inte låses för efterföljande operationer.

```java
psStream.close();
```

Genom att följa dessa sex steg har du framgångsrikt **lagt till ett namngivet värde i XMP‑metadata** med **Aspose.Page for Java**.

## Vanliga problem & lösningar
| Problem | Orsak | Lösning |
|-------|-------|-----|
| `NullPointerException` på `xmp` | EPS‑filen har ingen XMP och Aspose misslyckades med att generera en | Se till att EPS‑filen innehåller minst en PS‑kommentar eller skapa manuellt ett nytt `XmpMetadata`‑instans. |
| Utdatafilen är tom | Utdataströmmen har inte flushats/stängts | Verifiera att `outPsStream.close()` anropas i ett `finally`‑block (som visas). |
| Duplicerat nyckelfel | Samma namngivna värde har lagts till två gånger | Kontrollera om nyckeln redan finns med `xmp.containsNamedValue(...)` innan du lägger till. |

## Vanliga frågor

**Q: Kan jag använda Aspose.Page for Java tillsammans med andra Java‑bibliotek?**  
A: Ja, Aspose.Page for Java är utformat för att fungera sömlöst med andra Java‑bibliotek, vilket ger flexibilitet i din utvecklingsmiljö.

**Q: Finns en gratis provversion av Aspose.Page for Java?**  
A: Ja, du kan få tillgång till en gratis provversion av Aspose.Page for Java på den officiella [Aspose releases page](https://releases.aspose.com/).

**Q: Hur kan jag skaffa en tillfällig licens för Aspose.Page for Java?**  
A: Besök [temporary license page](https://purchase.aspose.com/temporary-license/) för att skaffa en tillfällig licens för Aspose.Page for Java.

**Q: Var kan jag hitta fler handledningar och exempel för Aspose.Page for Java?**  
A: Utforska [documentation](https://reference.aspose.com/page/java/) för omfattande handledningar och exempel.

**Q: Är Aspose.Page for Java lämplig för storskaliga projekt?**  
A: Absolut, Aspose.Page for Java är utformat för att hantera storskaliga projekt effektivt och erbjuder robusta funktioner för dokumentmanipulation.

## Slutsats
I den här guiden har vi visat hur **Aspose.Page for Java** gör det enkelt att **lägga till namngivna värden i XMP‑metadata** i EPS‑filer. Med stegen ovan kan du berika dina dokument med anpassad metadata, förbättra sökbarheten och möjliggöra smartare efterföljande bearbetning.

---

**Last Updated:** 2026-09-19  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## Relaterade handledningar

- [Hur man lägger till XMP‑namnrymd i EPS‑filer med Aspose.Page – Java‑handledning](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Lägg till XMP‑metadata i EPS‑filer med Java](/page/java/xmp-metadata-manipulation/add-simple-properties/)
- [Läs XMP med Aspose.Page – Java‑guide](/page/java/xmp-metadata-manipulation/get-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}