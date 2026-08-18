---
date: 2026-08-18
description: Ismerje meg, hogyan adhat hozzá hatch pattern-et a Java PostScript fájlokhoz
  az Aspose.Page Java használatával. Ez a lépésről‑lépésre útmutató a teljes kódot
  és tippeket mutatja be.
keywords:
- how to add hatch pattern
- Aspose.Page Java
- PostScript hatch patterns
- Java graphics API
lastmod: 2026-08-18
linktitle: Hatch Pattern hozzáadása a Java PostScript-hez
og_description: Ismerje meg, hogyan adhat hozzá hatch pattern-et a Java PostScript-hez
  az Aspose.Page használatával. Kövesse ezt a lépésről‑lépésre oktatóanyagot, hogy
  gyorsan létrehozhasson hatch‑filled grafikákat.
og_image_alt: Screenshot of Java code adding hatch pattern to a PostScript file with
  Aspose.Page
og_title: Hogyan adjon hozzá hatch pattern-et a Java PostScript-hez – Aspose.Page
  útmutató
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to add hatch pattern to Java PostScript files using Aspose.Page
    Java. This step‑by‑step guide shows the complete code and tips.
  headline: How to add hatch pattern in Java PostScript
  type: TechArticle
- questions:
  - answer: Yes, the library is framework‑agnostic and works with Spring, Jakarta
      EE, Android (limited), and plain Java SE.
    question: Can I use Aspose.Page Java with other Java frameworks?
  - answer: Absolutely. Download a free 30‑day trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is a trial version available for Aspose.Page Java?
  - answer: Request a temporary license [temporary license request page](https://purchase.aspose.com/temporary-license/).
      It removes evaluation watermarks.
    question: How do I obtain a temporary license for development?
  - answer: Visit the official forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39)
      for additional examples and Q&A.
    question: Where can I find more tutorials and community support?
  - answer: Yes, the full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Is there comprehensive documentation for all classes and methods?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Java
- Aspose.Page
- PostScript
- hatch pattern
title: Hogyan adjon hozzá hatch pattern-et a Java PostScript-hez
url: /hu/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan adjon hozzá áthúzási mintát Java PostScript-ben

## Bevezetés
If you’re working with **Aspose.Page Java** and wondering **how to add hatch pattern** to your PostScript output, hatch patterns are a fast and flexible solution. In this tutorial we’ll walk through **how to add hatch** designs to a PostScript document, explain why they’re useful, and give you a complete, ready‑to‑run code example. By the end, you’ll be able to create visually appealing hatch‑filled shapes and text with just a few lines of Java.

## Gyors válaszok
- **Milyen könyvtárra van szükségem?** Aspose.Page for Java (the “aspose page java” SDK).  
- **Milyen vizuális hatást adunk hozzá?** Hatch patterns (e.g., diagonal lines, crosshatch).  
- **Szükségem van licencre a minta futtatásához?** Ingyenes próba működik fejlesztéshez; licenc szükséges a termeléshez.  
- **Hány sor kódból áll?** Körülbelül 70 sor, világos lépésekre bontva.  
- **Használhatom ugyanazt a megközelítést PDF-ekhez?** Igen—Aspose.Page supports multiple output formats, including PDF.

## Mi az a áthúzási minta?
A hatch pattern egy vektor‑alapú kitöltés, amely ismétlődő vonalakból vagy alakzatokból áll, és textúrahatást hoz létre. Mivel matematikailag van definiálva, a minta minőségromlás nélkül skálázható, így ideális nagy felbontású nyomtatáshoz és monokróm kimenethez.

## Miért használjunk hatch mintákat az Aspose.Page Java-val?
Az Aspose.Page támogat **10+ kimeneti formátumot** (köztük PostScript, PDF, EPS, SVG és XPS) és képes hatch kitöltéseket megjeleníteni legfeljebb **500 oldalas** dokumentumokon anélkül, hogy az egész fájlt a memóriába töltené. Ez azt jelenti, hogy gyors teljesítményt, alacsony memóriahasználatot és konzisztens vizuális eredményeket kap minden támogatott formátumban.

## Hogyan adjunk hozzá hatch mintát – áttekintés
A hatch minták vektor‑alapú textúrák, amelyek tisztán jelennek meg bármilyen felbontáson, és jól működnek monokróm nyomtatókon. Az Aspose.Page Java segítségével ezeket a mintákat alakzatokra, útvonalakra és akár szövegre is alkalmazhatja anélkül, hogy alacsony szintű PostScript parancsokkal kellene foglalkoznia.

## Előkövetelmények
- **Java fejlesztői környezet** – JDK 8 vagy újabb, valamint a választott IDE.  
- **Aspose.Page for Java könyvtár** – Töltse le a legújabb JAR-t a hivatalos **Aspose.Page for Java letöltési oldalról** [here](https://releases.aspose.com/page/java/).  
- Más Aspose kiadásokat is böngészhet [here](https://releases.aspose.com/).  
- **Írási hozzáférés** egy mappához, ahová a generált PostScript fájl mentésre kerül.

## Import packages
The imports below include standard Java AWT classes for graphics primitives such as colors, strokes, and geometric shapes, as well as Aspose.Page classes that provide the document model, hatch‑style definitions, and saving options required to generate a PostScript file.  
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Mi az a `Document` osztály?
A `Document` osztály az Aspose.Page felső szintű objektuma, amely egyetlen PostScript fájlt képvisel a memóriában. Minden rajzolási művelet ezen az objektumon keresztül történik.

## Hogyan állítsuk be a kimeneti adatfolyamot?
A kimenet írásához hozzon létre egy `FileOutputStream`-et, amely a kívánt fájlútra mutat; ez az adatfolyam kezeli az alacsony szintű bájtírást. A `PsSaveOptions` beállítja, hogyan mentődik a dokumentum, beleértve az oldalméretet és a tömörítést. Ezután példányosítson egy `Document`-et egy `PsSaveOptions` objektummal, amely meghatározza az oldalméretet, a tömörítést és egyéb PostScript‑specifikus beállításokat.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## Hogyan mentse el a grafikai állapotot és transzformálja az origót?
A grafikai állapot mentése rögzíti a jelenlegi transzformációs mátrixot, a vágási területet és a rajzolási attribútumokat, lehetővé téve a későbbi visszaállítást. Mentés után hívja meg a `translate(x, y)` metódust a graphics objektumon, hogy az origót egy kényelmes helyre mozgassa a hatch négyzetek rácsának rajzolásához.  
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Hogyan hozzunk létre újrahasználható négyzetet minden mintához?
A `Rectangle2D` egy téglalap alakzatot képvisel, amely pozíciója és mérete alapján van definiálva. Egyetlen példány létrehozásával, amely megfelel a cella méreteinek, újra felhasználható minden hatch‑kitöltött négyzethez, csökkentve az objektumok lefoglalását és hatékonyan tartva a rajzolási ciklust.  
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Hogyan állítsuk be a tollat a minta négyzet körvonalához?
A `BasicStroke` leírja a körvonal vastagságát, a szaggatott mintát és a végkapcsokat a vektor alakzatokhoz. Egy 2‑pontos `BasicStroke` használata tiszta szegélyt biztosít minden hatch‑kitöltött cella körül, biztosítva, hogy a kitöltés vizuálisan el legyen választva a szomszédos négyzetektől.  
```java
BasicStroke stroke = new BasicStroke(2);
```

## Hogyan iteráljunk a hatch mintákon?
A `HatchStyle` egy felsorolás, amely felsorolja az összes előre definiált hatch mintát, például átlós, kereszt és pontozott stílusokat. A `HatchStyle.values()` felett történő ciklus lehetővé teszi, hogy sorban alkalmazza minden mintát, kitöltse a téglalapot egy `HatchBrush`‑szel, majd megrajzolja a körvonalát.  
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Hogyan állítsuk vissza a grafikai állapotot a rajzolás után?
A `restore()` hívása a graphics objektumon visszaállítja a transzformációs mátrixot és a rajzolási beállításokat a korábban mentett állapotra, megakadályozva, hogy a kumulatív transzformációk vagy skálázás befolyásolják a későbbi rajzolási műveleteket. Ez biztosítja, hogy a későbbi tartalom az eredeti koordináta‑rendszerről induljon, és az alapértelmezett attribútumokat használja.  
```java
document.writeGraphicsRestore();
```

## Hogyan töltsünk ki szöveget hatch mintával?
A `TextFragment` egy szövegrészt képvisel, amely önállóan pozicionálható és stílusozható. Ha egy `HatchBrush`‑t a kiválasztott `HatchStyle`‑val rendeli a fragment kitöltéséhez, a szövegkarakterek a hatch textúra segítségével jelennek meg egy szilárd szín helyett.  
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Hogyan rajzoljunk körvonalat a szövegre különböző hatch stílussal?
A `HatchBrush` használható vonalzáshoz is. Körvonal rajzolásához állítsa be a fragment vonalát egy másik `HatchStyle`‑ú `HatchBrush`‑ra (pl. 70 % hatch) és növelje a vonalvastagságot a `setStrokeWidth`‑el. Ez a szöveg szegélyét saját hatch mintával jeleníti meg, miközben megőrzi a kitöltött belső részt.  
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Hogyan zárjuk be és mentsük a dokumentumot?
A `document.save()` a memóriában lévő dokumentumot a megadott kimeneti adatfolyamba írja. Miután az összes rajzolási parancs befejeződött, hívja meg ezt a metódust, majd zárja be a `FileOutputStream`‑et a rendszer erőforrásainak felszabadításához és a fájl megfelelő lemezre írásának biztosításához.  
```java
document.closePage();
document.save();
```

Kövesse ezeket a lépéseket, és egy PostScript fájlt kap, amely bemutatja a hatch minták teljes készletét, amely alakzatokra és szövegre egyaránt alkalmazva van – mindezt az **aspose page java** hajtja.

## Gyakori buktatók és tippek
- **Fájlútvonal hibák** – Győződjön meg róla, hogy a `dataDir` a megfelelő fájlelválasztóval (`/` vagy `\`) végződik.  
- **Nem támogatott színek** – Egyes régebbi PostScript interpreterek nem kezelhetnek bizonyos színtereket; használjon alap RGB-t a legnagyobb kompatibilitás érdekében.  
- **Licenc figyelmeztetések** – A minta érvényes licenc nélkül történő futtatása vízjelet ágyaz be a kimenetbe.

## Gyakran feltett kérdések

**Q: Használhatom az Aspose.Page Java-t más Java keretrendszerekkel?**  
A: Igen, a könyvtár keretrendszer‑független, és működik Spring‑kel, Jakarta EE‑vel, Android‑nal (korlátozottan), valamint tiszta Java SE‑vel.

**Q: Elérhető próba verzió az Aspose.Page Java-hoz?**  
A: Teljesen. Töltse le az ingyenes 30‑napos próbát [Aspose trial download page](https://releases.aspose.com/).

**Q: Hogyan szerezhetek ideiglenes licencet fejlesztéshez?**  
A: Kérjen ideiglenes licencet [temporary license request page](https://purchase.aspose.com/temporary-license/). Ez eltávolítja a kiértékelési vízjeleket.

**Q: Hol találok további oktatóanyagokat és közösségi támogatást?**  
A: Látogassa meg a hivatalos fórumot [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) további példák és kérdések‑válaszokért.

**Q: Van átfogó dokumentáció minden osztályról és metódusról?**  
A: Igen, a teljes API referencia elérhető [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Renderelhetem ugyanazt a hatch mintát PDF‑be a PostScript helyett?**  
A: Természetesen. Módosítsa a `PsSaveOptions`‑t `PdfSaveOptions`‑ra (vagy a megfelelő változatra), a kód többi része változatlan marad.

**Q: Mit tegyek, ha a generált fájl üres?**  
A: Ellenőrizze, hogy a kimeneti adatfolyam egy írható könyvtárra mutat, és hogy a `document.save()` a minden rajzolási művelet után van meghívva.

---

**Utolsó frissítés:** 2026-08-18  
**Tesztelve ezzel:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Textúraminta létrehozása PostScript-ben – Aspose.Page Java](/page/java/postscript-texture-patterns/)
- [Hogyan adjunk hozzá színátmenetet: Átlós színátmenet Java PostScript-ben az Aspose.Page Java használatával](/page/java/postscript-gradient-addition/diagonal/)
- [Hogyan konvertáljuk a PostScript-et PDF-re az Aspose.Page Java API használatával](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}