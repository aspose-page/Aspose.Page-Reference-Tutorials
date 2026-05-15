---
date: 2026-05-15
description: Ismerje meg, hogyan szerkessze az XMP metaadatokat, és hogyan módosítsa
  az XMP értékeket EPS fájlokban az Aspose.Page for Java segítségével – egy világos
  lépésről‑lépésre útmutató.
keywords:
- how to edit xmp
- how to change xmp
- Aspose.Page XMP Java
- edit EPS metadata
- XMP manipulation Java
linktitle: Név szerinti érték módosítása XMP-ben Java‑val
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  headline: how to edit xmp – Change Named Value in XMP using Java
  type: TechArticle
- description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  name: how to edit xmp – Change Named Value in XMP using Java
  steps:
  - name: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
    text: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
  - name: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
    text: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
  - name: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
    text: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
  type: HowTo
- questions:
  - answer: Aspose.Page primarily supports Java, but Aspose offers equivalent libraries
      for .NET, C++, and Python that expose similar XMP manipulation capabilities.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore a free trial of Aspose.Page for Java [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support and discussions.
    question: Where can I find additional support and discussions about Aspose.Page
      for Java?
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: To buy Aspose.Page for Java, visit the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: hogyan szerkesszük az XMP‑t – Név szerinti érték módosítása XMP-ben Java‑val
url: /hu/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan szerkesszük az XMP-t – Nevezett érték módosítása XMP-ben Java-val

A modern dokumentumfolyamatokban a **Aspose.Page for Java** egyszerűvé teszi az XMP metaadatok olvasását, szerkesztését és írását EPS fájlokban. **Ez a bemutató megmutatja, hogyan szerkesszük az XMP** metaadatokat EPS dokumentumokban az Aspose.Page API használatával, így a dokumentuminformációk pontosak, kereshetőek és az iparági szabványoknak megfelelőek maradnak. Akár az oldalméreteket, a szerzői adatokat vagy egyedi címkéket frissíti, az alábbi lépések végigvezetnek a folyamaton Java nyelven.

## Gyors válaszok
- **Miről szól ez a bemutató?** Nevezett XMP érték módosítása EPS fájlban az Aspose.Page for Java segítségével.  
- **Melyik könyvtárverzió szükséges?** Bármely friss Aspose.Page for Java kiadás (az API több éve stabil).  
- **Szükségem van licencre?** Ideiglenes vagy teljes licenc szükséges a termeléshez; egy ingyenes próba a teszteléshez elegendő.  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 10‑15 perc egy Java I/O-val jártas fejlesztőnek.  
- **Használhatom más fájlformátumokkal is?** Az XMP API elérhető PDF, SVG és az Aspose.Page által támogatott egyéb formátumokhoz is.

## Mi az XMP metaadat?
Az XMP (Extensible Metadata Platform) egy szabványosított, XML‑alapú formátum, amely lehetővé teszi gazdag metaadatok – például szerző, cím és egyedi tulajdonságok – közvetlen beágyazását fájlokba. EPS dokumentumokban az XMP a hagyományos PostScript megjegyzésekkel együtt él, lehetővé téve az alkalmazások számára a metaadatok olvasását és módosítását a vizuális tartalom megváltoztatása nélkül.

## Miért használjuk az Aspose.Page for Java-t XMP szerkesztéséhez?
Az Aspose.Page **teljes kontrollt biztosít több mint 150 XMP séma tulajdonság felett**, és konzisztensen működik EPS, PDF és SVG formátumokban. Fájlokat **500 MB‑ig** dolgoz fel anélkül, hogy a teljes dokumentumot a memóriába töltené, és beépített validációt tartalmaz, amely garantálja, hogy a kapott EPS megfeleljen a szabványoknak. Külső XML‑parszerek vagy natív könyvtárak nem szükségesek.

## Bevezetés
Az Aspose.Page for Java egy robusztus könyvtár, amely megkönnyíti az EPS fájlok manipulálását és feldolgozását. Az XMP metaadatok kezelésében ez a könyvtár átfogó funkciókészlettel ruházza fel a fejlesztőket. Ebben a bemutatóban a XMP‑ben egy nevezett érték módosítására összpontosítunk, világos és tömör útmutatót nyújtva azoknak a fejlesztőknek, akik fejleszteni szeretnék dokumentumfeldolgozási képességeiket.

## Előfeltételek
1. **Java fejlesztői környezet** – JDK (8 vagy újabb) és IDE vagy build eszköz (Maven/Gradle).  
2. **Aspose.Page for Java könyvtár** – Töltse le és integrálja az Aspose.Page for Java könyvtárat a projektjébe. A könyvtárat és a részletes dokumentációt [itt](https://reference.aspose.com/page/java/) találja.  
3. **Minta EPS fájl** – Legyen egy minta EPS fájl a kísérletezéshez. Ha nincs, használja a mellékelt példafájlt, amely **"xmp4.eps."** névre hallgat.

## Csomagok importálása
Az `import` utasítások beviszik a szükséges Aspose.Page osztályokat a láthatóságba.

A `PsDocument` osztály az Aspose.Page központi objektuma, amely egy EPS dokumentumot reprezentál a memóriában.  
Az `XmpMetadata` osztály hozzáférést biztosít az EPS fájlba ágyazott XMP csomaghoz.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Hogyan szerkesszük az XMP metaadatokat?
Töltse be az EPS fájlt, szerezze meg az XMP csomagot, módosítsa a kívánt tulajdonságot, majd mentse a dokumentumot – mindezt néhány egyszerű sorban. Ez a megközelítés bármely nevezett XMP értékre működik, legyen az egy szabványos Dublin Core mező vagy egy egyéni névtér, amelyet definiált.

## 1. lépés: Bemeneti EPS fájl stream inicializálása
`FileInputStream` egy csak olvasható streamet nyit a forrás EPS fájlhoz, lehetővé téve az Aspose.Page számára a dokumentum beolvasását a fájlrendszer zárolása nélkül.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## 2. lépés: PsDocument inicializálása
`PsDocument` az elsődleges objektum, amely az EPS tartalmat kapszulázza, és hozzáférést biztosít a metaadatokhoz, oldalakhoz és erőforrásokhoz.

```java
PsDocument document = new PsDocument(psStream);
```

## 3. lépés: XMP metaadatok lekérése
`XmpMetadata` az EPS fájlban lévő XMP csomagot képviseli, és módszereket kínál egyedi tulajdonságok olvasására, módosítására vagy törlésére.

```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## 4. lépés: Új érték beállítása az XMP-ben
`setProperty` beállítja egy megadott XMP tulajdonság értékét a metaadatcsomagban.

```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## 5. lépés: Kimeneti EPS fájl stream inicializálása
`FileOutputStream` egy írható streamet hoz létre a módosított EPS fájl mentéséhez.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## 6. lépés: Dokumentum mentése módosított XMP metaadatokkal
`save` a memóriában lévő PsDocument-et, beleértve a frissített XMP-t, az output streambe írja.

```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## 7. lépés: Bemeneti EPS stream bezárása
`close` felszabadítja a fájlkezelőt és felszabadítja a bemeneti streamhez kapcsolódó erőforrásokat.

```java
// Close input EPS stream
psStream.close();
```

## Gyakori problémák és megoldások
- **FileNotFoundException** – Ellenőrizze, hogy a `dataDir` a megfelelő mappára mutat-e, és hogy a `xmp4.eps` létezik-e.  
- **LicenseException** – Ha licenchibákat lát, győződjön meg róla, hogy egy érvényes Aspose.Page licencfájl be van töltve a `PsDocument` létrehozása előtt.  
- **Metadata Not Updated** – Mentés után nyissa meg a kapott EPS fájlt egy metaadat-olvasóval (pl. Adobe Bridge), hogy megerősítse az új érték megjelenését.

## Gyakran feltett kérdések
**Q: Használhatom az Aspose.Page for Java-t más programozási nyelvekkel?**  
A: Az Aspose.Page elsősorban Java-t támogat, de az Aspose ekvivalens könyvtárakat kínál .NET, C++ és Python számára, amelyek hasonló XMP manipulációs képességeket biztosítanak.

**Q: Van ingyenes próba az Aspose.Page for Java-hoz?**  
A: Igen, az Aspose.Page for Java ingyenes próbaverzióját [itt](https://releases.aspose.com/) tekintheti meg.

**Q: Hol találok további támogatást és megbeszéléseket az Aspose.Page for Java-ról?**  
A: Látogassa meg az [Aspose.Page fórumot](https://forum.aspose.com/c/page/39) a közösségi támogatásért és megbeszélésekért.

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.Page for Java-hoz?**  
A: Ideiglenes licencet [itt](https://purchase.aspose.com/temporary-license/) szerezhet be.

**Q: Hol vásárolhatom meg az Aspose.Page for Java-t?**  
A: Az Aspose.Page for Java megvásárlásához látogassa meg a [vásárlási oldalt](https://purchase.aspose.com/buy).

---

**Utolsó frissítés:** 2026-05-15  
**Tesztelve ezzel:** Aspose.Page for Java (legújabb kiadás)  
**Szerző:** Aspose

## Kapcsolódó bemutatók

- [Hogyan olvassuk el az XMP metaadatokat Java-val – Aspose.Page útmutató](/page/java/xmp-metadata-manipulation/get-metadata/)
- [Aspose Page Java bemutató – XMP metaadatok hozzáadása EPS fájlokhoz](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page módosítás xmp – Értékek módosítása XMP-ben Java-val](/page/java/xmp-metadata-manipulation/change-values/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}