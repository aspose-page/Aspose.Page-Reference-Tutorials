---
date: 2026-03-21
description: Leer hoe u Unicode‑tekst kunt toevoegen aan een XPS‑document met Aspose.Page
  voor .NET. Deze gids laat zien hoe u een XPS‑document maakt in C# en met Aspose.Page
  tekst toevoegt met Unicode‑strings.
linktitle: Add Text with Unicode String to XPS Document
second_title: Aspose.Page .NET API
title: Hoe Unicode-tekst toe te voegen aan een XPS-document met Aspose.Page
url: /nl/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe Unicode-tekst toe te voegen aan XPS-document met Aspose.Page

## Introductie

Als je **how to add unicode** tekens aan een XPS‑bestand moet toevoegen, ben je hier op de juiste plek. In deze tutorial lopen we de exacte stappen door die nodig zijn om **create XPS document C#**‑style te maken met Aspose.Page voor .NET en demonstreren we de **aspose page add text**‑functionaliteit met een Unicode‑string. Aan het einde heb je een volledig functioneel XPS‑document dat Unicode‑tekst van rechts‑naar‑links (RTL) correct weergeeft.

## Snelle antwoorden
- **Wat behandelt de tutorial?** Unicode‑tekst toevoegen aan een XPS‑document met Aspose.Page voor .NET.  
- **Welke taal wordt gebruikt?** C# (compatibel met .NET Framework en .NET Core).  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Kan ik het lettertype of de grootte wijzigen?** Ja – het voorbeeld gebruikt Arial 20 pt, maar elk geïnstalleerd lettertype werkt.  
- **Is RTL‑ondersteuning inbegrepen?** Het instellen van `BidiLevel = 1` schakelt rechts‑naar‑links rendering in voor Unicode‑strings.

## Wat is “how to add unicode” in XPS?

Unicode‑tekst toevoegen betekent dat je tekens uit elke taal—Arabisch, Hebreeuws, Chinees, enz.—in een XPS‑document invoegt. De `XpsGlyphs`‑klasse van Aspose.Page behandelt de low‑level glyph‑plaatsing, terwijl de `BidiLevel`‑eigenschap de tekstrichting voor RTL‑scripts regelt.

## Waarom Aspose.Page gebruiken om tekst toe te voegen?

- **Volledige .NET‑integratie** – werkt met .NET Framework, .NET Core, .NET 5/6+.  
- **Geen externe afhankelijkheden** – pure managed code, geen COM‑interop.  
- **Rijke typografie‑ondersteuning** – lettertypen, stijlen, kleuren en bidirectionele tekst.  
- **Hoge prestaties** – maakt en slaat XPS‑bestanden snel op, ideaal voor server‑side generatie.

## Voorvereisten

- Basiskennis van C# en .NET‑ontwikkeling.  
- Visual Studio (een recente versie).  
- Aspose.Page voor .NET‑bibliotheek – download deze van [hier](https://releases.aspose.com/page/net/).

## Namespaces importeren

Importeer eerst de namespaces die je toegang geven tot het XPS‑model en de teken‑hulpmiddelen.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Stap 1: Document opzetten – create XPS document C#

Maak een nieuw XPS‑document aan dat de Unicode‑tekst zal bevatten.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

## Stap 2: Unicode‑tekst toevoegen – aspose page add text

Nu voegen we de daadwerkelijke Unicode‑string toe. In dit voorbeeld gebruiken we het lettertype Arial, grootte 20, en positioneren we de tekst op (400 f, 200 f). De `BidiLevel` van 1 vertelt de renderer de string als rechts‑naar‑links te behandelen.

```csharp
// Add Text
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Stap 3: Document opslaan

Sla tenslotte het XPS‑bestand op schijf op.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Gefeliciteerd! Je hebt met succes **how to add unicode** tekst aan een XPS‑document toegevoegd met Aspose.Page voor .NET.

## Veelvoorkomende problemen en oplossingen

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| Tekst verschijnt onleesbaar | Lettertype ondersteunt het Unicode‑bereik niet | Gebruik een lettertype dat de benodigde glyphs bevat (bijv. Arial Unicode MS). |
| RTL‑tekst blijft nog steeds links‑naar‑rechts | `BidiLevel` niet ingesteld of ingesteld op 0 | Zorg ervoor dat `glyphs.BidiLevel = 1;` voor RTL‑scripts. |
| Bestand niet opgeslagen | Ongeldig `dataDir`‑pad | Controleer of de map bestaat en de applicatie schrijfrechten heeft. |

## Veelgestelde vragen

**Q: Is Aspose.Page compatibel met de nieuwste .NET‑frameworks?**  
A: Ja, Aspose.Page wordt regelmatig bijgewerkt om .NET Framework, .NET Core en .NET 5/6+ te ondersteunen.

**Q: Kan ik de lettertype‑stijl en -grootte aanpassen bij het toevoegen van tekst?**  
A: Absoluut! De `AddGlyphs`‑methode stelt je in staat om elke lettertype‑familie, grootte en `FontStyle` op te geven die je nodig hebt.

**Q: Waar kan ik aanvullende documentatie voor Aspose.Page vinden?**  
A: Je kunt de documentatie raadplegen [hier](https://reference.aspose.com/page/net/) voor uitgebreide API‑details.

**Q: Zijn er gratis bronnen om te beginnen met Aspose.Page?**  
A: Ja, verken het community‑forum op [Aspose.Page forum](https://forum.aspose.com/c/page/39) voor tips, voorbeelden en ondersteuning van mede‑gebruikers.

**Q: Is er een proefversie beschikbaar voordat je een aankoop doet?**  
A: Zeker! Download de gratis proefversie van [hier](https://releases.aspose.com/) om de bibliotheek te evalueren.

---

**Laatst bijgewerkt:** 2026-03-21  
**Getest met:** Aspose.Page 24.11 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}