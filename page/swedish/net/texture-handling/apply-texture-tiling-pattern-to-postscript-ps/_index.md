---
title: Applicera Texture Tiling Pattern på PostScript (PS) med Aspose.Page
linktitle: Applicera texturplattmönster på PostScript (PS)
second_title: Aspose.Page .NET API
description: Förbättra dina PostScript-dokument (PS) med texturmönster med hjälp av Aspose.Page för .NET. Följ vår steg-för-steg-guide för en kreativ touch.
weight: 10
url: /sv/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Applicera Texture Tiling Pattern på PostScript (PS) med Aspose.Page

## Introduktion

Välkommen till denna steg-för-steg handledning om hur man applicerar ett texturmönster på ett PostScript-dokument (PS) med Aspose.Page för .NET. Aspose.Page är ett kraftfullt bibliotek som låter dig arbeta med olika dokumentformat, och i den här självstudien kommer vi att utforska hur du kan förbättra dina PS-dokument genom att lägga till texturmönster.

## Förutsättningar

Innan vi dyker in i handledningen, se till att du har följande:

- [Visuell Studio](https://visualstudio.microsoft.com/) installerat på din maskin.
- Grundläggande kunskaper i C#-programmering.
-  Ladda ner och installera[Aspose.Page för .NET-bibliotek](https://releases.aspose.com/page/net/).
- En bildfil för texturmönstret (t.ex. "TestTexture.bmp").

## Importera namnområden

Se till att du importerar de nödvändiga namnrymden i din C#-kod:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Låt oss dela upp exemplet i flera steg för att guida dig genom processen.

## Steg 1: Konfigurera dokumentkatalog

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "Your Document Directory";
```

Se till att ersätta "Din dokumentkatalog" med sökvägen där du vill spara ditt PS-dokument.

## Steg 2: Skapa utdataström för PS-dokument

```csharp
// Skapa utdataström för PostScript-dokument
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Skapa sparalternativ med A4-storlek
    PsSaveOptions options = new PsSaveOptions();

    // Skapa nytt 1-sidigt PS-dokument
    PsDocument document = new PsDocument(outPsStream, options, false);
```

Detta steg ställer in utdataströmmen för PS-dokumentet, inklusive definition av dokumentstorleken.

## Steg 3: Applicera Texture Tiling Pattern

```csharp
// Skapa ett bitmappsobjekt från bildfilen
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Skapa texturpensel från bilden
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    //Lägg till skalning i X-riktning till mönstret
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Ställ in denna texturborste som den aktuella färgen
    document.SetPaint(brush);
}
```

Det här steget innebär att du skapar en texturpensel från en bild och ställer in den som aktuell färg för dokumentet.

## Steg 4: Skapa rektangelbana och fyll

```csharp
// Skapa rektangelbana
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Fyll rektangel
document.Fill(path);
```

Här definierar vi en rektangelbana och fyller den med den tidigare inställda texturborsten.

## Steg 5: Ställ in Stroke och Draw

```csharp
// Skaffa aktuell färg
Brush paint = document.GetPaint();

// Ställ in rött streck
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Stryk rektangeln
document.Draw(path);
```

Detta steg innebär att ställa in slagegenskaper och rita den konturerade rektangeln.

## Steg 6: Fyll och kontur text med texturmönster

```csharp
// Fyll text med texturmönster
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Konturtext med texturmönster
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

Slutligen fyller och konturerar vi text med texturmönstret, vilket förstärker ditt dokuments visuella tilltalande.

## Steg 7: Spara och stäng dokument

```csharp
// Stäng aktuell sida
document.ClosePage();

// Spara dokumentet
document.Save();
```

Se till att stänga den aktuella sidan och spara dokumentet för att tillämpa ändringarna.

## Slutsats

Grattis! Du har framgångsrikt lärt dig hur man applicerar ett texturmönster på ett PostScript-dokument med Aspose.Page för .NET. Experimentera med olika bilder och mönster för att anpassa dina PS-dokument ytterligare.

## FAQ's

### F1: Kan jag använda andra bildformat för strukturmönstret?

S1: Ja, Aspose.Page stöder olika bildformat. Säkerställ kompatibilitet med bibliotekets dokumentation.

### F2: Är Aspose.Page kompatibel med .NET Core?

S2: Ja, Aspose.Page är kompatibel med både .NET Framework och .NET Core.

### F3: Hur kan jag justera storleken på den strukturerade rektangeln?

 A3: Ändra måtten i`RectangleF` parametrar under skapandet av sökvägen.

### F4: Kan jag lägga till flera texturmönster i ett enda dokument?

A4: Ja, du kan upprepa processen med olika bilder och vägar.

### F5: Var kan jag hitta ytterligare resurser och support?

 A5: Besök[Aspose.Page Forum](https://forum.aspose.com/c/page/39) för samhällsstöd och utforska[dokumentation](https://reference.aspose.com/page/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
