---
date: 2026-08-23
description: Tanulja meg, hogyan használja az aspose.page image manipulation java-t
  képek beágyazásához és forgatásához PostScript fájlokban, egyértelmű Java példákkal.
keywords:
- aspose.page image manipulation java
- add image postscript java
- java postscript image rotation
- aspose.page java tutorial
- image embedding java
lastmod: 2026-08-23
linktitle: Kép hozzáadása Java PostScriptben
og_description: Tanulja meg, hogyan használja az aspose.page image manipulation java-t
  képek beágyazásához és forgatásához PostScript fájlokban, lépésről‑lépésre Java
  kódrészletekkel.
og_image_alt: Guide showing Java code to add and rotate images in PostScript using
  Aspose.Page
og_title: Hogyan használjuk az aspose.page image manipulation java-t a kép hozzáadásához
schemas:
- author: Aspose
  dateModified: '2026-08-23'
  description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  headline: How to use aspose.page image manipulation java to add image
  type: TechArticle
- description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  name: How to use aspose.page image manipulation java to add image
  steps:
  - name: write graphics save
    text: Saving the graphics state isolates your transformations so you can revert
      later. This is equivalent to the `gsave` operator in raw PostScript.
  - name: translate and transform (translate and rotate image)
    text: First, create a `BufferedImage` from the source file, then build an `AffineTransform`
      that translates the image to the desired coordinates and rotates it around its
      centre. `AffineTransform.rotate` expects an angle in radians, so convert degrees
      with `Math.toRadians(degrees)`. **AffineTransform** is
  - name: add image to document
    text: After configuring the transform, draw the image onto the current page. The
      library automatically converts the `BufferedImage` into an appropriate PostScript
      image stream.
  - name: write graphics restore
    text: Calling restore (`grestore`) returns the graphics state to what it was before
      the save, ensuring subsequent drawing commands are not affected by the previous
      transformation.
  - name: close current page and save
    text: Finish the page, close the document, and write the output file to disk.
      You can repeat the above sequence to embed additional images, adjusting the
      translation coordinates and rotation angle each time.
  type: HowTo
- questions:
  - answer: The core library is Java‑only, but Aspose provides equivalent APIs for
      .NET, C++, and Python, each tailored to its platform.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can access the free trial **[Aspose.Page free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for community assistance.
    question: Where can I find community support and discussions related to Aspose.Page
      for Java?
  - answer: You can buy the library **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.
    question: Are there any additional resources for purchasing Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image manipulation
- postscript
- image rotation
- java tutorial
title: Hogyan használjuk az aspose.page image manipulation java-t a kép hozzáadásához
url: /hu/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan használjuk az aspose.page képmanipulációt Java-ban kép hozzáadásához

## Bevezetés
Ebben az oktatóanyagban megtanulja, hogyan **use aspose.page image manipulation java** segítségével hozhat létre PostScript fájlokat, ágyazhat be raszteres képeket, és alkalmazhat eltolás‑ és forgatási transzformációkat. A útmutató végére képes lesz pixel‑tökéletes PostScript kimenetet generálni Java‑ból — ideális automatizált jelentéskészítéshez, nyomtatási folyamatokhoz, vagy bármely munkafolyamathoz, amely pontos képelhelyezést igényel egy PostScript dokumentumban.

## Gyors válaszok
- **Milyen könyvtár szükséges?** Aspose.Page for Java  
- **Hozzáadhatok több képet?** Yes – repeat the transform and draw steps for each image  
- **Szükségem van licencre fejlesztéshez?** A free trial works for testing; a license is required for production  
- **Melyik Java verzió támogatott?** Java 8 and later  
- **Támogatott a kép forgatása?** Absolutely – use `AffineTransform.rotate()`

## Mi az aspose.page image manipulation java?
`aspose.page image manipulation java` az Aspose.Page API, amely lehetővé teszi, hogy programozottan építsen, szerkesszen és rendereljen PostScript dokumentumokat Java kódból, beleértve a kép elhelyezésének, méretezésének és forgatásának teljes irányítását. Ezzel az API-val elkerülheti az alacsony szintű PostScript szintaxist, és a könyvtár belül kezeli a formátumkonverziót és beágyazást.

## Miért használjuk az aspose.page-t képmanipulációhoz?
Az Aspose.Page **50+ képformátumot** (köztük JPEG, PNG, BMP, TIFF) biztosít, és be tudja ágyazni őket PostScript-be anélkül, hogy az egész dokumentumot a memóriába töltené, lehetővé téve több száz oldalas fájlok feldolgozását, miközben a memóriahasználat egy tipikus szerveren 100 MB alatt marad. A magas szintű API elrejti a komplex PostScript parancsokat, így tömör Java kódot írhat a nyers PS operátorok helyett.

## Előfeltételek
- Java Development Kit (JDK) 8 vagy újabb telepítve.  
- Aspose.Page for Java könyvtár – töltse le **[Aspose.Page for Java download page](https://releases.aspose.com/page/java/)**.  
- Alapvető ismeretek a Java szintaxisról és az objektum‑orientált programozásról.

## Mi az create postscript java?
A PostScript fájl létrehozása Java‑ból azt jelenti, hogy programozottan generál egy `.ps` dokumentumot, amely a PostScript nyelv segítségével leírja az oldal elrendezését, vektorgrafikákat és raszteres képeket. Az Aspose.Page a Java hívásait érvényes PostScript utasításokká alakítja, lehetővé téve nyomtatásra kész fájlok előállítását külön PostScript értelmező nélkül.

## Hogyan adjunk hozzá egy képet eltolással és forgatással lépésről lépésre

Töltse be a képet, alkalmazzon egy `AffineTransform`-ot, és rajzolja az oldalra. A következő lépések vázolják a pontos sorrendet, amelyet követnie kell.

### 1. lépés: grafikai állapot mentése
A grafikai állapot mentése elkülöníti a transzformációkat, így később visszaállítható. Ez a nyers PostScript `gsave` operátorának felel meg.

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### 2. lépés: eltolás és transzformáció (kép eltolása és forgatása)
Először hozzon létre egy `BufferedImage`-et a forrásfájlból, majd építsen egy `AffineTransform`-ot, amely a képet a kívánt koordinátákra eltolja és a középpontja körül elforgatja. Az `AffineTransform.rotate` radiánban várja a szöget, ezért a fokokat konvertálja a `Math.toRadians(degrees)` segítségével.

**AffineTransform** egy Java osztály, amely 2‑D affín transzformációt képvisel, például eltolást, forgatást, méretezést vagy nyírást.  
**BufferedImage** egy Java osztály, amely egy képet tárol memóriában pixelraszterként.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

### 3. lépés: kép hozzáadása a dokumentumhoz
A transzformáció beállítása után rajzolja a képet az aktuális oldalra. A könyvtár automatikusan átalakítja a `BufferedImage`-et egy megfelelő PostScript képfolyammá.

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

### 4. lépés: grafikai állapot visszaállítása
A visszaállítás (`grestore`) meghívása visszaállítja a grafikai állapotot arra, ami a mentés előtt volt, biztosítva, hogy a későbbi rajzolási parancsok ne legyenek befolyásolva az előző transzformációtól.

```java
document.drawImage(image, transform, null);
```

### 5. lépés: aktuális oldal lezárása és mentése
Fejezze be az oldalt, zárja le a dokumentumot, és írja a kimeneti fájlt a lemezre.

```java
document.writeGraphicsRestore();
```

A fenti sorozatot megismételve további képeket ágyazhat be, minden alkalommal módosítva az eltolási koordinátákat és a forgásszöget.

## Gyakori problémák és megoldások
- **FileNotFoundException:** Ellenőrizze, hogy a `dataDir` fájlelválasztóval (`/` vagy `\\`) végződik-e, és hogy a kép fájlneve pontosan egyezik-e.  
- **ImageIO.read returns null:** Győződjön meg arról, hogy a képformátum szerepel a támogatott listán (JPEG, PNG, BMP, GIF, TIFF).  
- **Incorrect rotation angle:** Az `AffineTransform.rotate` radiánban működik; használja a `Math.toRadians(degrees)`-t a fokok konvertálásához.  
- **Memory spikes on large pages:** Használja a `Document.save`-et a `saveOptions.setCompress(true)` beállítással a memóriahasználat csökkentése érdekében.

## Gyakran feltett kérdések

**Q: Használhatom az Aspose.Page for Java-t más programozási nyelvekkel?**  
A: A magkönyvtár csak Java‑ra készült, de az Aspose ekvivalens API‑kat biztosít .NET, C++ és Python számára, mindegyik a saját platformjára szabva.

**Q: Elérhető ingyenes próba az Aspose.Page for Java-hoz?**  
A: Igen, hozzáférhet az ingyenes próba **[Aspose.Page free trial page](https://releases.aspose.com/)**.

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.Page for Java-hoz?**  
A: Ideiglenes licencet kérhet a **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.

**Q: Hol találok közösségi támogatást és megbeszéléseket az Aspose.Page for Java-val kapcsolatban?**  
A: Látogassa meg a **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** közösségi segítségért.

**Q: Van további forrás a vásárláshoz az Aspose.Page for Java-hoz?**  
A: Megvásárolhatja a könyvtárat a **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.

## Következtetés
Most már rendelkezik egy teljes, vég‑től‑végig példával a **aspose.page image manipulation java** használatára, amely PostScript fájlt hoz létre, eltolja és forgatja a képet, majd elmenti az eredményt. Fedezze fel a teljes **[documentation](https://reference.aspose.com/page/java/)**-t, hogy megismerje a fejlett funkciókat, például vektorgrafikákat, egyedi oldalméreteket és szövegrenderelést.

---

**Utoljára frissítve:** 2026-08-23  
**Tesztelve a következővel:** Aspose.Page for Java 23.11  
**Szerző:** Aspose  

```java
document.closePage();
document.save();
```

## Kapcsolódó oktatóanyagok

- [Hogyan konvertáljunk PostScript-et PDF-re az Aspose.Page Java API használatával](/page/java/postscript-conversion/to-pdf/)
- [Hogyan adjunk hozzá színátmenetet: átlós színátmenet Java PostScript-ben az Aspose.Page Java használatával](/page/java/postscript-gradient-addition/diagonal/)
- [Hogyan adjunk hozzá keresztmintát Java PostScript-ben az Aspose.Page használatával](/page/java/postscript-hatch-patterns/add-hatch-pattern/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}