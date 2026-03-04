---
date: 2025-12-20
description: Ismerje meg, hogyan hozhat létre XMP metaadatot EPS fájlokban az Aspose.Page
  for Java segítségével. Lépésről‑lépésre útmutató az egyszerű XMP tulajdonságok programozott
  hozzáadásához.
linktitle: Add Simple Properties in XMP using Java
second_title: Aspose.Page Java API
title: Hogyan lehet XMP metaadat EPS-t létrehozni Java-val
url: /hu/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Egyszerű tulajdonságok hozzáadása XMP-hez Java-val

## Bevezetés
A modern dokumentumáramlásokban a **XMP metaadat EPS** fájlok programozott létrehozása teljes irányítást ad a grafika leírása, keresése és archiválása felett. Az Aspose.Page for Java segítségével XMP csomagokat olvashat, módosíthat és írhat EPS dokumentumokba anélkül, hogy elhagyná a Java ökoszisztémát. Ebben az útmutatóban lépésről lépésre bemutatjuk, hogyan adhat egyszerű XMP tulajdonságokat egy EPS fájlhoz, hogy gyorsan és megbízhatóan gazdagíthassa grafikáit egyedi metaadatokkal.

## Gyors válaszok
- **Mit jelent a “create xmp metadata eps”?** XMP csomag (XML‑alapú metaadat) hozzáadása egy EPS fájlhoz.  
- **Melyik könyvtár szükséges?** Aspose.Page for Java (letölthető az Aspose weboldaláról).  
- **Szükség van licencre a teszteléshez?** Fejlesztéshez egy ingyenes próba elegendő; termeléshez kereskedelmi licenc szükséges.  
- **Hány sor kódra van szükség?** Kevesebb, mint 30 Java sor plusz néhány import utasítás.  
- **Hozzáadhatok más adat típusokat is?** Igen – dátumok, egész számok, double‑ok, stringek és még tömbök is támogatottak.

## Mi az a create xmp metadata eps?
Az XMP (Extensible Metadata Platform) egy szabvány a gazdag metaadatok fájlokba ágyazására. Amikor **XMP metaadat EPS‑t hoz létre**, egy XML csomagot ágyaz be egy EPS (Encapsulated PostScript) dokumentumba, lehetővé téve, hogy a downstream alkalmazások olvassák a szerzőt, a létrehozás dátumát, egyedi címkéket és egyebeket.

## Miért érdemes XMP metaadatokat hozzáadni EPS fájlokhoz?
- **Kereshetőség:** Automatikus indexelést tesz lehetővé DAM rendszerekben.  
- **Megfelelőség:** Jogi vagy licencinformációkat tárol közvetlenül a fájlban.  
- **Automatizálás:** Lehetővé teszi, hogy a downstream folyamatok beágyazott adatok alapján döntéseket hozzanak.  
- **Hordozhatóság:** A metaadat az EPS‑sel együtt utazik, biztosítva a konzisztenciát a különböző platformok között.

## Előfeltételek
Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

- Alapvető Java programozási ismeretekkel.  
- Aspose.Page for Java könyvtárral telepítve. Letöltheti **[itt](https://releases.aspose.com/page/java/)**.  
- Egy metaadatot tartalmazó EPS mintafájllal. Ha nincs, nyugodtan használja a mellékelt **`xmp3.eps`** fájlt.

## Csomagok importálása
Először importálja a szükséges osztályokat. Az importok pontosan megegyeznek az eredeti példával:

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

## 1. lépés: EPS dokumentum betöltése és XMP metaadatok lekérése
Megnyitjuk az EPS fájlt, létrehozzuk a `PsDocument` példányt, és lekérjük (vagy létrehozzuk) az XMP csomagot.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## 2. lépés: Dátum tulajdonság hozzáadása
Dátum hozzáadása olyan egyszerű, mint egy `Date` objektum létrehozása és az XMP térképbe helyezése.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## 3. lépés: Egész szám tulajdonság hozzáadása
Numerikus azonosítókat vagy verziószámokat tárolhat egész szám értékkel.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## 4. lépés: Double típusú tulajdonság hozzáadása
Lebegőpontos számok hasznosak mérési értékek vagy értékelések tárolásához.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## 5. lépés: String típusú tulajdonság hozzáadása
Egyedi szöveges címkék (pl. projektkódok) stringként kerülnek tárolásra.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## 6. lépés: Frissített EPS fájl mentése
Miután az összes tulajdonságot hozzáadta, írja vissza a dokumentumot a lemezre.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## 7. lépés: Erőforrások felszabadítása
Mindig zárja be a bemeneti streamet a fájl‑kezelő szivárgások elkerülése érdekében.

```java
// Close input EPS stream
psStream.close();
```

## Gyakori problémák és megoldások
| Probléma | Ok | Megoldás |
|----------|----|----------|
| **Null XMP metadata** | Az EPS fájl nem tartalmazott XMP csomagot, és a könyvtár nem tudta levezetni a PS kommenteket. | Győződjön meg róla, hogy a forrás EPS legalább egy PS kommentet tartalmaz (pl. `%%Creator`). A könyvtár automatikusan generál egy minimális XMP csomagot. |
| **Time zone mismatch** | Dátumok eltolódnak, amikor másik alkalmazásban nyitják meg. | Állítsa be a `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` hívást a `Date` objektum létrehozása előtt, ahogyan a 2. lépésben látható. |
| **License exception** | A futásidő `LicenseException`‑t dob. | Alkalmazzon érvényes Aspose.Page licencet az API használata előtt, vagy futtassa próbaverzióban az értékeléshez. |

## Következtetés
Ezekkel a lépésekkel most már tudja, hogyan **hozzon létre XMP metaadat EPS** fájlokat az Aspose.Page for Java segítségével. Egyszerű tulajdonságok, például dátumok, egész számok, double‑ok és stringek hozzáadása egyszerű, és a kapott EPS fájlok gazdag, kereshető metaadatot tartalmaznak, amely bármely downstream munkafolyamatot előnyösen támogat.

## Gyakran ismételt kérdések
### Használhatom az Aspose.Page for Java-t más programozási nyelvekkel?
Az Aspose.Page elsősorban Java‑t támogat, de elérhetők verziók más nyelvekhez, például .NET‑hez is.

### Elérhető ingyenes próba az Aspose.Page for Java-hoz?
Igen, a [itt](https://releases.aspose.com/) elérhető egy ingyenes próba, amely lehetővé teszi a funkciók kipróbálását.

### Hol találom az Aspose.Page for Java részletes dokumentációját?
A dokumentáció [itt](https://reference.aspose.com/page/java/) érhető el.

### Hogyan szerezhetek ideiglenes licencet az Aspose.Page for Java-hoz?
Ideiglenes licencet [itt](https://purchase.aspose.com/temporary-license/) kaphat.

### Hol vásárolhatom meg az Aspose.Page for Java-t?
A terméket [itt](https://purchase.aspose.com/buy) vásárolhatja meg.

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}