---
date: 2026-05-30
description: Ismerje meg, hogyan hozhat létre XPS dokumentumot Java-ban az Aspose.Page
  használatával, és adjon hozzá csempézett képet könnyedén ebben a lépésről-lépésre
  útmutatóban. Hogyan lehet gyorsan XPS fájlokat létrehozni.
keywords:
- how to create xps
- add tiled image java
- Aspose.Page XPS tutorial
linktitle: Csempézett kép hozzáadása Java XPS-hez
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  headline: How to Create XPS Document with a Tiled Image in Java
  type: TechArticle
- description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  name: How to Create XPS Document with a Tiled Image in Java
  steps:
  - name: Set Up Your Project
    text: Add the Aspose.Page JAR files to your project’s classpath and verify the
      import statements compile without errors.
  - name: Create XPS Document
    text: '`XpsDocument` is the core container that holds pages, paths, and resources.
      Instantiate it with the desired page size, then you can start adding graphical
      elements.'
  - name: Define the Tiled Image Path
    text: Place the image you want to tile (e.g., `R08LN_NN.jpg`) inside the directory
      referenced by `dataDir`. The image will be used as a brush pattern.
  - name: Add Tiled Image
    text: Create a rectangular path and fill it with an `XpsImageBrush`. By setting
      the tile mode to `Tile`, the image repeats across the rectangle. Adjust the
      source and destination rectangles to control tile size and positioning.
  - name: Save the Document
    text: Persist the XPS file to disk. The output file will contain the tiled image
      you just defined and can be opened with any XPS viewer. Repeat these steps whenever
      you need to **add tiled image** to other pages or shapes within the same XPS
      document.
  type: HowTo
- questions:
  - answer: It provides a high‑level API to generate and manipulate XPS documents
      in Java.
    question: What does Aspose.Page do?
  - answer: Yes – use `XpsImageBrush` with `XpsTileMode.Tile`.
    question: Can I tile an image?
  - answer: A temporary or commercial license is required for production use.
    question: Do I need a license?
  - answer: Any JDK 8+ is compatible.
    question: What Java version is supported?
  - answer: Roughly 10–15 minutes for a basic tiled‑image scenario.
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.Page Java API
title: Hogyan hozzunk létre XPS dokumentumot csempézett képpel Java-ban
url: /hu/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozzunk létre XPS dokumentumot mozaikos képpel Java-ban

## Bevezetés
Az XPS dokumentumok programozott létrehozása alapvető készség a Java fejlesztők számára, akik nyomtatható, eszközfüggetlen kimenetet igényelnek. Az **XPS fájlok hatékony létrehozása** kérdésre a Aspose.Page for Java ad választ, amely elrejti az alacsony szintű XML Paper Specification részleteket, és lehetővé teszi, hogy a vizuális tervezésre koncentráljon. Ebben az útmutatóban pontosan megmutatjuk, hogyan hozhat létre XPS dokumentumot, hogyan adhat hozzá egy mozaikos képet háttérként vagy mintaként, és hogyan mentheti az eredményt – mindezt tömör, termelésre kész kóddal.

## Gyors válaszok
- **Mit csinál az Aspose.Page?** Egy magas szintű API-t biztosít XPS dokumentumok generálásához és manipulálásához Java-ban.  
- **Tegyek mozaikot egy képpel?** Igen – használja a `XpsImageBrush`-t a `XpsTileMode.Tile`-el.  
- **Szükségem van licencre?** Ideiglenes vagy kereskedelmi licenc szükséges a termeléshez.  
- **Mely Java verzió támogatott?** Bármely JDK 8+ kompatibilis.  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 10–15 perc egy alap mozaikos kép szcenárióhoz.

## Mi az „XPS dokumentum létrehozása”?
`XpsDocument` az Aspose.Page felső szintű objektuma, amely egyetlen XPS fájlt képvisel a memóriában. Tartalmazza az oldalakat, erőforrásokat és metaadatokat, lehetővé téve a dokumentum programozott felépítését. XPS dokumentum létrehozása azt jelenti, hogy példányosítja ezt az osztályt, hozzáad vizuális elemeket, és végül meghívja a `save`-et, hogy a rögzített elrendezésű fájlt lemezre írja. Ez a megközelítés megszünteti a manuális XML kezelését és garantálja a XML Paper Specification megfelelőségét.

## Miért adjunk hozzá mozaikos képet?
A mozaikozás egy grafikát ismétel meg egy meghatározott területen, ami ideális háttérképekhez, vízjelekhez vagy mintafelületekhez. A `XpsTileMode.Tile` használatával a kép automatikusan ismétlődik manuális másolás nélkül, időt takarít meg a fejlesztésben és biztosítja a konzisztens megjelenítést minden eszközön. A mozaikos képek alacsony fájlméretet is biztosítanak, mivel ugyanaz a bitmap erőforrás újrahasznosul ahelyett, hogy többször beágyazódna.

## Előfeltételek
1. **Java Development Kit (JDK)** – JDK 8 vagy újabb telepítve.  
2. **Aspose.Page for Java** – letöltés a [website](https://releases.aspose.com/page/java/).  
3. **Írható könyvtár** – ahol a generált XPS fájl mentésre kerül.

## Csomagok importálása
In your Java project, import the necessary classes:

`XpsDocument` a fő objektum, amely egy XPS fájlt képvisel.  
`XpsImageBrush` képet használ a formák festéséhez.  
`XpsTileMode` meghatározza, hogyan kerül a kép mozaikozásra.  
`Rectangle2D` egy téglalap alakú régiót ír le a pozicionáláshoz.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Lépésről‑lépésre útmutató

### 1. lépés: Projekt beállítása
Adja hozzá az Aspose.Page JAR fájlokat a projekt classpath-jához, és ellenőrizze, hogy az importálási utasítások hibamentesen fordulnak.

### 2. lépés: XPS dokumentum létrehozása
`XpsDocument` a fő tároló, amely az oldalakat, útvonalakat és erőforrásokat tartalmazza. Hozza létre a kívánt oldalmérettel, majd elkezdhet grafikai elemeket hozzáadni.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### 3. lépés: A mozaikos kép útvonalának meghatározása
Helyezze el a mozaikozni kívánt képet (pl. `R08LN_NN.jpg`) a `dataDir` által hivatkozott könyvtárban. A kép ecsetmintaként lesz használva.

### 4. lépés: Mozaikos kép hozzáadása
Hozzon létre egy téglalap útvonalat, és töltse ki egy `XpsImageBrush`-szel. A tile mód `Tile`-re állításával a kép a téglalapon ismétlődik. Állítsa be a forrás- és céltéglalapokat a mozaik méretének és pozicionálásának szabályozásához.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### 5. lépés: Dokumentum mentése
Mentse az XPS fájlt a lemezre. A kimeneti fájl tartalmazni fogja a most definiált mozaikos képet, és bármely XPS megjelenítővel megnyitható.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Ismételje meg ezeket a lépéseket, amikor **mozaikos képet** kell hozzáadni más oldalakhoz vagy alakzatokhoz ugyanabban az XPS dokumentumban.

## Gyakori problémák és megoldások
| Probléma | Megoldás |
|----------|----------|
| A kép nem jelenik meg | Ellenőrizze, hogy a fájl útvonala (`dataDir + \"R08LN_NN.jpg\"`) helyes-e, és a kép elérhető. |
| A mozaik minta nyújtottnak tűnik | Állítsa be a forrás és cél `Rectangle2D` értékeket a mozaik méretének szabályozásához. |
| Az átlátszóság nincs hatással | Győződjön meg arról, hogy az ecset átlátszósága a tile mód konfigurációja **után** van beállítva. |

## Gyakran feltett kérdések

**K:** Kompatibilis az Aspose.Page minden Java verzióval?  
**V:** Az Aspose.Page támogatja a Java 8-tól a Java 21-ig; a teljes kompatibilitási mátrixot [itt](https://reference.aspose.com/page/java/) találja.

**K:** Használhatom az Aspose.Page-t kereskedelmi projektekhez?  
**V:** Igen, a termeléshez kereskedelmi licenc szükséges. A vásárlási lehetőségek [itt](https://purchase.aspose.com/buy) vannak felsorolva.

**K:** Elérhető ingyenes próba?  
**V:** Egy teljes funkcionalitású ingyenes próba letölthető az Aspose kiadási oldaláról [itt](https://releases.aspose.com/).

**K:** Hol kaphatok közösségi támogatást?  
**V:** Csatlakozzon az Aspose.Page közösségi fórumához a [forum](https://forum.aspose.com/c/page/39) címen, hogy kérdéseket tegyen fel és példákat osszon meg.

**K:** Hogyan szerezhetek ideiglenes licencet értékeléshez?  
**V:** Ideiglenes licenceket kérésre biztosít az Aspose portálon [itt](https://purchase.aspose.com/temporary-license/).

## Következtetés
Most már rendelkezik egy teljes, termelésre kész munkafolyamattal a **XPS dokumentumok létrehozásához** mozaikos képekkel az Aspose.Page for Java használatával. Az `XpsImageBrush` és `XpsTileMode.Tile` kihasználásával gazdag, ismételhető grafikákat hozhat létre anélkül, hogy a fájlméret nőne. Kísérletezzen különböző mozaikméretekkel, átlátszósági szintekkel és alakzatokkal, hogy kifinomult dokumentumelrendezéseket építsen. A következő lépésként fedezze fel vektoros alakzatok vagy szövegátfedések hozzáadását, hogy tovább javítsa XPS fájljait.

---

**Legutóbb frissítve:** 2026-05-30  
**Tesztelve ezzel:** Aspose.Page for Java 24.12 (latest)  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó oktatóanyagok

- [Hogyan adjunk hozzá képet Java XPS dokumentumokhoz – Egyszerű útmutató az Aspose.Page használatával](/page/java/xps-image-manipulation/add-image/)
- [Aspose.Page Java – Oldalak hozzáadása XPS-hez oktatóanyag](/page/java/xps-page-manipulation/add-page/)
- [XPS konvertálása PDF-be Java-ban az Aspose.Page Java használatával](/page/java/file-merging/xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}