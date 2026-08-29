---
date: 2026-04-03
description: Tanulja meg, hogyan adjon hozzá egy átlátszó téglalapot, és alkalmazzon
  Grid Visual Brush‑t .NET‑ben az Aspose.Page használatával lenyűgöző XPS-dokumentumokhoz.
keywords:
- add transparent rectangle
- grid visual brush
- Aspose.Page .NET
linktitle: Rács vizuális ecset alkalmazása
second_title: Aspose.Page .NET API
title: Átlátszó téglalap hozzáadása a Grid Visual Brush segítségével (.NET)
url: /hu/net/visual-brushes/apply-grid-visual-brush/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Átlátszó téglalap hozzáadása Grid Visual Brush segítségével (.NET)

## Bevezetés

Ha **átlátszó téglalapot** szeretnél hozzáadni egy XPS dokumentumhoz, miközben egy elegáns Grid Visual Brush‑t is alkalmazol, jó helyen jársz. Ebben az útmutatóban végigvezetünk a szükséges lépéseken az Aspose.Page for .NET segítségével, hogy vizuálisan gazdag dokumentumokat hozz létre, amelyek kiemelkednek. A végére egy teljes, futtatható példát kapsz, amely mindkét technikát egyetlen, könnyen követhető munkafolyamatban mutatja be.

## Gyors válaszok
- **Mi a feladata egy átlátszó téglalapnak?** Egy félig átlátszó fedést ad hozzá, amely lehetővé teszi, hogy a háttér tartalma átlátszódjon.  
- **Melyik API hozza létre a ecsetet?** `XpsDocument.CreateVisualBrush` építi fel a Grid Visual Brush‑t.  
- **Szükségem van licencre?** Egy ingyenes próba verzió teszteléshez megfelelő; a termeléshez kereskedelmi licenc szükséges.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 10‑15 perc egy alap példához.

## Mi az az átlátszó téglalap az XPS-ben?
Az átlátszó téglalap egyszerűen egy olyan alakzat, amelynek kitöltő színe alfa komponensben 1.0-nál kisebb értéket tartalmaz, így az alatta lévő grafika részben látható marad. Ez tökéletes a szakaszok kiemelésére anélkül, hogy teljesen eltakarná a hátteret.

## Miért használjunk Grid Visual Brush‑t?
A Grid Visual Brush lehetővé teszi, hogy egy kis vektorgrafikát ismételjünk egy nagyobb területen, ezzel mintákat hozva létre, például rácsot, keresztmintát vagy egyedi textúrákat. Az átlátszó téglalappal kombinálva réteges vizuális hatásokat kapunk, amelyek könnyűek és felbontásfüggetlenek.

## Előfeltételek

Mielőtt belemerülnél a kódba, győződj meg róla, hogy rendelkezel:

- **Aspose.Page for .NET** – letöltheted [itt](https://releases.aspose.com/page/net/).  
- Egy .NET fejlesztői környezettel (Visual Studio, VS Code vagy bármely kedvelt IDE).  
- Egy mappával, ahová a generált XPS fájlok mentésre kerülnek.

## Névterek importálása

A C# fájlodban importáld a szükséges névtereket:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Most bontsuk le a megoldást világos, számozott lépésekre.

## 1. lépés: XpsDocument inicializálása

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

Először létrehozunk egy `XpsDocument` példányt, amely a további rajzolási műveleteket fogja tartalmazni.

## 2. lépés: Magenta rács geometria létrehozása

```csharp
// ExStart:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExEnd:4
```

Ez a geometria meghatározza a rács körvonalát, amelyet a vizuális ecset kitölt.

## 3. lépés: Magenta rács VisualBrush tervezése

```csharp
// ExStart:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExEnd:5
```

Itt egy kis magenta csempét rajzolunk, amely a rácson ismétlődni fog.

## 4. lépés: VisualBrush alkalmazása a rácsra

```csharp
// ExStart:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExEnd:6
```

A `CreateVisualBrush` hívás összekapcsolja a magenta csempét a rács geometriával, és engedélyezi a csempézést.

## 5. lépés: Rács hozzáadása a vászonhoz

```csharp
// ExStart:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExEnd:7
```

A csempézett rácsot egy vászonra helyezzük, és egy transzlációs transzformációt alkalmazunk, hogy a kívánt helyen jelenjen meg.

## 6. lépés: Átlátszó téglalap hozzáadása

```csharp
// ExStart:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f; // This opacity makes the rectangle transparent
// ExEnd:8
```

Ebben a lépésben **átlátszó téglalapot adunk hozzá** (a piros alakzat `Opacity = 0.7f` értékkel). Állítsd be az átlátszóság értékét, hogy szabályozd, mennyire átlátszó a téglalap.

## 7. lépés: Dokumentum mentése

```csharp
// ExStart:9
doc.Save(dataDir + "AddGrid_out.xps");
// ExEnd:9
```

Az XPS fájl a korábban megadott mappába kerül mentésre.

## Gyakori felhasználási esetek

- **Jelentés kiemelése:** Egy félig átlátszó téglalap rétegezése egy diagram vagy táblázat hangsúlyozásához.  
- **Vízjel hatás:** Egy csempézett rács kombinálása átlátszó átfedéssel a finom márkajelzéshez.  
- **Interaktív PDF/XPS:** A mintát háttérként használni űrlapmezőkhöz, miközben az UI olvasható marad.

## Hibaelhárítási tippek

- **Az átlátszóság nem látható?** Győződj meg róla, hogy a megjelenítő támogatja az XPS átlátszóságot; néhány régebbi megjelenítő figyelmen kívül hagyhatja az `Opacity` tulajdonságot.  
- **Helytelen csempe méret?** Ellenőrizd, hogy a forrás téglalap (`new RectangleF(0f, 0f, 10f, 10f)`) megegyezik-e a vektor csempe méreteivel.  
- **A fájl nem mentődik?** Ellenőrizd, hogy a `dataDir` egy létező, írható könyvtárra mutat.

## Gyakran ismételt kérdések

**Q: Használhatom az Aspose.Page for .NET-et web‑ és asztali alkalmazásokban is?**  
A: Igen, a könyvtár minden .NET alkalmazástípusban működik.

**Q: Van elérhető próba verzió a vásárlás előtt?**  
A: Természetesen, a ingyenes próbát [itt](https://releases.aspose.com/) érheted el.

**Q: Hol találok további támogatást vagy közösségi megbeszéléseket?**  
A: Látogasd meg az [Aspose.Page Fórumot](https://forum.aspose.com/c/page/39) a közösség és az Aspose mérnökök segítségéért.

**Q: Hogyan szerezhetek ideiglenes licencet értékeléshez?**  
A: Ideiglenes licencet [itt](https://purchase.aspose.com/temporary-license/) szerezhetsz.

**Q: Milyen egyéb dokumentáció érhető el az Aspose.Page for .NET-hez?**  
A: Tekintsd meg a részletes dokumentációt [itt](https://reference.aspose.com/page/net/).

---

**Utoljára frissítve:** 2026-04-03  
**Tesztelve:** Aspose.Page 24.12 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}