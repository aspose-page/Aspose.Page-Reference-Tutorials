---
title: Módosítsa az értékeket az XMP-ben Java használatával
linktitle: Módosítsa az értékeket az XMP-ben Java használatával
second_title: Aspose.Page Java API
description: Javítsa az EPS-dokumentumokat az Aspose.Page for Java segítségével. Könnyedén módosíthatja az XMP metaadatokat a személyre szabott és professzionális tartalom érdekében. #JavaDevelopment
weight: 17
url: /hu/java/xmp-metadata-manipulation/change-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Módosítsa az értékeket az XMP-ben Java használatával

## Bevezetés
A dokumentumfeldolgozás és -kezelés területén az Aspose.Page for Java hatékony eszközként tűnik ki. Ez az oktatóanyag az EPS (Encapsulated PostScript) dokumentumokban az XMP (Extensible Metadata Platform) értékeinek módosításának folyamatát mutatja be Java használatával az Aspose.Page könyvtárral. A részletes útmutatót követve megtudhatja, hogyan módosíthatja könnyedén a metaadatokat, így biztosítva, hogy a dokumentumok az Ön igényeihez igazodjanak.
## Előfeltételek
Mielőtt elkezdené ezt az oktatóanyagot, győződjön meg arról, hogy a következő előfeltételeket teljesítette:
1. Java fejlesztői környezet: Győződjön meg arról, hogy a gépén van működő Java fejlesztői környezet.
2.  Aspose.Page for Java Library: Töltse le és telepítse az Aspose.Page for Java könyvtárat. Megtalálható a szükséges csomag[itt](https://releases.aspose.com/page/java/).
## Csomagok importálása
Kezdje azzal, hogy importálja a szükséges csomagokat a Java projektbe. Ezek a csomagok létfontosságúak az EPS dokumentumok kezeléséhez és kezeléséhez.
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
XMP-metaadatok lekérése az EPS-dokumentumból. Ha az EPS-fájl nem tartalmaz XMP-metaadatokat, egy új fájl jön létre a PS-metaadat-megjegyzésekből származó értékekkel, például %%Creator, %%CreateDate és %%Title.
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Inicializálja a bemeneti EPS fájlfolyamot
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Szerezze be az XMP metaadatokat. Ha az EPS-fájl nem tartalmaz XMP-metaadatokat, egy újat hoz létre a PS-metaadat-megjegyzésekből származó értékekkel
XmpMetadata xmp = document.getXmpMetadata();
```
## 2. lépés: Módosítsa a „ModifyDate” értékét
Módosítsa a "ModifyDate" értéket az XMP metaadatokban, hogy az tükrözze a kívánt dátumot.
```java
// Módosítsa a „ModifyDate” értéket
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```
## 3. lépés: Módosítsa a „Creator” értékét
Frissítse a „Creator” értéket az XMP-metaadatokban a dokumentum készítőjének megadásához.
```java
// Módosítsa az „alkotó” értékét
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```
## 4. lépés: Módosítsa a „Title” értékét
Módosítsa a "Title" értéket az XMP metaadatokban, hogy megfelelő címet állítson be a dokumentumhoz.
```java
//Módosítsa a "cím" értékét
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```
## 5. lépés: Mentse el a dokumentumot módosított XMP-metaadatokkal
Mentse a dokumentumot a frissített XMP-metaadatokkal egy új EPS-fájlba.
```java
// A kimeneti EPS fájlfolyam inicializálása
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
//Mentse a dokumentumot a megváltozott XMP-metaadatokkal
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Következtetés
Gratulálunk! Sikeresen navigált az XMP-értékek módosításának folyamatában az EPS-dokumentumokban az Aspose.Page for Java használatával. Ez az oktatóanyag a metaadatok módosításához szükséges ismeretekkel ruházta fel, így biztosítva, hogy a dokumentumok zökkenőmentesen illeszkedjenek az Ön speciális követelményeihez.
## GYIK
### K: Hogyan kezelhetem az időzóna szempontjait az XMP-értékek módosításakor?
 Használja`TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` az időzóna-beállítások következetességének biztosítása érdekében.
### K: Megváltoztathatok több XMP értéket egyetlen művelettel?
 Igen, a`put` módszer minden kívánt értékhez, egyszerre több XMP-értéket is módosíthat.
### K: Hol találok további dokumentációt az Aspose.Page for Java-hoz?
 Tekintse meg az átfogó dokumentációt[itt](https://reference.aspose.com/page/java/).
### K: Elérhető ingyenes próbaverzió az Aspose.Page for Java számára?
 Igen, hozzáférhet az ingyenes próbaverzióhoz[itt](https://releases.aspose.com/).
### K: Hogyan szerezhetek ideiglenes licencet az Aspose.Page for Java számára?
 Szerezzen ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
