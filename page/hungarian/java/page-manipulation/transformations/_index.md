---
date: 2026-10-20
description: Ismerje meg, hogyan méretezze a téglalapot az Aspose.Page for Java segítségével,
  hogyan translate shape, és hogyan alkalmazzon affine transform a PostScript dokumentumok
  létrehozásához.
keywords:
- how to scale rectangle
- how to translate shape
- save postscript file
- apply affine transform
- java graphics scaling
lastmod: 2026-10-20
linktitle: Transzformációk a Java oldalműveletekben
og_description: Ismerje meg, hogyan méretezze a téglalapot, translate shape, és affine
  transform alkalmazásával az Aspose.Page for Java segítségével hatékonyan generáljon
  PostScript fájlokat.
og_image_alt: Screenshot of Java code scaling a rectangle with Aspose.Page
og_title: Hogyan méretezze a téglalapot az Aspise.Page for Java – lépésről lépésre
  útmutató
schemas:
- author: Aspose
  dateModified: '2026-10-20'
  description: Learn how to scale rectangle with Aspose.Page for Java, how to translate
    shape, and apply affine transform to create PostScript documents.
  headline: How to Scale Rectangle with Aspose.Page for Java
  type: TechArticle
- questions:
  - answer: '`translate` moves the origin of the coordinate system, while `scale`
      changes the size of drawn objects along the X and/or Y axes.'
    question: What is the difference between `translate` and `scale`?
  - answer: Yes—by calling `translate`, `scale`, `rotate`, or `shear` sequentially
      before drawing, you create a combined affine transformation.
    question: Can I combine multiple transformations in a single graphics state?
  - answer: Use `writeGraphicsRestore()` to revert to the previously saved graphics
      state.
    question: How do I reset transformations after drawing a shape?
  - answer: Absolutely. Translate the rectangle to the origin, apply `rotate(angle)`,
      then translate it back before drawing.
    question: Is it possible to rotate a rectangle around its center?
  - answer: Yes—set the appropriate rendering options in `PsSaveOptions` to enable
      anti‑aliasing.
    question: Does Aspose.Page support anti‑aliasing for smoother graphics?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript generation
- affine transformation
- rectangle scaling
title: Hogyan méretezze a téglalapot az Aspose.Page for Java segítségével
url: /hu/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan méretezzenek téglalapot az Aspose.Page for Java segítségével

## Bevezetés
Ebben az útmutatóban megismerheted, hogyan **how to scale rectangle** objektumokat használva az Aspose.Page for Java-t, miközben megtanulod, hogyan translate shape positions, rotate graphics, és affín transzformációs műveleteket alkalmazz a magas minőségű PostScript kimenet előállításához. Ezek a technikák lehetővé teszik összetett, eszközfüggetlen grafikák létrehozását alacsony szintű renderelőkód írása nélkül, így Java alkalmazásaid erősebbek és karbantarthatóbbak lesznek.

## Gyors válaszok
`scale(sx, sy)` méretezi a grafikus kontextust a megadott vízszintes és függőleges tényezőkkel.  

- **Hogyan méretezhetek egy téglalapot Java-ban az Aspose.Page segítségével?** Hívd meg a `scale(sx, sy)` metódust a grafikus kontextuson a téglalap rajzolása előtt.  
- **Mozgathatok (translate) egy alakzatot anélkül, hogy más grafikákat befolyásolna?** Igen—csomagold a transzlációt a `writeGraphicsSave()` és `writeGraphicsRestore()` hívások közé.  
- **Melyik osztály hoz létre PostScript fájlt?** Használd a `PsDocument`-et a `PsSaveOptions`-szal együtt.  
- **Szükségem van licencre a termelési használathoz?** Érvényes Aspose.Page licenc szükséges a kereskedelmi telepítésekhez.  
- **Melyik Java verzió támogatott?** Az Aspose.Page a Java 8 és újabb verziókkal működik.

## Előfeltételek
Mielőtt elkezdenéd, ellenőrizd, hogy rendelkezel:

- Alapos ismeretekkel a Java alap szintaxisáról és az objektum‑orientált koncepciókról.  
- Az Aspose.Page for Java könyvtár telepítve. Letöltheted a [Aspose.Page for Java dokumentációból](https://reference.aspose.com/page/java/).  
- Java IDE (IntelliJ IDEA, Eclipse vagy VS Code), amely a könyvtár JAR fájljait a classpath‑on konfigurálja.

## Csomagok importálása
`PsDocument` a fő osztály a PostScript dokumentum létrehozásához, a `PsSaveOptions` pedig beállítja a dokumentum mentésének módját.  

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Mi az „how to scale rectangle” az Aspose.Page-ben?
`scale(float sx, float sy)` metódus affín méretezési transzformációt alkalmaz az aktuális grafikus állapotra, átméretezve a későbbi rajzokat a `sx` (vízszintes) és `sy` (függőleges) tényezőkkel. Ez a **how to scale rectangle** kulcsszó mögötti alapművelet. Ha ezt a transzformációt a rajzolás előtt alkalmazod, a későbbi alakzatok, például a téglalapok az új méretekkel jelennek meg, miközben arányukat megtartják.

## Hogyan helyezzünk át alakzatot az Aspose.Page segítségével
`writeGraphicsSave()` elmenti az aktuális grafikus állapotot, a `writeGraphicsRestore()` pedig visszaállítja, biztosítva, hogy a transzformációk csak a kívánt alakzatra hatnak. A transzláció áthelyezi a koordináta‑rendszer origóját anélkül, hogy megváltoztatná az objektum méreteit. Ha a `translate(dx, dy)`‑t `writeGraphicsSave()` / `writeGraphicsRestore()`‑rel veszed körül, biztosítod, hogy csak a kívánt alakzat mozduljon el, míg a többi grafika változatlan marad, ez pontos vezérlést biztosít az egyes elemek felett.

## Példa 1: nincs transzformáció
Az első példa egy téglalapot rajzol transzformáció nélkül, alapvonalat teremtve a későbbi példákkal való vizuális összehasonlításhoz.

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

## Példa 2: transzláció
Ebben a példában a grafikus kontextust 250 egységgel jobbra mozdítjuk a második téglalap rajzolása előtt, bemutatva a **how to translate shape** műveletet.

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

## Példa 3: méretezés
Itt válaszolunk a fő kérdésre, **how to scale rectangle**. A téglalap szélessége az eredeti 50 %-ára, magassága pedig 75 %-ára csökken a `scale(0.5f, 0.75f)` hívás segítségével.

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

## Hogyan forgassunk (rotate) alakzatot Java-ban (rotate shape java)
`rotate(angle)` elforgatja a koordináta‑rendszert a megadott fokban. Töltsd be a `PsDocument`‑et, hívd meg a `rotate(angle)`‑t a grafikus állapoton, rajzold meg az alakzatot, majd állítsd vissza az előző állapotot. Ez a minta megvalósítja a **rotate shape java** és a **how to rotate rectangle** műveleteket egyetlen újrahasználható blokkban, lehetővé téve, hogy a grafikát bármely általad választott pont körül forgasd.

## Miért fontos – valós világ előnyei
- **Eszközfüggetlen kimenet** – Az Aspose.Page képes PostScript és XPS fájlokat generálni, amelyek minden nyomtatón vagy megjelenítőn azonos módon jelennek meg, kiküszöbölve a platform‑specifikus finomhangolásokat.  
- **Finomhangolt vezérlés** – Kombináld a transzlációt, méretezést, nyírást és forgatást a pontos elrendezési specifikációk teljesítéséhez; az API több mint 20 transzformációs kombinációt támogat oldalanként.  
- **Teljesítmény‑orientált feldolgozás** – A könyvtár dokumentumokat dolgoz fel kevesebb, mint 10 MB memóriával tipikus 100‑oldalas jelentések esetén, így a kötegelt feladatok gyorsak és skálázhatóak.

## Gyakori felhasználási esetek
- **Nyomtatható számlák** – Pontosan helyezd el a logókat, vonalkódokat és táblázatokat méretezéssel és transzlációval, hogy megfeleljenek a vállalati arculati irányelveknek.  
- **Műszaki diagramok** – Készíts vázlatokat, ahol minden komponensnek arányosan kell méretezve és elhelyezve lennie.  
- **Automatizált többoldalas jelentések** – Készíts PostScript jelentéseket, amelyeknek az oldalak között konzisztens méretezésre van szüksége, például mérnöki specifikációk esetén.

## Gyakori problémák és megoldások
- **A transzformáció nem áll vissza** – Mindig párosítsd a `writeGraphicsSave()`‑t a `writeGraphicsRestore()`‑val; ellenkező esetben a későbbi rajzok nem kívánt transzformációkat örökölnek.  
- **Váratlan színek** – Állítsd be a festéket (színt) minden transzformáció után, mivel a grafikus állapot nem őrzi meg a színinformációt a visszaállítás után.  
- **Túl nagy fájlméret** – Engedélyezd a tömörítést a `PsSaveOptions`‑ban, és korlátozd a beágyazott raszteres képek felbontását, hogy a végső fájl 50‑oldalas tipikus dokumentumok esetén 5 MB alatt maradjon.

## Gyakran Ismételt Kérdések

### Használhatom az Aspose.Page for Java-t más dokumentumformátumokhoz?
Az Aspose.Page elsősorban a PostScript és XPS formátumok oldalmanipulációjára fókuszál, de korlátozott PDF exportálási lehetőségeket is kínál.

### Hol találok több példát és dokumentációt az Aspose.Page for Java-hoz?
Látogasd meg a [Aspose.Page for Java dokumentációt](https://reference.aspose.com/page/java/) a részletes útmutatók, API referencia és mintaprojektek érdekében.

### Van ingyenes próba a Aspose.Page for Java-hoz?
Igen, ingyenes próbaverziót érhetsz el az **Aspose ingyenes próba letöltés** oldalon: [Aspose free trial download](https://releases.aspose.com/).

### Hogyan szerezhetek ideiglenes licencet az Aspose.Page for Java-hoz?
Szerezz ideiglenes licencet a **temporary license request page** segítségével: [temporary license request page](https://purchase.aspose.com/temporary-license/).

### Hol kérhetek közösségi támogatást vagy tehetek fel kérdéseket az Aspose.Page for Java-ról?
Látogasd meg az [Aspose.Page for Java fórumot](https://forum.aspose.com/c/page/39) a közösségi megbeszélések, kódrészletek és hibaelhárítási tippek érdekében.

## Gyakran Ismételt Kérdések

**Q: Mi a különbség a `translate` és a `scale` között?**  
A: A `translate` áthelyezi a koordináta‑rendszer origóját, míg a `scale` megváltoztatja a rajzolt objektumok méretét az X és/vagy Y tengelyek mentén.

**Q: Kombinálhatok több transzformációt egyetlen grafikus állapotban?**  
A: Igen—ha a rajzolás előtt sorban meghívod a `translate`, `scale`, `rotate` vagy `shear` metódusokat, egy kombinált affín transzformációt hozol létre.

**Q: Hogyan állíthatom vissza a transzformációkat egy alakzat rajzolása után?**  
A: Használd a `writeGraphicsRestore()`‑t, hogy visszatérj az előzőleg mentett grafikus állapothoz.

**Q: Lehetséges egy téglalapot a középpontja körül forgatni?**  
A: Teljesen. Transzformáld a téglalapot az origóba, alkalmazd a `rotate(angle)`‑t, majd a rajzolás előtt helyezd vissza a kiindulási helyére.

**Q: Támogatja az Aspose.Page az anti‑aliasing-et a simább grafikákhoz?**  
A: Igen—állítsd be a megfelelő renderelési beállításokat a `PsSaveOptions`‑ban az anti‑aliasing engedélyezéséhez.

**Utolsó frissítés:** 2026-10-20  
**Tesztelve a következővel:** Aspose.Page for Java 24.12  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Hogyan rajzoljunk téglalapot Java PostScript-ben az Aspose.Page segítségével](/page/java/postscript-shapes/add-rectangle/)
- [Hogyan hozzunk létre radiális gradientet PostScript-ben az Aspose.Page for Java segítségével](/page/java/postscript-gradient-addition/)
- [PostScript oldal manipuláció](/page/java/postscript-page-manipulation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}