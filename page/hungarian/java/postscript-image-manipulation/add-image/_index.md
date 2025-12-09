---
date: 2025-12-09
description: Tanulja meg, hogyan hozhat létre PostScript dokumentumot Java-ban, és
  hogyan transzformálja és forgassa el a képet az Aspose.Page segítségével a zökkenőmentes
  képműveletekhez.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: PostScript dokumentum létrehozása Java – Kép hozzáadása Java PostScriptben
url: /hu/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PostScript dokumentum létrehozása Java-ban – Kép hozzáadása Java PostScriptben

## Bevezetés
Ebben az útmutatóban megtanulja, hogyan **hozzon létre PostScript dokumentumot Java-ban**, és hogyan ágyazhat be képeket az Aspose.Page for Java könyvtár segítségével. Lépésről lépésre végigvezetjük a dokumentum beállításától a **kép eltolás és forgatás** műveletek alkalmazásáig. A végére képes lesz programozottan gazdag PostScript fájlokat generálni, és testre szabni a képek elhelyezését a pontos elrendezési igényeihez.

## Gyors válaszok
- **Melyik könyvtár szükséges?** Aspose.Page for Java  
- **Hozzáadhatok több képet?** Igen – ismételje meg az átalakítási és rajzolási lépéseket  
- **Szükség van licencre fejlesztéshez?** Egy ingyenes próba a teszteléshez működik; licenc szükséges a termeléshez  
- **Melyik Java verzió támogatott?** Java 8 és újabb  
- **Támogatott a kép forgatása?** Teljes mértékben – használja a `AffineTransform.rotate()`-t  

## Mi az a PostScript dokumentum létrehozása Java-ban?
A PostScript dokumentum egy oldal leíró nyelv fájl, amely szöveget, grafikát és képeket ír le. Az Aspose.Page segítségével programozottan generálhatja ezeket a fájlokat Java-ban, teljes irányítást biztosítva az elrendezés, a grafikai állapot és a képfeldolgozás felett, anélkül, hogy PostScript értelmezőre lenne szükség.

## Miért használja az Aspose.Page-t képfeldolgozáshoz?
- **Magas szintű API:** Egyszerűsíti a komplex PostScript parancsokat.  
- **Keresztplatformos:** Minden Java-t támogató operációs rendszeren működik.  
- **Teljes grafikai állapot vezérlés:** Könnyedén menthet, visszaállíthat, eltolhat, méretezhet és forgathat grafikákat.  
- **Nincs külső függőség:** Belsőleg kezeli a képek betöltését és konvertálását.  

## Előfeltételek
Mielőtt a kódba merülnénk, győződjön meg róla, hogy rendelkezik a következőkkel:

- Java Development Kit (JDK) telepítve a rendszerén.  
- Aspose.Page for Java könyvtár. Letöltheti [itt](https://releases.aspose.com/page/java/).  
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
Az első lépés a grafika mentés írása a dokumentumba. Ez biztosítja, hogy a később végrehajtott átalakítások vagy módosítások szükség esetén visszavonhatók legyenek.

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

## 2. lépés: Eltolás és átalakítás (kép eltolása és forgatása)
Ezután tolja el a dokumentumot, és hozza létre a `BufferedImage` objektumot a képfájlból. Alkalmazzon egy sor átalakítást, például méretezést és forgatást a `AffineTransform` használatával. Itt történik a **kép eltolása és forgatása** művelet.

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
Most adja hozzá az átalakított képet a dokumentumhoz.

```java
document.drawImage(image, transform, null);
```

## 4. lépés: Grafika visszaállítás írása
A kép hozzáadása után írja a grafika visszaállítását a módosítások befejezéséhez.

```java
document.writeGraphicsRestore();
```

## 5. lépés: Aktuális oldal bezárása és mentése
Zárja be az aktuális oldalt, és mentse a dokumentumot.

```java
document.closePage();
document.save();
```

Ezeket a lépéseket megismételheti több kép hozzáadásához, vagy testre szabhatja az átalakításokat az igényei szerint.

## Gyakori problémák és megoldások
- **FileNotFoundException:** Győződjön meg róla, hogy a `dataDir` útvonal fájlválasztóval (`/` vagy `\\`) végződik, és a képfájl neve pontosan egyezik.  
- **ImageIO.read null értéket ad:** Ellenőrizze, hogy a képformátum támogatott-e (pl. JPEG, PNG).  
- **Helytelen forgatási szög:** A `AffineTransform.rotate` radiánokat vár. Szükség esetén konvertálja a fokokat radiánokra (`Math.toRadians(degrees)`).

## Gyakran ismételt kérdések

**Q: Használhatom az Aspose.Page for Java-t más programozási nyelvekkel?**  
A: Az Aspose.Page elsősorban Java-t támogat, de más programozási nyelvekhez is elérhetők verziók.

**Q: Van ingyenes próba a Aspose.Page for Java-hoz?**  
A: Igen, az ingyenes próbát [itt](https://releases.aspose.com/) érheti el.

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.Page for Java-hoz?**  
A: Ideiglenes licencet [itt](https://purchase.aspose.com/temporary-license/) kaphat.

**Q: Hol találhatok közösségi támogatást és megbeszéléseket az Aspose.Page for Java-hoz?**  
A: Látogassa meg az [Aspose.Page Fórumot](https://forum.aspose.com/c/page/39) a közösségi támogatásért.

**Q: Van további forrás a Aspose.Page for Java megvásárlásához?**  
A: A könyvtárat [itt](https://purchase.aspose.com/buy) vásárolhatja meg.

## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan **hozzon létre PostScript dokumentumot Java-ban**, és hogyan ágyazzon be képeket az Aspose.Page for Java segítségével. Fedezze fel a [dokumentációt](https://reference.aspose.com/page/java/), hogy további fejlett funkciókat és lehetőségeket ismerjen meg, például vektorgrafikát, szövegmegjelenítést és egyedi oldalméreteket.

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.Page for Java 23.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}