---
date: 2026-02-25
description: Lär dig hur du skapar XPS‑dokument och applicerar linjär gradient med
  Aspose.Page för .NET. Följ vår steg‑för‑steg‑guide för att spara XPS‑filen.
linktitle: Add Vertical Gradient to XPS
second_title: Aspose.Page .NET API
title: Skapa XPS-dokument med vertikal gradient med Aspose.Page
url: /sv/net/gradient-fills/add-vertical-gradient-to-xps/
weight: 15
---

 keep same.

Make sure to keep markdown formatting.

Also keep code block placeholders unchanged.

Let's produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till vertikal gradient i XPS med Aspose.Page för .NET

## Introduktion

I den här handledningen kommer du att **skapa XPS-dokument** som innehåller en mjuk vertikal gradient. Att lägga till gradienter är ett vanligt sätt att få XPS‑filer att se mer professionella ut – perfekt för rapporter, broschyrer eller andra utskrivbara grafikfiler. Vi går igenom varje steg, från att konfigurera projektet till att spara den färdiga XPS‑filen, så att du snabbt kan applicera en linjär gradient på vilken bana som helst.

## Snabba svar
- **Vad täcker den här handledningen?** Att lägga till en vertikal linjär gradient på en bana i ett XPS‑dokument.  
- **Vilket bibliotek krävs?** Aspose.Page för .NET.  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Hur lång tid tar implementeringen?** Ungefär 10‑15 minuter för ett grundläggande exempel.  
- **Kan jag spara resultatet som en XPS‑fil?** Ja, `Save`‑metoden skriver filen till disk.

## Vad är en vertikal gradient i XPS?

En vertikal gradient är en färgövergång som löper från toppen av en form till botten. I XPS uppnås detta med en **linear gradient brush** som definierar start‑ och slutpunkter samt en samling gradientstopp som styr färgen vid specifika positioner.

## Varför använda Aspose.Page för att skapa XPS‑dokument med gradienter?

- **Full .NET‑integration** – fungerar med .NET Framework, .NET Core och .NET 5/6+.  
- **Inga externa beroenden** – all rendering hanteras av biblioteket.  
- **Hög noggrannhet** – gradienter renderas exakt som definierat, i enlighet med XPS‑specifikationen.  
- **Lätt att underhålla** – tydlig objektmodell för banor, penslar och färger.

## Förutsättningar

- Aspose.Page för .NET‑bibliotek: Säkerställ att du har Aspose.Page för .NET installerat i din utvecklingsmiljö. Du kan ladda ner det [här](https://releases.aspose.com/page/net/).
- Utvecklingsmiljö: Ställ in en .NET‑utvecklingsmiljö med din föredragna IDE, till exempel Visual Studio.

Nu när vi har allt klart, låt oss dyka ner i koden.

## Importera namnrymder

I din .NET‑applikation, inkludera de nödvändiga namnrymderna för att komma åt Aspose.Page‑klasser och -metoder.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Steg 1: Konfigurera dokumentkatalogen

Definiera mappen där den genererade XPS‑filen ska sparas.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Steg 2: Skapa ett nytt XPS‑dokument

Instansiera ett nytt XPS‑dokument som vi senare kommer att fylla med en gradient‑fylld bana.

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Steg 3: Definiera gradientstopp

Gradientstopp bestämmer färgerna och deras positioner längs gradientlinjen. Här skapar vi fem stopp för att producera en mjuk vertikal övergång.

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExEnd:5
```

## Steg 4: Skapa en bana med gradient

Vi ritar en rektangel‑formad bana och applicerar en **linear gradient brush** som löper vertikalt från punkt (10, 110) till punkt (10, 200). Penseln får de gradientstopp som definierades tidigare.

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Steg 5: Spara det resulterande XPS‑dokumentet

Till sist skriver vi XPS‑dokumentet till disk. Detta **spara XPS‑fil**‑steg skapar `AddVerticalGradient_outXPS.xps` i den mapp du angav.

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

**Proffstips:** Verifiera resultatet genom att öppna XPS‑filen i Windows XPS Viewer eller någon tredjeparts‑visare för att säkerställa att gradienten visas som förväntat.

## Vanliga problem & felsökning

| Symptom | Trolig orsak | Lösning |
|---------|--------------|-----|
| Gradient visas som enfärgad | Gradientstopp har inte lagts till i penseln | Säkerställ att `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` körs. |
| Filen hittas inte vid sparning | `dataDir` pekar på en icke‑existerande mapp | Skapa katalogen först eller använd en absolut sökväg. |
| Färger ser annorlunda ut | Färgvärden använder ARGB‑ordning; kontrollera kanalordning | Använd `CreateColor(alpha, red, green, blue)` korrekt. |

## Vanliga frågor

**Q: Är Aspose.Page kompatibel med Visual Studio 2019?**  
A: Ja, Aspose.Page är kompatibel med Visual Studio 2019. Säkerställ att du har rätt version av biblioteket installerat.

**Q: Kan jag använda Aspose.Page i kommersiella projekt?**  
A: Ja, Aspose.Page kan användas i kommersiella projekt. Besök [här](https://purchase.aspose.com/buy) för att utforska licensalternativ.

**Q: Finns det en gratis provversion?**  
A: Ja, du kan få en gratis provversion av Aspose.Page [här](https://releases.aspose.com/).

**Q: Var hittar jag dokumentationen för Aspose.Page?**  
A: Dokumentationen finns tillgänglig [här](https://reference.aspose.com/page/net/).

**Q: Hur får jag support eller kan ställa frågor?**  
A: Besök [Aspose.Page‑forumet](https://forum.aspose.com/c/page/39) för community‑support.

## Slutsats

Du vet nu hur du **skapar XPS‑dokument**, **applikerar linjär gradient** och **sparar XPS‑fil** med Aspose.Page för .NET. Detta tillvägagångssätt ger dig full kontroll över den visuella stilen i XPS‑utdata, så att dina utskrivbara dokument verkligen sticker ut.

---  

**Senast uppdaterad:** 2026-02-25  
**Testad med:** Aspose.Page för .NET 24.11  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}