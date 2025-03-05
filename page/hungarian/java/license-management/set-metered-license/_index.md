---
title: Könnyedén mérhető licencintegráció az Aspose.Page Java-val
linktitle: Állítsa be a mért licencet a Java-ban
second_title: Aspose.Page Java API
description: Fedezze fel az Aspose.Page és a Java zökkenőmentes integrációját. Könnyedén állíthat be fizetős licenceket, és javíthatja dokumentumfeldolgozási képességeit.
type: docs
weight: 10
url: /hu/java/license-management/set-metered-license/
---
## Bevezetés
Üdvözöljük átfogó útmutatónkban, amely az Aspose.Page használatával állíthatja be a fizetős licenceket Java nyelven. Ha javítani szeretné dokumentumfeldolgozási képességeit, és biztosítani szeretné az Aspose.Page zökkenőmentes integrációját, akkor jó helyen jár. Ebben az oktatóanyagban végigvezetjük a folyamaton, az egyes lépéseket könnyen emészthető darabokra bontva.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételeket teljesítette:
- Java programozási alapismeretek.
-  Aspose.Page könyvtár telepítve. Letöltheti innen[itt](https://releases.aspose.com/page/java/).
- Mért nyilvános és privát kulcsok, amelyeket az Aspose-fiókján keresztül szerezhet be.
## Csomagok importálása
Kezdjük a Java programunkhoz szükséges csomagok importálásával. Győződjön meg arról, hogy az Aspose.Page könyvtár integrálva van a projektbe.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;

```
## 1. lépés: Inicializálja a dokumentum- és képformátumot
Az első lépés a dokumentum beállítása és a kívánt képformátum meghatározása.
```java
// állítsa be a mért nyilvános és privát kulcsokat
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Hozzáférés a setMeteredKey tulajdonsághoz, és paraméterként adjon át nyilvános és privát kulcsokat
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```
## 2. lépés: Inicializálja a PostScript beviteli adatfolyamot
Ebben a lépésben inicializáljuk a PostScript bemeneti adatfolyamot a feldolgozáshoz.
```java
// A PostScript beviteli adatfolyam inicializálása
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```
## 3. lépés: Ellenőrizze a dokumentumengedélyt
A folytatás előtt nagyon fontos ellenőrizni, hogy a dokumentum megfelelő-e.
```java
// Ellenőrizze, hogy a dokumentum engedélyezett-e
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```
## 4. lépés: Inicializálja a beállításokat és a képeszközt
Most inicializáljuk az opciókat és a képeszközt az alapértelmezett paraméterekkel.
```java
// Az Options objektum inicializálása az alapértelmezett paraméterekkel.
ImageSaveOptions options = new ImageSaveOptions();
// Inicializálja az ImageDevice objektumot az alapértelmezett paraméterekkel.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```
## 5. lépés: Mentse az EPS-fájlt képként
Mentse az EPS-fájlt képként a megadott beállítások és eszköz használatával.
```java
// Mentse az EPS fájlt képként
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```
## 6. lépés: Képbájtok beszerzése és mentése
Kép byte-ok lekérése és fájlba mentése.
```java
// Képek bájt beszerzése. Egy bájtos tömb egy oldalhoz. A mi esetünkben egy oldalunk van.
byte[][] imagesBytes = device.getImagesBytes();
// Kép byte-ok mentése fájlba
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```
## Következtetés
Gratulálunk! Az Aspose.Page segítségével sikeresen beállította a fizetős licencet a Java nyelven. Ez az oktatóanyag lépésenkénti útmutatót nyújtott a zökkenőmentes integrációs folyamat biztosításához.
## GYIK
### K: Hogyan szerezhetek számlás nyilvános és privát kulcsokat?
Ezeket a kulcsokat Aspose-fiókján keresztül szerezheti be.
### K: Ingyenes az Aspose.Page könyvtár?
 Az Aspose.Page ingyenes próbaverziót és fizetős verziót is kínál. Látogatás[itt](https://releases.aspose.com/) ingyenes próbaverzióra.
### K: Használhatom az Aspose.Page-t kereskedelmi projektekhez?
 Igen, az Aspose.Page kereskedelmi licenceket kínál. Megvásárolhatja őket[itt](https://purchase.aspose.com/buy).
### K: Hol találok további dokumentumokat?
 Lásd a dokumentációt[itt](https://reference.aspose.com/page/java/).
### K: Hogyan szerezhetek ideiglenes engedélyeket?
 Ideiglenes jogosítványok szerezhetők be[itt](https://purchase.aspose.com/temporary-license/).