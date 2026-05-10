---
date: 2026-02-07
description: Tanulja meg, hogyan méretezze a téglalapot az Aspose.Page for Java segítségével,
  hogyan tolja el a formát, és hogyan alkalmazzon affín transzformációt PostScript
  dokumentumok létrehozásához.
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Hogyan méretezzen téglalapot az Aspose.Page for Java használatával
url: /hu/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan méretezzenünk téglalapot az Aspose.Page for Java segítségével

## Bevezetés
Üdvözöljük egy átfogó útmutatóban, amely bemutatja a **Aspose.Page for Java** erőteljes funkcióinak kihasználását különféle oldaltranszformációk végrehajtásához. Ebben az oktatóanyagban megtanulja, hogyan **méretezzen téglalapot**, transzformálja (fordítsa) alakzatokat, forgassa objektumokat, és **alkalmazzon affín transzformációt** technikákat **PostScript dokumentum** létrehozása közben. Ezek a képességek lehetővé teszik, hogy gazdag, grafika‑intenzív Java alkalmazásokat építsen alacsony szintű renderelési kód nélkül.

## Gyors válaszok
- **Hogyan méretezhetek egy téglalapot Java-ban az Aspose.Page segítségével?** Használja a `document.scale()` metódust az alakzat rajzolása előtt.  
- **Mozgathatok (transzformálhatok) egy alakzatot anélkül, hogy más grafikákat befolyásolna?** Igen—mentse el a grafikai állapotot, hívja a `document.translate(x, y)`-t, rajzoljon, majd állítsa vissza az állapotot.  
- **Melyik osztály hoz létre PostScript fájlt?** `PsDocument` a `PsSaveOptions`-szal együtt.  
- **Szükségem van licencre a termelési használathoz?** Érvényes Aspose.Page licenc szükséges a kereskedelmi telepítésekhez.  
- **Melyik Java verzió támogatott?** Az Aspose.Page a Java 8 és újabb verziókkal működik.

## Előfeltételek
Mielőtt belemerülnénk a lépésről‑lépésre útmutatóba, győződjön meg róla, hogy a következő előfeltételek adottak:

- Alapvető Java programozási ismeretek.  
- Az Aspose.Page for Java könyvtár telepítve van. Letöltheti a [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) oldalról.  
- Java integrált fejlesztőkörnyezet (IDE) telepítve van a gépén.

## Csomagok importálása
A Java projektjében importálja a szükséges csomagokat az Aspose.Page for Java használatához:

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Mi az a „how to scale rectangle” az Aspose.Page-ben?
A téglalap méretezése megváltoztatja annak méretét az X és Y tengelyek mentén, miközben megőrzi az alakját. Az Aspose.Page a `scale(float sx, float sy)` metódust biztosítja, amely **affín transzformációt** alkalmaz az aktuális grafikai állapotra. Ez a **how to scale rectangle** kulcsszó mögötti alapvető technika.

## Hogyan transzformáljunk (fordítsunk) alakzatot az Aspose.Page segítségével
A transzformáció egy alakzatot új helyre mozgat anélkül, hogy megváltoztatná annak méreteit. Ez a **how to translate shape** lényege. A grafikai állapot mentésével, a `translate(dx, dy)` alkalmazásával, rajzolással, majd az állapot visszaállításával a többi objektum érintetlen marad.

## Példa 1: Transzformációk nélkül
Az első példa egy egyszerű téglalapot rajzol, amelyre nincs alkalmazva transzformáció. Ez alapvonalként szolgál a későbbi példákkal való összehasonlításhoz.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## Példa 2: Transzformáció
Itt bemutatjuk a **how to translate shape** módszert, a grafikai kontextus 250 egységgel jobbra mozgatásával, mielőtt a második téglalapot rajzolnánk.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Példa 3: Méretezés
Ez a példa megválaszolja a fő kérdést: **how to scale rectangle**. A téglalapot az eredeti szélességének 50 %-ára és magasságának 75 %-ára zsugorítjuk.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Hogyan forgassuk el az alakzatot Java-ban (rotate shape java)
A forgatás egy másik gyakori affín művelet. Bár a forgatáshoz tartozó kódrészleteket a rövidség kedvéért kihagyjuk, a minta azonos: mentse el a grafikai állapotot, hívja a `document.rotate(angle)`-t, rajzolja meg az alakzatot, majd állítsa vissza. Ez a gyakorlatban bemutatja a **rotate shape java** és a **how to rotate rectangle** kifejezéseket.

## Miért fontos – Valós‑világi előnyök
- **Eszköz‑független kimenet** – Írjon egyszer, és generáljon PostScript vagy XPS fájlokat platform‑specifikus módosítások nélkül.  
- **Finomhangolt vezérlés** – Kombinálja a transzformációt, méretezést, nyírást és forgatást a pontos elrendezési követelményekhez.  
- **Teljesítmény‑orientált** – Alacsony terhelésű API, amely ideális nagy‑méretű dokumentumok kötegelt feldolgozásához.  

## Gyakori felhasználási esetek
- Nyomtatható számlák generálása – például egy **printable invoice java** megoldás, amely pontosan helyezi el a logókat és vonalkódokat.  
- Műszaki diagramok létrehozása, ahol a pontos méretezés és pozicionálás szükséges.  
- Többoldalas jelentések automatikus előállítása PostScript formátumban.

## Gyakori problémák és megoldások
- **A transzformáció nem áll vissza** – Mindig párosítsa a `document.writeGraphicsSave()`-t a `document.writeGraphicsRestore()`-rel, hogy elkerülje a nem kívánt átvitel hatásokat.  
- **Váratlan színek** – Győződjön meg róla, hogy minden transzformáció után beállítja a festéket; a grafikai állapot nem őrzi meg a korábbi színbeállításokat a visszaállítás után.  
- **A fájlméret túl nagy** – Használja a `PsSaveOptions`-t a tömörítés engedélyezéséhez vagy a beágyazott raszteres grafikák képfelbontásának csökkentéséhez.

## Gyakran Ismételt Kérdések
### Használhatom az Aspose.Page for Java-t más dokumentumformátumokhoz?
Az Aspose.Page elsősorban a PostScript és XPS formátumok oldalkezelésére koncentrál.

### Hol találok több példát és dokumentációt az Aspose.Page for Java-hoz?
Látogassa meg a [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) oldalt a részletes információkért.

### Van ingyenes próba a Aspose.Page for Java-hoz?
Igen, ingyenes próbát érhet el [itt](https://releases.aspose.com/).

### Hogyan szerezhetek ideiglenes licencet az Aspose.Page for Java-hoz?
Ideiglenes licencet szerezhet [itt](https://purchase.aspose.com/temporary-license/).

### Hol kérhetek közösségi támogatást vagy tehetek fel kérdéseket az Aspose.Page for Java-val kapcsolatban?
Látogassa meg az [Aspose.Page for Java fórumot](https://forum.aspose.com/c/page/39) a közösségi megbeszélésekért.

## Gyakran Ismételt Kérdések

**Q: Mi a különbség a `translate` és a `scale` között?**  
A: A `translate` a koordináta‑rendszer origóját mozgatja, míg a `scale` a rajzolt objektumok méretét változtatja az X és/vagy Y tengelyek mentén.

**Q: Kombinálhatok több transzformációt egyetlen grafikai állapotban?**  
A: Igen—ha a rajzolás előtt sorban meghívja a `translate`, `scale`, `rotate` vagy `shear` metódusokat, egy kombinált affín transzformációt hoz létre.

**Q: Hogyan állíthatom vissza a transzformációkat egy alakzat rajzolása után?**  
A: Használja a `document.writeGraphicsRestore()`-t a korábban mentett grafikai állapot visszaállításához.

**Q: Lehet-e egy téglalapot a középpontja körül elforgatni?**  
A: Teljesen. A téglalapot transzformálja az origóba, alkalmazza a `rotate(angle)`‑t, majd vissza transzformálja a kiindulási helyére a rajzolás előtt.

**Q: Támogatja-e az Aspose.Page az anti‑aliasing-et a simább grafikákhoz?**  
A: Igen—állítsa be a megfelelő renderelési opciókat a `PsSaveOptions`‑ban az anti‑aliasing engedélyezéséhez.

---

**Utoljára frissítve:** 2026-02-07  
**Tesztelve:** Aspose.Page for Java 24.12  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}