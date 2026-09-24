---
date: 2026-09-24
description: Ismerje meg, hogyan használhatja az Aspose.Page‑t EPS‑ről PNG‑re Java‑ban,
  hogyan konfigurálhatja a mért licencet, és hogyan írhat hatékonyan PNG‑fájl Java‑kódot.
keywords:
- aspose page convert eps
- write png file java
- metered license java
- eps to png conversion
lastmod: 2026-09-24
linktitle: Metered License beállítása Java‑ban
og_description: Aspose.Page konvertálása EPS‑ről PNG‑re Java‑ban mért licenccel. Ez
  az útmutató lépésről‑lépésre bemutatja, hogyan konfigurálja a licencet, hogyan rendereli
  az EPS‑t, és hogyan ír PNG‑fájl Java‑kódot.
og_image_alt: Guide showing Aspose.Page Java converting EPS to PNG with metered license
og_title: Aspose.Page konvertálása EPS‑ről PNG‑re Java‑ban (mért licenc)
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  headline: Aspose.Page convert EPS to PNG in Java (metered license)
  type: TechArticle
- description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  name: Aspose.Page convert EPS to PNG in Java (metered license)
  steps:
  - name: initialize document and image format
    text: First, set the metered keys and define the output format (PNG). This establishes
      the foundation for the conversion. The `MeteredLicense` class stores your public
      and private keys, while `ImageSaveOptions` tells Aspose.Page to produce PNG
      output.
  - name: initialize PostScript input stream
    text: Open the EPS file you want to convert. The stream feeds the document into
      Aspose.Page. The `FileInputStream` reads the EPS file from disk, allowing the
      `Document` constructor to parse the PostScript data.
  - name: check document license
    text: Always verify that the metered license was applied correctly before processing.
      The `isLicensed()` method returns `true` only when the supplied keys are valid,
      preventing accidental usage of an unlicensed library.
  - name: initialize options and image device
    text: Create the options object that controls conversion settings and the device
      that will receive the rendered image. `ImageDevice` captures the rasterized
      output in memory, while `ImageSaveOptions` lets you tweak DPI, compression level,
      and color depth.
  - name: save EPS file as image
    text: This is the core **save EPS as PNG** call. The document is rendered into
      the image device using the options we configured. The `document.save(device,
      options)` method performs the rasterization in a single step.
  - name: get and save image bytes
    text: Extract the PNG bytes from the device and write them to a file on disk.
      This step demonstrates how to **write PNG file Java** safely. `Files.write(Paths.get("output.png"),
      device.getImagesBytes()[0])` persists the image without additional libraries.
  type: HowTo
- questions:
  - answer: Log into your Aspose account, navigate to the **Metered License** section,
      and copy the generated public and private keys.
    question: How do I obtain metered public and private keys?
  - answer: Aspose.Page offers a free trial with full functionality; production use
      requires a paid license. Download the trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is the Aspose.Page library free?
  - answer: Yes, a commercial license permits deployment in production environments.
      Purchase a license [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for commercial projects?
  - answer: The full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: Temporary licenses are provided through the Aspose portal [Aspose temporary
      license page](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image conversion
- metered licensing
title: Aspose.Page konvertálása EPS‑ről PNG‑re Java‑ban (mért licenc)
url: /hu/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page EPS konvertálása PNG-re Java-ban (mért licenc)

## Bevezetés
Ha **EPS mentése PNG-ként** Java alkalmazásban, egyszerű licencelés mellett van szükséged, jó helyen vagy. Ez az útmutató végigvezet a **mért licenc** beállításán az Aspose.Page-hez, egy EPS (Encapsulated PostScript) fájl betöltésén, és a PNG képre konvertálásán. A végére megérted, hogyan **renderelj EPS-t PNG-re hatékonyan**, és hogyan **írj PNG fájlt Java-ban** olyan kóddal, amely megbízhatóan működik éles környezetben.

## Gyors válaszok
- **Mi jelent a “save EPS as PNG”?** Egy vektor EPS fájlt raszteres PNG képpé konvertál, megőrizve az átlátszóságot és a veszteségmentes tömörítést.  
- **Miért használjunk mért licencet?** Csak a feldolgozott oldalakat fizeted, ami ideális változó terhelés esetén.  
- **Szükség van internetkapcsolatra?** Nem, a mért kulcsok helyben, a JVM-en ellenőrződnek.  
- **Melyik Java verzió szükséges?** A Java 8 vagy újabb teljesen támogatott.  
- **Mennyi időt vesz igénybe a beállítás?** Körülbelül 10 perc egy alap megvalósításhoz.

## Mi a “save EPS to PNG”?
Az EPS PNG-ként mentése egy vektor Encapsulated PostScript dokumentumot raszteres PNG képpé konvertál, megőrizve az átlátszóságot és a veszteségmentes tömörítést. Ez a átalakítás hasznos, ha web‑kész grafikákra, bélyegképekre vagy nyomtatható előnézetekre van szükség, amelyeket bármely böngésző megjeleníthet PostScript értelmező nélkül.

## Miért rendereljünk EPS-t PNG-re az Aspose.Page segítségével?
Aspose.Page egy tisztán Java API-t biztosít, amely magas hűséggel rasterizálja az EPS fájlokat, több mint 50 kimeneti formátumot támogat, és mért licencelést kínál, így csak a konvertált mennyiségért fizetsz. A könyvtár több száz oldalas dokumentumokat képes feldolgozni anélkül, hogy az egész fájlt a memóriába töltené, gyors, pontos renderelést biztosítva bármely JVM‑t támogató platformon.

## Előfeltételek
- Alap Java fejlesztői tapasztalat.  
- Az Aspose.Page könyvtár letöltve a [Aspose.Page Java letöltési oldalról](https://releases.aspose.com/page/java/).  
- Egy pár mért nyilvános és privát kulcs a Aspose fiókodból.  

## Csomagok importálása
Az `import` utasítások a szükséges osztályokat a láthatóságba hozzák. Tartsd ezt a blokkot pontosan úgy, ahogy látható, hogy a kód változtatás nélkül leforduljon.

A `java.io` osztályok a fájlfolyamokat kezelik, míg az Aspose.Page osztályok a licencelést, a dokumentum betöltését és a kép renderelését.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Hogyan mentsünk EPS-t PNG-ként az Aspose.Page Java használatával
Az alábbi lépésről‑lépésre útmutató a licencelést, betöltést, renderelést és a végső PNG fájl írását egyesíti.

### Közvetlen válasz
Töltsd be az EPS fájlt, alkalmazz egy mért licencet, konfiguráld a `ImageSaveOptions`-t PNG-re, rendereld a dokumentumot egy `ImageDevice`-re, és végül írd a kapott bájt tömböt a lemezre. Ez a sorozat befejezi a **save EPS as PNG** munkafolyamatot néhány Java sorban.

### 1. lépés: dokumentum és képpformátum inicializálása
Először állítsd be a mért kulcsokat és definiáld a kimeneti formátumot (PNG). Ez lefekteti a konverzió alapját.

A `MeteredLicense` osztály tárolja a nyilvános és privát kulcsaidat, míg az `ImageSaveOptions` azt mondja az Aspose.Page-nek, hogy PNG kimenetet állítson elő.

```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```

### 2. lépés: PostScript bemeneti adatfolyam inicializálása
Nyisd meg a konvertálni kívánt EPS fájlt. Az adatfolyam a dokumentumot az Aspose.Page-be táplálja.

A `FileInputStream` a lemezről olvassa be az EPS fájlt, lehetővé téve a `Document` konstruktor számára a PostScript adatok elemzését.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### 3. lépés: dokumentum licenc ellenőrzése
Mindig ellenőrizd, hogy a mért licenc helyesen alkalmazva lett-e a feldolgozás előtt.

Az `isLicensed()` metódus csak akkor ad vissza `true` értéket, ha a megadott kulcsok érvényesek, így megakadályozva egy nem licencelt könyvtár véletlen használatát.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### 4. lépés: beállítások és képeszköz inicializálása
Hozd létre a beállítási objektumot, amely a konverziós beállításokat irányítja, és az eszközt, amely a renderelt képet fogadja.

Az `ImageDevice` a rasterizált kimenetet memóriában tárolja, míg az `ImageSaveOptions` lehetővé teszi a DPI, a tömörítési szint és a színmélység finomhangolását.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### 5. lépés: EPS fájl mentése képként
Ez a fő **save EPS as PNG** hívás. A dokumentum a beállított opciókkal a képeszközbe renderelődik.

A `document.save(device, options)` metódus egy lépésben végzi el a rasterizációt.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### 6. lépés: kép bájtok lekérése és mentése
Vedd ki a PNG bájtokat az eszközből, és írd őket egy fájlba a lemezen. Ez a lépés bemutatja, hogyan **írj PNG fájlt Java-ban** biztonságosan.

A `Files.write(Paths.get("output.png"), device.getImagesBytes()[0])` a képet további könyvtárak nélkül menti.

```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```

## Gyakori problémák és megoldások
| Probléma | Miért fordul elő | Megoldás |
|----------|------------------|----------|
| **A licenc nem ismerhető fel** | A kulcsok helytelenek, vagy a `setMeteredKey` a dokumentum feldolgozása után van meghívva. | Ellenőrizd újra a nyilvános/privát kulcs karakterláncokat, és győződj meg róla, hogy a `setMeteredKey` minden Aspose.Page hívás előtt fut. |
| **A kimeneti fájl üres** | `device.getImagesBytes()` `null` értéket adott vissza, mert az EPS fájlt nem sikerült feldolgozni. | Ellenőrizd, hogy az EPS fájl érvényes, és hogy az `ImageSaveOptions` nem nulla vászonméretet határoz meg. |
| **OutOfMemoryError nagy EPS esetén** | Nagy vektorfájlok renderelése sok heap memóriát fogyaszt. | Feldolgozd az oldalakat egyesével, vagy növeld a JVM heap méretét (`-Xmx2g`). |

## Gyakran ismételt kérdések

**Q: Hogyan szerezhetem meg a mért nyilvános és privát kulcsokat?**  
A: Jelentkezz be a Aspose fiókodba, navigálj a **Metered License** szekcióba, és másold ki a generált nyilvános és privát kulcsokat.

**Q: Ingyenes az Aspose.Page könyvtár?**  
A: Az Aspose.Page ingyenes próbaidőszakot kínál teljes funkcionalitással; a termelési használathoz fizetős licenc szükséges. Töltsd le a próbaverziót a [Aspose trial download page](https://releases.aspose.com/) oldalról.

**Q: Használhatom az Aspose.Page-t kereskedelmi projektekhez?**  
A: Igen, egy kereskedelmi licenc lehetővé teszi a telepítést éles környezetben. Vásárolj licencet a [Aspose purchase page](https://purchase.aspose.com/buy) oldalon.

**Q: Hol találok további dokumentációt?**  
A: A teljes API referencia elérhető a [Aspose.Page Java API reference](https://reference.aspose.com/page/java/) oldalon.

**Q: Hogyan szerezhetek ideiglenes licencet értékeléshez?**  
A: Ideiglenes licenceket a Aspose portálon keresztül biztosítanak: [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: Mi a teendő, ha többoldalas EPS fájlokat kell konvertálni?**  
A: Iterálj végig az egyes oldalakon a `device.getImagesBytes()` használatával, és írd minden bájt tömböt külön PNG fájlba.

**Q: Módosíthatom a PNG minőségét vagy színmélységét?**  
A: Igen, állítsd be az `ImageSaveOptions`-t (pl. `options.setCompressionLevel(9)`) a `document.save(...)` hívása előtt.

---

**Utolsó frissítés:** 2026-09-24  
**Tesztelve:** Aspose.Page 24.12 for Java (legújabb)  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Hogyan állítsunk be licencet az Aspose.Page Java API-hoz – Licenckezelés](/page/java/license-management/)
- [PS konvertálása PNG-re az Aspose.Page Java API-val](/page/java/postscript-conversion/to-image/)
- [EPS átméretezése az Aspose.Page használatával – Java EPS manipuláció](/page/java/manipulation-eps/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}