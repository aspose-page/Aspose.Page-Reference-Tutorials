---
date: 2026-02-20
description: Ismerje meg, hogyan állíthatja be a szöveg színét Java-ban az Aspose.Page
  for Java segítségével, hogyan változtathatja meg a betűméretet Java-ban, hogyan
  generálhat PostScript fájlt, hogyan töltheti ki és vonalazhatja a szöveget, valamint
  hogyan használhat egyedi betűtípusokat Java-ban egy PostScript dokumentum létrehozása
  során.
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: Szöveg színének beállítása Java-ban az Aspose.Page használatával – Szövegmanipulációs
  útmutató
url: /hu/java/postscript-text-manipulation/add-text/
weight: 10
---

 produce final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Szöveg szín beállítása Java-val az Aspose.Page használatával – Szövegmanipulációs útmutató

## Bevezetés
Üdvözöljük lépésről‑lépésre útmutatónkban, amely a **set text color java** témakörét tárgyalja PostScript fájlok kezelésekor az Aspose.Page for Java segítségével. Az Aspose.Page for Java egy erőteljes könyvtár, amely lehetővé teszi a fejlesztők számára **postscript dokumentum** fájlok létrehozását, betűtípusok manipulálását és a szöveg stílusának precíz beállítását. Ebben a tutorialban megtanulja, hogyan adjon szöveget, változtassa meg annak színét, **change font size java**, és akár **apply fill and stroke text** is alkalmazzon a professzionális megjelenés érdekében.

## Gyors válaszok
- **Melyik könyvtár teszi lehetővé a szöveg színének beállítását Java-ban?** Aspose.Page for Java.  
- **Használhatok rendszer‑ és egyedi betűtípusokat?** Igen, mindkettő támogatott, és **use custom fonts java** könnyedén alkalmazható.  
- **Hogyan változtathatom meg a szöveg méretét?** A betűméret megadásával a `Font` vagy `DrFont` létrehozásakor.  
- **Lehet-e egyszerre körvonalazni és kitölteni a szöveget?** Természetesen – használja a `fillAndStrokeText` metódust.  
- **Milyen kimeneti formátumot állít elő ez a tutorial?** Egy PostScript (`.ps`) dokumentumot, amelyet **generate postscript file** programozottan hozhat létre.

## Mi az a “set text color java”?
A szöveg színének beállítása Java-ban azt jelenti, hogy definiáljuk a `Color` objektumot, amelyet a renderelő motor (jelen esetben az Aspose.Page) a karakterek oldalra rajzolásakor használ. Ez a művelet elengedhetetlen a vizuálisan megkülönböztethető dokumentumok létrehozásához, különösen akkor, amikor **generate postscript file** programozottan kell előállítani.

## Miért használjuk az Aspose.Page for Java‑t?
- **Teljes irányítás** a PostScript generálása felett anélkül, hogy natív interpreterre lenne szükség.  
- **Támogatás rendszer‑ és külső betűtípusokra**, így bármilyen tipográfiát beágyazhat.  
- **Egyszerű API** a kitöltéshez, körvonalazáshoz és **fill and stroke text** alkalmazásához, amely rugalmasságot biztosít a stílusban.  
- **Kereszt‑platform** kompatibilitás – írjon egyszer, futtassa bárhol, ahol Java elérhető.  

## Előfeltételek
Mielőtt belevágna, győződjön meg róla, hogy rendelkezik:

- Alapvető Java programozási ismeretekkel.  
- Az Aspose.Page for Java könyvtárral telepítve. Letöltheti a [Aspose.Page for Java letöltő oldaláról](https://releases.aspose.com/page/java/).  
- A szükséges betűtípusokkal a megadott mappában. További részletek a [Aspose.Page for Java dokumentációjában](https://reference.aspose.com/page/java/).  

## Csomagok importálása
A Java projektjében importálja a szükséges Aspose.Page for Java csomagokat:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```

## 1. lépés: Dokumentum előkészítése
Először hozzunk létre egy új **PostScript dokumentumot**, és állítsuk be a kimeneti opciókat.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// A text to write to PS file
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Hogyan állítsuk be a szöveg színét Java‑ban rendszerbetűtípussal
Most bemutatjuk a **set text color java** műveletet egy rendszer‑által biztosított betűtípussal.

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **Tipp:** A `fillText` metódus automatikusan az aktuális színt használja, ha nem adunk meg `Color` argumentumot, amely alapértelmezés szerint fekete.

## Egyedi betűtípus használata és a szöveg méretének módosítása
Emellett **change font size java** is elvégezhető, és egy egyedi betűtípust is használhat a betűk mappájában tárolt fájlból.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Szöveg körvonalazása (Stroke) – Stroke szöveg alkalmazása
A szöveg körvonalazása éles határt ad. Itt **apply stroke text**-et használunk egy `BasicStroke` segítségével.

```java
// Using system font for outlining text
document.outlineText(str, font, 50, 300);
// Outline text with blue‑violet colored 2‑points width pen
Stroke stroke = new BasicStroke(2);
Color strokeColor = new Color(138, 43, 226); // blue‑violet
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```

## Szöveg körvonalazása egyedi betűtípussal
Ugyanez a technika alkalmazható egyedi betűtípusok esetén is.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## 6. lépés: Dokumentum mentése
Végül zárjuk le az oldalt, és írjuk a fájlt a lemezre.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Miért fontos ez
A **set text color java** és a kitöltés‑körvonal kombinációjának ismerete teljes művészi irányítást biztosít a végső PostScript kimenet felett. Legyen szó számlák, bizonyítványok vagy egyedi grafikák generálásáról, a **create postscript document** fájlok pontos stílusú előállítása csökkenti a grafikus szerkesztőkkel való utómunka szükségességét.

## Gyakori problémák és megoldások
| Probléma | Megoldás |
|----------|----------|
| **Betűtípus nem található** | Győződjön meg róla, hogy a betűfájl a `necessary_fonts` mappában van, és a mappa útvonalát helyesen adta meg az `options.setAdditionalFontsFolders` segítségével. |
| **A szín nem jelenik meg** | Ellenőrizze, hogy a `fillText` vagy `outlineText` megfelelő, `Color` argumentummal rendelkező változatát hívja. |
| **A körvonal túl vékony** | Növelje a `BasicStroke` szélességét (pl. `new BasicStroke(3)`). |
| **A dokumentum nem nyílik meg** | Ellenőrizze, hogy a generált `.ps` fájl a megfelelő kiterjesztéssel van mentve, és hogy a megjelenítő program támogatja a PostScriptet. |

## Gyakran feltett kérdések

**K:** Használhatok saját egyedi betűtípusokat az Aspose.Page for Java‑val?  
**V:** Igen, **use custom fonts java**-t megadhatja a betűtípus nevét és méretét a `DrFont` osztályban.

**K:** Hogyan változtathatom meg a szöveg színét?  
**V:** A kívánt színt a `Color` osztály segítségével állíthatja be a szöveg kitöltésekor vagy körvonalazásakor.

**K:** Lehet-e több oldalt hozzáadni egy PostScript dokumentumhoz?  
**V:** Természetesen! Több oldalt hozhat létre a dokumentum létrehozási és mentési lépések ismétlésével.

**K:** Mi a `ExternalFontCache` osztály célja?  
**V:** Az `ExternalFontCache` arra szolgál, hogy egyedi betűtípusokat töltsön be, biztosítva azok elérhetőségét a szövegmanipuláció során.

**K:** Alkalmazhatok különböző körvonalakat a körvonalazott szövegre?  
**V:** Igen, a `Stroke` osztály és a `Color` osztály segítségével testreszabhatja a körvonal szélességét és színét.

## Összegzés
Gratulálunk! Most már tudja, hogyan **set text color java**, **change font size java**, **apply fill and stroke text**, és **create postscript document** fájlokat készíthet az Aspose.Page for Java segítségével. Kísérletezzen különböző betűtípusokkal, színekkel és körvonalstílusokkal, hogy professzionális megjelenésű PostScript kimenetet érjen el.

---

**Utoljára frissítve:** 2026-02-20  
**Tesztelt verzió:** Aspose.Page for Java 23.12 (legújabb)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}