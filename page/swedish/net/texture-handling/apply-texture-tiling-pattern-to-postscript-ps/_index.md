---
date: 2026-03-26
description: Lär dig hur du skapar PostScript‑dokument i .NET med textur‑tillblandningsmönster
  med Aspose.Page. Följ vår steg‑för‑steg‑guide för att lägga till rika texturer i
  dina PS‑filer.
linktitle: Create PostScript .NET document with texture tiling
second_title: Aspose.Page .NET API
title: Skapa PostScript .NET-dokument med texturtilning
url: /sv/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa PostScript .NET-dokument med texturupprepning

## Hur man skapar PostScript-dokument .NET med texturupprepning

I den här handledningen kommer du att lära dig hur du **skapar PostScript-dokument .NET** och berikar det med ett texturupprepningsmönster med hjälp av Aspose.Page-biblioteket. Vi går igenom varje steg, från att konfigurera ditt projekt till att fylla och rita text med texturpenseln, så att du kan producera visuellt tilltalande PS-filer på några minuter.

## Snabba svar
- **Vilket bibliotek används?** Aspose.Page for .NET  
- **Kan jag använda .NET Core?** Ja, biblioteket stödjer .NET Core och .NET 5/6  
- **Vilka bildformat fungerar för texturen?** Alla format som stöds av System.Drawing (BMP, PNG, JPEG, etc.)  
- **Hur lång tid tar implementeringen?** Ungefär 10‑15 minuter för ett grundläggande exempel  
- **Behöver jag en licens?** En gratis provversion fungerar för testning; en licens krävs för produktion  

## Förutsättningar

- [Visual Studio](https://visualstudio.microsoft.com/) installerat på din maskin.  
- Grundläggande kunskaper i C#-programmering.  
- Ladda ner och installera [Aspose.Page for .NET library](https://releases.aspose.com/page/net/).  
- En bildfil för texturmönstret (t.ex. **TestTexture.bmp**).

## Importera namnrymder

I din C#-fil importerar du de nödvändiga namnrymderna så att kompilatorn vet var den ska hitta de typer vi kommer att använda:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Steg 1: Ställ in dokumentkatalogen

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Byt ut **Your Document Directory** mot den mapp där du vill att den genererade PS-filen ska sparas.

## Steg 2: Skapa utdataflöde för PS-dokument

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

Detta block öppnar ett filström, konfigurerar sidstorleken (A4 som standard) och skapar en ny **PsDocument**-instans som vi kommer att rita på.

## Steg 3: Tillämpa texturupprepningsmönster

```csharp
// Create a Bitmap object from the image file
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Create texture brush from the image
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    // Add scaling in X direction to the pattern
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Set this texture brush as the current paint
    document.SetPaint(brush);
}
```

Här laddar vi bitmapen, omsluter den i en **TextureBrush**, sträcker den eventuellt horisontellt och instruerar **PsDocument** att använda denna pensel för efterföljande ritoperationer.

## Steg 4: Skapa rektangelväg och fyll

```csharp
// Create rectangle path
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Fill rectangle
document.Fill(path);
```

En enkel rektangel definieras och fylls med texturpenseln som vi satte tidigare.

## Steg 5: Ställ in linje och rita

```csharp
// Get current paint
Brush paint = document.GetPaint();

// Set red stroke
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Stroke the rectangle
document.Draw(path);
```

Vi hämtar den aktuella färgen (texturpenseln), skapar en röd penna för konturen och ritar rektangelns kant.

## Steg 6: Fyll och rita text med texturmönster

```csharp
// Fill text with texture pattern                
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Outline text with texture pattern
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

Detta steg demonstrerar möjligheten att **fylla och rita text**: tecknen “ABC” fylls med texturpenseln och kontureras sedan, vilket ger en slående visuell effekt.

## Steg 7: Spara och stäng dokumentet

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

När sidan stängs slutförs ritkommandona, och `Save()` skriver PostScript-filen till disk.

## Vanliga problem och lösningar

- **Texturen ser felaktigt utsträckt** – Justera `Matrix`-värdena för att kontrollera skalning i X/Y-riktning.  
- **Bild ej hittad** – Verifiera att `dataDir` pekar på rätt mapp och att filnamnet matchar exakt, inklusive versaler.  
- **Färger ser felaktiga ut** – Kom ihåg att PostScript använder ett enhetsoberoende färgrymd; se till att du använder `Color`-objekt som mappas korrekt.

## Vanliga frågor

**Q:** Kan jag använda andra bildformat för texturmönstret?  
**A:** Ja, alla format som stöds av `System.Drawing.Bitmap` (BMP, PNG, JPEG, GIF, etc.) fungerar.

**Q:** Är Aspose.Page kompatibelt med .NET Core?  
**A:** Absolut. Biblioteket körs på .NET Framework, .NET Core och .NET 5/6.

**Q:** Hur ändrar jag storleken på den texturerade rektangeln?  
**A:** Ändra `RectangleF`-värdena i steget där rektangeln skapas (t.ex. `new RectangleF(0, 0, 300, 150)`).

**Q:** Kan jag använda flera texturmönster i ett dokument?  
**A:** Ja. Skapa helt enkelt en ny `TextureBrush` med en annan bild och anropa `SetPaint` igen innan du ritar nästa form eller text.

**Q:** Var kan jag hitta fler exempel och API‑referens?  
**A:** Besök [Aspose.Page Forum](https://forum.aspose.com/c/page/39) för community‑hjälp och den officiella [dokumentationen](https://reference.aspose.com/page/net/) för detaljerad API‑användning.

## Slutsats

Du vet nu hur du **skapar PostScript-dokument .NET** och tillämpar ett texturupprepningsmönster, inklusive hur du **fyller och ritar text** med den texturen. Experimentera med olika bilder, skalningsmatriser och ritprimitive för att producera skräddarsydda PS-filer för rapporter, flygblad eller annat grafikintensivt material.

---

**Last Updated:** 2026-03-26  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}