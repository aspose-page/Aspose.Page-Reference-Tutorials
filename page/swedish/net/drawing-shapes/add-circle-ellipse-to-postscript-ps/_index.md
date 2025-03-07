---
title: Lägg till Circle Ellipse till PostScript (PS) med Aspose.Page
linktitle: Lägg till Circle Ellipse till PostScript (PS)
second_title: Aspose.Page .NET API
description: Lär dig hur du enkelt lägger till cirkelellipser till PostScript-dokument (PS) med Aspose.Page för .NET. Följ vår steg-för-steg-guide för sömlös integration.
weight: 10
url: /sv/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till Circle Ellipse till PostScript (PS) med Aspose.Page

## Introduktion

Välkommen till denna omfattande handledning om att lägga till cirkelellipser till PostScript-dokument (PS) med Aspose.Page för .NET. Aspose.Page är ett kraftfullt bibliotek som låter utvecklare arbeta med PostScript och andra dokumentformat sömlöst. I den här guiden kommer vi att leda dig genom processen att enkelt införliva cirkelellipser i dina PS-dokument.

## Förutsättningar

Innan vi dyker in i handledningen, se till att du har följande förutsättningar på plats:

1.  Aspose.Page for .NET Library: Ladda ner och installera Aspose.Page for .NET-biblioteket från[här](https://releases.aspose.com/page/net/).

2. Utvecklingsmiljö: Se till att du har en fungerande .NET-utvecklingsmiljö inställd på din dator.

Låt oss nu komma igång med steg-för-steg-guiden.

## Importera namnområden

I det första steget måste du importera de nödvändiga namnområdena för att göra Aspose.Page-funktionaliteten tillgänglig i din kod.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Låt oss nu dela upp exemplet i flera steg för att guida dig genom processen att lägga till cirkelellipser i ett PostScript-dokument.

## Steg 1: Ställ in dokumentkatalogen

```csharp
// ExStart:1
// Sökvägen till dokumentkatalogen.
string dataDir = "Your Document Directory";
```

Se till att ersätta "Din dokumentkatalog" med den faktiska sökvägen till din dokumentkatalog.

## Steg 2: Skapa utdataström för PostScript-dokument

```csharp
//Skapa utdataström för PostScript-dokument
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

Här skapas en FileStream för att skriva PostScript-dokumentet, och filläget är inställt för att skapa en ny fil.

## Steg 3: Skapa sparalternativ och PS-dokument

```csharp
//Skapa sparalternativ med A4-storlek
PsSaveOptions options = new PsSaveOptions();

// Skapa nytt 1-sidigt PS-dokument
PsDocument document = new PsDocument(outPsStream, options, false);
```

Det här steget innebär att skapa sparaalternativ med A4-storlek och initiera ett nytt PS-dokument på en sida.

## Steg 4: Skapa grafikväg för den första ellipsen

```csharp
//Skapa grafikbana från den första ellipsen
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

En grafisk bana skapas för den första ellipsen, som specificerar dess position och dimensioner.

## Steg 5: Ställ in Paint and Fill the Ellipse

```csharp
//Ställ in färg
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//Fyll ellipsen
document.Fill(path);
```

Här sätts färgen och den första ellipsen fylls med den angivna färgen.

## Steg 6: Skapa grafikväg för den andra ellipsen

```csharp
//Skapa grafikbana från den andra ellipsen
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

På liknande sätt skapas en grafisk bana för den andra ellipsen, som definierar dess position och dimensioner.

## Steg 7: Ställ in Stroke och rita Ellipsen

```csharp
//Ställ in slaglängd
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//Stryk (kontur) ellipsen
document.Draw(path);
```

I det här steget ställs strecket in och den andra ellipsen skisseras med den angivna färgen och linjetjockleken.

## Steg 8: Stäng den aktuella sidan och spara dokumentet

```csharp
//Stäng aktuell sida
document.ClosePage();

//Spara dokumentet
document.Save();
```

Slutligen stängs den aktuella sidan och hela dokumentet sparas, vilket slutför processen.

## Slutsats

Grattis! Du har framgångsrikt lärt dig hur du lägger till cirkelellipser i PostScript-dokument med Aspose.Page för .NET. Denna handledning gav en detaljerad, steg-för-steg-guide som hjälper dig att integrera den här funktionen i dina projekt sömlöst.

## FAQ's

### F1: Kan jag använda Aspose.Page för .NET med andra dokumentformat?

 S1: Aspose.Page fokuserar främst på PostScript, men Aspose tillhandahåller andra bibliotek för olika dokumentformat. Kolla[Aspose dokumentation](https://reference.aspose.com/page/net/) för mer detaljer.

### F2: Var kan jag hitta ytterligare stöd och diskussioner i samhället?

 A2: Besök[Aspose.Page forum](https://forum.aspose.com/c/page/39) för samhällsdiskussioner och stöd.

### F3: Finns det en gratis testversion tillgänglig för Aspose.Page för .NET?

 A3: Ja, du kan komma åt[gratis provperiod](https://releases.aspose.com/)för att utforska funktionerna i Aspose.Page för .NET.

### F4: Hur kan jag få en tillfällig licens för Aspose.Page?

 A4: Skaffa en tillfällig licens[här](https://purchase.aspose.com/temporary-license/) för test- och utvärderingsändamål.

### F5: Var kan jag köpa Aspose.Page för .NET?

 S5: Köp Aspose.Page för .NET från[köpsida](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
