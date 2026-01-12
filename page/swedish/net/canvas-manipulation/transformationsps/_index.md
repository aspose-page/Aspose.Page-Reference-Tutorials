---
date: 2026-01-12
description: Lär dig hur du sparar en PostScript‑fil och skapar ett PostScript‑dokument
  med Aspose.Page för .NET, samt tillämpar flera transformationer för dynamisk grafik.
linktitle: Transformations PS
second_title: Aspose.Page .NET API
title: Spara PostScript‑fil med Aspose.Page Transformations (.NET)
url: /sv/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Spara PostScript-fil med Aspose.Page-transformeringar (.NET)

## Introduktion

I den här handledningen kommer du att upptäcka hur du **sparar en PostScript-fil** när du arbetar med Aspose.Page för .NET. Vi går igenom hur du skapar ett PostScript-dokument, applicerar flera transformationer såsom translation, skalning, rotation och skevning, och slutligen sparar resultatet. När du är klar kommer du att känna dig bekväm med att skapa dynamisk grafik programmässigt och veta exakt var du ska placera varje transformation i grafikstatusen.

## Snabba svar
- **Vad kan jag skapa?** Ett fullständigt PostScript-dokument med transformerad grafik.  
- **Vilket bibliotek krävs?** Aspose.Page för .NET (nedladdningsbart från den officiella webbplatsen).  
- **Hur sparar jag filen?** Använd `PsDocument.Save()` efter att ha konfigurerat grafikstatusar.  
- **Kan jag applicera flera transformationer?** Ja – kombinera dem med `Transform` eller sekventiella anrop.  
- **Behövs en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.

## Vad är en “spara postscript-fil” operation?

Att spara en PostScript-fil innebär att lagra de ritkommandon du har byggt i minnet till en `.ps`-fil på disk. Filen kan sedan renderas av vilken PostScript-tolk, skrivare eller visare som helst.

## Varför använda Aspose.Page för .NET för att skapa ett postscript-dokument?

Aspose.Page tillhandahåller ett hög‑nivå, enhets‑oberoende API som abstraherar den lågnivå PostScript‑syntaxen. Du får:

- Starkt typade C#‑objekt för banor, penslar och transformationer.  
- Automatisk hantering av grafikstatus‑stacken (save/restore).  
- Fullt stöd för komplexa transformationsmatriser utan manuella beräkningar.  

## Förutsättningar

Innan du börjar, se till att du har:

- **Aspose.Page för .NET**-biblioteket integrerat i ditt projekt. Hämta det från [nedladdningslänken](https://releases.aspose.com/page/net/).  
- En skrivbar mapp där den genererade `.ps`‑filen kommer att lagras. Ersätt platshållar‑sökvägen i koden med din faktiska katalog.

## Importera namnrymder

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Låt oss nu utforska varje transformation steg för steg.

## Inga transformationer

### Steg 1: Skapa utmatningsström

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

Detta kodsnutt skapar ett **PostScript-dokument** med en enda orange rektangel och **sparar PostScript-filen** utan att tillämpa några transformationer.

## Translation

### Steg 1: Spara grafikstatus

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

Att spara grafikstatusen låter dig återgå efter att ha flyttat objekt.

### Steg 2: Translatera grafikstatus

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

Transleringen flyttar allt som ritas efter detta anrop 250 enheter åt höger.

### Steg 3: Fyll rektangel med translaterings‑transformation

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

Nu visas en blå rektangel 250 punkter till höger om den orange.

### Steg 4: Återställ grafikstatus

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

Återställning återför koordinatsystemet till sin ursprungliga position, så efterföljande ritning påverkas inte av translateringen.

## Scaling

> *Du kan följa samma mönster – spara status, applicera `Scale`, rita och sedan återställa.*  
> **Pro tip:** Använd icke‑uniform skalning (`Scale(sx, sy)`) för att sträcka objekt endast i en riktning.

## Rotation

> *Rotera kring origo eller en anpassad pivotpunkt med `Rotate(angle)`.*
> **Pro tip:** Kombinera `Translate` före rotation för att rotera kring en specifik punkt.

## Shearing

> *Shear‑transformationer (`Shear(shx, shy)`) lutande former, användbara för kursiva effekter.*

## Komplexa transformationer

> *För avancerade scenarier, bygg en anpassad `Matrix` och skicka den till `Transform(matrix)`.*
> Detta är där du **tillämpar flera transformationer** i ett enda steg.

## Slutsats

Du har lärt dig hur du **sparar en PostScript-fil**, **skapar ett PostScript-dokument** och **tillämpar flera transformationer** med Aspose.Page för .NET. Experimentera med olika transformationsordningar, kombinera dem och se hur grafiken utvecklas.

## Vanliga frågor

**Q: Hur kan jag tillämpa flera transformationer på ett enda objekt?**  
A: Använd `Transform`‑metoden med en anpassad `Matrix` som kombinerar translation, skalning, rotation eller skevning i den ordning du behöver.

**Q: Kan jag förhandsgranska transformationerna innan jag sparar dokumentet?**  
A: Ja – rendera `PsDocument` till en bild eller använd en PostScript‑visare för att inspektera resultatet innan du anropar `Save()`.

**Q: Är det möjligt att tillämpa transformationer på specifika element i ett dokument?**  
A: Absolut. Spara grafikstatusen innan du ritar elementet, applicera önskad transformation, rita och återställ sedan statusen.

**Q: Finns det några prestandaöverväganden när man arbetar med komplexa transformationer?**  
A: Komplexa matriser ökar CPU‑arbetet. Håll transformationerna så enkla som möjligt och återanvänd sparade statusar när du ritar många liknande objekt.

**Q: Hur kan jag få support eller söka hjälp för frågor relaterade till Aspose.Page?**  
A: Besök [Aspose.Page‑forumet](https://forum.aspose.com/c/page/39) för gemenskapsstöd, eller kontakta Aspose‑supporten direkt.

---

**Senast uppdaterad:** 2026-01-12  
**Testat med:** Aspose.Page 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}