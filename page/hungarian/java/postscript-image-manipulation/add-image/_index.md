---
date: 2026-02-15
description: Tanulja meg, hogyan hozhat létre PostScript Java dokumentumokat, és hogyan
  generálhat PostScript dokumentumfájlokat a kép elmozdításával és forgatásával az
  Aspose.Page for Java használatával.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: PostScript létrehozása Java – Kép hozzáadása Java PostScriptben
url: /hu/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PostScript Java létrehozása – Kép hozzáadása Java PostScriptben

## Bevezetés
Ebben az oktatóanyagban megtanulja, hogyan **create postscript java** dokumentumokat hozhat létre, és hogyan ágyazhat be képeket az Aspose.Page for Java könyvtár segítségével. Lépésről lépésre végigvezetjük a folyamaton, az új PostScript fájl inicializálásától a **translate and rotate image** transzformációk alkalmazásáig. A végére képes lesz programozottan generálni PostScript fájlokat, és pixel‑pontos pontossággal szabályozni a képek elhelyezését – tökéletes automatizált jelentéskészítéshez, nyomtatási munkafolyamatokhoz vagy bármilyen olyan helyzethez, ahol **generate postscript document** kimenetre van szükség Java-ból.

## Gyors válaszok
- **Melyik könyvtár szükséges?** Aspose.Page for Java  
- **Hozzáadhatok több képet?** Igen – ismételje meg a transzformációs és rajzolási lépéseket  
- **Szükségem van licencre a fejlesztéshez?** Egy ingyenes próba verzió teszteléshez megfelelő; licenc szükséges a termeléshez  
- **Melyik Java verzió támogatott?** Java 8 és újabb  
- **Támogatott a kép forgatása?** Teljes mértékben – használja a `AffineTransform.rotate()`-t  

## Mi az a create postscript java?
A **create postscript java** művelet egy PostScript oldal leíró fájlt hoz létre, amely szöveget, vektorgrafikát és raszter képeket kódol. Az Aspose.Page segítségével ezeket a fájlokat közvetlenül Java kódból építheti fel, teljes programozott vezérlést biztosítva az elrendezés, a méretezés és a forgatás felett, anélkül, hogy külön PostScript interpreterre lenne szükség.

## Miért használja az Aspose.Page-t képműveletekhez?
- **High‑level API:** Alacsony szintű PostScript parancsokat egyszerű Java metódusokká absztrahálja.  
- **Cross‑platform:** Bármely, Java-t támogató operációs rendszeren fut.  
- **Full graphics‑state control:** Szabadon mentheti, visszaállíthatja, transzformálhatja, méretezheti és forgathatja a grafikát.  
- **No external dependencies:** Belsőleg kezeli a kép betöltését, formátumkonverziót és beágyazást.  

## Előfeltételek
Mielőtt a kódba merülnénk, győződjön meg róla, hogy rendelkezik:

- Java Development Kit (JDK) telepítve a rendszerén.  
- Aspose.Page for Java könyvtárral. Letöltheti [itt](https://releases.aspose.com/page/java/).  
- Alapvető Java programozási ismeretekkel.  

## Csomagok importálása
A kezdéshez importálja a szükséges csomagokat a Java projektjébe. Használja az alábbi kódrészletet referenciaként:

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 1. lépés: Grafika mentés írása
Az első lépés a grafika mentés (save) írása a dokumentumba. Ez biztosítja, hogy a később végrehajtott transzformációk vagy módosítások szükség esetén visszavonhatók legyenek.

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

## 2. lépés: Transzformálás (translate and rotate image)
Ezután transzformálja a dokumentumot, és hozza létre a `BufferedImage` objektumot a képfájlból. Alkalmazzon egy sor transzformációt, például méretezést és forgatást a `AffineTransform` segítségével. Itt történik a **translate and rotate image** művelet.

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

## 3. lépés: Kép hozzáadása a dokumentumhoz
Most adja hozzá a transzformált képet a dokumentumhoz.

```java
document.drawImage(image, transform, null);
```

## 4. lépés: Grafika visszaállítás írása
A kép hozzáadása után írja a grafika visszaállítás (restore) parancsot a végrehajtott módosítások befejezéséhez.

```java
document.writeGraphicsRestore();
```

## 5. lépés: Aktuális oldal bezárása és mentése
Zárja be az aktuális oldalt, és mentse a dokumentumot.

```java
document.closePage();
document.save();
```

Ezeket a lépéseket megismételheti több kép hozzáadásához, vagy testreszabhatja a transzformációkat az igényei szerint.

## Gyakori problémák és megoldások
- **FileNotFoundException:** Győződjön meg róla, hogy a `dataDir` útvonal fájlelválasztóval (`/` vagy `\\`) végződik, és a kép fájlneve pontosan egyezik.  
- **ImageIO.read returns null:** Ellenőrizze, hogy a képformátum támogatott-e (pl. JPEG, PNG).  
- **Incorrect rotation angle:** A `AffineTransform.rotate` radiánokat vár. Szükség esetén konvertálja a fokokat radiánra (`Math.toRadians(degrees)`).  

## Gyakran feltett kérdések

**Q: Használhatom az Aspose.Page for Java-t más programozási nyelvekkel?**  
A: Az Aspose.Page elsősorban Java-t támogat, de elérhetők verziók más programozási nyelvekhez is.

**Q: Van ingyenes próba verzió az Aspose.Page for Java-hoz?**  
A: Igen, az ingyenes próbát elérheti [itt](https://releases.aspose.com/).

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.Page for Java-hoz?**  
A: Ideiglenes licencet kaphat [itt](https://purchase.aspose.com/temporary-license/).

**Q: Hol találok közösségi támogatást és megbeszéléseket az Aspose.Page for Java-val kapcsolatban?**  
A: Látogassa meg az [Aspose.Page Fórumot](https://forum.aspose.com/c/page/39) a közösségi támogatásért.

**Q: Van további forrás a vásárláshoz az Aspose.Page for Java-hoz?**  
A: A könyvtárat megvásárolhatja [itt](https://purchase.aspose.com/buy).

## Összegzés
Gratulálunk! Sikeresen megtanulta, hogyan **create postscript java** dokumentumokat hozhat létre, és hogyan ágyazhat be képeket az Aspose.Page for Java segítségével. Tekintse meg a [dokumentációt](https://reference.aspose.com/page/java/) a fejlettebb funkciók és lehetőségek, például vektorgrafika, szövegmegjelenítés és egyedi oldalméretek megismeréséhez.

---

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.Page for Java 23.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}