---
date: 2026-05-25
description: Ismerje meg, hogyan olvashatja az XMP-t az Aspose.Page segítségével Java-ban.
  Ez a lépésről‑lépésre útmutató bemutatja az XMP metadata, creator info, timestamps,
  thumbnails és egyéb elemek kinyerését.
keywords:
- read xmp using aspose.page
- xmp metadata java
- aspose.page java
linktitle: Hogyan olvassuk az XMP metadata-t Java-val
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to read xmp using aspose.page with Java. This step‑by‑step
    guide shows extracting XMP metadata, creator info, timestamps, thumbnails, and
    more.
  headline: Read XMP using Aspose.Page – Java Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page can read XMP from PDF, EPS, and several image formats.
    question: Does this approach work with PDF files that contain XMP?
  - answer: Absolutely. The `XmpMetadata` object is mutable; you can add, update,
      or remove keys and then save the document.
    question: Can I modify XMP metadata after reading it?
  - answer: You can retrieve the binary data from the `xmpGImg:data` property of each
      thumbnail entry and write it to a file.
    question: Is there a way to extract all thumbnail images, not just dimensions?
  type: FAQPage
second_title: Aspose.Page Java API
title: XMP olvasása az Aspose.Page segítségével – Java útmutató
url: /hu/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XMP metaadatok lekérése Java használatával

## Hogyan olvassuk be az XMP-t az Aspose.Page (Java) használatával?

Töltsd be az EPS fájlt a `new Document("file.eps")` segítségével — a `Document` osztály egy betöltött fájlt képviseli. Hívd meg a `getXmpMetadata()` metódust, amely kinyeri az XMP csomagot, majd lekérdezd a visszakapott `XmpMetadata` objektumot — egy térképszerű felületet az XMP tulajdonságokhoz — hogy megszerezd a szükséges kulcsokat. Ez minden, ami az XMP beolvasásához szükséges az Aspose.Page használatával. Az API elrejti az alacsony szintű feldolgozást, így csak két sor kóddal kapsz egy használatra kész tulajdonságok térképét.

Üdvözlünk a lépésről‑lépésre útmutatónkban, amely bemutatja, hogyan olvassuk be az **XMP** metaadatokat Java és az Aspose.Page könyvtár segítségével. Az XMP (Extensible Metadata Platform) egy széles körben elfogadott szabvány a gazdag metaadatok dokumentumokba ágyazásához. Az útmutató végére képes leszel beolvasni a dokumentum formátum XMP-jét, kinyerni a készítő információkat, időbélyegeket, bélyegképeket és egyebeket — lehetővé téve, hogy intelligensebb dokumentumelemző megoldásokat építs.

## Gyors válaszok
- **Mi jelent a „read XMP”?** Ez azt jelenti, hogy programozott módon kinyerjük az XMP csomagot, amely a metaadatokat tárolja egy fájlban.  
- **Melyik könyvtár szükséges?** Aspose.Page for Java (download from the official page [here](https://releases.aspose.com/page/java/)).  
- **Szükségem van licencre?** Ideiglenes vagy teljes licenc szükséges a termeléshez; egy ingyenes próba a kiértékeléshez elegendő.  
- **Melyik Java verzió támogatott?** Java 8 vagy újabb.  
- **Olvashatok XMP-t más formátumokból?** Igen – az Aspose.Page XMP-t nyer ki EPS, PDF, JPEG, PNG és több mint 20 másik formátumból.

## Előfeltételek
Mielőtt a kódba merülnél, győződj meg róla, hogy rendelkezel:

- **Java Development Kit (JDK)** – Java 8+ telepítve és konfigurálva a gépeden.  
- **Aspose.Page for Java** – Töltsd le a könyvtárat a hivatalos oldalról [here](https://releases.aspose.com/page/java/).  
- Egy EPS fájl, amely XMP metaadatokat tartalmaz (például `xmp1.eps`).  

## Csomagok importálása
Az `XmpMetadata` osztály a `com.aspose.page.xmp` névtérben található, míg a `Document` osztály a `com.aspose.page` névtérben. Importáld mindkettőt, hogy dolgozhass az EPS fájllal és annak metaadataival.  
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## 1. lépés: EPS bemeneti fájl stream inicializálása
Állítsd be a dokumentum könyvtárának útvonalát, és inicializáld a bemeneti EPS fájl stream-et.  
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## 2. lépés: XMP metaadatok lekérése
Az `XmpMetadata` az Aspose.Page objektuma, amely a dokumentumból kinyert XMP csomagot tárolja. Szerezd meg a `document.getXmpMetadata()` hívással. Ha a fájl nem tartalmaz XMP-t, az API egy minimális csomagot szintetizál a meglévő PostScript megjegyzések alapján.  
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## 3. lépés: CreatorTool információ kinyerése
A `CreatorTool` kulcs az `xmp` névtér alatt él, és rögzíti a fájlt előállító alkalmazást. Ellenőrizd a jelenlétét, és írd ki az értékét.  
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## 4. lépés: CreateDate információ kinyerése
A `CreateDate` tárolja azt az időbélyeget, amikor a dokumentum eredetileg létrejött. Használd ugyanazt a `containsKey`/`get` mintát a beolvasásához.  
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## 5. lépés: Bélyegkép szélességének lekérése
Ha bélyegképek léteznek, az `xmp:Thumbnails` tömb egy vagy több bejegyzést tartalmaz. Minden bejegyzés `width`, `height` és bináris adatot tartalmaz. A példa az első bélyegkép szélességét nyeri ki.  
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## 6. lépés: Formátum információ kinyerése
A `format` kulcs megmondja az eredeti fájlformátumot (például „application/postscript”). Hasznos, ha naplózni vagy ellenőrizni kell a forrás típusokat.  
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## 7. lépés: DocumentID lekérése
A `DocumentID` egy egyedi azonosító, amelyet a készítő alkalmazás rendelt hozzá. Nagy eszközkönyvtárakban deduplikációra használható.  
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Miért fontos ez
Az Aspose.Page **20+** fájlformátumból képes XMP-t olvasni, és akár **500 MB** méretű dokumentumokat is feldolgoz anélkül, hogy az egész fájlt a memóriába töltené, így gyors, alacsony erőforrásigényű hozzáférést biztosít a lényeges metaadatokhoz. Ez a képesség kritikus a kötegelt feldolgozási csővezetékek, digitális eszközkezelő rendszerek és minden olyan megoldás számára, amely kereshető, gép‑olvasható dokumentumattribútumokra támaszkodik.

## Gyakori buktatók és tippek
- **Missing XMP:** Egyes EPS fájlok nem tartalmazhatnak XMP-t. A `getXmpMetadata()` hívás egy minimális halmazt szintetizál a meglévő PS megjegyzések alapján, de a teljes metaadat csak akkor lesz elérhető, ha be van ágyazva.  
- **Thumbnail Arrays:** Az `xmp:Thumbnails` kulcs több bejegyzést is tartalmazhat. A példa csak az elsőt nyeri ki; ha minden bélyegképre szükséged van, iteráld a tömböt.  
- **Namespace Awareness:** Az XMP kulcsok névtereket használnak (pl. `xmp:`, `dc:`). Győződj meg róla, hogy a pontos kulcsnevet hivatkozod, különben a `containsKey` hamis értéket ad vissza.  

## Gyakran Ismételt Kérdések
### Használhatom az Aspose.Page for Java-t más programozási nyelvekkel?
Igen, az Aspose.Page támogatja a Java, .NET és több más nyelvet. Lásd a teljes listát a [documentation](https://reference.aspose.com/page/java/) oldalon.

### Elérhető ingyenes próba az Aspose.Page for Java-hoz?
Igen, a ingyenes próbaverziót [here](https://releases.aspose.com/) érheted el.

### Hol találok támogatást az Aspose.Page for Java-hoz?
Látogasd meg az [Aspose.Page fórumot](https://forum.aspose.com/c/page/39) a közösségi segítségért és a hivatalos támogatásért.

### Hogyan szerezhetek ideiglenes licencet az Aspose.Page for Java-hoz?
Ideiglenes licencet [here](https://purchase.aspose.com/temporary-license/) kaphatsz.

### Vannak további források az Aspose.Page for Java-hoz?
Fedezd fel a teljes [documentation](https://reference.aspose.com/page/java/) és töltsd le a könyvtárat [here](https://releases.aspose.com/page/java/).

## További GYIK
**Q: Működik ez a megközelítés PDF fájlokkal, amelyek XMP-t tartalmaznak?**  
A: Igen, az Aspose.Page képes XMP-t olvasni PDF, EPS és több képformátumból.

**Q: Módosíthatom az XMP metaadatokat a beolvasás után?**  
A: Teljesen. Az `XmpMetadata` objektum módosítható; kulcsokat hozzáadhatsz, frissíthetsz vagy eltávolíthatsz, majd elmentheted a dokumentumot.

**Q: Van mód az összes bélyegkép kinyerésére, nem csak a méretekre?**  
A: A `xmpGImg:data` tulajdonságból lekérheted a bináris adatot minden bélyegkép bejegyzésnél, és fájlba írhatod.

## Összegzés
Most már elsajátítottad, **hogyan olvassuk be az XMP** metaadatokat Java és az Aspose.Page segítségével. A lépések követésével ki tudod nyerni a készítőeszközöket, időbélyegeket, bélyegképeket, formátuminformációkat és a dokumentumazonosítókat — teljes betekintést nyújtva az EPS fájlokba ágyazott metaadatokba. Nyugodtan kísérletezz további XMP névterekkel, hogy még gazdagabb adatokat nyerj ki alkalmazásaid számára.

---

**Legutóbb frissítve:** 2026-05-25  
**Tesztelve a következővel:** Aspose.Page for Java 24.12 (latest)  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Aspose Page Java Tutorial – Add XMP Metadata to EPS Files](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page xmp tutorial – Add Namespace in XMP using Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [aspose page xmp tutorial – Change Named Value in XMP using Java](/page/java/xmp-metadata-manipulation/change-named-value/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}