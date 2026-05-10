---
date: 2026-02-23
description: Lär dig hur du skapar diagonala gradient‑XPS‑dokument med Aspose.Page
  för .NET och höj dina visuella presentationer utan ansträngning.
linktitle: Add Diagonal Gradient to XPS
second_title: Aspose.Page .NET API
title: Skapa diagonalgradient XPS med Aspose.Page för .NET
url: /sv/net/gradient-fills/add-diagonal-gradient-to-xps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa diagonal gradient XPS med Aspose.Page för .NET

## Introduktion

Om du behöver **skapa diagonal gradient XPS**-filer som fångar ögat, gör Aspose.Page för .NET det enkelt. I den här handledningen lär du dig hur du lägger till en diagonal gradient i ett XPS‑dokument, steg för steg, med hjälp av Aspose.Page‑API:et. I slutet har du ett återanvändbart mönster som du kan anpassa till vilken form eller färgschema som helst.

## Snabba svar
- **Vad gör API‑metoden?** Den skapar en linjär gradientpensel som sträcker sig diagonalt över en bana.  
- **Vilken klass representerar XPS‑dokumentet?** `XpsDocument`.  
- **Behöver jag en licens för att köra exemplet?** En gratis provversion fungerar för utveckling; en licens krävs för produktion.  
- **Kan jag ändra gradientens riktning?** Ja—justera start‑ och slut‑`PointF`‑värdena.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Vad är **create diagonal gradient xps**?
En diagonal gradient är en mjuk färgövergång som löper från ett hörn av en form till motsatt hörn. I XPS uppnås denna effekt genom att applicera en `LinearGradientBrush` på en bana:s fyllningsegenskap. Aspose.Page‑biblioteket abstraherar den lågnivå‑XPS‑markupen, så att du kan fokusera på färger och geometri.

## Varför använda Aspose.Page för diagonala gradienter?
- **Högupplöst rendering** – utdata matchar XPS‑specifikationen exakt.  
- **Full .NET‑integration** – fungerar med C#, VB.NET och alla .NET‑språk.  
- **Inga externa beroenden** – allt hanteras i‑process, ingen COM eller Office krävs.  
- **Skalbar till komplexa dokument** – du kan kombinera flera gradienter, bilder och text på samma sida.

## Förutsättningar

1. **Aspose.Page for .NET Library** – ladda ner den [här](https://releases.aspose.com/page/net/).  
2. **Utvecklingsmiljö** – Visual Studio, Rider eller någon editor som stödjer .NET‑projekt.  

Nu dyker vi ner i koden.

## Importera namnrymder

I ditt .NET‑projekt, inkludera de nödvändiga namnrymderna från Aspose.Page‑biblioteket för att få åtkomst till de erforderliga klasserna och metoderna. Lägg till följande namnrymder i början av din kod:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Steg 1: Ange dokumentkatalogen

Börja med att ange sökvägen till din dokumentkatalog. Detta är där det resulterande XPS‑dokumentet med den diagonala gradienten kommer att sparas.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Steg 2: Skapa ett nytt XPS‑dokument

Initiera ett nytt `XpsDocument` med hjälp av Aspose.Page‑biblioteket.

```csharp
XpsDocument doc = new XpsDocument();
```

## Steg 3: Definiera gradientfärger

Skapa en lista med `XpsGradientStop`‑objekt, där varje objekt representerar en färg i den diagonala gradienten.

```csharp
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 142, 4), 0f));
// ... Repeat for other colors
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 199, 80), 1f));
```

## Steg 4: Lägg till en diagonal gradient på en bana

Skapa en ny bana med en definierad geometri och applicera den diagonala gradienten på den. Justera renderings‑transformen och fyllningsegenskaperna efter behov.

```csharp
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 10f), new PointF(228f, 100f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
```

## Steg 5: Spara det resulterande XPS‑dokumentet

Spara slutligen det modifierade XPS‑dokumentet till den angivna katalogen.

```csharp
doc.Save(dataDir + "AddDiagonalGradient_outXPS.xps");
```

Du har nu framgångsrikt **skapat en diagonal gradient XPS**‑fil. Känn dig fri att experimentera med olika färgstopp, geometriska strängar eller transform‑matriser för att skapa en mängd olika visuella effekter.

## Vanliga problem och lösningar
- **Gradienten syns inte** – Verifiera att bana‑geometrin är sluten och att penselns start‑/slut‑punkter ligger inom bana‑gränserna.  
- **Felaktiga färger** – Se till att du använder `CreateColor` med korrekta ARGB‑värden; metoden förväntar sig värden i intervallet 0‑255.  
- **Filen sparas inte** – Kontrollera att `dataDir` pekar på en befintlig mapp och att applikationen har skrivbehörighet.

## Vanliga frågor

**Q: Kan jag applicera flera gradienter på olika delar av dokumentet?**  
A: Ja, du kan skapa flera banor och applicera olika gradienter på var och en.

**Q: Finns fördefinierade gradientstilar tillgängliga?**  
A: Aspose.Page tillåter anpassade gradienter, vilket ger dig full kontroll över färgövergångar.

**Q: Kan jag använda Aspose.Page för .NET med andra dokumentformat?**  
A: Aspose.Page fokuserar främst på manipulation av XPS‑dokument.

**Q: Hur kan jag hantera fel relaterade till dokumentbehandling?**  
A: Se [dokumentationen](https://reference.aspose.com/page/net/) för bästa praxis för felhantering.

**Q: Finns en provversion tillgänglig innan köp?**  
A: Ja, du kan utforska den [gratis provversionen](https://releases.aspose.com/) för att uppleva Aspose.Page för .NET.

**Q: Hur ändrar jag gradientens riktning till vertikal eller horisontell?**  
A: Ändra `PointF`‑argumenten i `CreateLinearGradientBrush` för att ange nya start‑ och slutpunkter.

**Q: Stöder biblioteket transparens i gradienter?**  
A: Ja—inkludera ett alfavärde när du skapar färger med `CreateColor`.

## Slutsats

Aspose.Page för .NET förenklar processen att förbättra XPS‑dokument med diagonala gradienter. Denna guide har lett dig genom allt från att ställa in förutsättningar till att spara den slutliga filen. Fortsätt experimentera med olika former och färgpaletter för att få dina XPS‑rapporter, broschyrer eller fakturor att verkligen sticka ut.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Senast uppdaterad:** 2026-02-23  
**Testad med:** Aspose.Page 24.11 for .NET  
**Författare:** Aspose  

---