---
date: 2026-05-20
description: Ismerje meg, hogyan adhat XMP metaadatokat EPS fájlokhoz az Aspose.Page
  for Java segítségével. Lépésről‑lépésre útmutató az egyszerű XMP tulajdonságok programozott
  beágyazásához.
keywords:
- add xmp metadata
- how to add xmp
- Aspose.Page Java XMP
linktitle: Egyszerű XMP tulajdonságok hozzáadása Java-val
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add XMP metadata to EPS files with Aspose.Page for Java.
    Step‑by‑step guide to embed simple XMP properties programmatically.
  headline: Add XMP Metadata to EPS Files Using Java
  type: TechArticle
- questions:
  - answer: Aspose.Page primarily supports Java, but equivalent libraries are available
      for .NET, C++, and Python.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore the features of Aspose.Page by obtaining a free trial
      **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Page for Java?
  - answer: The documentation is available **[here](https://reference.aspose.com/page/java/)**.
    question: Where can I find detailed documentation for Aspose.Page for Java?
  - answer: A temporary license can be acquired **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: You can purchase the product **[here](https://purchase.aspose.com/buy)**.
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: XMP metaadatok hozzáadása EPS fájlokhoz Java használatával
url: /hu/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XMP metaadatok hozzáadása EPS fájlokhoz Java használatával

## Bevezetés
A modern grafikai csővezetékekben az **XMP metaadatok hozzáadása** EPS fájlokhoz programozott módon teljes irányítást biztosít a grafikai illusztrációk leírása, keresése és archiválása felett. Az Aspose.Page for Java segítségével beolvashatod, módosíthatod és írhatod az XMP csomagokat EPS dokumentumokba anélkül, hogy elhagynád a Java ökoszisztémát. Ebben az oktatóanyagban lépésről lépésre bemutatjuk, hogyan adhatunk egyszerű XMP tulajdonságokat egy EPS fájlhoz, hogy gyorsan és megbízhatóan gazdagíthasd grafikáidat egyedi metaadatokkal.

## Gyors válaszok
- **Mit jelent az “XMP metaadatok hozzáadása EPS-hez”?** XMP csomag (XML‑alapú metaadat) beágyazása egy EPS fájlba.  
- **Melyik könyvtár szükséges?** Aspose.Page for Java (letölthető az Aspose weboldaláról).  
- **Szükségem van licencre a teszteléshez?** Egy ingyenes próba működik fejlesztéshez; kereskedelmi licenc szükséges a termeléshez.  
- **Hány sor kód?** Kevesebb, mint 30 Java sor plusz néhány import utasítás.  
- **Hozzáadhatok más adat típusokat?** Igen – dátumok, egész számok, dupla pontosságú számok, karakterláncok és még tömbök is támogatottak.

## Hogyan adhatunk hozzá XMP metaadatokat EPS fájlokhoz Java használatával?
Töltsd be az EPS fájlt a `new PsDocument("input.eps")` segítségével, szerezd meg vagy hozd létre az XMP csomagot, illeszd be a kívánt tulajdonságokat, majd mentsd vissza a dokumentumot a lemezre – mindezt tíz Java sor alatt. Ez a megközelítés lehetővé teszi kereshető, szabványos metaadatok beágyazását manuális EPS szerkesztés nélkül.

## Mi az XMP metaadat az EPS-ben?
Az XMP metaadat az EPS-ben egy XML csomag, amely az EPS fájl belsejében él, és olyan információkat tárol, mint a szerző, a létrehozás dátuma és egyedi címkék. Ennek a csomagnak a beágyazása lehetővé teszi, hogy a downstream eszközök elolvassák és felhasználják az adatokat külön mellékállományok nélkül.

## Miért adjunk hozzá XMP metaadatot EPS fájlokhoz?
Az XMP metaadat beágyazása az EPS eszközöket azonnal kereshetővé teszi, biztosítja a megfelelőséget a licencinformációk fájlba történő tárolásával, lehetővé teszi az automatizált csővezetékek számára, hogy beágyazott címkék alapján döntéseket hozzanak, és garantálja, hogy a metaadat a grafikával együtt utazik minden platformon. Az Aspose.Page akár 500 MB méretű fájlokat is képes feldolgozni a teljes dokumentum memóriába töltése nélkül, gyors teljesítményt nyújtva nagyméretű munkaterhelésekhez.

## Előfeltételek
Mielőtt elkezdenéd, győződj meg róla, hogy rendelkezel:

- Alapvető Java programozási ismeretekkel.  
- Aspose.Page for Java könyvtár telepítve. Letöltheted **[itt](https://releases.aspose.com/page/java/)**.  
- Egy mint EPS fájl metaadatokkal. Ha nincs, nyugodtan használd a mellékelt **`xmp3.eps`** fájlt.

## Csomagok importálása
Először importáld a szükséges osztályokat. Az importok pontosan ugyanazok, mint az eredeti példában:

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
A `PsDocument` osztály egy EPS fájlt képvisel, és módszereket biztosít a tartalom és a metaadatok eléréséhez.  
Az `XmpMetadata` objektum tartalmazza a dokumentumhoz kapcsolódó XMP csomagot.

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
A `Date` osztály egy adott pillanatot reprezentál, ezredmásodperc pontossággal.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## 3. lépés: Egész szám tulajdonság hozzáadása
Az `Integer` osztály egy primitív `int` értéket csomagol objektummá.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## 4. lépés: Double típusú tulajdonság hozzáadása
A `Double` osztály egy primitív `double` értéket csomagol objektummá.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## 5. lépés: String típusú tulajdonság hozzáadása
A `String` osztály karakterek sorozatát reprezentálja.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## 6. lépés: Frissített EPS fájl mentése
A `save` metódus visszaírja a módosított dokumentumot a lemezre, megőrizve az EPS struktúrát.

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
Mindig zárd le a stream-eket, hogy elkerüld a fájl‑kezelő szivárgásokat, és biztosítsd, hogy minden puffer ki legyen ürítve.

```java
// Close input EPS stream
psStream.close();
```

## Gyakori problémák és megoldások
| Probléma | Ok | Megoldás |
|----------|----|----------|
| **Null XMP metaadat** | Az EPS fájl nem tartalmazott XMP csomagot, és a könyvtár nem tudta meghatározni a PS kommenteket. | Győződj meg róla, hogy a forrás EPS legalább egy PS kommentet tartalmaz (pl. `%%Creator`). A könyvtár automatikusan generál egy minimális XMP csomagot. |
| **Időzóna eltérés** | A dátumok eltolódnak, amikor egy másik alkalmazásban nyitod meg. | Állítsd be a `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))`‑t a `Date` objektum létrehozása előtt, ahogy a 2. lépésben látható. |
| **Licenc kivétel** | A futás közben `LicenseException` kivételt dob. | Alkalmazz érvényes Aspose.Page licencet az API használata előtt, vagy futtasd próba módban értékeléshez. |

## Gyakran ismételt kérdések
**Q: Használhatom az Aspose.Page for Java-t más programozási nyelvekkel?**  
A: Az Aspose.Page elsősorban Java-t támogat, de ekvivalens könyvtárak elérhetők .NET, C++ és Python számára.

**Q: Elérhető ingyenes próba az Aspose.Page for Java-hoz?**  
A: Igen, a funkciókat ingyenes próba **[itt](https://releases.aspose.com/)** keresztül fedezheted fel.

**Q: Hol találom meg a részletes dokumentációt az Aspose.Page for Java-hoz?**  
A: A dokumentáció **[itt](https://reference.aspose.com/page/java/)** érhető el.

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.Page for Java-hoz?**  
A: Ideiglenes licencet **[itt](https://purchase.aspose.com/temporary-license/)** lehet beszerezni.

**Q: Hol vásárolhatom meg az Aspose.Page for Java-t?**  
A: A terméket **[itt](https://purchase.aspose.com/buy)** vásárolhatod meg.

---

**Last Updated:** 2026-05-20  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó oktatóanyagok

- [Hogyan olvassuk el az XMP metaadatokat Java-val – Aspose.Page útmutató](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page xmp oktatóanyag – Namespace hozzáadása XMP-hez Java használatával](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Tömb elemek hozzáadása XMP metaadatokhoz Java használatával](/page/java/xmp-metadata-manipulation/add-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}