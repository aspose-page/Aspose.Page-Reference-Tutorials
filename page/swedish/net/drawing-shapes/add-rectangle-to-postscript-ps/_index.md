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

## Introduction

Om du vill **create postscript document .net**, så erbjuder Aspose.Page en kraftfull lösning för att hantera PostScript‑filer. I den här handledningen går vi igenom hur du lägger till rektanglar i ett PostScript‑dokument med Aspose.Page för .NET, vilket ger dig en solid grund för rikare grafikgenerering.

## Quick Answers
- **What library do I need?** Aspose.Page for .NET.
- **Can I create a PostScript document from scratch?** Ja – API‑et låter dig bygga PS‑filer programatiskt.
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Do I need a license for development?** En gratis provversion fungerar för testning; en licens krävs för produktion.
- **How long does the implementation take?** Vanligtvis under 10 minuter för grundläggande former.

## What is creating a postscript document .net?

Att skapa ett PostScript‑dokument i .NET innebär att programatiskt generera en .ps‑fil som beskriver sidinnehåll—text, grafik eller former—med hjälp av Aspose.Page‑API:t. Detta tillvägagångssätt är idealiskt för server‑sidig grafikgenerering, automatiserad rapportskapning eller någon situation där du behöver exakt kontroll över utdataformatet.

## Why use Aspose.Page for .NET?
- **Full control over graphics** – Full kontroll över grafik – rita former, sätt färger och applicera linjer utan att behöva hantera låg‑nivå PS‑syntax.
- **Cross‑platform** – Plattformsoberoende – fungerar på Windows, Linux och macOS‑miljöer.
- **No external dependencies** – Inga externa beroenden – biblioteket hanterar all PS‑generering internt.
- **Rich documentation & examples** – Rik dokumentation & exempel – kom snabbt igång.

## Prerequisites

- **Aspose.Page for .NET Library** – Aspose.Page för .NET‑biblioteket – ladda ner och installera från [here](https://releases.aspose.com/page/net/).
- **Development Environment** – Utvecklingsmiljö – Visual Studio, VS Code eller någon .NET‑kompatibel IDE.

## Import Namespaces

Innan du börjar koda, importera de namnrymder som exponerar de nödvändiga klasserna:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Låt oss nu dela upp exemplet i tydliga, numrerade steg.

## Step 1: Set up Your Document Directory

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Byt ut `"Your Document Directory"` mot den mapp där du vill spara den resulterande PS‑filen.

## Step 2: Create Output Stream for the PostScript Document

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Denna ström pekar på **AddRectangle_outPS.ps**. Du kan gärna byta namn på filen eller ändra platsen vid behov.

## Step 3: Set Save Options and Create the PS Document

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Här instruerar vi Aspose.Page att använda en A4‑sidstorlek och skapa ett enkelsidigt dokument.

## Step 4: Add a Filled Rectangle

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

## Step 5: Add an Outlined Rectangle

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

## Step 6: Close the Page and Save the Document

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

När sidan stängs slutförs ritningen, och `Save()` skriver PS‑filen till disk.

## Common Issues & Tips

- **Incorrect file path** – Felaktig filsökväg – Se till att `dataDir` slutar med en sökvägsseparator (`\\` eller `/`) eller använd `Path.Combine`.
- **Missing license** – Saknad licens – I en produktionsmiljö, applicera din Aspose‑licens innan du skapar dokumentet för att undvika utvärderingsvattenstämplar.
- **Color visibility** – Färgens synlighet – Om rektangeln visas tom, kontrollera att pensel‑ eller linjefärgerna kontrasterar mot sidans bakgrund.

## Frequently Asked Questions

**Q:** Kan jag anpassa färgerna på rektanglarna?  
**A:** Absolut. Ändra `Color.Orange` eller `Color.Red` i `SolidBrush`‑ och `Pen`‑konstruktörerna till vilken `System.Drawing.Color` du föredrar.

**Q:** Är Aspose.Page kompatibel med andra dokumentformat?  
**A:** Ja. Förutom PostScript stödjer Aspose.Page även generering av XPS och EPS.

**Q:** Hur kan jag lägga till text i samma dokument?  
**A:** Använd `TextFragment`‑klassen för att placera text på önskade koordinater, och anropa sedan `document.Draw(textFragment)`.

**Q:** Var kan jag hitta fler exempel och fullständig API‑referens?  
**A:** Utforska dokumentationen [here](https://reference.aspose.com/page/net/) och gå med i communityn på [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q:** Kan jag prova Aspose.Page innan jag köper?  
**A:** Ja, ladda ner en gratis provversion [here](https://releases.aspose.com/). För förlängd utvärdering, överväg en [temporary license](https://purchase.aspose.com/temporary-license/).

---

**Senast uppdaterad:** 2026-01-18  
**Testat med:** Aspose.Page 24.12 for .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}