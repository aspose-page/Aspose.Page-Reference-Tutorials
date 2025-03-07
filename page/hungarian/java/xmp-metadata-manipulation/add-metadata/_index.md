---
title: Metaadatok hozzáadása az XMP-ben Java használatával
linktitle: Metaadatok hozzáadása az XMP-ben Java használatával
second_title: Aspose.Page Java API
description: Fedezze fel az Aspose.Page for Java zökkenőmentes integrációját, és tanulja meg, hogyan adhat hozzá XMP-metaadatokat könnyedén EPS-fájljaihoz. Emelje fel dokumentumkezelési játékát még ma!
weight: 11
url: /hu/java/xmp-metadata-manipulation/add-metadata/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Metaadatok hozzáadása az XMP-ben Java használatával

## Bevezetés
Szeretné javítani dokumentuma metaadatait azáltal, hogy Java használatával XMP-információkat ad hozzá? Ne keressen tovább! Ez a lépésenkénti útmutató végigvezeti a metaadatok EPS-fájlhoz való hozzáadásának folyamatán az Aspose.Page for Java könyvtár használatával. Az Aspose.Page egy hatékony eszköz, amely leegyszerűsíti a dokumentumkezelési feladatokat a Java alkalmazásokban.
## Előfeltételek
Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- Java programozási alapismeretek.
-  Aspose.Page a Java könyvtárhoz telepítve. Letöltheti[itt](https://releases.aspose.com/page/java/).
- Egy módosítani kívánt EPS-fájl.
## Csomagok importálása
Először is importálja a szükséges csomagokat a Java programba:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```
## 1. lépés: Szerezze be az XMP metaadatokat
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Inicializálja a bemeneti EPS fájlfolyamot
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Szerezze be az XMP metaadatokat. Ha az EPS-fájl nem tartalmaz XMP-metaadatokat, egy újat hoz létre a PS-metaadat-megjegyzések értékei alapján (%%Creator, %%CreateDate, %%Title stb.)
XmpMetadata xmp = document.getXmpMetadata();
```
Ügyeljen arra, hogy a „Saját dokumentumkönyvtár” helyére a tényleges elérési út kerüljön, ahol a dokumentumokat tárolják.

## 2. lépés: A CreatorTool értékének lekérése
```java
// Szerezze be a „CreatorTool” értéket
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## 3. lépés: A CreateDate érték lekérése
```java
// Szerezze be a "CreateDate" értéket
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## 4. lépés: A cím értékének lekérése
```java
// Szerezze be a „Title” értéket
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```
## 5. lépés: A formátum értékének lekérése
```java
//Szerezze be a "formátum" értéket
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## 6. lépés: Az Alkotói érték lekérése
```java
// Szerezzen „alkotói” értéket
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```
## 7. lépés: A MetadataDate érték lekérése
```java
// Szerezze be a „MetadataDate” értéket
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```
## 8. lépés: Mentse el a dokumentumot új XMP-metaadatokkal
```java
// A kimeneti EPS fájlfolyam inicializálása
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Mentse a dokumentumot új XMP-metaadatokkal
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Végül ne felejtse el bezárni a bemeneti EPS adatfolyamot:
```java
// Zárja be a bemeneti EPS adatfolyamot
psStream.close();
```
Sikeresen hozzáadta a metaadatokat az EPS-fájlhoz az Aspose.Page for Java segítségével!
## Következtetés
Ebben az oktatóanyagban megvizsgáltuk az XMP-metaadatok EPS-fájlhoz való hozzáadásának folyamatát az Aspose.Page for Java könyvtár használatával. Ez a hatékony eszköz lehetővé teszi a dokumentumok zökkenőmentes kezelését, javítva ezzel az általános dokumentumkezelési élményt.
## GYIK
### K: Ingyenesen használható az Aspose.Page for Java?
 V: Az Aspose.Page for Java kereskedelmi termék. Funkcióit ingyenes próbaverzióval fedezheti fel[itt](https://releases.aspose.com/).
### K: Hol találom az Aspose.Page for Java dokumentációját?
 V: A dokumentáció elérhető[itt](https://reference.aspose.com/page/java/).
### K: Hogyan szerezhetek ideiglenes licencet az Aspose.Page for Java számára?
 V: Kaphat ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).
### K: Milyen fájlformátumokat támogat az Aspose.Page for Java?
V: Az Aspose.Page for Java különféle formátumokat támogat, beleértve az EPS-t, a PDF-t és az XPS-t.
### K: Megvásárolhatom az Aspose.Page-t Java-hoz?
 V: Igen, megvásárolhatja az Aspose.Page-t Java-hoz[itt](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
