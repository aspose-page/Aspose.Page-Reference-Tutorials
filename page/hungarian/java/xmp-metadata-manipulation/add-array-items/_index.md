---
title: Adjon hozzá tömbelemeket az XMP metaadatokhoz Java használatával
linktitle: Adjon hozzá tömbelemeket az XMP metaadatokhoz Java használatával
second_title: Aspose.Page Java API
description: Javítsa az EPS-fájlokat az Aspose.Page for Java segítségével. Tanuljon meg tömbelemeket könnyedén hozzáadni XMP-metaadatokhoz. Kövesse lépésről lépésre útmutatónkat most!
weight: 10
url: /hu/java/xmp-metadata-manipulation/add-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adjon hozzá tömbelemeket az XMP metaadatokhoz Java használatával

## Bevezetés
Üdvözöljük az Aspose.Page for Java használatáról szóló, lépésenkénti útmutatónkban tömbelemek XMP-metaadatokhoz való hozzáadásához. Az Aspose.Page egy hatékony Java-könyvtár, amely lehetővé teszi a különféle dokumentumformátumok, köztük az EPS-fájlok kezelését és kezelését. Ebben az oktatóanyagban arra a konkrét feladatra összpontosítunk, hogy tömbelemeket adjunk hozzá az XMP metaadatokhoz Java használatával.
## Előfeltételek
Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- Aspose.Page for Java könyvtár telepítve.
- A Java programozás alapvető ismerete.
- Érvényes EPS-fájl meglévő XMP-metaadatokkal vagy PS-metaadat-megjegyzésekkel.
## Csomagok importálása
A kezdéshez importálnia kell az Aspose.Page használatához szükséges csomagokat. Írja be a következő sorokat a Java fájl elejére:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
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
Ebben a lépésben lekérjük a meglévő XMP-metaadatokat az EPS-fájlból. Ha az EPS-fájl még nem tartalmaz XMP-metaadatokat, az Aspose.Page újat generál, és kitölti a PS-metaadat-megjegyzésekből származó értékekkel.
## 2. lépés: Adja hozzá a "dc:title" tömbelemet
```java
// Adjon hozzá még egy "dc:title" tömbelemet
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Most hozzáadunk egy új tömbelemet a "dc:title" tulajdonsághoz az XMP metaadatokban. Cserélje ki a „NewTitle”-t a kívánt címre.
## 3. lépés: Adja hozzá a "dc:creator" tömbelemet
```java
// Adjon hozzá még egy "dc:creator" tömbelemet
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
Hasonlóképpen hozzáadunk egy új tömbelemet a "dc:creator" tulajdonsághoz az XMP metaadatokban. Cserélje ki a „NewCreator” szót a kívánt alkotói információval.
## 4. lépés: Inicializálja a kimeneti EPS fájlfolyamot
```java
// A kimeneti EPS fájlfolyam inicializálása
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Készítse elő a kimeneti EPS-fájlfolyamot, amelybe a frissített XMP-metaadatokkal rendelkező módosított dokumentum mentésre kerül.
## 5. lépés: Mentse el a dokumentumot módosított XMP-metaadatokkal
```java
//Mentse a dokumentumot a megváltozott XMP-metaadatokkal
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Mentse a dokumentumot a frissített XMP-metaadatokkal a kimeneti EPS-fájlba.
## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan adhat hozzá tömbelemeket XMP-metaadatokhoz az Aspose.Page for Java segítségével. Ez a hatékony könyvtár leegyszerűsíti az EPS-fájlok kezelésének folyamatát, és széleskörű funkcionalitást biztosít a dokumentumfeldolgozáshoz.
## Gyakran Ismételt Kérdések

### Használhatom az Aspose.Page for Java oldalt más dokumentumformátumokkal?
Igen, az Aspose.Page különféle dokumentumformátumokat támogat, beleértve az EPS-t, a PDF-t és az XPS-t.
### Létezik ingyenes próbaverzió az Aspose.Page for Java számára?
 Igen, hozzáférhet az ingyenes próbaverzióhoz[itt](https://releases.aspose.com/).
### Hol találom az Aspose.Page for Java dokumentációját?
 A dokumentáció elérhető[itt](https://reference.aspose.com/page/java/).
### Hogyan vásárolhatom meg az Aspose.Page for Java oldalt?
 Megvásárolhatja a terméket[itt](https://purchase.aspose.com/buy).
### Rendelkezésre állnak ideiglenes licencek az Aspose.Page for Java számára?
 Igen, kaphat ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
