---
date: 2026-06-20
description: Ismerje meg, hogyan állíthatja be az A4-es oldalméretet, hozhat létre
  PostScript fájlokat Java-ban, és adhat hozzá egyedi betűtípusokat az Aspose.Page
  használatával. Próbálja ki ingyenes próba verzióját még ma!
keywords:
- set a4 page size
- add custom fonts java
- java create postscript
linktitle: Dokumentum létrehozása Java-ban PostScript-szel
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to set A4 page size and create PostScript in Java with Aspose.Page
  type: TechArticle
- description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to set A4 page size and create PostScript in Java with Aspose.Page
  steps:
  - name: Set Document Directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define Fonts Folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create Output Stream for PostScript Document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create Save Options with A4 Size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set Page Margins and Add Custom Fonts Folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a Multipaged or Single‑Paged PS Document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close Current Page and Save Document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [here](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [here](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page forum [forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
title: Hogyan állítsuk be az A4-es oldalméretet, és hozzunk létre PostScript fájlokat
  Java-ban az Aspose.Page segítségével
url: /hu/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan állítsuk be az A4 oldalméretet és hozzunk létre PostScript-et Java-ban az Aspose.Page segítségével

## Bevezetés
Ha **A4 oldalméretet** kell beállítania Java-ból PostScript fájlok generálása közben, az Aspose.Page egy gyors, megbízható API-t biztosít, amely elrejti az alacsony szintű részleteket. Ebben az útmutatóban végigvezetjük az egész munkafolyamatot – PostScript dokumentum létrehozása, az A4 oldalméretek konfigurálása, és **egyedi betűtípusok hozzáadása** szükség esetén. A végére egy kész, használatra kész kódrészletet kap, amelyet bármely Java projektbe beilleszthet.

## Gyors válaszok
- **Melyik könyvtár hoz létre PostScript-et Java-ban?** Aspose.Page for Java.  
- **Melyik oldalméretet célozza ez az útmutató?** A4 (210 mm × 297 mm).  
- **Beágyazhatom a saját betűtípusaimat?** Igen – állítsa be a kiegészítő betűtípusok mappáját a mentési beállításokban.  
- **Szükségem van licencre a termeléshez?** Kereskedelmi licenc szükséges; ingyenes próbaverzió is elérhető.  
- **Mely Java verziók támogatottak?** Java 8 és újabb.

## Hogyan állítsuk be az A4 oldalméretet és hozzunk létre PostScript-et Java-ban
Töltse be az Aspose.Page könyvtárat, konfigurálja a `PsSaveOptions`-t az A4 konstansokkal, és írja a dokumentumot egy fájlba – mindez tíz sor kódban. Ez a közvetlen megközelítés garantálja a helyes oldalméreteket, és lehetővé teszi egyedi betűtípusok hozzáadását további konfiguráció nélkül.

## Mi a PostScript A4 méret?
A PostScript A4 méret az ISO 216 szabvány (210 mm × 297 mm) a PostScript oldalleíró nyelvben kifejezve. Meghatározza a nyomtatható területet, amelyet a nyomtatók és megjelenítők értelmeznek, biztosítva a konzisztens elrendezést a platformok között. Mivel a PostScript az oldal tartalmát eszközfüggetlen módon írja le, az A4 méret használata garantálja, hogy a dokumentum minden A4‑képes nyomtatón vagy megjelenítőn világszerte ugyanúgy jelenik meg.

## Miért használjuk az Aspose.Page-et a PostScript oldalméret beállításához?
Az Aspose.Page támogatja a **30+ PostScript operátort**, és akár **500 MB** méretű fájlokat is képes előállítani anélkül, hogy a teljes dokumentumot a memóriába töltené. Ez pontos kontrollt biztosít az oldalméretek felett, miközben nagy terheléseket is hatékonyan kezel. A könyvtár továbbá elvonja a komplex PostScript szintaxist, automatikusan kezeli az erőforrásokat, és nagy teljesítményű streaminget biztosít, így ideális egyszerű egyoldalas szórólapok és összetett többoldalas jelentések számára is.

## Hogyan adjunk hozzá egyedi betűtípusokat Java-ban
A saját betűtípusok beágyazása biztosítja, hogy a generált dokumentum pontosan úgy nézzen ki, ahogy tervezve, bármely nyomtatón vagy megjelenítőn, és az Aspose.Page automatikusan felderíti a megadott mappában elhelyezett betűtípusokat. Egy kiegészítő betűtípusok mappájának regisztrálásával bármilyen TrueType vagy OpenType betűtípust használhat, elkerülheti a helyettesítő betűtípusokat, és megőrizheti a márka konzisztenciáját minden kimeneti eszközön.

## Előfeltételek
- Java programozás alapvető ismerete.  
- Aspose.Page for Java telepítve. Letöltheti [itt](https://releases.aspose.com/page/java/).  
- `necessary_fonts` nevű mappa (vagy bármilyen más név), amely a beágyazni kívánt egyedi betűtípusokat tartalmazza.

## Csomagok importálása
A Java projektjében importálja a szükséges Aspose.Page osztályokat:

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Most bontsuk le a példát világos, számozott lépésekre.

### 1. lépés: Dokumentum könyvtár beállítása
`OUTPUT_DIR` állandó megmondja a könyvtárnak, hová írja a generált fájlt.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### 2. lépés: Betűtípus mappa meghatározása
`FONTS_FOLDER` a könyvtárra mutat, amely az egyedi TrueType vagy OpenType betűtípusokat tartalmazza.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### 3. lépés: Kimeneti stream létrehozása a PostScript dokumentumhoz
`FileOutputStream` megnyit egy streamet, amely a végleges PostScript A4 kimenetet fogadja.

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### 4. lépés: Mentési beállítások létrehozása A4 mérettel
`PsSaveOptions` lehetővé teszi a céloldalméret megadását.  
**Definíció:** `PsPageSize` egy felsorolás, amely standard oldalméret‑konstansokat tartalmaz, mint az A4, Letter és Legal.  
Az `options.setPageSize(PsPageSize.A4)` beállítása konfigurálja a dokumentumot a standard A4 méretekre.

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### 5. lépés: Oldalmargók beállítása és egyedi betűtípus mappa hozzáadása
`options.setMargins(0, 0, 0, 0)` eltávolítja az összes margót egy teljes széles oldalhoz, és `options.setAdditionalFontsFolder(FONTS_FOLDER)` regisztrálja az egyedi betűtípusokat.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### 6. lépés: Többoldalas vagy egyoldalas PS dokumentum létrehozása
`PsDocument document = new PsDocument(outputStream, options)` létrehozza a dokumentumot. A `PsDocument` egy PostScript dokumentumot képvisel, amely egy vagy több oldalt tartalmazhat. Állítsa a `multiPaged` értékét `true`-ra a többoldalas kimenethez.

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### 7. lépés: Aktuális oldal bezárása és dokumentum mentése
A `document.close()` hívása befejezi a fájlt, és a **PostScript A4 méret** kimenetet a lemezre írja.

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Gyakori problémák és tippek
- **A betűtípus nem jelenik meg?** Ellenőrizze, hogy a betűtípus fájl támogatott TrueType vagy OpenType formátumú, és hogy a `FONTS_FOLDER` perjellel (`/`) végződik.  
- **A margók még láthatóak?** Hívja meg a `options.setMargins(...)` **a** `PsDocument` létrehozása **előtt**.  
- **A többoldalas kimenet üresnek tűnik?** Ne felejtse el meghívni a `document.newPage()`-t minden további oldalhoz.

## Gyakran feltett kérdések

**Q: Használhatok egyedi betűtípusokat a PostScript dokumentumban?**  
A: Igen, állítsa be a kiegészítő betűtípusok mappáját a mentési beállításokban (lásd 5. lépés), és az Aspose.Page automatikusan beágyazza a betűtípusokat.

**Q: Elérhető próba verzió az Aspose.Page for Java-hoz?**  
A: Igen, ingyenes próbaverziót kaphat [itt](https://releases.aspose.com/).

**Q: Hogyan férhetek hozzá a teljes API referenciához?**  
A: Tekintse meg a dokumentációt [itt](https://reference.aspose.com/page/java/).

**Q: Hol vásárolhatok licencet az Aspose.Page for Java-hoz?**  
A: Licencet vásárolhat [itt](https://purchase.aspose.com/buy).

**Q: Hol kérhetek segítséget a közösségtől?**  
A: Látogassa meg az Aspose.Page fórumot [forum](https://forum.aspose.com/c/page/39).

**Q: Generálhatok többoldalas PostScript fájlokat?**  
A: Természetesen – állítsa a `multiPaged` értékét `true`-ra a 6. lépésben, és hívja a `document.newPage()`-t minden extra oldalhoz.

## Összegzés
Ezeknek a lépéseknek a követésével most már tudja, **hogyan állítsa be az A4 oldalméretet** és hozzon létre **PostScript** fájlokat Java-ban az Aspose.Page segítségével, miközben **egyedi betűtípusokat is hozzáadhat Java-ban** és szabályozhatja az oldalméret beállításait. Az Aspose.Page végzi a nehéz munkát, így Ön a dokumentumok tartalmára koncentrálhat.

---

**Utoljára frissítve:** 2026-06-20  
**Tesztelve:** Aspose.Page for Java 24.11  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó útmutatók

- [Aspose.Page Java útmutató – egyedi oldalméret beállítása oldalak hozzáadása közben PostScript-ben](/page/java/postscript-page-manipulation/add-pages2/)
- [Hogyan adjunk hozzá szöveget PostScript-hez az Aspose.Page for Java segítségével](/page/java/postscript-text-manipulation/)
- [Aspose Page Java útmutató – PostScript konvertálása PDF-be](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
document.closePage();
document.save();
```