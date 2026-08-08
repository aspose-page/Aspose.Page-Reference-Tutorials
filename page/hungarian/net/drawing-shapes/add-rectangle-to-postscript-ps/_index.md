---
date: 2026-06-30
description: Ismerje meg, hogyan hozhat létre postscript dokumentumot .NET-ben, és
  adhat hozzá téglalapokat az Aspose.Page for .NET használatával. Lépésről‑lépésre
  útmutató kódrészletekkel.
keywords:
- create postscript document .net
- how to generate postscript file
- Aspose.Page rectangle
linktitle: Téglalap hozzáadása a PostScript (PS) dokumentumhoz
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create postscript document .net and add rectangles using
    Aspose.Page for .NET. Step‑by‑step guide with code samples.
  headline: Create PostScript Document .NET – Add Rectangle Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page for .NET.
    question: What library do I need?
  - answer: Yes – the API lets you build PS files programmatically.
    question: Can I create a PostScript document from scratch?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: Typically under 10 minutes for basic shapes.
    question: How long does the implementation take?
  type: FAQPage
second_title: Aspose.Page .NET API
title: PostScript dokumentum létrehozása .NET – Téglalap hozzáadása Aspose.Page
url: /hu/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Téglalap hozzáadása a PostScript (PS) fájlhoz az Aspose.Page for .NET használatával

## Bevezetés

Az Aspose.Page for .NET egy könyvtár, amely lehetővé teszi a PostScript, EPS és XPS fájlok programozott létrehozását és manipulálását. Ha **postscript dokumentum .net** létrehozására keres megoldást, ez az útmutató végigvezet a téglalapok hozzáadásán egy PostScript dokumentumhoz az Aspose.Page segítségével, és szilárd alapot nyújt a gazdagabb grafika generálásához.

## Gyors válaszok
- **Milyen könyvtárra van szükségem?** Aspose.Page for .NET.  
- **Létrehozhatok egy PostScript dokumentumot a semmiből?** Igen – az API lehetővé teszi a PS fájlok programozott építését.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Szükségem van licencre a fejlesztéshez?** Egy ingyenes próba a teszteléshez működik; licenc szükséges a termeléshez.  
- **Mennyi időt vesz igénybe a megvalósítás?** Általában 10 percnél kevesebb az alap alakzatokhoz.

## Mi a postscript dokumentum .net létrehozása?
A PostScript dokumentum létrehozása .NET-ben azt jelenti, hogy programozott módon generálunk egy `.ps` fájlt, amely leírja az oldal tartalmát – szöveget, grafikát vagy alakzatokat – az Aspose.Page API használatával. Ez a megközelítés ideális szerver‑oldali grafika generálásához, automatizált jelentéskészítéshez, vagy bármely olyan helyzetben, ahol pontos irányítást igényel a kimeneti formátum.

## Miért használjuk az Aspose.Page for .NET-et?
Az Aspose.Page **30+ grafikai primitívát** támogat, és akár **500 MB** méretű fájlokat is képes előállítani anélkül, hogy a teljes dokumentumot a memóriába töltené, így magas teljesítményű renderelést biztosít Windows, Linux és macOS rendszereken. Teljes irányítást ad az alakzatok, színek és vonalstílusok felett, miközben megszünteti az alacsony szintű PostScript kód írásának szükségességét.

- **Teljes irányítás a grafikák felett** – alakzatok rajzolása, színek beállítása és vonalstílusok alkalmazása alacsony szintű PS szintaxis nélkül.  
- **Kereszt‑platform** – működik Windows, Linux és macOS futtatókörnyezetekben.  
- **Nincs külső függőség** – a könyvtár belsőleg kezeli az összes PS generálást.  
- **Gazdag dokumentáció és példák** – gyorsan belevághatsz.

## Előfeltételek

- **Aspose.Page for .NET könyvtár** – töltsd le és telepítsd innen: [here](https://releases.aspose.com/page/net/).  
- **Fejlesztői környezet** – Visual Studio, VS Code vagy bármely .NET‑kompatibilis IDE.

## Névterek importálása

Az `Aspose.Page` névtér elérhetővé teszi a szükséges alap osztályokat, például a `Document`, `Page`, `SolidBrush` és `Pen` osztályokat. Importáld, mielőtt elkezdenéd a kódolást.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Most bontsuk le a példát világos, számozott lépésekre.

## 1. lépés: A dokumentum könyvtár beállítása

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Cseréld le a `"Your Document Directory"`-t arra a mappára, ahol a létrehozott PS fájlt menteni szeretnéd.

## 2. lépés: Kimeneti adatfolyam létrehozása a PostScript dokumentumhoz

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Ez az adatfolyam a **AddRectangle_outPS.ps** fájlra mutat. Nyugodtan átnevezheted a fájlt vagy megváltoztathatod a helyét, ahogy szükséges.

## 3. lépés: Mentési beállítások megadása és a PS dokumentum létrehozása

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Itt megadjuk az Aspose.Page-nek, hogy A4 méretű oldalt használjon, és egyoldalas dokumentumot hozzon létre.

## 4. lépés: Kitöltött téglalap hozzáadása

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

Definiálunk egy téglalapot a (250, 100) koordinátán, 150 szélességgel és 100 magassággal, beállítunk egy narancssárga ecsetet, és kitöltjük az alakzatot.

## 5. lépés: Körvonalas téglalap hozzáadása

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

Egy második téglalap kerül létrehozásra az oldal alján, ezúttal egy piros, 3‑pont vastagságú vonallal.

## 6. lépés: Az oldal lezárása és a dokumentum mentése

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Az oldal lezárása befejezi a rajzolást, és a `Save()` a PS fájlt a lemezre írja.

## Hogyan hozható létre postscript dokumentum .net-ben?
`Document` az Aspose.Page fő osztálya, amely egy PostScript fájlt képvisel. A `SaveOptions` beállításokat ad meg, például az oldal méretét és a kimeneti formátumot. Töltsd be a `Document` objektumot, konfiguráld a `SaveOptions`‑t egy A4-es oldalra, rajzold meg az alakzatokat `SolidBrush` vagy `Pen` segítségével, majd hívd meg a `document.Save()`‑t – a teljes munkafolyamat csak néhány kódsort igényel, és bármely támogatott .NET futtatókörnyezetben fut. Ez a minta lehetővé teszi a teljesen kompatibilis PostScript fájlok generálását anélkül, hogy nyers PS szintaxist kellene használnod.

## Hogyan generáljunk postscript fájlt
Használd az Aspose.Page `SaveOptions` osztályát, hogy a kimeneti formátumot PostScript‑ként (`SaveFormat.PS`) állítsd be. A könyvtár közvetlenül egy fájlba vagy memóriafolyamba streameli a tartalmat, lehetővé téve nagy dokumentumok hatékony előállítását túlzott memóriahasználat nélkül.

## Gyakori problémák és tippek

- **Helytelen fájlútvonal** – Győződj meg róla, hogy a `dataDir` útvonalelválasztóval (`\\` vagy `/`) végződik, vagy használd a `Path.Combine`‑t.  
- **Hiányzó licenc** – Egy termelési környezetben alkalmazd az Aspose licencet a dokumentum létrehozása előtt, hogy elkerüld a kiértékelési vízjeleket.  
- **Szín láthatóság** – Ha a téglalap üresnek tűnik, ellenőrizd, hogy az ecset vagy a toll színei kontrasztban vannak-e az oldal háttérrel.

## Gyakran feltett kérdések

**Q:** Testreszabhatom a téglalapok színeit?  
**A:** Természetesen. Módosítsd a `Color.Orange` vagy `Color.Red` értékeket a `SolidBrush` és `Pen` konstruktorokban bármely általad preferált `System.Drawing.Color` értékre.

**Q:** Az Aspose.Page kompatibilis más dokumentumformátumokkal?  
**A:** Igen. A PostScript mellett az Aspose.Page támogatja az XPS és EPS generálást is.

**Q:** Hogyan adhatok szöveget ugyanahhoz a dokumentumhoz?  
**A:** Használd a `TextFragment` osztályt a szöveg kívánt koordinátákra helyezéséhez, majd hívd meg a `document.Draw(textFragment)`‑t.

**Q:** Hol találok további példákat és a teljes API referenciát?  
**A:** Tekintsd meg a dokumentációt [here](https://reference.aspose.com/page/net/) és csatlakozz a közösséghez az [Aspose.Page fórumon](https://forum.aspose.com/c/page/39).

**Q:** Kipróbálhatom az Aspose.Page‑t vásárlás előtt?  
**A:** Igen, tölts le egy ingyenes próbaverziót [here](https://releases.aspose.com/). Kiterjesztett értékeléshez fontold meg a [temporary license](https://purchase.aspose.com/temporary-license/) lehetőséget.

---

**Utolsó frissítés:** 2026-06-30  
**Tesztelve:** Aspose.Page 24.12 for .NET  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó oktatóanyagok

- [Hogyan hozzunk létre PostScript dokumentumot az Aspose.Page for .NET használatával](/page/net/document-creation/create-postscript-document/)
- [Kép hozzáadása a PostScript (PS) dokumentumhoz az Aspose.Page használatával](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Szöveg hozzáadása a PostScript (PS) dokumentumhoz az Aspose.Page használatával](/page/net/text-manipulation/add-text-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}