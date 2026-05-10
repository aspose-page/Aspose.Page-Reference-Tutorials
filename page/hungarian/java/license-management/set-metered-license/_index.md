---
date: 2026-02-05
description: Ismerje meg, hogyan menthet EPS-t PNG formátumba az Aspose.Page for Java
  használatával, miközben metered licencet konfigurál. Lépésről‑lépésre útmutató teljes
  kódrészlettel.
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: EPS mentése PNG-ként az Aspose.Page Java-val (Mérői licenc)
url: /hu/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# EPS mentése PNG formátumba az Aspose.Page Java (Mérői licenc) segítségével

## Introduction
Ha **EPS mentése PNG** formátumba szükséges egy Java‑alkalmazásban, és egy egyszerű megoldást keresel a licenckezelésre, jó helyen vagy. Ez az útmutató végigvezet a mérői licenc konfigurálásán az Aspose.Page‑hez, egy PostScript (EPS) fájl betöltésén, és a PNG képre konvertálásán – mindezt világos, lépésről‑lépésre követhető módon. A végére megérted, hogyan **renderelj EPS‑t PNG‑re** hatékonyan, és hogyan írd meg a **write PNG file Java** kódot, amely a termelési környezetben is működik.

## Quick Answers
- **Mi jelent a „save EPS as PNG”?** Átalakít egy vektor EPS fájlt raszteres PNG képpé.  
- **Miért használjunk mérői licencet?** Lehetővé teszi, hogy csak a feldolgozott oldalakat fizessük, ami tökéletes változó terhelés esetén.  
- **Szükség van internetkapcsolatra?** Nem, a mérői kulcsok helyben ellenőrződnek.  
- **Melyik Java verzió szükséges?** Java 8 vagy újabb.  
- **Mennyi időt vesz igénybe a beállítás?** Körülbelül 10 perc egy alap megvalósításhoz.  

## What is “save EPS as PNG”?
Az EPS mentése PNG formátumba egy skálázható Encapsulated PostScript dokumentumot alakít át egy széles körben támogatott bitmap formátummá. A PNG megőrzi az átlátszóságot és veszteségmentes tömörítést kínál, így ideális webgrafikákhoz, bélyegképekhez és nyomtatási előnézetekhez.

## Why render EPS to PNG with Aspose.Page?
- **Pure Java API** – nincs natív függőség, így bárhol futtatható, ahol a JVM támogatott.  
- **High fidelity rendering** – a vektor grafikák pontosan raszterizálódnak, megőrizve a vonalminőséget.  
- **Metered licensing** – csak a konvertált mennyiségért fizetsz, ami kiszámítható költségeket biztosít.  
- **Multiple output options** – a PNG mellett JPEG, TIFF és egyéb formátumok is előállíthatók, ami rugalmasságot biztosít különböző projektekhez.  

## Prerequisites
Mielőtt elkezdenéd, győződj meg róla, hogy rendelkezel:

- Alapvető Java programozási ismeretekkel.  
- Aspose.Page könyvtár telepítve – töltsd le [itt](https://releases.aspose.com/page/java/).  
- Mérői nyilvános és privát kulcsokkal, amelyeket az Aspose fiókodon keresztül szerezhetsz be.  

## Import Packages
Először importáld a szükséges osztályokat. Hagyd a import blokkot pontosan úgy, ahogy látható, hogy a kód változtatás nélkül leforduljon.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## How to save EPS as PNG using Aspose.Page Java
Az alábbi lépésről‑lépésre útmutató egyesíti a licencbeállítást, a betöltést, a renderelést és a végleges PNG fájl írását.

### Step 1: Initialize Document and Image Format
Itt állítjuk be a mérői kulcsokat és definiáljuk a kimeneti formátumot (PNG). Ez a **save EPS as PNG** művelet alapja.

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

### Step 2: Initialize PostScript Input Stream
Nyisd meg a konvertálni kívánt EPS fájlt. A stream táplálja a dokumentumot az Aspose.Page‑nek.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### Step 3: Check Document License
Mindig ellenőrizd, hogy a mérői licenc helyesen lett‑e alkalmazva a feldolgozás előtt.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### Step 4: Initialize Options and Image Device
Hozd létre az opciós objektumot, amely a konverziós beállításokat szabályozza, valamint az eszközt, amely a renderelt képet fogadja.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### Step 5: Save EPS File as Image
Ez a **save EPS as PNG** hívás központi része. A dokumentum a beállított opciók alapján renderelődik az image device‑be.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### Step 6: Get and Save Image Bytes
Vedd ki a PNG bájtokat az eszközből, és írd őket egy fájlba a lemezen. Ez a lépés bemutatja, hogyan **write PNG file Java** kódot használj biztonságosan.

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

## Common Issues and Solutions
| Probléma | Miért fordul elő | Megoldás |
|----------|------------------|----------|
| **License not recognized** | A kulcsok helytelenek vagy rossz sorrendben vannak megadva. | Ellenőrizd a nyilvános/privát kulcs karakterláncokat, és győződj meg róla, hogy a `setMeteredKey` a dokumentumfeldolgozás előtt kerül meghívásra. |
| **Output file is empty** | A `device.getImagesBytes()` `null`‑t adott vissza. | Győződj meg arról, hogy az EPS fájl érvényes, és az `ImageSaveOptions` nem nulla méretű vásznat állít be. |
| **OutOfMemoryError on large EPS** | Nagy vektor fájlok renderelése sok memóriát igényel. | Oldalak egyenkénti feldolgozása, vagy a JVM heap növelése (`-Xmx2g`). |

## Frequently Asked Questions

**Q: How do I obtain metered public and private keys?**  
A: Ezeket a kulcsokat az Aspose fiókodon keresztül szerezheted be.

**Q: Is the Aspose.Page library free?**  
A: Az Aspose.Page ingyenes próbaverzióval és fizetős változatokkal is elérhető. Ingyenes próbaért látogass el [ide](https://releases.aspose.com/).

**Q: Can I use Aspose.Page for commercial projects?**  
A: Igen, az Aspose.Page kereskedelmi licenceket kínál. Vásárolhatsz [itt](https://purchase.aspose.com/buy).

**Q: Where can I find additional documentation?**  
A: Tekintsd meg a dokumentációt [itt](https://reference.aspose.com/page/java/).

**Q: How can I get temporary licenses?**  
A: Ideiglenes licencek igényelhetők [itt](https://purchase.aspose.com/temporary-license/).

**Q: What if I need to convert multi‑page EPS files?**  
A: Iterálj minden oldal felett a `device.getImagesBytes()` használatával, és írd ki az egyes bájt tömböket külön PNG fájlokba.

**Q: Can I change the PNG quality or color depth?**  
A: Igen, állítsd be az `ImageSaveOptions`‑t (pl. `options.setCompressionLevel(...)`) a `document.save(...)` hívás előtt.

---

**Last Updated:** 2025-12-03  
**Tested With:** Aspose.Page 24.12 for Java  
**Author:** Aspose  

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.Page 24.12 for Java (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}