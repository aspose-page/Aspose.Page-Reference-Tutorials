---
date: 2025-12-18
description: Tudja meg, hogyan adhat hozzá metaadatokat az EPS fájlok XMP metaadataiba
  tömbelemek beszúrásával az Aspose.Page for Java használatával. Kövesse lépésről‑lépésre
  útmutatónkat.
linktitle: Add Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Hogyan adjunk hozzá metaadatokat – Tömb elemek hozzáadása XMP-ben (Java)
url: /hu/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tömbelemek hozzáadása XMP metaadatokhoz Java-val

## Hogyan adjunk hozzá metaadatokat
Üdvözöljük lépésről‑lépésre útmutatónkban, amely **megmutatja, hogyan adhatunk hozzá metaadatokat** EPS fájlokhoz az Aspose.Page for Java segítségével. Ebben az oktatóanyagban végigvezetjük a tömbelemek XMP metaadatokhoz való hozzáadásának folyamatán – egy gyakori igény, amikor a dokumentum információit, például címeket vagy szerzőket szeretnénk gazdagabbá tenni. A végére megérti, miért értékes az XMP, hogyan lehet programozottan manipulálni, és hogyan mentse el a frissített EPS fájlt.

## Gyors válaszok
- **Melyik könyvtárat használja?** Aspose.Page for Java  
- **Melyik fájlformátum a cél?** EPS (Encapsulated PostScript)  
- **Hozzáadhatok több címet?** Igen, használja többször a `xmp.addArrayItem("dc:title", ...)` metódust  
- **Szükséges licenc a termeléshez?** Igen, érvényes Aspose.Page licenc szükséges  
- **Kompatibilis a Java 8+ verziókkal?** Teljesen, minden modern Java verzióval működik  

## Előfeltételek
Mielőtt elkezdenénk, győződjön meg róla, hogy rendelkezik a következőkkel:
- Telepített Aspose.Page for Java könyvtár.
- Alapvető Java programozási ismeretek.
- Érvényes EPS fájl, amely már tartalmaz XMP metaadatokat vagy PS metaadat‑megjegyzéseket.

## Csomagok importálása
A kezdéshez importálnia kell a szükséges csomagokat az Aspose.Page használatához. Helyezze a következő sorokat a Java fájlja elejére:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## 1. lépés: XMP metaadatok lekérése
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
Ebben a lépésben lekérjük a meglévő XMP metaadatokat az EPS fájlból. Ha az EPS fájl még nem tartalmaz XMP metaadatokat, az Aspose.Page egy újat generál, és feltölti a PS metaadat‑megjegyzések értékeivel.

## 2. lépés: "dc:title" tömbelem hozzáadása
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Most egy új tömbelemet adunk a **dc:title** tulajdonsághoz az XMP metaadatokban. Cserélje le a `"NewTitle"` értéket a kívánt címre.

## 3. lépés: "dc:creator" tömbelem hozzáadása
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
Hasonlóan, egy új tömbelemet adunk a **dc:creator** tulajdonsághoz az XMP metaadatokban. Cserélje le a `"NewCreator"` értéket a kívánt szerzői információra.

## 4. lépés: Kimeneti EPS fájl stream inicializálása
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Készítse elő a kimeneti EPS fájl stream-et, ahová a módosított dokumentumot, frissített XMP metaadatokkal menteni fogja.

## 5. lépés: Dokumentum mentése módosított XMP metaadatokkal
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Mentse a dokumentumot a frissített XMP metaadatokkal a kimeneti EPS fájlba.

## Összegzés
Gratulálunk! Sikeresen megtanulta, **hogyan adjon hozzá metaadatokat** tömbelemek beszúrásával az XMP metaadatokba az Aspose.Page for Java segítségével. Ez a hatékony könyvtár leegyszerűsíti az EPS fájlását, és kiterjedt funkcionalitást biztosít a dokumentumfeldolgozáshoz.

## Gyakran Ismételt Kérdések

### Használhatom az Aspose.Page for Java-t más dokumentumformátumokkal?
Igen, az Aspose.Page számos dokumentumformátumot támogat, többek között EPS, PDF és XPS.

### Van ingyenes próba a Aspose.Page for Java-hoz?
Igen, a próba verziót [itt](https://releases.aspose.com/) érheti el.

### Hol találom az Aspose.Page for Java dokumentációját?
A dokumentáció [itt](https://reference.aspose.com/page/java/) érhető el.

### Hogyan vásárolhatom meg az Aspose.Page for Java-t?
A terméket [itt](https://purchase.aspose.com/buy) vásárolhatja meg.

### Elérhetők ideiglenes licencek az Aspose.Page for Java-hoz?
Igen, ideiglenes licencet [itt](https://purchase.aspose.com/temporary-license/) szerezhet.

## További Gyakran Ismételt Kérdések

**K: Hozzáadhatok több mint egy tömbelemet ugyanahhoz a tulajdonsághoz?**  
V: Természetesen. Hívja meg többször a `xmp.addArrayItem` metódust ugyanarra a tulajdonságra, hogy listát építsen fel.

**K: Ez a megközelítés működik-e más XMP sémákkal a Dublin Core-on kívül?**  
V: Igen, bármely XMP tulajdonsághoz hozzáadhat tömbelemeket, amennyiben a névtér helyesen van hivatkozva.

**K: Hogyan ellenőrizhetem, hogy a metaadatok helyesen lettek-e hozzáadva?**  
V: Nyissa meg a keletkezett EPS fájlt egy XMP‑t támogató megjelenítőben (pl. Adobe Bridge), vagy programozottan extrahálja a metaadatokat a `XmpMetadata` metódusok segítségével.

---

**Utolsó frissítés:** 2025-12-18  
**Tesztelve:** Aspose.Page for Java 24.11  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}