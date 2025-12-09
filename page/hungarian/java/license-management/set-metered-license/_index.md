---
date: 2025-12-03
description: Tanulja meg, hogyan menthet EPS-t PNG‑ként az Aspose.Page for Java használatával,
  miközben metered licencet konfigurál. Lépésről‑lépésre útmutató teljes kódrészlettel.
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: EPS mentése PNG‑ként az Aspose.Page Java‑val (Mérő licenc)
url: /hu/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# EPS mentése PNG-ként az Aspose.Page Java (Mérői licenc)

## Bevezetés
Ha **EPS-t PNG-ként** szeretnél menteni egy Java alkalmazásban, és egy gondtalan módot keresel a licenckezelésre, jó helyen vagy. Ez az útmutató végigvezet a mérői licenc beállításán az Aspose.Page számára, egy PostScript (EPS) fájl betöltésén, és annak PNG képpé konvertálásán – mindezt világos, könnyen követhető lépésekben.

## Gyors válaszok
- **Mit jelent az “EPS mentése PNG-ként”?** Egy vektor EPS fájlt raszteres PNG képpé konvertál.  
- **Miért használjunk mérői licencet?** Csak a feldolgozott oldalakat fizeted, ami tökéletes változó terheléshez.  
- **Szükség van internetkapcsolatra?** Nem, a mérői kulcsok helyben kerülnek ellenőrzésre.  
- **Melyik Java verzió szükséges?** Java 8 vagy újabb.  
- **Mennyi időt vesz igénybe a beállítás?** Körülbelül 10 perc egy alap megvalósításhoz.

## Mi az “EPS mentése PNG-ként”?
Az EPS PNG-ként való mentése egy skálázható Encapsulated PostScript dokumentumot alakít át egy széles körben támogatott bitmap formátummá. A PNG megőrzi az átlátszóságot és veszteségmentes tömörítést kínál, így ideális webgrafikákhoz, bélyegképekhez és nyomtatási előnézetekhez.

## Miért használjuk az Aspose.Page-t ehhez a feladathoz?
- **Pure Java API** – nincs natív függőség.  
- **Magas hűség** – a vektor grafika pontosan renderelődik.  
- **Mérői licencelés** – csak a konvertált mennyiségért fizetsz.  
- **Több kimeneti formátum támogatása** – PNG, JPEG, TIFF, stb.

## Előfeltételek
Mielőtt elkezdenéd, győződj meg róla, hogy rendelkezel:

- Alapvető Java programozási ismeretekkel.  
- Aspose.Page könyvtár telepítve – töltsd le [itt](https://releases.aspose.com/page/java/).  
- Mérői nyilvános és privát kulcsok, amelyeket az Aspose fiókodon keresztül szerezhetsz.

## Csomagok importálása
Először importáld a szükséges osztályokat. Tartsd meg az import blokkot pontosan úgy, ahogy látható, hogy a kód változtatás nélkül leforduljon.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## 1. lépés: Dokumentum és képpformátum inicializálása
Itt állítjuk be a mérői kulcsokat és definiáljuk a kimeneti formátumot (PNG). Ez a **EPS mentése PNG-ként** művelet alapja.

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

## 2. lépés: PostScript bemeneti stream inicializálása
Nyisd meg azt az EPS fájlt, amelyet konvertálni szeretnél. A stream táplálja a dokumentumot az Aspose.Page-be.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

## 3. lépés: Dokumentum licenc ellenőrzése
Mindig ellenőrizd, hogy a mérői licenc helyesen lett-e alkalmazva a feldolgozás előtt.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

## 4. lépés: Opciók és képeszköz inicializálása
Hozd létre az opciós objektumot, amely a konverziós beállításokat szabályozza, valamint az eszközt, amely a renderelt képet fogadja.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

## 5. lépés: EPS fájl mentése képként
Ez a **EPS mentése PNG-ként** hívás magja. A dokumentum a beállított opciók szerint kerül renderelésre a képeszközbe.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

## 6. lépés: Képadatok lekérése és mentése
Vedd ki a PNG bájtokat az eszközből, és írd őket egy fájlba a lemezen.

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
| **A licenc nem ismerhető fel** | A kulcsok helytelenek vagy rossz sorrendben vannak. | Ellenőrizd a nyilvános/privát kulcssztringeket, és győződj meg róla, hogy a `setMeteredKey` a dokumentum feldolgozása előtt kerül meghívásra. |
| **A kimeneti fájl üres** | `device.getImagesBytes()` `null` értéket adott vissza. | Ellenőrizd, hogy az EPS fájl érvényes-e, és hogy az `ImageSaveOptions` nincs-e nullméretű vászonra állítva. |
| **OutOfMemoryError nagy EPS esetén** | Nagy vektor fájlok renderelése sok memóriát fogyaszt. | Oldalak feldolgozása egyesével, vagy növeld a JVM heap méretét (`-Xmx2g`). |

## Gyakran ismételt kérdések

**K: Hogyan szerezhetem meg a mérői nyilvános és privát kulcsokat?**  
V: Ezeket a kulcsokat az Aspose fiókodon keresztül szerezheted meg.

**K: Ingyenes-e az Aspose.Page könyvtár?**  
V: Az Aspose.Page ingyenes próba és fizetős verziókat is kínál. A próba verzióért látogass el [ide](https://releases.aspose.com/).

**K: Használhatom az Aspose.Page-t kereskedelmi projektekhez?**  
V: Igen, az Aspose.Page kereskedelmi licenceket kínál. Ezeket megvásárolhatod [itt](https://purchase.aspose.com/buy).

**K: Hol találok további dokumentációt?**  
V: Tekintsd meg a dokumentációt [itt](https://reference.aspose.com/page/java/).

**K: Hogyan szerezhetek ideiglenes licenceket?**  
V: Ideiglenes licenceket itt szerezhetsz [itt](https://purchase.aspose.com/temporary-license/).

---

**Utolsó frissítés:** 2025-12-03  
**Tesztelve a következővel:** Aspose.Page 24.12 for Java  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}