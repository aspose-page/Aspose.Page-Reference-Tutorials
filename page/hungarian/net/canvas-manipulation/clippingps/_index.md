---
date: 2026-01-05
description: Tanulja meg, hogyan adjon hozzá vágóutat a PostScriptben az Aspose.Page
  for .NET használatával – lépésről‑lépésre útmutató a festőecset beállításával és
  a szaggatott téglalap rajzolásával.
linktitle: Clipping PS
second_title: Aspose.Page .NET API
title: Clipping útvonal hozzáadása a PS-hez az Aspose.Page for .NET segítségével
url: /hu/net/canvas-manipulation/clippingps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kivágási útvonal hozzáadása PS-hez az Aspose.Page for .NET segítségével

## Bevezetés

Ebben az átfogó útmutatóban megtudja, hogyan **adhat hozzá kivágási útvonalat** egy PostScript (PS) dokumentumhoz az Aspose.Page for .NET használatával. Lépésről lépésre végigvezetjük, megmutatjuk, hogyan **állíthat be festőecsetet**, és bemutatjuk, hogyan **rajzolhat szaggatott téglalapot** a kivágott tartalom köré. A végére egy teljesen működő PS fájlt kap, amely alakzat alapján mutatja be a kivágást, így grafikai elemei dinamikusabbak és professzionálisabbak lesznek.

## Gyors válaszok
- **Mi a “kivágási útvonal hozzáadása” funkció?** Korlátozza a rajzolási műveleteket egy meghatározott alakzatra, elrejtve mindent, ami azon kívül van.  
- **Melyik könyvtár kezeli a kivágást .NET-ben?** Az Aspose.Page for .NET gazdag API-t biztosít a PS/EPS manipulációhoz.  
- **Szükségem van licencre?** A ingyenes próba verzió fejlesztéshez megfelelő; a termeléshez kereskedelmi licenc szükséges.  
- **Megváltoztathatom az ecset színét?** Igen, használja a `SetPaint`-et bármely `SolidBrush` vagy kedvenc színátmenetével.  
- **Lehetséges szaggatott téglalapot rajzolni?** Természetesen – hozzon létre egy `Pen`-t `DashStyle.Dash` beállítással, és használja a `Draw`-ot.  

## Mi az a kivágási útvonal a PostScript-ben?

A kivágási útvonal meghatározza a későbbi rajzolási parancsok látható területét. Minden, ami az útvonalon kívül kerül, figyelmen kívül marad, lehetővé téve összetett maszkolt grafikák létrehozását az eredeti tartalom módosítása nélkül.

## Miért használja az Aspose.Page-t a kivágáshoz?
- **Nincs külső függőség** – tiszta .NET könyvtár.  
- **Teljes irányítás** a grafikai állapot felett (mentés/visszaállítás, transzformáció, forgatás).  
- **Gazdag rajzoló primitívek** mint a `SetPaint`, `Clip` és `Draw`, testreszabható tollakkal és ecsetekkel.  

## Előfeltételek

- Alapvető C# programozási ismeretek.  
- Az Aspose.Page for .NET könyvtár telepítve – letöltheti [itt](https://releases.aspose.com/page/net/).  
- Visual Studio vagy bármely kedvelt .NET IDE.  

## Névterek importálása

Először importálja a grafikai manipulációhoz szükséges névtereket:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Most bontsuk le a példát világos, számozott lépésekre.

### 1. lépés: Dokumentum könyvtár beállítása

Határozza meg a mappát, ahol a forrás- és kimeneti fájlok tárolódnak.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### 2. lépés: Kimeneti adatfolyam létrehozása a PostScript dokumentumhoz

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

### 3. lépés: Mentési beállítások létrehozása

`PsSaveOptions` példányosítása alapértelmezett beállításokkal. Később testreszabható, ha szükséges.

```csharp
// Create save options with default values
PsSaveOptions options = new PsSaveOptions();
```

### 4. lépés: Új, egyoldalas PS dokumentum létrehozása

```csharp
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

### 5. lépés: Grafikai útvonal létrehozása a téglalapból

```csharp
// Create graphics path from the rectangle
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

### 6. lépés: Kivágás alakzattal

Itt **kivágási útvonalat adunk hozzá** egy kör használatával, **kék színű festőecsetet állítunk be**, és kitöltjük a téglalapot a kivágott területen belül.

```csharp
// Save graphics state in order to return back to this state after transformation
document.WriteGraphicsSave();

// Displace current graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

// Create graphics path from the circle
GraphicsPath circlePath = new GraphicsPath();
circlePath.AddEllipse(new RectangleF(50, 0, 200, 200));

// Add clipping by circle to the current graphics state
document.Clip(circlePath);

// Set paint in the current graphics state
document.SetPaint(new SolidBrush(Color.Blue));

// Fill the rectangle in the current graphics state (with clipping)
document.Fill(rectanglePath);

// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

### 7. lépés: Felső szintű grafikai állapot eltolása és szaggatott téglalap rajzolása

Az előző állapot visszaállítása után újra eltoljuk a grafikai kurzort, **szaggatott téglalapot rajzolunk**, és kék vonalat alkalmazunk.

```csharp
// Displace upper-level graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// Draw the rectangle in the current graphics state (has no clipping) above the clipped rectangle
document.Draw(rectanglePath);
```

### 8. lépés: Dokumentum bezárása és mentése

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Most már sikeresen **hozzáadtál egy kivágási útvonalat**, beállítottál egy egyedi festőecsetet, és szaggatott téglalapot rajzoltál a grafikád köré az Aspose.Page for .NET használatával.

## Gyakori problémák és megoldások

- **A kivágás nem látható:** Győződjön meg róla, hogy a `WriteGraphicsSave()`-t a transzformáció előtt, a `WriteGraphicsRestore()`-t a kitöltés után hívja.  
- **Helytelen színek:** Ellenőrizze, hogy a `SetPaint` a `Clip` után és a `Fill` előtt van meghívva.  
- **A szaggatott vonalak szilárdnak tűnnek:** Győződjön meg róla, hogy a `Pen` `DashStyle`-ja `DashStyle.Dash` értékre van állítva a `SetStroke` előtt.  

## Gyakran ismételt kérdések

### Q1: Használhatom az Aspose.Page for .NET-et más programozási nyelvekkel?
A: Az Aspose.Page elsősorban .NET alkalmazásokhoz készült. Azonban az Aspose hasonló könyvtárakat kínál más programozási nyelvekhez is.

### Q2: Hol találok további példákat és dokumentációt az Aspose.Page for .NET-hez?
A: További példákat és részletes dokumentációt a [Aspose.Page dokumentációban](https://reference.aspose.com/page/net/) talál.

### Q3: Elérhető ingyenes próba verzió az Aspose.Page for .NET-hez?
A: Igen, ingyenes próba verziót az Aspose.Page for .NET-hez [itt](https://releases.aspose.com/) érhet el.

### Q4: Hogyan szerezhetek ideiglenes licencet az Aspose.Page for .NET-hez?
A: Ideiglenes licencet [itt](https://purchase.aspose.com/temporary-license/) szerezhet.

### Q5: Hol kaphatok támogatást vagy vitathatok meg Aspose.Page‑hez kapcsolódó kérdéseket?
A: Látogassa meg az [Aspose.Page fórumokat](https://forum.aspose.com/c/page/39) a közösségi támogatás és megbeszélések érdekében.

---

**Last Updated:** 2026-01-05  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}