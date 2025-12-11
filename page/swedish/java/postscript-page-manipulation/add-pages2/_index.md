---
date: 2025-12-11
description: Lär dig hur du ställer in anpassad sidstorlek och lägger till sidor i
  Java PostScript‑dokument med Aspose.Page. Följ vår steg‑för‑steg‑guide för sömlös
  dokumentmanipulation.
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: Aspose.Page Java-handledning – ange anpassad sidstorlek när du lägger till
  sidor i PostScript
url: /sv/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java‑handledning – ange anpassad sidstorlek när du lägger till sidor i PostScript

## Introduktion
I moderna Java‑applikationer är **att ange en anpassad sidstorlek** för PostScript‑utdata ofta nödvändigt—oavsett om du genererar fakturor, biljetter eller anpassad grafik. Aspose.Page för Java gör denna uppgift enkel. I den här handledningen lär du dig hur du lägger till sidor och anger anpassade sidstorlekar i ett PostScript‑dokument, steg för steg, så att du kan producera exakt rätt layout varje gång.

## Snabba svar
- **Kan jag ange olika sidstorlekar för varje sida?** Ja, du kan öppna sidor med anpassade dimensioner med `document.openPage(width, height)`.  
- **Behöver jag en licens för produktionsanvändning?** En giltig Aspose.Page‑licens krävs för icke‑utvärderingsdistributioner.  
- **Vilka Java‑versioner stöds?** Biblioteket fungerar med Java 8 och senare.  
- **Är API‑et trådsäkert?** Dokumentinstanser är inte trådsäkra; skapa ett separat `PsDocument` per tråd.  
- **Hur stor kan en PostScript‑fil vara?** Aspose.Page hanterar fler‑megabyte‑filer effektivt; minnesanvändningen skalar med innehållet, inte antalet sidor.

## Förutsättningar
Innan vi dyker ner, se till att du har:

- Grundläggande kunskaper i Java‑programmering.  
- Aspose.Page för Java tillagt i ditt projekt (Maven/Gradle eller manuell JAR).  
- En Java‑utvecklingsmiljö (IDE, JDK 8+).  

## Importera paket
För att börja, importera de nödvändiga klasserna från Aspose.Page‑biblioteket.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Steg 1: Skapa ett flersidigt PostScript‑dokument
Först, skapa ett nytt `PsDocument` konfigurerat för flera sidor. Detta ställer in utströmmen och talar om för biblioteket att vi kommer att arbeta med en flersidig fil.

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

## Steg 2: Lägg till innehåll på den första sidan
När dokumentet är klart kan du lägga till vilket innehåll du behöver på den första sidan. När du är färdig, stäng sidan för att låsa dess innehåll.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## Hur man anger anpassad sidstorlek
Om standardsidstorleken inte är vad du behöver, kan du **ange en anpassad sidstorlek** när du öppnar en ny sida. Detta är användbart för kvitton, etiketter eller någon icke‑standard layout.

## Steg 3: Lägg till en andra sida med annan storlek
Nedan öppnar vi en andra sida och anger explicit en anpassad bredd och höjd (i punkter). Detta demonstrerar hur du sätter en anpassad sidstorlek för enskilda sidor.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Steg 4: Spara dokumentet
Till sist, skriv ändringarna till fil genom att spara dokumentet. Alla sidor—inklusive de med anpassade storlekar—skrivs till utdatafilen.

```java
// Save the document
document.save();
```

Genom att följa dessa steg kan du sömlöst lägga till sidor och **ange anpassade sidstorlekar** i ett Java‑PostScript‑dokument med Aspose.Page, vilket ger dig full kontroll över layouten på varje sida.

## Slutsats
Aspose.Page för Java erbjuder ett robust, utvecklarvänligt API för hantering av PostScript‑dokument. Du vet nu hur du lägger till flera sidor, använder anpassade dimensioner och sparar resultatet—så att du kan generera exakt formaterad utdata för vilken Java‑baserad lösning som helst.

## Vanliga frågor
### Kan jag lägga till sidor med olika storlekar i ett enda PostScript‑dokument?
Ja, som demonstrerats i den här handledningen kan du lägga till sidor med varierande storlekar i ett flersidigt PostScript‑dokument.  
### Finns det några begränsningar för hur många sidor jag kan lägga till?
Aspose.Page stöder att lägga till ett praktiskt taget obegränsat antal sidor i ett dokument.  
### Kan jag lägga till anpassat innehåll, såsom bilder eller grafik, på sidorna?
Absolut! Aspose.Page låter dig lägga till ett brett spektrum av innehåll, inklusive text, bilder och andra grafiska element.  
### Är Aspose.Page lämplig för att hantera stora dokument?
Ja, Aspose.Page är designat för att effektivt hantera både små och stora dokument med lätthet.  
### Var kan jag hitta ytterligare resurser och support för Aspose.Page?
Utforska [Aspose.Page documentation](https://reference.aspose.com/page/java/), eller besök [Aspose.Page forum](https://forum.aspose.com/c/page/39) för community‑support.  

**Additional Q&A**

**Q:** *Vilka bildformat stöds när man ritar på en PostScript‑sida?*  
**A:** Du kan bädda in PNG-, JPEG-, BMP- och GIF‑bilder direkt med rit‑API‑et.  

**Q:** *Hur ändrar jag standard‑DPI för dokumentet?*  
**A:** Ange `PsSaveOptions.setResolution(int dpi)` innan du skapar `PsDocument`.  

**Q:** *Kan jag kryptera en PostScript‑fil med ett lösenord?*  
**A:** PostScript i sig stödjer inte kryptering, men du kan paketera utdata i en PDF och tillämpa säkerhetsinställningar om så behövs.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Senast uppdaterad:** 2025-12-11  
**Testat med:** Aspose.Page for Java 24.10  
**Författare:** Aspose  

---