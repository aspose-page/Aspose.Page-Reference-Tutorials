---
date: 2026-03-03
description: Lär dig hur du ändrar storlek på EPS‑bilder i .NET med Aspose.Page –
  en steg‑för‑steg‑guide om hur du ändrar storlek på EPS med punkter, tum, millimeter
  eller procent.
linktitle: Resize EPS Images
second_title: Aspose.Page .NET API
title: Hur man ändrar storlek på EPS‑bilder med Aspose.Page för .NET
url: /sv/net/image-manipulation/resize-eps-images/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så här ändrar du storlek på EPS‑bilder med Aspose.Page för .NET

## Introduktion

Letar du efter **hur man ändrar storlek på EPS**‑bilder sömlöst med Aspose.Page för .NET? Denna handledning är din omfattande guide för att enkelt manipulera storleken på EPS‑bilder i olika enheter som punkter, tum, millimeter och procent. Aspose.Page för .NET erbjuder ett kraftfullt verktygssats, och i den här handledningen går vi igenom processen steg för steg.

## Snabba svar
- **Vilket bibliotek hanterar EPS‑storleksändring?** Aspose.Page for .NET  
- **Vilka enheter stöds?** Points, Inches, Millimeters, and Percents  
- **Behöver jag en licens för produktion?** Ja – en kommersiell licens krävs  
- **Kan jag ändra storlek på flera filer samtidigt?** Absolut – loopa bara igenom filerna  
- **Stöds .NET Core?** Ja, API:et fungerar med .NET Framework och .NET Core  

## Vad är EPS‑storleksändring?
Encapsulated PostScript (EPS) är ett vektorbaserat grafikformat som ofta används i tryck‑ och designarbetsflöden. Att ändra storlek på en EPS‑fil förändrar dess omgivningsruta utan att rasterisera grafiken, vilket bevarar skärpan i alla skalor.

## Varför ändra storlek på EPS‑bilder?
- **Behålla utskriftskvalitet:** Vektorskala håller kanterna skarpa.  
- **Anpassa layoutkrav:** Justera dimensioner för att matcha sid- eller dukstorlekar.  
- **Automatisera batch‑jobb:** Programmera storleksändring av dussintals filer på sekunder.  

## Förutsättningar

Innan du dyker ner i storleksändringens magi, se till att du har följande förutsättningar på plats:

- Aspose.Page for .NET Library: Se till att du har Aspose.Page for .NET‑biblioteket installerat. Du kan ladda ner det från [här](https://releases.aspose.com/page/net/).
- Document Directory: Skapa en katalog där du lagrar din inmatnings‑EPS‑fil och de utdata‑filer som har ändrad storlek.

Nu när du har allt på plats, låt oss fortsätta med att importera de nödvändiga namnrymderna och gå in i steg‑för‑steg‑guiden.

## Importera namnrymder

I ditt .NET‑projekt, börja med att importera de nödvändiga namnrymderna för att arbeta med Aspose.Page. Lägg till följande kod i början av din fil:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

## Hur man ändrar storlek på EPS i punkter

Punkter är en standardmåttenhet inom tryckeribranschen. Exemplet nedan fördubblar den ursprungliga bredden och höjden.

```csharp
public static void ResizeInPoints()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_points.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(oldSize.Width * 2, oldSize.Height * 2), Units.Points);
        }
    }
}
```

## Hur man ändrar storlek på EPS i tum

Tum används ofta av grafiska formgivare när de förbereder material för tryck.

```csharp
public static void ResizeInInches()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_inches.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
        }
    }
}
```

## Hur man ändrar storlek på EPS i millimeter

Millimeter är vanliga i regioner som använder det metriska systemet.

```csharp
public static void ResizeInMillimeters()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_mms.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
        }
    }
}
```

## Hur man ändrar storlek på EPS med procent

Procentbaserad storleksändring låter dig skala bilden i förhållande till dess ursprungliga storlek.

```csharp
public static void ResizeInPercents()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_percents.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
        }
    }
}
```

Känn dig fri att integrera dessa metoder i ditt projekt, så kommer du att ändra storlek på EPS‑bilder utan ansträngning. Experimentera med olika enheter för att uppnå önskade dimensioner.

## Vanliga problem och lösningar
- **Fil ej hittad:** Verifiera att `dataDir` pekar på rätt mapp och att `input.eps` finns.  
- **Oväntad storlek:** Kom ihåg att `Units.Percents` förväntar sig värden som 150 för 150 % av originalstorleken.  
- **Licensundantag:** Om du får ett licensfel, se till att en giltig Aspose.Page‑licensfil laddas innan du skapar `PsDocument`.

## Slutsats

Grattis! Du har nu bemästrat **hur man ändrar storlek på EPS**‑bilder med Aspose.Page för .NET. Detta kraftfulla bibliotek öppnar en värld av möjligheter för att manipulera vektorgrafik. Oavsett om du designar för tryck eller digitala medier, ger Aspose.Page dig möjlighet att uppnå precisa och anpassade resultat.

## Vanliga frågor

### Q1: Kan jag ändra storlek på flera EPS‑bilder samtidigt?

A1: Ja, du kan loopa igenom en samling EPS‑filer och tillämpa storleksändringsmetoderna därefter.

### Q2: Är Aspose.Page kompatibel med andra bildformat?

A2: Aspose.Page fokuserar främst på PostScript‑ och EPS‑format. För andra bildformat, överväg att använda Aspose.Imaging.

### Q3: Finns det licensrelaterade överväganden för kommersiella projekt?

A3: Ja, se till att du har en giltig licens. Besök [här](https://purchase.aspose.com/buy) för licensdetaljer.

### Q4: Kan jag prova Aspose.Page innan jag köper?

A4: Absolut! Du kan få en gratis provversion [här](https://releases.aspose.com/).

### Q5: Var kan jag få ytterligare hjälp eller diskutera problem?

A5: Besök [Aspose.Page‑forumet](https://forum.aspose.com/c/page/39) för att ansluta till communityn och få hjälp.

## Vanliga frågor och svar

**Q: Fungerar den här koden med .NET Core 6?**  
A: Ja. API:et är kompatibelt med .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ och .NET 6+.

**Q: Hur kan jag bevara den ursprungliga färgprofilen?**  
A: Metoden `ResizeEps` ändrar inte färgdata; den ändrar bara omgivningsrutan.

**Q: Är det möjligt att ändra storlek på en EPS utan att ladda hela filen i minnet?**  
A: Genom att använda en ström som i exemplet hålls minnesanvändningen låg; dokumentet bearbetas i farten.

**Q: Kan jag kedja flera storleksändringsoperationer?**  
A: Absolut. Anropa `ResizeEps` sekventiellt på samma `PsDocument`‑instans.

**Q: Vad händer med inbäddade bilder i EPS‑filen?**  
A: De skalas proportionellt med vektor innehållet, vilket bevarar kvaliteten.

---

**Senast uppdaterad:** 2026-03-03  
**Testad med:** Aspose.Page 24.12 for .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}