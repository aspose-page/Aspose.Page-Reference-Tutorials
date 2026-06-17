---
date: 2026-01-18
description: Lär dig hur du skapar PostScript‑dokument i .NET och lägger till rektanglar
  med Aspose.Page för .NET. Steg‑för‑steg‑guide med kodexempel.
linktitle: Add Rectangle to PostScript (PS)
second_title: Aspose.Page .NET API
title: Skapa postscript-dokument .net – Lägg till rektangel med Aspose.Page
url: /sv/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till rektangel i PostScript (PS) med Aspose.Page för .NET

## Introduktion

Om du vill **skapa postscript-dokument .net**, så erbjuder Aspose.Page en kraftfull lösning för att hantera PostScript‑filer. I den här handledningen går vi igenom hur du lägger till rektanglar i ett PostScript‑dokument med Aspose.Page för .NET, vilket ger dig en solid grund för rika grafikgenerering.

## Snabba svar
- **Vilket bibliotek behöver jag?** Aspose.Page för .NET.
- **Kan jag skapa ett PostScript-dokument från början?** Ja – API‑et låter dig bygga PS‑filer programatiskt.
- **Vilka .NET-versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en licens krävs för produktion.
- **Hur lång tid tar implementeringen?** Vanligtvis under 10minuter för grundläggande former.

## Vad är att skapa ett postscript-dokument .net?

Att skapa ett PostScript‑dokument i .NET innebär att programatiskt generera en.ps‑fil som beskriver sidinnehåll—text, grafik eller tidigare—med hjälp av Aspose.Page‑API:t. Detta tillvägagångssätt är idealiskt för server-sidig grafikgenerering, automatiserad rapportskapning eller någon situation där du behöver exakt kontroll över utdataformatet.

## Varför använda Aspose.Page för .NET?
- **Full kontroll över grafik** – Full kontroll över grafik – rita former, sätt färger och applicera linjer utan att behöva hantera låg‑nivå PS‑syntax.
- **Cross-platform** – Plattformsoberoende – fungerar på Windows, Linux och macOS‑miljöer.
- **Inga externa beroenden** – Inga externa beroenden – biblioteket hanterar all PS-generering internt.
- **Rik dokumentation & exempel** – Rik dokumentation & exempel – kom snabbt igång.

## Förutsättningar

- **Aspose.Page for .NET Library** – Aspose.Page för .NET‑biblioteket – ladda ner och installera från [här](https://releases.aspose.com/page/net/).
- **Utvecklingsmiljö** – Utvecklingsmiljö – Visual Studio, VS Code eller någon .NET-kompatibel IDE.

## Importera namnområden

Innan du börjar koda, importera de namnrymder som exponerar de nödvändiga klasserna:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Låt oss nu dela upp exemplet i tydliga, numrerade steg.

## Steg 1: Konfigurera din dokumentkatalog

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Byt ut `"Your Document Directory"` mot den mapp där du vill spara den resulterande PS‑filen.

## Steg 2: Skapa utdataström för PostScript-dokumentet

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Denna ström pekar på **AddRectangle_outPS.ps**. Du kan gärna byta namn på filen eller ändra platsen vid behov.

## Steg 3: Ange sparalternativ och skapa PS-dokumentet

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Här instruerar vi Aspose.Page att använda en A4‑sidstorlek och skapa ett enkelsidigt dokument.

## Steg 4: Lägg till en fylld rektangel

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

Vi definierar en rektangel vid (250, 100) med bredd 150 och höjd 100, sätter en orange pensel och fyller formen.

## Steg 5: Lägg till en konturerad rektangel

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

En andra rektangel skapas längre ner på sidan, den här gången med en röd 3‑punkts linje.

## Steg 6: Stäng sidan och spara dokumentet

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

När sidan stängs slutförs ritningen, och `Save()` skriver PS‑filen till disk.

## Vanliga frågor och tips

- **Felaktig filsökväg** – Felaktig filsökväg – Se till att `dataDir` slutar med en sökvägsseparator (`\\` eller `/`) eller använd `Path.Combine`.
- **Saknad licens** – Saknad licens – I en produktionsmiljö, applicera din Aspose‑licens innan du skapar dokumentet för att undvika utvärderingsvattenstämplar.
- **Color visibility** – Färgens synlighet – Om rektangeln visa tom, kontrollera att pensel‑ eller linjefärgerna kontrasterar mot sidans bakgrund.

## Vanliga frågor

**F:** Kan jag anpassa färgerna på rektanglarna?
**S:** Absolut. Ändra `Color.Orange` eller `Color.Red` i `SolidBrush`‑ och `Pen`‑konstruktörerna till vilken `System.Drawing.Color` du föredrar.

**F:** Är Aspose.Page kompatibel med andra dokumentformat?
**A:** Ja. Förutom PostScript-stödjer Aspose.Page även generering av XPS och EPS.

**F:** Hur kan jag lägga till text i samma dokument?
**A:** Använd `TextFragment`‑klassen för att placera text på önskade koordinater, och anropa sedan `document.Draw(textFragment)`.

**F:** Kan jag hitta fler exempel och fullständiga API‑referens?
**A:** Utforska dokumentationen [här](https://reference.aspose.com/page/net/) och gå med i communityn på [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**F:** Kan jag prova Aspose.Page innan jag köper?
**S:** Ja, ladda ner en gratis provversion [här](https://releases.aspose.com/). För förlängd utvärdering, överväg en [tillfällig licens](https://purchase.aspose.com/temporary-license/).

---

**Senast uppdaterad:** 2026-01-18
**Testat med:** Aspose.Page 24.12 för .NET
**Författare:** Aspose 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}