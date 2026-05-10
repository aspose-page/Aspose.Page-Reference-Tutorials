---
date: 2026-02-18
description: Tanulja meg, hogyan állíthatja be a festék színét, és hozhat létre PostScript
  ellipszist Java-ban az Aspose.Page segítségével. Ez az útmutató bemutatja, hogyan
  töltheti ki az ellipszist Java-ban, hogyan rajzolhatja meg az ellipszis körvonalát,
  és hogyan állíthatja be a vonalvastagságot.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Állítsd be a festék színét a PostScript ellipszis Java‑ban való rajzolásához
url: /hu/java/postscript-shapes/add-ellipse/
weight: 10
---

/tutorial-page-section >}} etc.

Make sure to keep all shortcodes and code block placeholders unchanged.

Also note "## Quick Answers" list items have bold Q. Keep same formatting.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Állítsa be a festék színét PostScript ellipszis rajzolásához Java-ban

## Bevezetés
Ha **festék színt kell beállítania** vektoros grafikák rajzolása közben, az Aspose.Page for Java könyvtár teljes ellenőrzést biztosít minden vonal és kitöltés felett. Ebben az útmutatóban megtudja, hogyan **állítsa be a festék színét**, **töltsön ki ellipszist Java-ban**, és **rajzoljon ellipszis körvonalat** egy egyszerű, lépésről‑lépésre megközelítéssel. A végére képes lesz magas minőségű PostScript ellipsziseket hozzáadni számlákhoz, jelentésekhez vagy bármely nyomtatható dokumentumhoz.

## Gyors válaszok
- **Melyik könyvtár a legjobb PostScript grafikák rajzolásához Java-ban?** Aspose.Page for Java.  
- **Kitölthetek egy ellipszist egyszínű színnel?** Igen – használja a `document.setPaint(Color.YOUR_COLOR)`-t a `fill` előtt.  
- **Hogyan rajzolhatom csak az ellipszis körvonalát?** Állítsa be a festéket és a vonalvastagságot, majd hívja meg a `document.draw(...)`-t.  
- **Szükségem van licencre a termelési használathoz?** Kereskedelmi licenc szükséges; teszteléshez ideiglenes licenc is elérhető.  
- **Melyik Java verzió támogatott?** Bármely Java 8+ futtatókörnyezet működik a jelenlegi Aspose.Page kiadással.

## Mi az a PostScript ellipszis?
A PostScript ellipszis egy vektoros alak, amelyet egy határoló téglalap definiál. A raszteres képektől eltérően méretezhető minőségromlás nélkül, így ideális nagy felbontású nyomtatáshoz és PDF konverzióhoz.

## Miért használja az Aspose.Page-t PostScript ellipszis létrehozásához?
- **Teljes ellenőrzés** a rajzolási primitívek (vonalak, görbék, ellipszisek) felett.  
- **Keresztplatformos** – működik Windows, Linux és macOS rendszereken.  
- **Nincsenek külső függőségek** – tiszta Java API, nincs natív kód.  
- **Könnyű integráció** meglévő Java alkalmazásokkal és build eszközökkel.

## Előkövetelmények
Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

1. Egy működő Java fejlesztői környezettel (JDK 8 vagy újabb).  
2. Az Aspose.Page for Java könyvtárral, amelyet a projektjéhez adott. Letöltheti **[itt](https://releases.aspose.com/page/java/)**.

## Csomagok importálása
A Java forrásfájljában importálja a PostScript tartalom rajzolásához és mentéséhez szükséges osztályokat.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Hogyan állítsa be a festék színét egy ellipszishez
A festék színének beállítása az első lépés minden kitöltés vagy vonal művelet előtt. A `setPaint` metódus határozza meg a színt, amely a következő rajzolási parancshoz lesz használva.

### 1. lépés: PostScript dokumentum előkészítése
Hozzon létre egy kimeneti adatfolyamot, állítsa be az oldal méretét, és példányosítson egy `PsDocument`-et.

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

### 2. lépés: Ellipszis kitöltése – használja a festék színének beállítását
Az **ellipszis kitöltéséhez** először hívja meg a `setPaint`-ot a kívánt kitöltő színnel, majd hajtsa végre a `fill`-t egy `Ellipse2D` példánnyal.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### 3. lépés: Ellipszis körvonal rajzolása és vonalvastagság beállítása
Kitöltés után megváltoztathatja a festéket egy másik színre, definiálhat egy `BasicStroke`-ot a vonalvastagság szabályozásához, és rajzolhatja az ellipszis körvonalát.

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

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Most már rendelkezik egy PostScript fájllal, amely két ellipszist tartalmaz – egyet narancssárgával kitöltve és egyet piros körvonallal. Nyugodtan kísérletezzen különböző koordinátákkal, méretekkel és színekkel, hogy megfeleljen a tervezési igényeinek.

## Gyakori buktatók és hibaelhárítás
- **Helytelen fájlútvonal** – Győződjön meg róla, hogy a `dataDir` a megfelelő elválasztóval (`/` vagy `\\`) végződik az operációs rendszeréhez.  
- **Hiányzó licenc** – Érvényes licenc nélkül a könyvtár értékelő módban fut, és vízjeleket adhat hozzá.  
- **A szín nem alkalmazódik** – Ne felejtse el a `document.setPaint(...)`-t *mielőtt* minden `fill` vagy `draw` hívás előtt beállítani; a festék beállítás nem marad meg automatikusan a különálló műveletek között.

## Gyakran Ismételt Kérdések

**Q: Használhatom az Aspose.Page for Java-t más Java könyvtárakkal?**  
A: Igen, az Aspose.Page for Java úgy van tervezve, hogy zökkenőmentesen integrálódjon más Java könyvtárakkal.

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.Page for Java-hoz?**  
A: Szerezzen ideiglenes licencet **[itt](https://purchase.aspose.com/temporary-license/)** tesztelési célokra.

**Q: Alkalmas-e az Aspose.Page kereskedelmi projektekhez?**  
A: Teljes mértékben! Látogasson el **[ide](https://purchase.aspose.com/buy)**, hogy megtekintse a kereskedelmi felhasználásra vonatkozó licenc opciókat.

**Q: Hol kérhetek segítséget vagy vitathatok Aspose.Page‑hez kapcsolódó kérdéseket?**  
A: Csatlakozzon a közösséghez a **[Aspose.Page Fórumon](https://forum.aspose.com/c/page/39)** a megbeszélésekhez és segítséghez.

**Q: Vannak ingyenes források az Aspose.Page for Java további megismeréséhez?**  
A: Használja a **[ingyenes próbaverziót](https://releases.aspose.com/)** és tekintse meg a dokumentációban található példákat.

## Következtetés
Az Aspose.Page for Java egyszerűvé teszi a **festék színének beállítását**, az **ellipszis kitöltését**, és az **ellipszis körvonalának rajzolását** – legyen szó egyszerű kitöltött alakról vagy összetett vonalas grafikáról. A fenti lépésekkel gyorsan hozzáadhat professzionális szintű vektoros grafikákat bármely nyomtatható dokumentumhoz. A mélyebb felfedezéshez – például több alak kombinálása, színátmenetek alkalmazása vagy PDF‑re konvertálás – tekintse meg a hivatalos **[dokumentációt](https://reference.aspose.com/page/java/)**.

---

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}