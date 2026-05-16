---
date: 2026-02-15
description: Tanulja meg, hogyan adhat hozzá hálómintát a Java PostScript fájlokhoz
  az Aspose.Page Java használatával. Ez a lépésről‑lépésre útmutató bemutatja a teljes
  kódot és tippeket.
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: Hogyan adjon hozzá keresztrejtmintát Java PostScriptben az Aspose.Page használatával
url: /hu/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan adjon hozzá csíkozott mintát Java PostScriptben

## Bevezetés
Ha **Aspose.Page Java**‑val dolgozik, és arra kíváncsi, **hogyan adjon hozzá hatch pattern**‑t a PostScript kimenetéhez, a csíkozott minták gyors és rugalmas megoldást jelentenek. Ebben az útmutatóban végigvezetjük, **hogyan adjon hozzá hatch** tervezeteket egy PostScript dokumentumhoz, elmagyarázzuk, miért hasznosak, és egy teljes, azonnal futtatható kódrészletet is bemutatunk. A végére képes lesz vizuálisan vonzó, csíkozott kitöltésű alakzatokat és szöveget létrehozni néhány Java sorral.

## Gyors válaszok
- **Melyik könyvtárra van szükségem?** Aspose.Page for Java (az „aspose page java” SDK).  
- **Milyen vizuális hatást adunk hozzá?** Hatch pattern‑ek (pl. átlós vonalak, keresztcsíkozás).  
- **Szükség van licencre a minta futtatásához?** Egy ingyenes próba verzió elegendő fejlesztéshez; licenc szükséges a termeléshez.  
- **Hány sor kód?** Körülbelül 70 sor, világos lépésekre bontva.  
- **Ugyanazt a megközelítést használhatom PDF‑ekhez is?** Igen — az Aspose.Page több kimeneti formátumot támogat, köztük a PDF‑et.

## Hogyan adjon hozzá hatch pattern‑t – Áttekintés
A hatch pattern‑ek vektor‑alapú textúrák, amelyek bármilyen felbontáson tisztán jelennek meg, és jól működnek monokróm nyomtatókon. Az Aspose.Page Java segítségével ezeket a mintákat alakzatokra, útvonalakra és akár szövegre is alkalmazhatja anélkül, hogy alacsony szintű PostScript parancsokkal kellene foglalkoznia.

## Előfeltételek
Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik a következőkkel:

- **Java fejlesztői környezet** — JDK 8 vagy újabb, valamint a választott IDE.  
- **Aspose.Page for Java könyvtár** — Töltse le a legújabb JAR‑t a hivatalos oldalról [itt](https://releases.aspose.com/page/java/).  
- **Írási jogosultság** egy olyan mappához, ahová a generált PostScript fájlt menteni fogja.

## Csomagok importálása
Először hozza be a szükséges osztályokat a projektbe. Ezek az importok hozzáférést biztosítanak a rajzolási primitívekhez, a színkezeléshez és az Aspose.Page API‑hoz.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 1. lépés: Kezdeti paraméterek beállítása
Hozza létre a kimeneti streamet, konfigurálja az oldal méretét (A4), és definiáljon néhány elrendezési változót, amelyeket a csíkozott négyzetek rajzolásakor újra felhasználunk.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## 2. lépés: Grafikai állapot mentése és transzformáció
A grafikai állapot mentése lehetővé teszi, hogy később visszatérjünk az eredeti koordináta‑rendszerhez, míg a `translate` a kiindulási pontot egy kényelmes helyre helyezi.

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## 3. lépés: Négyzet létrehozása minden mintához
Definiáljon egy újrahasználható téglalapot, amely minden csíkozott cellát képvisel.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## 4. lépés: Toll beállítása a minta négyzet körvonalához
A 2 pont vastagságú `BasicStroke` tiszta körvonalat ad minden négyzet köré.

```java
BasicStroke stroke = new BasicStroke(2);
```

## 5. lépés: Hatch pattern‑ök bejárása
Iteráljon végig a `HatchStyle` enum minden értékén, töltse ki a négyzetet a megfelelő textúrával, majd rajzolja meg a körvonalát. Ez a **hatch pattern hozzáadásának** magja.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## 6. lépés: Grafikai állapot visszaállítása
Térjen vissza az eredeti koordináta‑rendszerhez, miután befejezte a négyzetek rácsának rajzolását.

```java
document.writeGraphicsRestore();
```

## 7. lépés: Szöveg kitöltése hatch pattern‑nel
Itt bemutatjuk, hogyan lehet szöveget festeni egy csíkozott textúrával. A példa a „ABC” szót tölti ki egy átlós‑kereszt mintával.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## 8. lépés: Szöveg körvonalazása hatch pattern‑nel
Most ugyanazt a szöveget körvonalazzuk, de ezúttal 70 % hatch stílust és vastagabb vonalat használunk.

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## 9. lépés: Dokumentum lezárása és mentése
Fejezze be az oldalt, írja a fájlt a lemezre, és szabadítsa fel az erőforrásokat.

```java
document.closePage();
document.save();
```

Kövesse ezeket a lépéseket, és egy olyan PostScript fájlt kap, amely teljes körű hatch pattern‑eket mutat be alakzatokra és szövegre egyaránt — mindezt a **aspose page java** hajtja.

## Miért használjon hatch pattern‑eket az Aspose.Page Java‑val?
- **Vizuális megkülönböztetés** — A hatch kitöltések akkor is működnek, ha a nyomtatók csak monokróm kimenetet támogatnak.  
- **Teljesítmény** — A textúrák futás közben generálódnak, így elkerülhető a nagy képfájlok használata.  
- **Kereszt‑formátum támogatás** — Ugyanaz a kód célzottan PDF, EPS vagy SVG formátumra is átalakítható minimális módosítással.

## Gyakori hibák és tippek
- **Fájlútvonal hibák** — Győződjön meg róla, hogy a `dataDir` a megfelelő fájl‑elválasztóval (`/` vagy `\`) végződik.  
- **Nem támogatott színek** — Egyes régebbi PostScript interpreterek nem kezelik bizonyos színtereket; a maximális kompatibilitás érdekében maradjon az alap RGB‑nél.  
- **Licenc figyelmeztetések** — A minta licenc nélküli futtatása vízjelet helyez a kimenetre.

## Következtetés
A hatch pattern‑ek beépítése drámaian javíthatja a technikai rajzok, térképek vagy bármely Java‑val generált grafika olvashatóságát és esztétikáját. Az **Aspose.Page Java** egy tömör API‑t biztosít, amely elrejti az alacsony szintű PostScript parancsokat, így a tervezésre koncentrálhat a fájlformátum részletei helyett. Most már tudja, **hogyan adjon hozzá hatch pattern‑t** a PostScript dokumentumokhoz — kísérletezzen különböző `HatchStyle` értékekkel, hogy a kívánt megjelenést érje el.

## Gyakran Ismételt Kérdések

**Q: Használhatom az Aspose.Page Java‑t más Java keretrendszerekkel?**  
A: Igen, a könyvtár keretrendszer‑független, és működik Spring‑kel, Jakarta EE‑vel, Android‑nal (korlátozottan) és tiszta Java SE‑vel.

**Q: Elérhető próba verzió az Aspose.Page Java‑hoz?**  
A: Természetesen. Töltse le a 30‑napos ingyenes próba verziót [itt](https://releases.aspose.com/).

**Q: Hogyan szerezhetek ideiglenes licencet fejlesztéshez?**  
A: Kérjen ideiglenes licencet [itt](https://purchase.aspose.com/temporary-license/). Ez eltávolítja a kiértékelési vízjelet.

**Q: Hol találok további oktatóanyagokat és közösségi támogatást?**  
A: Látogassa meg a hivatalos fórumot [Aspose.Page for Java fórum](https://forum.aspose.com/c/page/39) további példák és Q&A céljából.

**Q: Van átfogó dokumentáció minden osztályhoz és metódushoz?**  
A: Igen, a teljes API referencia elérhető [itt](https://reference.aspose.com/page/java/).

**Q: Renderelhetem ugyanazt a hatch pattern‑t PDF‑ben a PostScript helyett?**  
A: Teljesen. Cserélje a `PsSaveOptions`‑t `PdfSaveOptions`‑ra (vagy a megfelelő ekvivalensre), a kód többi része változatlan marad.

**Q: Mit tegyek, ha a generált fájl üres?**  
A: Ellenőrizze, hogy a kimeneti stream egy írható könyvtárra mutat, és hogy a `document.save()` a rajzolási műveletek után meghívásra kerül.

---

**Utoljára frissítve:** 2026-02-15  
**Tesztelve:** Aspose.Page for Java 24.12 (a cikk írásakor legújabb)  
**Szerző:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}