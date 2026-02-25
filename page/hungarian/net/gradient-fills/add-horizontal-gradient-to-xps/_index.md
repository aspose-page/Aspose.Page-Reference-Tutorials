---
date: 2026-02-25
description: Tanulja meg, hogyan hozhat létre XPS színátmenetet vízszintes kitöltéssel
  az Aspose.Page for .NET segítségével. Emelje vizuális megjelenését könnyedén dokumentumaiban.
linktitle: Add Horizontal Gradient to XPS
second_title: Aspose.Page .NET API
title: 'XPS-színátmenet létrehozása: vízszintes kitöltés az Aspose.Page for .NET segítségével'
url: /hu/net/gradient-fills/add-horizontal-gradient-to-xps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS Gradient létrehozása – Vízszintes gradient hozzáadása XPS-hez az Aspose.Page for .NET segítségével

## Bevezetés

Ebben az útmutatóban **XPS gradient** kitöltéseket hozunk létre, amelyek vízszintesen futnak az oldalak mentén. Egy vízszintes gradient hozzáadása azonnal professzionálisabbá és vonzóbbá teheti az XPS dokumentumot, különösen jelentések, prospektusok vagy bármilyen vizuálisan gazdag kimenet esetén. Végigvezetünk a teljes folyamaton az Aspose.Page for .NET használatával, a környezet beállításától a végleges XPS fájl mentéséig.

## Gyors válaszok
- **Miről szól ez az útmutató?** Ví­zszintes gradient hozzáadása XPS dokumentumhoz az Aspose.Page for .NET segítségével.  
- **Melyik könyvtár szükséges?** Aspose.Page for .NET (bármely friss verzió).  
- **Szükség van licencre?** Fejlesztéshez egy próba verzió működik; termeléshez kereskedelmi licenc szükséges.  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 5–10 perc egy alap gradienthez.  
- **Módosítható a gradient iránya?** Igen – a `LinearGradientBrush` kezdő‑ és végpontjainak módosításával.

## Hogyan hozzunk létre XPS gradientet az Aspose.Page for .NET segítségével

Az alábbiakban egy lépésről‑lépésre útmutatót találsz, amely elmagyarázza, **miért** létezik minden kódsor, nem csak **mit** csinál. Nyugodtan kövesd Visual Studio‑ban vagy a kedvenc .NET szerkesztődben.

## Előkövetelmények

Mielőtt elkezdenénk, győződj meg róla, hogy a következő előkövetelmények rendelkezésre állnak:

1. Aspose.Page for .NET Library: Győződj meg arról, hogy az Aspose.Page for .NET könyvtár telepítve van a fejlesztői környezetedben. Letöltheted a [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/) oldalról.

2. Development Environment: Állíts be egy megfelelő fejlesztői környezetet, beleértve egy kódszerkesztőt, például a Visual Studio‑t.

## Névterek importálása

Kezdjük a szükséges névterek importálásával a projektedbe. Ezek a névterek elengedhetetlenek az Aspose.Page for .NET használatához:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Most bontsuk le a megadott példát több lépésre.

## 1. lépés: A dokumentum könyvtár útvonalának beállítása

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## 2. lépés: Új XPS dokumentum létrehozása

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## 3. lépés: Gradient állomások inicializálása

```csharp
// ExStart:5
// Initialize List of XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## 4. lépés: Új útvonal létrehozása

```csharp
// ExStart:6
// Create new path by defining geometry in abbreviation form
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## 5. lépés: Az eredmény XPS dokumentum mentése

```csharp
// ExStart:7
// Save resultant XPS document
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

Most sikeresen hozzáadtál egy vízszintes gradientet az XPS dokumentumodhoz az Aspose.Page for .NET segítségével.

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| A gradient egyszínűnek tűnik | Gradient állomásokat nem adták hozzá helyesen | Győződj meg arról, hogy a `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` a ecset beállítása után kerül végrehajtásra. |
| A mentett fájl üres | `dataDir` egy nem létező mappára mutat | Ellenőrizd, hogy a mappa létezik, vagy használj abszolút útvonalat. |
| Fordítási hiba a `PointF`-nél | `System.Drawing` hivatkozás hiányzik | Adj hozzá hivatkozást a `System.Drawing.Common`-hoz (a .NET Core/5+ esetén). |

## GYIK

### Q1: Hol találom az Aspose.Page for .NET dokumentációt?

A1: A dokumentációt [itt](https://reference.aspose.com/page/net/) találod.

### Q2: Hogyan tölthetem le az Aspose.Page for .NET-et?

A2: A könyvtárat a [Aspose.Page for .NET letöltési oldalról](https://releases.aspose.com/page/net/) töltheted le.

### Q3: Hol vásárolhatom meg az Aspose.Page for .NET-et?

A3: Az Aspose.Page for .NET-et a [vásárlási oldalon](https://purchase.aspose.com/buy) vásárolhatod meg.

### Q4: Van ingyenes próba?

A4: Igen, ingyenes próbaverziót [itt](https://releases.aspose.com/) kaphatsz.

### Q5: Hogyan szerezhetek ideiglenes licencet az Aspose.Page for .NET-hez?

A5: Ideiglenes licencet a [következő linken](https://purchase.aspose.com/temporary-license/) szerezhetsz be.

## Gyakran Ismételt Kérdések

**Q: Használhatom ezt a gradient technikát olyan XPS dokumentumokkal, amelyek már tartalmaznak képeket?**  
**A:** Természetesen. A gradient egy útvonal rétegre kerül alkalmazásra, így a meglévő képek érintetlenek maradnak.

**Q: Lehet-e helyette függőleges gradientet létrehozni?**  
**A:** Igen. A `LinearGradientBrush` kezdő‑ és végpontjainak Y‑koordinátáit módosítva, az X‑et állandóan tartva, függőleges gradientet hozhatsz létre.

**Q: Támogatja-e az Aspose.Page a .NET Core‑t?**  
**A:** A könyvtár teljes mértékben kompatibilis a .NET Core‑dal, a .NET 5‑tel és az újabb verziókkal.

**Q: Hogyan használhatom újra ugyanazt a gradientet több oldalon?**  
**A:** Hozd létre egyszer az `XpsLinearGradientBrush`‑t, tárold változóban, és minden oldal útvonalához rendeld hozzá.

## Összegzés

Az XPS dokumentumok gradientekkel való gazdagítása nemcsak a vizuális vonzerőt növeli, hanem egy vonzóbb felhasználói élményt is nyújt. Az Aspose.Page for .NET segítségével **XPS gradient** kitöltéseket hozhatsz létre gyorsan és megbízhatóan, így jelentéseid, prospektusaid vagy e‑könyveid professzionális megjelenést kapnak.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Legutóbb frissítve:** 2026-02-25  
**Tesztelve ezzel:** Aspose.Page for .NET 24.11  
**Szerző:** Aspose  

---