---
date: 2026-02-25
description: Tanulja meg, hogyan hozhat létre XPS dokumentumot, és alkalmazhat lineáris
  gradientet az Aspose.Page for .NET segítségével. Kövesse lépésről‑lépésre útmutatónkat
  az XPS fájl mentéséhez.
linktitle: Add Vertical Gradient to XPS
second_title: Aspose.Page .NET API
title: XPS-dokumentum létrehozása függőleges színátmenettel az Aspose.Page segítségével
url: /hu/net/gradient-fills/add-vertical-gradient-to-xps/
weight: 15
---

 to translate shortcodes.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Függőleges színátmenet hozzáadása XPS-hez az Aspose.Page for .NET segítségével

## Introduction

Ebben a tutorialban **XPS dokumentumot hozol létre**, amely egy sima függőleges színátmenetet tartalmaz. A színátmenetek hozzáadása gyakori módja annak, hogy az XPS fájlok professzionálisabb megjelenést kapjanak – tökéletes jelentésekhez, brosúrákhoz vagy bármilyen nyomtatható grafikához. Lépésről lépésre végigvezetünk a projekt beállításától a végleges XPS fájl mentéséig, hogy gyorsan alkalmazhass egy lineáris színátmenetet bármely útvonalra.

## Quick Answers
- **Mi a tutorial témája?** Függőleges lineáris színátmenet hozzáadása egy útvonalhoz egy XPS dokumentumban.  
- **Melyik könyvtár szükséges?** Aspose.Page for .NET.  
- **Szükségem van licencre?** A fejlesztéshez ingyenes próba verzió működik; a termeléshez kereskedelmi licenc szükséges.  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 10‑15 perc egy alap példához.  
- **Menthetem az eredményt XPS fájlként?** Igen, a `Save` metódus a fájlt a lemezre írja.

## What is a vertical gradient in XPS?

A függőleges színátmenet egy olyan színátmenet, amely a forma tetejétől az aljáig fut. XPS-ben ezt egy **lineáris színátmenet ecset** valósítja meg, amely meghatározza a kezdő‑ és végpontokat, valamint egy színátmeneti állomások gyűjteményét, amelyek a színeket a meghatározott pozíciókban szabályozzák.

## Why use Aspose.Page to create XPS document with gradients?

- **Teljes .NET integráció** – működik .NET Framework, .NET Core és .NET 5/6+ környezetekkel.  
- **Nincs külső függőség** – a teljes renderelés a könyvtár által történik.  
- **Magas hűség** – a színátmenetek pontosan úgy jelennek meg, ahogy definiálták, megfelelve az XPS specifikációnak.  
- **Könnyen karbantartható** – tiszta objektummodell útvonalakhoz, ecsetekhez és színekhez.

## Prerequisites

- Aspose.Page for .NET Library: Győződj meg arról, hogy az Aspose.Page for .NET könyvtár telepítve van a fejlesztői környezetedben. Letöltheted [itt](https://releases.aspose.com/page/net/).  
- Fejlesztői környezet: Állíts be egy .NET fejlesztői környezetet a kedvenc IDE-d, például a Visual Studio használatával.

Most, hogy minden készen áll, merüljünk el a kódban.

## Import Namespaces

A .NET alkalmazásodban add hozzá a szükséges névtereket az Aspose.Page osztályok és metódusok eléréséhez.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Step 1: Set Up Your Document Directory

Határozd meg a mappát, ahová a generált XPS fájlt menteni fogod.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Step 2: Create a New XPS Document

Hozz létre egy új XPS dokumentumot, amelyet később egy színátmenettel kitöltött útvonallal fogunk feltölteni.

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Step 3: Define Gradient Stops

A színátmeneti állomások határozzák meg a színeket és azok pozícióját a színátmeneti vonalon. Itt öt állomást hozunk létre a sima függőleges átmenet érdekében.

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExEnd:5
```

## Step 4: Create a Path with Gradient

Rajzolunk egy téglalap alakú útvonalat, és alkalmazunk egy **lineáris színátmenet ecsetet**, amely függőlegesen fut a (10, 110) ponttól a (10, 200) pontig. Az ecset megkapja a korábban definiált színátmeneti állomásokat.

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Step 5: Save the Resultant XPS Document

Végül írd a XPS dokumentumot a lemezre. Ez a **save XPS file** lépés létrehozza a `AddVerticalGradient_outXPS.xps` fájlt a megadott mappában.

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

**Pro tip:** Ellenőrizd a kimenetet úgy, hogy megnyitod az XPS fájlt a Windows XPS Viewerben vagy bármely harmadik fél által biztosított megjelenítőben, hogy megbizonyosodj róla, a színátmenet a várt módon jelenik meg.

## Common Issues & Troubleshooting

| Tünet | Valószínű ok | Megoldás |
|---------|--------------|-----|
| A színátmenet egyszínűként jelenik meg | A színátmeneti állomásokat nem adták hozzá az ecsethez | Győződj meg arról, hogy a `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` végrehajtásra került. |
| Fájl nem található mentéskor | `dataDir` egy nem létező mappára mutat | Először hozd létre a könyvtárat, vagy használj abszolút elérési utat. |
| A színek másként néznek ki | A színértékek ARGB sorrendet használnak; ellenőrizd a csatornasorrendet | Használd a `CreateColor(alpha, red, green, blue)` függvényt helyesen. |

## Frequently Asked Questions

**Q: Az Aspose.Page kompatibilis a Visual Studio 2019-vel?**  
A: Igen, az Aspose.Page kompatibilis a Visual Studio 2019-vel. Győződj meg arról, hogy a könyvtár megfelelő verziója van telepítve.

**Q: Használhatom az Aspose.Page-et kereskedelmi projektekhez?**  
A: Igen, az Aspose.Page használható kereskedelmi projektekhez. Látogass el [ide](https://purchase.aspose.com/buy) a licencelési lehetőségek megtekintéséhez.

**Q: Elérhető ingyenes próba?**  
A: Igen, az Aspose.Page ingyenes próbaverziója [itt](https://releases.aspose.com/) letölthető.

**Q: Hol találom az Aspose.Page dokumentációját?**  
A: A dokumentáció [itt](https://reference.aspose.com/page/net/) érhető el.

**Q: Hogyan kaphatok támogatást vagy tehetek fel kérdéseket?**  
A: Látogasd meg az [Aspose.Page fórumot](https://forum.aspose.com/c/page/39) a közösségi támogatásért.

## Conclusion

Most már tudod, hogyan **hozz létre XPS dokumentumot**, **alkalmazz lineáris színátmenetet**, és **ments XPS fájlt** az Aspose.Page for .NET segítségével. Ez a megközelítés teljes irányítást ad a vizuális stílus felett az XPS kimenetekben, így nyomtatható dokumentumaid kitűnnek.

---  

**Utolsó frissítés:** 2026-02-25  
**Tesztelve ezzel:** Aspose.Page for .NET 24.11  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}