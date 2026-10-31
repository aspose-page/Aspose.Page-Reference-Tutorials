---
date: 2026-10-31
description: Tanulja meg, hogyan állítsa be a paint color-t és töltsön ki ellipse-t
  a Java PostScript-ben az Aspose.Page használatával. Ez az útmutató megmutatja, hogyan
  kell fill ellipse, draw ellipse outline, és set stroke thickness, világos kódlépésekkel.
keywords:
- how to fill ellipse
- how to set paint color
- Aspose.Page Java ellipse
- PostScript drawing Java
lastmod: 2026-10-31
linktitle: Ellipse hozzáadása a Java PostScript-ben
og_description: Tanulja meg, hogyan töltsön ki ellipse-t és állítsa be a paint color-t
  a Java PostScript-ben az Aspose.Page használatával. Kövesse a lépésről‑lépésre kódot,
  hogy másodpercek alatt draw filled and outlined ellipses-t készítsen.
og_image_alt: Developer guide showing how to fill ellipse and set paint color in Java
  PostScript with Aspose.Page
og_title: Hogyan töltsünk ki ellipse-t és állítsuk be a paint color-t a Java PostScript-ben
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  headline: How to fill ellipse and set paint color in Java PostScript
  type: TechArticle
- description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  name: How to fill ellipse and set paint color in Java PostScript
  steps:
  - name: Set up the PostScript document
    text: Create an output stream, configure page size, and instantiate a `PsDocument`.
      `PsDocument` is the core class that represents a PostScript file in memory.
      All drawing commands are routed through this object, and it handles page layout,
      resource management, and final file generation.
  - name: Fill ellipse – use set paint color
    text: To **fill ellipse**, you must first call `setPaint` with the desired fill
      color, then invoke `fill` with an `Ellipse2D` instance. `setPaint` sets the
      current drawing color used for subsequent fill or stroke operations. `Ellipse2D`
      defines the geometric bounds of the ellipse; its constructor takes th
  - name: Draw ellipse outline and set stroke thickness
    text: After filling, you can change the paint to a different color, define a `BasicStroke`
      to control line width, and draw the ellipse outline. `BasicStroke` specifies
      line width, dash pattern, and end‑cap style for drawing outlines. By adjusting
      its `width` property you control how bold the ellipse borde
  - name: Close and save the document
    text: Finalize the page and write the PostScript file to disk. Calling `document.close()`
      flushes all pending drawing commands and releases resources. The resulting `.ps`
      file can be opened with any PostScript viewer or converted to PDF. You now have
      a PostScript file that contains two ellipses—one filled
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to seamlessly integrate with other
      Java libraries.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Obtain a temporary license **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)**
      for testing purposes.
    question: How can I get a temporary license for Aspose.Page for Java?
  - answer: Absolutely! Visit **[the Aspose purchase page](https://purchase.aspose.com/buy)**
      to explore licensing options for commercial use.
    question: Is Aspose.Page suitable for commercial projects?
  - answer: Join the community at the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for discussions and assistance.
    question: Where can I seek help or discuss Aspose.Page‑related queries?
  - answer: Utilize the **[Aspose free trial page](https://releases.aspose.com/)**
      and explore examples in the documentation.
    question: Are there any free resources to learn more about Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript ellipse
- vector drawing
title: Hogyan töltsünk ki ellipse-t és állítsuk be a paint color-t a Java PostScript-ben
url: /hu/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan töltsünk ki ellipszist és állítsuk be a festék színét Java PostScript-ben

## Bevezetés
Ha vektoros grafikát rajzolva **festék színét kell beállítani**, az Aspose.Page for Java könyvtár teljes irányítást biztosít minden vonal és kitöltés felett. Ebben az útmutatóban megtudja, hogyan **állítsa be a festék színét**, **töltse ki az ellipszist**, és **rajzolja meg az ellipszis körvonalát** egy egyszerű, lépésről‑lépésre megközelítéssel. A végére képes lesz magas minőségű PostScript ellipsziseket hozzáadni számlákhoz, jelentésekhez vagy bármely nyomtatható dokumentumhoz.

## Gyors válaszok
- **Melyik könyvtár a legjobb PostScript grafikák rajzolásához Java-ban?** Aspose.Page for Java.  
- **Tölthetek-e egy ellipszist egyszínű színnel?** Igen – használja a `document.setPaint(Color.YOUR_COLOR)`-t a `fill` előtt.  
- **Hogyan rajzolhatom csak az ellipszis körvonalát?** Állítsa be a festéket és a vonalvastagságot, majd hívja meg a `document.draw(...)`-t.  
- **Szükségem van licencre a termelési használathoz?** Kereskedelmi licenc szükséges; teszteléshez ideiglenes licenc is elérhető.  
- **Melyik Java verzió támogatott?** Bármely Java 8+ futtatókörnyezet működik a jelenlegi Aspose.Page kiadással.

## Mi az a PostScript ellipszis?
A PostScript ellipszis egy vektoros alakzat, amelyet egy határoló téglalap definiál. A raszteres képektől eltérően minőségromlás nélkül méretezhető, így ideális nagy felbontású nyomtatáshoz és PDF konverzióhoz. Mivel az alakzatot matematikailag írják le, bármilyen méretben vagy felbontásban megjeleníthető, miközben megőrzi a tiszta éleket és a sima görbéket.

## Miért használja az Aspose.Page-t PostScript ellipszis létrehozásához?
Az Aspose.Page meghatározott irányítást biztosít minden rajzolási primitív felett. Támogatja a **3 fő operációs rendszert (Windows, Linux, macOS)**, **0 natív függőséget**, és egy tipikus szerveren **50+ vektoros primitívet** képes renderelni másodpercenként. A könyvtár tisztán Java, így beágyazható bármely Java 8+ alkalmazásba további natív könyvtárak nélkül.

## Előfeltételek
Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

1. Egy működő Java fejlesztői környezet (JDK 8 vagy újabb).  
2. Az Aspose.Page for Java könyvtár hozzáadva a projektjéhez. Letöltheti **[az Aspose.Page for Java kiadási oldaláról](https://releases.aspose.com/page/java/)**.  

## Csomagok importálása
A Java forrásfájljában importálja azokat az osztályokat, amelyek a PostScript tartalom rajzolásához és mentéséhez szükségesek.

A `java.awt` csomag biztosítja az alap grafikai típusokat, mint a `Color`, `Ellipse2D` és `BasicStroke`. A `com.aspose.page` csomag a `PsDocument` osztályt biztosítja, amely PostScript kimenetet ír.

- **`Color`** – egy sRGB színt képvisel, amely a festéshez használható.  
- **`Ellipse2D`** – egy ellipszis alakzatot ír le, amelyet egy határoló téglalap definiál.  
- **`BasicStroke`** – megadja a vonalvastagságot, a szaggatott mintát és a vonalvége stílusát a körvonalak rajzolásához.  
- **`PsDocument`** – egy PostScript dokumentumot képvisel, és metódusokat biztosít a grafika rajzolásához és az oldalak kezeléséhez.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Hogyan állítsuk be a festék színét egy ellipszishez
Az első lépés, hogy megmondjuk a dokumentumnak, melyik színt használja a következő rajzolási művelethez. A `setPaint` metódus egy egyszínű színt állít be, amely a kitöltésre vagy a vonalra lesz alkalmazva, a későbbi hívástól függően.

### 1. lépés: PostScript dokumentum beállítása
Hozzon létre egy kimeneti adatfolyamot, állítsa be az oldal méretét, és példányosítsa a `PsDocument`-ot.

`PsDocument` a központi osztály, amely egy PostScript fájlt reprezentál a memóriában. Minden rajzolási parancs ezen az objektumon keresztül kerül továbbításra, és kezeli az oldalelrendezést, az erőforrás-kezelést és a végső fájl generálását.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### 2. lépés: Ellipszis kitöltése – a setPaint szín használata
Az **ellipszis kitöltéséhez** először a kívánt kitöltőszínnel kell meghívni a `setPaint`-ot, majd egy `Ellipse2D` példánnyal meghívni a `fill`-et.

`setPaint` állítja be a jelenlegi rajzolási színt, amelyet a későbbi kitöltési vagy vonalrajzolási műveletekhez használnak.  
`Ellipse2D` meghatározza az ellipszis geometriai határait; konstruktora a bal‑felső sarok X‑Y koordinátáit, valamint a szélességet és magasságot veszi fel.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### 3. lépés: Ellipszis körvonalának rajzolása és vonalvastagság beállítása
Kitöltés után megváltoztathatja a festéket egy másik színre, definiálhat egy `BasicStroke`-ot a vonalvastagság szabályozásához, és rajzolhatja meg az ellipszis körvonalát.

`BasicStroke` meghatározza a vonalvastagságot, a szaggatott mintát és a vonalvége stílusát a körvonalak rajzolásához. A `width` tulajdonságának módosításával szabályozhatja, milyen vastag legyen az ellipszis szegélye.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### 4. lépés: Dokumentum lezárása és mentése
Fejezze be az oldalt, és írja a PostScript fájlt a lemezre.

A `document.close()` hívás kiüríti az összes függőben lévő rajzolási parancsot és felszabadítja az erőforrásokat. A kapott `.ps` fájl bármely PostScript megjelenítővel megnyitható vagy PDF‑re konvertálható.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Most már van egy PostScript fájlja, amely két ellipszist tartalmaz – egyet narancssárgával kitöltve, a másikat piros körvonallal. Nyugodtan kísérletezzen különböző koordinátákkal, méretekkel és színekkel, hogy megfeleljen a tervezési igényeinek.

## Gyakori buktatók és hibaelhárítás
- **Helytelen fájlútvonal** – Győződjön meg róla, hogy a `dataDir` a megfelelő elválasztóval (`/` vagy `\\`) végződik az operációs rendszerének megfelelően.  
- **Hiányzó licenc** – Érvényes licenc nélkül a könyvtár értékelő módban fut, és vízjeleket adhat hozzá.  
- **A szín nem alkalmazódik** – Ne felejtse el a `document.setPaint(...)`-t *minden* `fill` vagy `draw` hívás *előtt* beállítani; a festék beállítás nem marad meg automatikusan a különálló műveletek között.

## Gyakran feltett kérdések

**Q: Használhatom az Aspose.Page for Java-t más Java könyvtárakkal?**  
A: Igen, az Aspose.Page for Java úgy van tervezve, hogy zökkenőmentesen integrálódjon más Java könyvtárakkal.

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.Page for Java-hoz?**  
A: Szerezzen ideiglenes licencet **[az Aspose ideiglenes licenc oldaláról](https://purchase.aspose.com/temporary-license/)** tesztelési célokra.

**Q: Alkalmas-e az Aspose.Page kereskedelmi projektekhez?**  
A: Teljesen! Látogassa meg a **[Aspose vásárlási oldalát](https://purchase.aspose.com/buy)**, hogy megismerje a kereskedelmi felhasználásra vonatkozó licencelési lehetőségeket.

**Q: Hol kérhetek segítséget vagy vitathatok Aspose.Page‑hez kapcsolódó kérdéseket?**  
A: Csatlakozzon a közösséghez a **[Aspose.Page Fórumon](https://forum.aspose.com/c/page/39)** a megbeszélésekhez és segítséghez.

**Q: Vannak-e ingyenes források az Aspose.Page for Java további megismeréséhez?**  
A: Használja a **[Aspose ingyenes próbaoldalt](https://releases.aspose.com/)** és tekintse meg a dokumentációban található példákat.

## Összegzés
Az Aspose.Page for Java egyszerűvé teszi a **festék színének beállítását**, az **ellipszis kitöltését**, és az **ellipszis körvonalának rajzolását** – legyen szó egyszerű kitöltött alakzatról vagy összetett vonalas grafikáról. A fenti lépésekkel gyorsan hozzáadhat professzionális szintű vektoros grafikát bármely nyomtatható dokumentumhoz. A mélyebb felfedezéshez – például több alakzat kombinálása, színátmenetek alkalmazása vagy PDF‑re konvertálás – tekintse meg a hivatalos **[Aspose.Page Java dokumentációt](https://reference.aspose.com/page/java/)**.

---

**Legutóbb frissítve:** 2026-10-31  
**Tesztelve a következővel:** Aspose.Page for Java 24.11  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Hogyan rajzoljunk téglalapot Java PostScript-ben az Aspose.Page használatával](/page/java/postscript-shapes/add-rectangle/)
- [Hogyan adjunk hozzá Unicode szöveget Java PostScript-ben az Aspose.Page használatával](/page/java/postscript-text-manipulation/add-text-unicode/)
- [Radiális színátmenet létrehozása PostScript-ben az Aspose.Page for Java használatával](/page/java/postscript-gradient-addition/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}