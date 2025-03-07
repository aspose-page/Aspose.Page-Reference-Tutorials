---
title: Metaadatok beszerzése az XMP-ből Java használatával
linktitle: Metaadatok beszerzése az XMP-ből Java használatával
second_title: Aspose.Page Java API
description: Fedezze fel az Aspose.Page for Java erejét, amellyel könnyedén kinyerheti az XMP metaadatokat. Emelje fel a dokumentumelemzést lépésenkénti útmutatónkkal!
weight: 18
url: /hu/java/xmp-metadata-manipulation/get-metadata/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Metaadatok beszerzése az XMP-ből Java használatával

## Bevezetés
Üdvözöljük lépésenkénti útmutatónkban az Aspose.Page for Java használatáról metaadatok kinyerésére XMP-fájlokból. Az XMP (Extensible Metadata Platform) szabványos módot biztosít a metaadatok fájlokban való tárolására. Ez az oktatóanyag az alapvető információk lekérésére összpontosít az XMP-ből Java használatával, és betekintést nyújt a dokumentum részleteibe.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- Java Development Kit (JDK): Győződjön meg arról, hogy a Java telepítve van a gépen.
-  Aspose.Page for Java: Töltse le és telepítse az Aspose.Page könyvtárat, amelyet megtalál[itt](https://releases.aspose.com/page/java/).
## Csomagok importálása
A Java projektben importálja a szükséges csomagokat:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## 1. lépés: Inicializálja a bemeneti EPS fájlfolyamot
Először állítsa be a dokumentumkönyvtár elérési útját, és inicializálja a bemeneti EPS fájlfolyamot.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```
## 2. lépés: Szerezze be az XMP metaadatokat
Az XMP metaadatok lekérése az EPS-fájlból. Ha a fájlból hiányoznak az XMP-metaadatok, akkor a rendszer egy újat generál a PS-metaadat-megjegyzések értékeivel.
```java
XmpMetadata xmp = document.getXmpMetadata();
```
## 3. lépés: A CreatorTool információinak kibontása
Ellenőrizze és nyomtassa ki a „CreatorTool” értéket az XMP metaadatokból.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## 4. lépés: A CreateDate információk kibontása
Ellenőrizze és nyomtassa ki a „CreateDate” értéket az XMP metaadatokból.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## 5. lépés: A miniatűr szélességének lekérése
Ha léteznek bélyegképek, akkor bontsa ki és nyomtassa ki az első bélyegkép szélességét.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```
## 6. lépés: Formátuminformációk kibontása
Ellenőrizze és nyomtassa ki a "formátum" értéket az XMP metaadatokból.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## 7. lépés: Szerezze be a DocumentID-t
Ellenőrizze és nyomtassa ki a „DocumentID” értéket az XMP metaadatokból.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```
## Következtetés
Gratulálunk! Sikeresen megtanulta az XMP metaadatok kibontását az Aspose.Page for Java segítségével. Ez az útmutató átfogó áttekintést nyújt a folyamatról, biztosítva, hogy hatékonyan lehessen lekérni a dokumentumokból a lényeges információkat.
## Gyakran Ismételt Kérdések
### Használhatom az Aspose.Page for Java-t más programozási nyelvekkel?
 Igen, az Aspose.Page több nyelvet is támogat, beleértve a Java-t, a .NET-et stb. Ellenőrizd a[dokumentáció](https://reference.aspose.com/page/java/) a részletekért.
### Elérhető ingyenes próbaverzió az Aspose.Page for Java számára?
 Igen, hozzáférhet az ingyenes próbaverzióhoz[itt](https://releases.aspose.com/).
### Hol találok támogatást az Aspose.Page for Java számára?
 Meglátogatni a[Aspose.Page fórum](https://forum.aspose.com/c/page/39) közösségi támogatásért.
### Hogyan szerezhetek ideiglenes licencet az Aspose.Page for Java számára?
 Kaphat ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).
### Vannak további források az Aspose.Page for Java számára?
 Fedezze fel a teljes[dokumentáció](https://reference.aspose.com/page/java/) és töltse le a könyvtárat[itt](https://releases.aspose.com/page/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
