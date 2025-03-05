---
title: Egyszerű tulajdonságok hozzáadása az XMP-hez Java használatával
linktitle: Egyszerű tulajdonságok hozzáadása az XMP-hez Java használatával
second_title: Aspose.Page Java API
description: Oldja fel az Aspose.Page-t a Java-ban rejlő lehetőségekhez az EPS-fájlokban lévő XMP-metaadatok tulajdonságainak hozzáadására vonatkozó útmutatónkkal. Emelje fel a dokumentumfeldolgozást könnyedén!
type: docs
weight: 14
url: /hu/java/xmp-metadata-manipulation/add-simple-properties/
---
## Bevezetés
dokumentumfeldolgozás folyamatosan változó környezetében a metaadatok hatékony kezelése kulcsfontosságú. Az Aspose.Page for Java feljogosítja a fejlesztőket az Extensible Metadata Platform (XMP) adatainak zökkenőmentes manipulálására. Ebben az oktatóanyagban megvizsgáljuk az egyszerű tulajdonságok hozzáadásának folyamatát az XMP-hez Java használatával, és átfogó, lépésről lépésre szóló útmutatót nyújtunk Önnek.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételeket teljesítette:
- Java programozási alapismeretek.
-  Aspose.Page a Java könyvtárhoz telepítve. Letöltheti[itt](https://releases.aspose.com/page/java/).
- Egy minta EPS-fájl, amely metaadatokat tartalmaz. Ha nem rendelkezik ilyennel, nyugodtan használja a mellékelt „xmp3.eps” fájlt.
## Csomagok importálása
Győződjön meg róla, hogy importálja a szükséges csomagokat a projekt elindításához:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```
## 1. lépés: Szerezze be az XMP metaadatokat
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Inicializálja a bemeneti EPS fájlfolyamot
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Szerezze be az XMP metaadatokat. Ha az EPS-fájl nem tartalmaz XMP-metaadatokat, akkor egy újat kapunk, amely tele van a PS-metaadatok megjegyzéseiből származó értékekkel (%%Creator, %%CreateDate, %%Title stb.)
XmpMetadata xmp = document.getXmpMetadata();
```
## 2. lépés: Adja hozzá a dátumtulajdonságot
```java
// Adja hozzá a dátumtulajdonság „xmp:Date1” értékét
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```
## 3. lépés: Adja hozzá az Integer tulajdonságot
```java
// Adja hozzá az egész tulajdonság "xmp:Intg1" értékét
xmp.put("xmp:Intg1", new XmpValue(111));
```
## 4. lépés: Dupla tulajdonság hozzáadása
```java
// Adjon hozzá dupla tulajdonság "xmp:Double1" értéket
xmp.put("xmp:Double1", new XmpValue(111.11D));
```
## 5. lépés: Adja hozzá a karakterlánc tulajdonságot
```java
// Adja hozzá a karakterlánc tulajdonság "xmp:String1" értékét
xmp.put("xmp:String1", new XmpValue("ABC"));
```
## 6. lépés: Mentse el a dokumentumot
```java
// A kimeneti EPS fájlfolyam inicializálása
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
//Mentse a dokumentumot a megváltozott XMP-metaadatokkal
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## 7. lépés: Zárja be az adatfolyamokat
```java
// Zárja be a bemeneti EPS adatfolyamot
psStream.close();
```
## Következtetés
Az Aspose.Page for Java leegyszerűsíti az XMP-metaadatok kezelésének folyamatát az EPS-fájlokban. Ennek a lépésről-lépésre szóló útmutatónak a követésével könnyedén hozzáadhat egyszerű tulajdonságokat a dokumentum metaadatainak javításához.
## Gyakran Ismételt Kérdések
### Használhatom az Aspose.Page for Java-t más programozási nyelvekkel?
Az Aspose.Page elsősorban a Java-t támogatja, de vannak verziók más nyelvekhez is, például a .NET-hez.
### Elérhető ingyenes próbaverzió az Aspose.Page for Java számára?
 Igen, az Aspose.Page szolgáltatásait ingyenes próbaverzióval fedezheti fel[itt](https://releases.aspose.com/).
### Hol találom az Aspose.Page for Java részletes dokumentációját?
 A dokumentáció elérhető[itt](https://reference.aspose.com/page/java/).
### Hogyan szerezhetek ideiglenes licencet az Aspose.Page for Java számára?
 Ideiglenes jogosítvány szerezhető[itt](https://purchase.aspose.com/temporary-license/).
### Hol vásárolhatom meg az Aspose.Page for Java oldalt?
 Megvásárolhatja a terméket[itt](https://purchase.aspose.com/buy).