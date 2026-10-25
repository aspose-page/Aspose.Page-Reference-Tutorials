---
date: 2026-10-25
description: Lär dig hur du anger anpassad sidstorlek och lägger till sidor i Java‑PostScript‑dokument
  med Aspose.Page. Följ vår steg‑för‑steg‑guide för smidig dokumentmanipulation.
keywords:
- set custom page size
- Aspose.Page Java
- PostScript page manipulation
- add pages PostScript
lastmod: 2026-10-25
linktitle: Lägga till sidor i PostScript
og_description: Lär dig hur du anger anpassad sidstorlek i PostScript med Aspose.Page
  för Java. Följ steg‑för‑steg‑instruktioner för att lägga till sidor, ange dimensioner
  och spara dokumentet effektivt.
og_image_alt: Aspose.Page Java tutorial showing how to set custom page size in a PostScript
  document
og_title: Ange anpassad sidstorlek i PostScript med Aspose.Page Java
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to set custom page size and add pages to Java PostScript
    documents using Aspose.Page. Follow our step‑by‑step guide for seamless document
    manipulation.
  headline: Aspose.Page Java Tutorial – set custom page size while Adding Pages in
    PostScript
  type: TechArticle
- questions:
  - answer: Yes—you can open pages with custom dimensions using `document.openPage(width,
      height)`.
    question: Can I set different page sizes for each page?
  - answer: A valid Aspose.Page license is required for non‑evaluation deployments.
    question: Do I need a license for production use?
  - answer: The library works with Java 8 and newer.
    question: Which Java versions are supported?
  - answer: Document instances are not thread‑safe; create a separate `PsDocument`
      per thread.
    question: Is the API thread‑safe?
  - answer: Aspose.Page handles multi‑megabyte files efficiently; memory usage scales
      with content, not page count.
    question: How large can a PostScript file be?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java PostScript
- custom page size
- add pages
- document generation
title: Aspose.Page Java‑handledning – ange anpassad sidstorlek när du lägger till
  sidor i PostScript
url: /sv/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java‑handledning – ange anpassad sidstorlek när du lägger till sidor i PostScript

## Introduktion
I moderna Java‑applikationer är det ofta nödvändigt att **ange anpassad sidstorlek** för PostScript‑utdata – oavsett om du genererar fakturor, biljetter eller anpassad grafik. Denna handledning visar hur du anger anpassad sidstorlek för varje sida, lägger till flera sidor och genererar en PostScript‑fil som matchar dina exakta layoutbehov. Du får ett komplett, körbart exempel som du kan släppa in i vilket Java 8+‑projekt som helst.

## Snabba svar
- **Kan jag ange olika sidstorlekar för varje sida?** Ja – du kan öppna sidor med anpassade dimensioner med `document.openPage(width, height)`.  
- **Behöver jag en licens för produktionsanvändning?** En giltig Aspose.Page‑licens krävs för icke‑utvärderingsdistributioner.  
- **Vilka Java‑versioner stöds?** Biblioteket fungerar med Java 8 och nyare.  
- **Är API‑et trådsäkert?** Dokumentinstanser är inte trådsäkra; skapa ett separat `PsDocument` per tråd.  
- **Hur stor kan en PostScript‑fil vara?** Aspose.Page hanterar multi‑megabyte‑filer effektivt; minnesanvändningen skalar med innehållet, inte antalet sidor.  
- **Kan jag använda overload‑metoden för bredd/höjd?** Absolut – `openPage(double width, double height)` låter dig ange valfria dimensioner i punkter.  

## Förutsättningar
Innan vi dyker ner, se till att du har:

- Grundläggande kunskaper i Java‑programmering.  
- Aspose.Page för Java tillagt i ditt projekt (Maven/Gradle eller manuellt JAR).  
- En Java‑utvecklingsmiljö (IDE, JDK 8+).  

## Importera paket
Följande klasser krävs: `FileOutputStream` för att skriva filer, `PsDocument` för att skapa PostScript‑dokument och `PsSaveOptions` för att konfigurera utskriftsalternativ.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Steg 1: skapa ett flersidigt PostScript‑dokument
`PsDocument` är kärnklassen som representerar ett PostScript‑dokument som kan innehålla flera sidor.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddPages2_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Set variable that indicates if resulting PostScript document will be multipaged
boolean multiPaged = true;
// Create new multipaged PS Document with one page opened
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Steg 2: lägg till innehåll på den första sidan
När dokumentet är klart kan du lägga till vilket innehåll du vill på den första sidan. När du är färdig stänger du sidan för att låsa dess innehåll.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## Hur man anger anpassad sidstorlek
Du anger en anpassad sidstorlek genom att anropa `document.openPage(width, height)` med önskade dimensioner i punkter innan du ritar något innehåll. `openPage(width, height)` öppnar en ny sida med den angivna bredden och höjden och ger dig full kontroll över sidans canvas. Om standardsidstorleken inte passar kan du **ange en anpassad sidstorlek** när du öppnar en ny sida. Detta är användbart för kvitton, etiketter eller någon icke‑standardlayout.

## Steg 3: lägg till en andra sida med annan storlek
Nedan öppnar vi en andra sida och anger explicit en anpassad bredd och höjd (i punkter). Detta demonstrerar hur du ställer in en anpassad sidstorlek för enskilda sidor, vilket ger dig möjlighet att arbeta med **olika sidstorlekar** i samma dokument.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Steg 4: spara dokumentet
Till sist persisterar du ändringarna genom att spara dokumentet. Alla sidor – inklusive de med anpassade storlekar – skrivs till utdatafilen.

```java
// Save the document
document.save();
```

Genom att följa dessa steg kan du sömlöst lägga till sidor och **ange anpassad sidstorlek** i ett Java‑PostScript‑dokument med Aspose.Page, vilket ger dig full kontroll över layouten på varje sida.

## Varför använda Aspose.Page för att ange anpassad sidstorlek?
Aspose.Page ger exakt kontroll över sidimensioner, så att du kan definiera vilken bredd och höjd som helst i punkter, blanda flera sidstorlekar i ett enda dokument och strömma innehåll effektivt för högpresterande PostScript‑generering. Detta gör det idealiskt för fakturor, biljetter och storskalig batch‑bearbetning där minnesanvändningen måste hållas låg.

Aspose.Page låter dig definiera exakta siddimensioner i punkter, blanda flera storlekar i en fil och strömma innehåll effektivt, vilket ger dig precis kontroll och hög prestanda för att generera PostScript.  
- **Precision:** Dimensioner definieras i punkter, så du får exakt kontroll över sidans bredd och höjd.  
- **Flexibilitet:** Blanda och matcha **olika sidstorlekar** i en enda PostScript‑fil.  
- **Prestanda:** Biblioteket strömmar innehåll direkt till utdatafilen, hanterar filer upp till 500 MB samtidigt som heap‑användningen hålls under 100 MB, vilket gör det lämpligt för stora **generera PostScript‑fil**‑scenarier.  
- **Rik API:** Stöder över 30 grafiska primitive, 10 bildformat och obegränsade textobjekt per sida – allt medan de anpassade dimensionerna du anger respekteras.

## Vanliga problem och lösningar
| Problem | Lösning |
|-------|----------|
| **Sidans dimensioner verkar omvända** | Kom ihåg att `openPage(width, height)` förväntar sig bredd först, sedan höjd (båda i punkter). |
| **Innehållet överskrider sidan** | Använd `PsGraphics`‑koordinatsystemet för att placera element inom de anpassade gränserna, eller skala din ritning. |
| **Minnesbristfel på stora dokument** | Aktivera strömning genom att skriva direkt till en `FileOutputStream` som visas, och undvik att ladda stora bilder i minnet på en gång. |

## Vanliga frågor
### Kan jag lägga till sidor med olika storlekar i ett enda PostScript‑dokument?
Ja, som demonstrerats i den här handledningen kan du lägga till sidor med varierande storlekar i ett flersidigt PostScript‑dokument.  

### Finns det några begränsningar för hur många sidor jag kan lägga till?
Aspose.Page stöder att lägga till ett praktiskt taget obegränsat antal sidor i ett dokument.  

### Kan jag lägga till anpassat innehåll, såsom bilder eller grafik, på sidorna?
Absolut! Aspose.Page låter dig lägga till ett brett spektrum av innehåll, inklusive text, bilder och andra grafiska element.  

### Är Aspose.Page lämpligt för att hantera stora dokument?
Ja, Aspose.Page är designat för att effektivt hantera både små och stora dokument med lätthet.  

### Var kan jag hitta ytterligare resurser och support för Aspose.Page?
Utforska [Aspose.Page‑dokumentationen](https://reference.aspose.com/page/java/), eller besök [Aspose.Page‑forumet](https://forum.aspose.com/c/page/39) för community‑support.  

**Ytterligare frågor och svar**

**Q:** *Vilka bildformat stöds när man ritar på en PostScript‑sida?*  
**A:** Du kan bädda in PNG, JPEG, BMP och GIF‑bilder direkt via rit‑API‑et.  

**Q:** *Hur ändrar jag standard‑DPI för dokumentet?*  
**A:** Anropa `PsSaveOptions.setResolution(int dpi)` innan du skapar `PsDocument`.  

**Q:** *Kan jag kryptera en PostScript‑fil med ett lösenord?*  
**A:** PostScript i sig stödjer ingen kryptering, men du kan paketera utdata i en PDF och applicera säkerhetsinställningar om så behövs.

---

**Senast uppdaterad:** 2026-10-25  
**Testat med:** Aspose.Page för Java 24.10  
**Författare:** Aspose  

## Relaterade handledningar

- [Hur man ställer in A4‑sidstorlek och skapar PostScript i Java med Aspose.Page](/page/java/document-creation/postscript/)
- [Hur man konverterar PostScript till PDF med Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [Hur man ritar rektangel i Java PostScript med Aspose.Page](/page/java/postscript-shapes/add-rectangle/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}