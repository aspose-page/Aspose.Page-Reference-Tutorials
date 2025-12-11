---
date: 2025-12-11
description: Tanulja meg, hogyan hozhat létre PostScript ellipszist Java-ban az Aspose.Page
  segítségével. Ez a lépésről‑lépésre útmutató megmutatja, hogyan töltheti ki az ellipszist
  színnel, és hogyan rajzolhat ellipszist Java-val.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Hogyan hozhatunk létre PostScript ellipszist Java-ban az Aspose.Page segítségével
url: /hu/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozzunk létre PostScript ellipszist Java-ban az Aspose.Page segítségével

## Bevezetés
A **PostScript ellipszis** programozott létrehozása finomhangolt vezérlést biztosít a vektoros grafikák felett jelentésekben, számlákban vagy bármely nyomtatható dokumentumban. Ebben az útmutatóban megtanulja, hogyan **hozzon létre PostScript ellipszis** alakzatokat az Aspose.Page for Java könyvtár segítségével, hogyan töltsön ki egy ellipszist színnel, és hogyan rajzoljon meg egy ellipszis körvonalát. A végére készen áll majd, hogy egyedi grafikákat ágyazzon be közvetlenül a PostScript kimenetbe.

## Gyors válaszok
- **Melyik könyvtár a legjobb a PostScript grafikák rajzolásához Java-ban?** Aspose.Page for Java.  
- **Tölthetek-e ki egy ellipszist egyetlen színnel?** Igen – használja a `document.setPaint(Color.YOUR_COLOR)`-t a `fill` előtt.  
- **Hogyan rajzolhatom csak az ellipszis körvonalát?** Állítsa be a festéket és a vonalat, majd hívja a `document.draw(...)`-t.  
- **Szükségem van licencre a termelési használathoz?** Kereskedelmi licenc szükséges; teszteléshez ideiglenes licenc elérhető.  
- **Melyik Java verzió támogatott?** Bármely Java 8+ futtatókörnyezet működik a jelenlegi Aspose.Page kiadással.

## Mi az a PostScript ellipszis?
A PostScript ellipszis egy vektoros alakzat, amelyet egy határoló téglalap határoz meg. A raszteres képektől eltérően minőségvesztés nélkül méretezhető, így ideális nagy felbontású nyomtatáshoz és PDF konvertáláshoz.

## Miért használjuk az Aspose.Page-et PostScript ellipszis létrehozásához?
- **Teljes irányítás** a rajzolási primitívek (vonalak, görbék, ellipszisek) felett.  
- **Keresztplatformos** – működik Windows, Linux és macOS rendszereken.  
- **Nincs külső függőség** – tiszta Java API, nincs natív kód.  
- **Könnyű integráció** meglévő Java alkalmazásokkal és build eszközökkel.

## Előfeltételek
Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

1. Egy működő Java fejlesztői környezettel (JDK 8 vagy újabb).  
2. Az Aspose.Page for Java könyvtár hozzáadva a projekthez. Letöltheti **[itt](https://releases.aspose.com/page/java/)**.

## Csomagok importálása
A Java forrásfájlban importálja a rajzoláshoz és a PostScript tartalom mentéséhez szükséges osztályokat.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Lépésről‑lépésre útmutató

### 1. lépés: PostScript dokumentum beállítása
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

### 2. lépés: Ellipszis kitöltése színnel
Állítsa be a festéket a kívánt kitöltőszínre, és hívja a `fill`-t egy `Ellipse2D` példánnyal.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### 3. lépés: Ellipszis körvonalának megrajzolása vonallal
Váltassa a festéket a vonal színére, definiáljon egy `BasicStroke`-ot a vonalvastagsághoz, és rajzolja meg az ellipszis körvonalát.

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

Most már rendelkezik egy PostScript fájllal, amely két ellipszist tartalmaz – egyet narancssárgával kitöltve, a másikat piros körvonallal. Nyugodtan kísérletezzen különböző koordinátákkal, méretekkel és színekkel, hogy megfeleljen a tervezési igényeinek.

## Gyakori hibák és hibaelhárítás
- **Helytelen fájlútvonal** – Győződjön meg róla, hogy a `dataDir` megfelelő elválasztóval (`/` vagy `\\`) végződik az operációs rendszernek megfelelően.  
- **Hiányzó licenc** – Érvényes licenc nélkül a könyvtár értékelő módban fut, és vízjelet adhat hozzá.  
- **A szín nem alkalmazódik** – Ne felejtse el a `document.setPaint(...)`-t *minden* `fill` vagy `draw` hívás előtt beállítani; a festékbeállítás nem marad meg automatikusan a különálló műveletek között.

## Gyakran Ismételt Kérdések

**Q: Használhatom-e az Aspose.Page for Java-t más Java könyvtárakkal?**  
A: Igen, az Aspose.Page for Java úgy van tervezve, hogy zökkenőmentesen integrálódjon más Java könyvtárakkal.

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.Page for Java-hoz?**  
A: Szerezzen ideiglenes licencet **[itt](https://purchase.aspose.com/temporary-license/)** tesztelési célokra.

**Q: Alkalmas-e az Aspose.Page kereskedelmi projektekhez?**  
A: Teljes mértékben! Látogasson el **[ide](https://purchase.aspose.com/buy)**, hogy megismerje a kereskedelmi felhasználásra vonatkozó licencelési lehetőségeket.

**Q: Hol kérhetek segítséget vagy vitathatok Aspose.Page‑hez kapcsolódó kérdéseket?**  
A: Csatlakozzon a közösséghez a **[Aspose.Page Fórumon](https://forum.aspose.com/c/page/39)** a megbeszélések és segítség érdekében.

**Q: Van-e ingyenes forrás a Aspose.Page for Java további megismeréséhez?**  
A: Használja a **[ingyenes próbaverziót](https://releases.aspose.com/)**, és tekintse meg a dokumentációban található példákat.

## Összegzés
Az Aspose.Page for Java egyszerűvé teszi a **PostScript ellipszis** grafikák létrehozását, akár egyszerű kitöltött alakzatra, akár összetett vonallal körvonalazott formára van szükség. A fenti lépésekkel gyorsan hozzáadhat professzionális szintű vektoros grafikákat bármely nyomtatható dokumentumhoz. A mélyebb felfedezéshez – például több alakzat kombinálása, színátmenetek alkalmazása vagy PDF‑re konvertálás – tekintse meg a hivatalos **[dokumentációt](https://reference.aspose.com/page/java/)**.

---

**Legutóbb frissítve:** 2025-12-11  
**Tesztelve a következővel:** Aspose.Page for Java 24.11  
**Szerző:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
