---
date: 2026-03-21
description: Tanulja meg, hogyan töltsön ki szöveget és adjon szöveget PS-dokumentumokhoz
  az Aspose.Page for .NET használatával. Lépésről‑lépésre útmutató kódrészletekkel.
linktitle: Add Text to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Hogyan töltsünk ki szöveget PostScript (PS) dokumentumokban az Aspose.Page
  segítségével
url: /hu/net/text-manipulation/add-text-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan töltsünk ki szöveget PostScript (PS) dokumentumokban az Aspose.Page segítségével

## Bevezetés

Ha **szöveget kell kitölteni** egy PostScript (PS) fájlban, az Aspose.Page for .NET egyszerűvé teszi ezt. Akár jelentéseket, számlákat vagy egyedi grafikákat generálsz, a szöveg hozzáadása és formázása alapvető követelmény. Ebben az útmutatóban végigvezetünk a teljes folyamaton – a környezet beállításától a végleges PS dokumentum mentéséig – hogy magabiztosan tudj szöveget hozzáadni PS fájlokhoz .NET alkalmazásaidban.

## Gyors válaszok
- **Mit jelent a „fill text”?** A karaktereket egy szilárd ecsettel rendereli, közvetlenül a lapra festve a glifeket.  
- **Használhatok egyedi betűtípusokat?** Igen – az Aspose.Page támogatja az egyedi betűtípusokat a `add custom font ps` funkción keresztül.  
- **Hogyan mentem a PS dokumentumot?** A `document.Save()` hívásával a lap lezárása után; ez a fájlt a lemezre írja (`save ps document`).  
- **Támogatja a „fill and stroke text” funkciót?** Természetesen; használd a `FillAndStrokeText`-et a kitöltés és a körvonal egyidejű alkalmazásához.  
- **Milyen .NET verziók szükségesek?** Bármely .NET Framework 4.5+ vagy .NET Core/5/6+ futtatókörnyezet.

## Mi az a „how to fill text” egy PS dokumentumban?

A szöveg kitöltése azt jelenti, hogy a karaktereket egy szilárd színnel (vagy ecsettel) festjük meg körvonal nélkül. PostScriptben ez a `fill` operátornak felel meg. Az Aspose.Page ezt egyszerűen használható metódusokba, például `FillText` és `FillAndStrokeText`-be absztrahálja.

## Miért használjuk az Aspose.Page-et egyedi betűtípusok PS-hez való hozzáadásához?

- **Teljes betűtípus támogatás** – a rendszerbetűtípusok és külső TrueType/OpenType betűtípusok azonnal működnek.  
- **Pontos pozicionálás** – szabályozhatod az X/Y koordinátákat, méretet és stílust.  
- **Gazdag stílus** – kombinálhatod a kitöltéseket, körvonalakat és tollakat olyan hatásokhoz, mint a „fill and stroke text”.  
- **Keresztplatformos** – ugyanazzal az API-val működik Windows, Linux és macOS rendszereken.

## Előkövetelmények

Mielőtt elkezdenéd, győződj meg róla, hogy rendelkezel a következőkkel:

- **Aspose.Page for .NET** – töltsd le a könyvtárat a [Aspose.Page .NET dokumentációból](https://reference.aspose.com/page/net/).  
- **Dokumentum könyvtár** – egy mappa a gépeden, ahol a forrás- és kimeneti PS fájlok tárolódnak (a kódban *Your Document Directory*-ként hivatkozva).  
- **Betűtípusok mappa** – egy alkönyvtár, amely a használni kívánt egyedi betűtípusokat tartalmazza.

## Névterek importálása

Először importáld a szükséges névtereket, hogy a fordító tudja, hol találja a használandó osztályokat:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Lépésről‑lépésre útmutató

### 1. lépés: Kimeneti stream létrehozása PS dokumentumhoz  

Megnyitunk egy `FileStream`-et, amely a generált PS fájlt tárolja, beállítjuk a `PsSaveOptions`-t, hogy az egyedi betűtípusok mappájára mutasson, és példányosítunk egy `PsDocument`-et.

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

> **Pro tipp:** Tartsd meg a `using` blokkot, hogy a stream automatikusan lezáródjon, ami egyben befejezi a PS fájlt is (`save ps document`).

### 2. lépés: Szöveg kitöltése rendszerbetűtípussal  

Itt bemutatjuk az alap **szöveg kitöltése** műveletet a beépített *Times New Roman* betűtípussal.

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

### 3. lépés: Szöveg kitöltése egyedi betűtípussal  

Ha egyedi megjelenésre van szükséged, tölts be egy egyedi betűtípust a betűtípusok mappájából a `ExternalFontCache.FetchDrFont` használatával. Ez teljesíti a **add custom font ps** követelményt.

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

### 4. lépés: Szöveg körvonalazása (stroke) rendszerbetűtípussal  

A körvonalazás a glif kontúrját rajzolja. Kombináld egy kitöltéssel a „fill and stroke” hatás eléréséhez.

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

> **Miért fontos:** A `FillAndStrokeText` hívás megmutatja, hogyan **fill and stroke text** egyetlen lépésben, gazdagabb tipográfiai irányítást biztosítva.

### 5. lépés: Szöveg körvonalazása egyedi betűtípussal  

Ugyanaz a körvonalazási technika működik bármely betöltött egyedi betűtípussal.

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

### 6. lépés: Oldal lezárása és a dokumentum mentése  

A befejezés egyszerű: zárd le az aktuális oldalt, és hívd meg a `Save()`-et a PS fájl lemezre írásához.

```csharp
document.ClosePage();
document.Save();
}
```

> **Eredmény:** A `AddText_outPS.ps` fájlt megtalálod a *Your Document Directory*-ben, amely mind a kitöltött, mind a körvonalazott szöveget tartalmazza, rendszer- és egyedi betűtípusokkal renderelve.

## Gyakori problémák és megoldások

| Probléma | Megoldás |
|----------|----------|
| **Egyedi betűtípus nem található** | Ellenőrizd, hogy a betűtípusfájl (.ttf/.otf) létezik-e a `AdditionalFontsFolders` által hivatkozott mappában. |
| **A szöveg rossz helyen jelenik meg** | Állítsd be a `FillText`/`OutlineText`-nek átadott X/Y koordinátákat. Ne feledd, hogy a PostScript pontokat (1/72 hüvelyk) használ. |
| **A színek másként jelennek meg** | Győződj meg róla, hogy a megfelelő `Color` értékekkel használod a `SolidBrush` vagy `Pen`-t. |
| **A dokumentum nem mentődik** | Erősítsd meg, hogy a `using` blokk kivétel nélkül befejeződik, és az alkalmazásnak írási jogosultsága van a célmappához. |

## Gyakran Ismételt Kérdések

**K: Használhatom az Aspose.Page-et más .NET könyvtárakkal?**  
V: Igen, az Aspose.Page zökkenőmentesen integrálódik más .NET komponensekkel, lehetővé téve PDF, kép vagy diagram könyvtárak kombinálását ugyanabban a megoldásban.

**K: Elengedhetetlenek az egyedi betűtípusok ehhez a folyamathoz?**  
V: Bár a rendszerbetűtípusok is működnek, az egyedi betűtípusok teljes tervezési szabadságot biztosítanak, és hasznosak, ha márka‑specifikus tipográfiára van szükség.

**K: Az Aspose.Page alkalmas nagyszabású dokumentumfeldolgozásra?**  
V: Teljes mértékben. A könyvtár nagy áteresztőképességű szcenáriókra van optimalizálva, és hatékonyan képes több ezer PS fájlt kezelni.

**K: Módosíthatom a szöveg pozícióját a PS dokumentumban?**  
V: Természetesen – egyszerűen változtasd meg a numerikus X/Y értékeket a `FillText` vagy `OutlineText` hívásokban.

**K: Hol kérhetek segítséget az Aspose.Page‑hez kapcsolódó kérdésekben?**  
V: Látogasd meg az [Aspose.Page Fórumot](https://forum.aspose.com/c/page/39), hogy a közösséggel kapcsolatba léphess és szakértői segítséget kapj.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose