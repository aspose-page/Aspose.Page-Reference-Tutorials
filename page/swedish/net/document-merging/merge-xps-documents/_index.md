---
date: 2026-01-15
description: Lär dig hur du slår ihop XPS‑dokument med Aspose.Page för .NET – en steg‑för‑steg‑guide
  för sömlös dokumentsammanfogning.
linktitle: Merge XPS Documents
second_title: Aspose.Page .NET API
title: Hur man slår samman XPS-dokument med Aspose.Page för .NET
url: /sv/net/document-merging/merge-xps-documents/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man slår ihop XPS‑dokument med Aspose.Page för .NET

## Introduktion

Letar du efter ett pålitligt sätt **hur man slår ihop XPS**‑filer programatiskt? I den här handledningen går vi igenom de exakta stegen för att slå ihop XPS‑dokument med Aspose.Page för .NET. Oavsett om du behöver kombinera rapporter, fakturor eller andra XPS‑baserade tillgångar är processen enkel och helt automatiserad. Låt oss dyka ner och se hur du kan uppnå en ren, sammanslagen XPS‑utdata med bara några rader C#‑kod.

## Snabba svar
- **Vilket bibliotek hanterar XPS‑sammanfogning?** Aspose.Page for .NET  
- **Hur lång tid tar implementeringen?** Vanligtvis under 10 minuter  
- **Behöver jag en licens?** En licens krävs för produktionsanvändning; en gratis provversion finns tillgänglig  
- **Supported .NET versions?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Kan jag slå ihop krypterade XPS‑filer?** Ja – Aspose.Page kan hantera krypterade dokument

## Vad är XPS‑dokumentsammanfogning?
XPS (XML Paper Specification) är ett fast‑layout dokumentformat skapat av Microsoft. Att slå ihop XPS‑filer innebär att sammanfoga flera XPS‑dokument till en enda, kontinuerlig fil samtidigt som originalens layout, typsnitt och grafik bevaras.

## Varför använda Aspose.Page för .NET?
- **Full kontroll** över sammanslagningsprocessen utan att behöva Microsoft XPS Viewer  
- **Inga externa beroenden** – allt körs inom din .NET‑applikation  
- **Hög prestanda** – fungerar effektivt även med stora dokument  
- **Plattformsoberoende** – kompatibel med .NET Framework, .NET Core och .NET 5+

## Förutsättningar

- Grundläggande kunskap om C# och .NET‑ekosystemet.  
- **Aspose.Page for .NET** installerat – du kan ladda ner det [here](https://releases.aspose.com/page/net/).  
- En eller flera XPS‑filer som du vill kombinera.

## Importera namnrymder

I ditt C#‑projekt importerar du namnrymden som ger dig åtkomst till XPS‑API:n:

```csharp
using Aspose.Page.XPS;
```

## Steg 1: Ställ in ditt projekt

Skapa ett nytt C#‑konsol‑ eller bibliotekprojekt i Visual Studio, Rider eller din föredragna IDE. Lägg till en referens till Aspose.Page‑DLL:n (eller installera NuGet‑paketet `Aspose.Page`). Detta ger dig åtkomst till `XpsDocument`‑klassen som används senare.

## Steg 2: Initiera strömmar

Öppna käll‑XPS‑filerna som inmatningsströmmar och skapa en utmatningsström för det sammanslagna dokumentet. `using`‑satserna säkerställer att alla strömmar stängs korrekt efter operationen.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Initialize XPS output stream
using (System.IO.Stream outStream = System.IO.File.Open(dataDir + "mergedXPSfiles.xps", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream inStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

## Steg 3: Ladda XPS‑dokument

Skapa en `XpsDocument`‑instans från den primära inmatningsströmmen. `XpsLoadOptions`‑objektet låter dig anpassa laddningsbeteendet om så behövs.

```csharp
XpsDocument document = new XpsDocument(inStream, new XpsLoadOptions());
```

## Steg 4: Skapa en array av XPS‑filer

Förbered en string‑array som listar varje XPS‑fil du vill slå ihop. Ordningen i arrayen bestämmer ordningen i det slutgiltiga dokumentet.

```csharp
string[] filesToMerge = new string[] { dataDir + "Demo.xps", dataDir + "sample.xps" };
```

## Steg 5: Slå ihop XPS‑filer

Anropa `Merge`‑metoden, skicka in arrayen med filsökvägar och utmatningsströmmen. Aspose.Page sköter allt tungt arbete – kombinerar sidor, bevarar resurser och skriver den slutgiltiga XPS‑filen.

```csharp
document.Merge(filesToMerge, outStream);
```

## Vanliga problem & tips

- **Fil ej hittad** – Dubbelkolla sökvägarna i `filesToMerge`. Att använda `Path.Combine` kan hjälpa till att undvika fel med sökvägsseparatorer.  
- **Minnesanvändning** – När du slår ihop ett stort antal filer, överväg att bearbeta dem i batcher för att hålla minnesförbrukningen låg.  
- **Krypterade dokument** – Om någon källa‑XPS är lösenordsskyddad, ladda den med rätt autentiseringsuppgifter innan sammanslagning.

## Vanliga frågor

**Q1: Kan jag slå ihop XPS‑filer med olika sidstorlekar?**  
A: Ja. Aspose.Page normaliserar automatiskt siddimensionerna under sammanslagningen.

**Q2: Finns det någon gräns för hur många XPS‑filer jag kan kombinera?**  
A: Det finns ingen strikt gräns, men mycket stora samlingar kan påverka prestandan; övervaka minnesanvändningen.

**Q3: Behöver jag en speciell licens för att slå ihop krypterade XPS‑dokument?**  
A: En fullständig Aspose.Page‑licens krävs för alla produktionsfunktioner, inklusive hantering av krypterade dokument.

**Q4: Hur lägger jag till en anpassad sidfot på varje sida efter sammanslagning?**  
A: Efter sammanslagning kan du öppna den resulterande XPS‑filen med `XpsDocument` och använda rit‑API:t för att infoga sidfötter.

**Q5: Stöder Aspose.Page .NET Core?**  
A: Absolut. Biblioteket är kompatibelt med .NET Core 3.1 och senare, samt .NET 5/6/7.

## Slutsats

Du har nu lärt dig **hur man slår ihop XPS**‑dokument effektivt med Aspose.Page för .NET. Genom att följa stegen ovan kan du automatisera dokumentkonsolidering i vilken .NET‑applikation som helst, spara tid och minska manuellt arbete. Utforska API:t vidare för att lägga till vattenstämplar, kryptera den slutliga filen eller manipulera enskilda sidor efter behov.

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.Page for .NET (latest version)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}