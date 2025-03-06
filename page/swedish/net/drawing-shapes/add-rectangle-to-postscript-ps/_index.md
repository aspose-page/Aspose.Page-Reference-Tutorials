---
title: Lägg till rektangel till PostScript (PS) med Aspose.Page för .NET
linktitle: Lägg till rektangel till PostScript (PS)
second_title: Aspose.Page .NET API
description: Förbättra dokumentskapandet i .NET med Aspose.Page. Lär dig att lägga till rektanglar till PostScript-filer (PS) steg för steg.
weight: 12
url: /sv/net/drawing-shapes/add-rectangle-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till rektangel till PostScript (PS) med Aspose.Page för .NET

## Introduktion

Om du vill förbättra din förmåga att skapa dokument i .NET, erbjuder Aspose.Page en kraftfull lösning för att hantera PostScript-dokument. I den här handledningen guidar vi dig genom processen att lägga till rektanglar till ett PostScript-dokument med Aspose.Page för .NET.

## Förutsättningar

Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:

-  Aspose.Page for .NET Library: Ladda ner och installera Aspose.Page for .NET-biblioteket från[här](https://releases.aspose.com/page/net/).

- Utvecklingsmiljö: Se till att du har en .NET-utvecklingsmiljö inställd på din maskin.

## Importera namnområden

Innan du börjar koda, se till att importera de nödvändiga namnrymden för att komma åt de obligatoriska klasserna och metoderna:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Låt oss nu dela upp exemplet i flera steg:

## Steg 1: Konfigurera din dokumentkatalog

```csharp
// ExStart:1
// Sökvägen till dokumentkatalogen.
string dataDir = "Your Document Directory";
```

I det här steget ersätter du "Din dokumentkatalog" med sökvägen där du vill spara ditt PostScript-dokument.

## Steg 2: Skapa utdataström för PostScript-dokument

```csharp
//Skapa utdataström för PostScript-dokument
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Här skapar vi en utdataström för PostScript-dokumentet och anger filnamnet ("AddRectangle_outPS.ps"). Justera filnamnet och platsen enligt dina önskemål.

## Steg 3: Ställ in Spara-alternativ och skapa PS-dokument

```csharp
//Skapa sparalternativ med A4-storlek
PsSaveOptions options = new PsSaveOptions();

// Skapa nytt 1-sidigt PS-dokument
PsDocument document = new PsDocument(outPsStream, options, false);
```

Ställ in alternativen för att spara och ange önskad sidstorlek (A4 i det här fallet). Skapa sedan ett nytt ensidigt PostScript-dokument.

## Steg 4: Lägg till rektangel och fyll

```csharp
//Skapa grafikbana från den första rektangeln
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Ställ in färg
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fyll rektangeln
document.Fill(path);
```

Här skapar vi en grafikbana som representerar den första rektangeln, ställer in färgfärgen (i det här fallet orange) och fyller rektangeln.

## Steg 5: Lägg till ytterligare en rektangel och slag

```csharp
//Skapa grafikbana från den andra rektangeln
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Ställ in slaglängd
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stryk (kontur) rektangeln
document.Draw(path);
```

I likhet med föregående steg skapar vi en grafikbana för den andra rektangeln, ställer in streckfärgen (röd med en tjocklek på 3) och skisserar rektangeln.

## Steg 6: Stäng sidan och spara dokumentet

```csharp
//Stäng aktuell sida
document.ClosePage();

//Spara dokumentet
document.Save();
```

Slutligen, stäng den aktuella sidan och spara hela dokumentet.

## Slutsats

Grattis! Du har framgångsrikt lagt till rektanglar i ett PostScript-dokument med Aspose.Page för .NET. Denna handledning täckte de väsentliga stegen, från att ställa in din utvecklingsmiljö till att spara det slutliga dokumentet.

## FAQ's

### F1: Kan jag anpassa färgerna på rektanglarna?

A1: Ja, du kan anpassa färgerna genom att justera parametrarna i`SolidBrush` och`Pen` klasser.

### F2: Är Aspose.Page kompatibel med andra dokumentformat?

S2: Ja, Aspose.Page stöder olika dokumentformat, inklusive XPS och PostScript.

### F3: Hur kan jag lägga till text i dokumentet?

 A3: Du kan använda`TextFragment` klass i Aspose.Page för att lägga till text i ditt dokument.

### F4: Var kan jag hitta ytterligare exempel och dokumentation?

 S4: Utforska dokumentationen[här](https://reference.aspose.com/page/net/) och besöka[Aspose.Page forum](https://forum.aspose.com/c/page/39) för samhällsstöd.

### F5: Kan jag prova Aspose.Page innan jag köper?

 A5: Ja, du kan få en gratis testversion[här](https://releases.aspose.com/) , och för utökad användning, överväg a[tillfällig licens](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
