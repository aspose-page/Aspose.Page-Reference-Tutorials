---
date: 2026-01-23
description: Lär dig hur du redigerar EPS‑filer genom att lägga till namngivna värden
  med Aspose.Page för .NET. Denna steg‑för‑steg‑guide hjälper utvecklare att manipulera
  EPS‑metadata.
linktitle: Add Named Value
second_title: Aspose.Page .NET API
title: Hur man redigerar EPS-filer – Lägg till namngivet värde med Aspose.Page
url: /sv/net/eps-metadata-management/modify-eps-metadata-add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man redigerar EPS-filer – Lägg till namngivet värde med Aspose.Page

## Hur man redigerar EPS-filer – Introduktion

I den här handledningenivet värde i ett EPS.Page‑biblioteket för .NET. Oavsett om du bygger ett verktyg för batch‑behandling eller behöver berika EPS‑metadata i farten, ger stegen nedan en tydlig, praktisk guide.

## Snabba svar
- **Vad kan Aspose.Page göra?** Det låter dig läsa, modifiera och skriva EPS‑filer, inklusive XMP‑metadata.  
- **Vil  
-** Vanligtvis under 10 minuter för det grundläggande scenariot Aspose.Page strömmar data, vilket håller minnesanvändningen låg.

## Förutsättningar

Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:

- Grundläggande kunskaper i programmeringsspråket C#.  
- En integrerad utvecklingsmiljö (IDE) såsom Visual Studio installerad.  
- Aspose.Page för .NET‑biblioteket. Om det inte är installerat kan du ladda ner det [här](https://releases.aspose.com/page/net/).

## Importera namnrymder

Först importerar vi de nödvändiga namnrymderna i din C#‑kod. Dessa namnrymder är viktiga för att komma åt funktionerna som tillhandahålls av Aspose.Page:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Steg 1: Initiera EPS-filens inmatningsström

Det första steget är att initiera inmatningsströmmen för EPS‑filen. Ersätt `"Your Document Directory"` med sökvägen till din dokumentkatalog:

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Steg 2: Hämta XMP-metadata

Hämta XMP‑metadata från EPS‑filen. Om EPS‑filen saknar XMP‑metadata skapas en ny, fylld med värden från PS‑metadata‑kommentarer:

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## Steg 3: Ändra XMP-metadatavärden

Nu gör vi ändringar i XMP‑metadata. I detta exempel lägger vi till ett namngivet värde i strukturen `"xmpTPg:MaxPageSize"`:

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## Steg 4: Spara EPS-filen med ändrad XMP-metadata

Spara EPS‑filen med den uppdaterade XMP‑metadata. Skapa en utmatningsström och spara den modifierade EPS‑filen:

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## Slutsats

Grattis! Du har framgångsrikt lagt till ett namngivet värde i en EPS‑fil med Aspose.Page i .NET. Denna genomgång visar hur enkelt det är att **redigera EPS**‑metadata, vilket ger dig möjlighet att berika dokument programmässigt.

## Vanliga frågor

### Q1: Är Aspose.Page kompatibel med olika EPS‑filversioner?

A1: Aspose.Page stödjer olika EPS‑filversioner och säkerställer kompatibilitet med ett brett spektrum av dokument.

### Q2: Kan jag använda Aspose.Page i kommersiella projekt?

A2: Ja, Aspose.Page levereras med en kommersiell licens, och du kan köpa den [här](https://purchase.aspose.com/buy).

### Q3: Finns det en gratis provversion av Aspose.Page?

A3: Ja, du kan utforska Aspose.Page med en gratis provversion som finns [här](https://releases.aspose.com/).

### Q4: Hur får jag support eller kontaktar Aspose‑gemenskapen?

A4: Besök [Aspose.Page‑forumet](https://forum.aspose.com/c/page/39) för att få support och ansluta till gemenskapen.

### Q5: Vad är en tillfällig licens och hur kan jag skaffa en?

A5: Om du behöver en tillfällig licens för test‑ eller utvärderingsändamål kan du skaffa en [här](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

---

**Senast uppdaterad:** 2026-01-23  
**Testad med:** Aspose.Page 24.11 för .NET  
**Författare:** Aspose  

---