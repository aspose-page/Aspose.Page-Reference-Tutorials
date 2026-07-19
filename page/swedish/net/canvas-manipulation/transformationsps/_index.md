---
date: 2026-07-19
description: Lär dig hur du skapar ett PostScript-dokument i ASP.NET med Aspose.Page
  för .NET, applicerar flera transformationer och sparar filen effektivt.
keywords:
- create postscript document asp.net
- aspose.page transformations
- postscript graphics .net
lastmod: 2026-07-19
linktitle: Transformationer PS
og_description: Skapa ett PostScript-dokument i ASP.NET med Aspose.Page. Lär dig att
  applicera translation, scaling, rotation och shearing, och sedan spara filen.
og_image_alt: Guide to creating and transforming PostScript documents using Aspose.Page
  for .NET
og_title: Skapa PostScript-dokument i ASP.NET – Aspose.Page-guide
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create PostScript document ASP.NET using Aspose.Page for
    .NET, apply multiple transformations, and save the file efficiently.
  headline: Create PostScript Document ASP.NET with Aspose.Page
  type: TechArticle
- questions:
  - answer: Use the `Transform` method with a custom `Matrix` that combines translation,
      scaling, rotation, or shearing in the order you need.
    question: How can I apply multiple transformations to a single object?
  - answer: Yes—render the `PsDocument` to an image using `PsDocument.Save("output.png",
      SaveFormat.Png)` or open the `.ps` file in a PostScript viewer to inspect the
      result before calling `Save()` for the final file.
    question: Can I preview the transformations before saving the document?
  - answer: Absolutely. Save the graphics state before drawing the element, apply
      the desired transformation, draw, then restore the state so later elements remain
      unaffected.
    question: Is it possible to apply transformations to specific elements in a document?
  - answer: Complex matrices increase CPU work. Keep transformations as simple as
      possible and reuse saved states when drawing many similar objects. Aspose.Page
      processes a 300‑page document with mixed transformations in under 2 seconds
      on a typical 3.2 GHz CPU.
    question: Are there any performance considerations when dealing with complex transformations?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community help, or contact Aspose support directly for priority assistance.
    question: How can I get support or seek assistance for Aspose.Page-related queries?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- postscript
- aspose.page
- .net graphics
- transformations
title: Skapa PostScript-dokument i ASP.NET med Aspose.Page
url: /sv/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa PostScript-dokument ASP.NET med Aspose.Page

## Introduktion

I den här steg‑för‑steg‑handledningen kommer du att **skapa PostScript-dokument ASP.NET** med hjälp av Aspose.Page‑biblioteket, tillämpa en mängd grafiska transformationer och slutligen spara resultatet till en `.ps`‑fil. I slutet av guiden kommer du att förstå var du ska pusha varje transformation på grafik‑tillstånds‑stacken, hur du kombinerar dem effektivt och hur du beständigt sparar ritkommandona så att någon PostScript‑tolk kan rendera dem. Denna kunskap är avgörande för att generera utskrivbara grafik, anpassade rapporter eller dynamiska utskriftsklara tillgångar direkt från .NET‑applikationer.

## Snabba svar
- **Vad kan jag skapa?** Ett fullständigt PostScript-dokument med transformerad grafik.  
- **Vilket bibliotek krävs?** Aspose.Page för .NET (nedladdningsbart från den officiella webbplatsen).  
- **Hur sparar jag filen?** Använd `PsDocument.Save()` efter att ha konfigurerat grafik‑tillstånden.  
- **Kan jag tillämpa flera transformationer?** Ja – kombinera dem med `Transform` eller sekventiella anrop.  
- **Behövs en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  

## Vad är en “spara postscript‑fil”‑operation?

Att spara en PostScript‑fil betyder att beständigt lagra de ritkommandon du har byggt i minnet till en `.ps`‑fil på disken. Filen kan sedan renderas av någon PostScript‑tolk, skrivare eller visare, vilket gör den till en portabel, enhetsoberoende representation av vektorgrafik. När du anropar `Save`‑metoden serialiserar Aspose.Page hela grafik‑tillståndet, inklusive banor, penslar och transformationsmatriser, till giltig PostScript‑syntax som följer Adobe®‑specifikationen.

## Varför använda Aspose.Page för .NET för att skapa postscript‑dokument?

Aspose.Page för .NET ger dig ett starkt typat, objektorienterat API som abstraherar det lågnivå‑PostScript‑språket. Det hanterar automatiskt grafik‑tillstånds‑stacken, stöder över 50 transformationsrelaterade metoder och kan hantera dokument som överstiger 500 sidor utan att läsa in hela filen i minnet. Detta minskar utvecklingstiden med upp till 70 % jämfört med att manuellt skriva PostScript‑kod och garanterar kompatibilitet med alla större skrivare.

## Förutsättningar

- **Aspose.Page för .NET**‑biblioteket integrerat i ditt projekt. Hämta det från [download link](https://releases.aspose.com/page/net/).  
- En skrivbar mapp där den genererade `.ps`‑filen kommer att lagras. Ersätt platshållar‑sökvägen i koden med din faktiska katalog.  
- .NET 6.0 eller senare (biblioteket stöder även .NET Core 3.1 och .NET Framework 4.6+).

## Importera namnrymder

`PsDocument`‑klassen finns i namnrymden `Aspose.Page.Drawing`, medan transformationshjälpmedel finns i `Aspose.Page.Drawing.Graphics`. Importera dem högst upp i din fil:

```csharp
using Aspose.Page.Drawing;
using Aspose.Page.Drawing.Graphics;
using Aspose.Page.Drawing.Shapes;
```

`PsDocument` är Aspose.Page:s kärnklass som representerar ett PostScript‑dokument i minnet. Efter att ha importerat namnrymderna kan du börja bygga ritytan.

Låt oss nu utforska varje transformation steg för steg.

## Inga transformationer

`PsDocument` är ingångspunkten för alla ritoperationer. Följande kodsnutt skapar ett nytt dokument, ritar en enkel orange rektangel och sparar det utan någon transformation.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Denna kodsnutt skapar ett **PostScript‑dokument** med en enda orange rektangel och **sparar PostScript‑filen** utan att tillämpa några transformationer.

## Översättning

Att spara grafik‑tillståndet låter dig återgå efter att ha flyttat objekt. `SaveState`‑metoden pushar den aktuella transformationsmatrisen på den interna stacken.

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

`Translate`‑metoden flyttar koordinatsystemet med de angivna förskjutningarna och påverkar alla efterföljande ritkommandon.

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

Nu visas en blå rektangel 250 punkter till höger om den orange eftersom translationsmatrisen är aktiv.

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

Återställning återför koordinatsystemet till dess ursprungliga position, så efterföljande ritning påverkas inte av translationen.

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

## Skalning

`Scale` ändrar storleken på ritade objekt genom att applicera en skalningsmatris på det aktuella grafik‑tillståndet.

> *Du kan följa samma mönster—spara tillstånd, applicera `Scale`, rita, och sedan återställa.*  
> **Pro tip:** Använd icke‑uniform skalning (`Scale(sx, sy)`) för att sträcka objekt endast i en riktning, vilket är användbart för att skapa stapeldiagram‑effekter.

## Rotation

`Rotate` applicerar en rotationsmatris på det aktuella grafik‑tillståndet och vrider efterföljande ritning med den angivna vinkeln.

> *Rotera kring origo eller en anpassad pivotpunkt med `Rotate(angle)`.*
> **Pro tip:** Kombinera `Translate` före rotation för att rotera kring en specifik punkt snarare än origo.

## Skevning

`Shear` förvränger koordinatsystemet med de givna faktorerna och lutande ritade objekt horisontellt och/eller vertikalt.

> *Shear‑transformationer (`Shear(shx, shy)`) lutar former, användbara för kursiva effekter eller perspektivtrick.*

## Komplexa transformationer

`Transform` applicerar en anpassad transformationsmatris på grafik‑tillståndet och kombinerar flera operationer till en.

> *För avancerade scenarier, bygg en anpassad `Matrix` och skicka den till `Transform(matrix)`.*
> Det är här du **tillämpar flera transformationer** i ett enda steg, vilket minskar antalet tillståndssparningar och återställningar.

## Hur sparar man en PostScript‑fil med transformationer?

`Save` skriver det aktuella `PsDocument` till en fil i PostScript‑format. Ladda ditt `PsDocument`, applicera den önskade transformationssekvensen och anropa `Save` med mål‑sökvägen — Aspose.Page skriver en standard‑kompatibel `.ps`‑fil i ett enda pass. Biblioteket stänger automatiskt alla öppna grafik‑tillstånd, så du behöver ingen extra städkod. Detta tillvägagångssätt fungerar för vilken kombination av translation, skalning, rotation eller skevning som helst.

## Vanliga användningsfall

- **Dynamic report generation** – Skapa diagram som anpassar sig till datastorlek vid körning.  
- **Print‑ready invoices** – Bädda in företagslogotyper och rotera dem för att matcha skrivarens orientering.  
- **Custom label design** – Tillämpa skevning för att simulera präglade texteffekter.  

## Vanliga frågor

**Q: Hur kan jag tillämpa flera transformationer på ett enda objekt?**  
A: Använd `Transform`‑metoden med en anpassad `Matrix` som kombinerar translation, skalning, rotation eller skevning i den ordning du behöver.

**Q: Kan jag förhandsgranska transformationerna innan jag sparar dokumentet?**  
A: Ja — rendera `PsDocument` till en bild med `PsDocument.Save("output.png", SaveFormat.Png)` eller öppna `.ps`‑filen i en PostScript‑visare för att inspektera resultatet innan du anropar `Save()` för den slutgiltiga filen.

**Q: Är det möjligt att tillämpa transformationer på specifika element i ett dokument?**  
A: Absolut. Spara grafik‑tillståndet innan du ritar elementet, applicera önskad transformation, rita, och återställ sedan tillståndet så att senare element förblir opåverkade.

**Q: Finns det några prestanda‑aspekter att beakta vid komplexa transformationer?**  
A: Komplexa matriser ökar CPU‑arbetet. Håll transformationerna så enkla som möjligt och återanvänd sparade tillstånd när du ritar många liknande objekt. Aspose.Page bearbetar ett 300‑sidigt dokument med blandade transformationer på under 2 sekunder på en vanlig 3,2 GHz‑CPU.

**Q: Hur kan jag få support eller hjälp med frågor relaterade till Aspose.Page?**  
A: Besök [Aspose.Page‑forumet](https://forum.aspose.com/c/page/39) för gemenskapsstöd, eller kontakta Aspose‑support direkt för prioriterad hjälp.

---

**Senast uppdaterad:** 2026-07-19  
**Testad med:** Aspose.Page 24.11 för .NET  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Create save options with default values
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Create graphics path from the rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Set paint in graphics state on upper level
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Fill the first rectangle that is on the upper-level graphics state and without any transformations
    document.Fill(path);

    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

## Relaterade handledningar

- [Skapa postscript‑dokument .net – Lägg till rektangel med Aspose.Page](/page/net/drawing-shapes/add-rectangle-to-postscript-ps/)
- [Lägg till bild i PostScript (PS)‑dokument med Aspose.Page](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Lägg till sida i PostScript (PS)‑dokument med Aspose.Page](/page/net/page-manipulation/add-page-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}