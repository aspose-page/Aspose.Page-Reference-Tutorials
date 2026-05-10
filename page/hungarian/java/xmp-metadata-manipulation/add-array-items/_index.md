---
date: 2026-03-05
description: Tanulja meg, hogyan adhat hozzá dc:title tömb elemeket az EPS fájlok
  XMP metaadataihoz az Aspose.Page for Java használatával. Kövesse ezt a lépésről‑lépésre
  útmutatót a gyors eredményekért.
linktitle: How to Add dc:title Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Hogyan adjunk hozzá dc:title tömb elemeket XMP metaadatokhoz Java-val
url: /hu/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tömbelemek hozzáadása XMP metaadatokhoz Java-val

## Bevezetés
Ebben az útmutatóban megtudja, **hogyan adhat hozzá dc:title** (és más tömbelemeket) az XMP metaadatokhoz egy EPS fájlban az Aspose.Page for Java segítségével. Az XMP metaadatok frissítése akkor hasznos, ha kereshető információkat—például címeket, szerzőket vagy kulcsszavakat—közvetlenül a grafikus fájlokba szeretne beágyazni. Lépésről lépésre végigvezetjük, elmagyarázzuk, miért fontos minden sor, és megmutatjuk, hogyan ellenőrizheti a változásokat.

## Gyors válaszok
- **Mi jelenti a “dc:title” kifejezést?** Ez a Dublin Core cím tulajdonság, amely XMP tömbként van tárolva.  
- **Miért módosítsuk az XMP metaadatokat?** Ez jobb eszközkezelést, kereshetőséget és a szabványoknak való megfelelést tesz lehetővé.  
- **Szükségem van meglévő XMP blokkra?** Nem—az Aspose.Page automatikusan generál egyet a PS megjegyzésekből, ha hiányzik.  
- **Melyik könyvtárverzió szükséges?** Bármelyik friss Aspose.Page for Java kiadás (tesztelve a legújabb 2026-os builddel).  
- **Hozzáadhatok más tömbtulajdonságokat is?** Igen—használja ugyanazt a `addArrayItem` metódust olyan tulajdonságokhoz, mint a `dc:creator`.

## Előfeltételek
Mielőtt belemerülnénk, győződjön meg róla, hogy rendelkezik:

- Aspose.Page for Java könyvtár telepítve (adja hozzá a JAR-t a projekt osztályútvonalához).  
- Alap Java fejlesztési tapasztalattal (JDK 8+ ajánlott).  
- Egy EPS fájl, amely már tartalmaz XMP metaadatokat vagy legalább PS metaadat megjegyzéseket (pl. `%%Title`, `%%Creator`).  

## Csomagok importálása
A kezdéshez importálja a EPS fájlok olvasásához, manipulálásához és mentéséhez szükséges osztályokat:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## 1. lépés: EPS dokumentum betöltése és XMP metaadatok lekérése
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

Itt megnyitjuk az EPS fájlt, és kérjük az Aspose.Page‑t az XMP blokkért. Ha a fájl nem tartalmaz XMP‑t, a könyvtár automatikusan létrehoz egyet a meglévő PS megjegyzések alapján, biztosítva, hogy mindig legyen egy metaadat konténer, amivel dolgozhat.

## 2. lépés: Új **dc:title** tömbelem hozzáadása  
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```

Ez a sor bemutatja, **hogyan adhatunk hozzá dc:title**-t. Cserélje le a `"NewTitle"` értéket a beágyazni kívánt tényleges címre. A metódus hozzáfűzi az értéket a meglévő cím tömbhöz, megőrizve az esetleges korábbi címeket.

## 3. lépés: Új **dc:creator** tömbelem hozzáadása  
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```

Hasonlóan, gazdagíthatja a `dc:creator` tulajdonságot. Több szerző is tárolható; minden hívás egy új bejegyzést ad hozzá.

## 4. lépés: Kimeneti adatfolyam előkészítése  
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

Létrehozunk egy adatfolyamot a módosított EPS fájlhoz. Egy másik fájlnév (`xmp3_changed.eps`) használata érintetlenül hagyja az eredeti fájlt.

## 5. lépés: Dokumentum mentése frissített XMP metaadatokkal  
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

A `save` hívás az EPS adatokat a frissített XMP blokkal együtt írja ki. A `finally` blokk biztosítja, hogy a fájlkezelő felszabaduljon még akkor is, ha kivétel lép fel.

## Miért fontos ez
A pontos `dc:title` és `dc:creator` értékek beágyazása javítja:

- **Kereshetőség** a digitális eszközkezelő (DAM) rendszerekben.  
- **Megfelelés** a metaadatokat megkövetelő kiadási szabványoknak.  
- **Együttműködés**, mivel a csapattagok gyorsan azonosíthatják a fájl tartalmát az EPS megnyitása nélkül.

## Gyakori hibák és tippek
- **Hiba:** A meglévő tömbelemek véletlen felülírása.  
  **Tipp:** Használja az `xmp.getArrayItems("dc:title")` metódust a jelenlegi értékek ellenőrzéséhez, mielőtt újat adna hozzá.  
- **Hiba:** Az adatfolyamok bezárásának elfelejtése, ami fájlzároláshoz vezet.  
  **Tipp:** Mindig csomagolja az I/O műveleteket try‑with‑resources vagy a bemutatott `finally` blokkba.  
- **Tipp:** Több `addArrayItem` hívást is láncolhat, hogy egyszerre több címet vagy szerzőt adjon hozzá.

## Gyakran ismételt kérdések

### Használhatom az Aspose.Page for Java-t más dokumentumformátumokkal?
Igen, az Aspose.Page számos dokumentumformátumot támogat, többek között EPS, PDF és XPS.

### Van ingyenes próba az Aspose.Page for Java-hoz?
Igen, az ingyenes próbát [itt](https://releases.aspose.com/) érheti el.

### Hol találom az Aspose.Page for Java dokumentációját?
A dokumentáció [itt](https://reference.aspose.com/page/java/) érhető el.

### Hogyan vásárolhatom meg az Aspose.Page for Java-t?
A terméket [itt](https://purchase.aspose.com/buy) vásárolhatja meg.

### Elérhetők ideiglenes licence-ek az Aspose.Page for Java-hoz?
Igen, ideiglenes licencet [itt](https://purchase.aspose.com/temporary-license/) szerezhet.

---

**Utoljára frissítve:** 2026-03-05  
**Tesztelve:** Aspose.Page for Java (legújabb 2026-os kiadás)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}