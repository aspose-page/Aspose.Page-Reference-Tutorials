---
date: 2025-12-08
description: Tanulja meg, hogyan adhat hozzá hálómintákat Java PostScript dokumentumokhoz
  az Aspose.Page Java használatával. Ez a lépésről‑lépésre útmutató megmutatja, hogyan
  lehet hatékonyan hozzáadni hálóminta grafikákat.
language: hu
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: 'Aspose.Page Java: Hálóminta hozzáadása Java PostScriptben'
url: /java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hatch-minta hozzáadása Java PostScriptben

## Bevezetés
Ha **Aspose.Page Java**-val dolgozol, és szeretnéd gazdagabbá tenni a PostScript kimenetedet textúrázott grafikákkal, a hatch-minták gyors és rugalmas megoldást nyújtanak. Ebben az útmutatóban végigvezetünk a **hatch-minták hozzáadásának** folyamatán egy PostScript dokumentumban, elmagyarázzuk, miért hasznosak, és egy teljes, azonnal futtatható kódrészletet adunk. A végére képes leszel vizuálisan vonzó, hatch‑kitöltésű alakzatokat és szöveget létrehozni néhány Java sorral.

## Gyors válaszok
- **Milyen könyvtárra van szükségem?** Aspose.Page for Java (az “aspose page java” SDK).  
- **Milyen vizuális hatást adunk hozzá?** Hatch-minták (pl. átlós vonalak, keresztminták).  
- **Szükség van licencre a minta futtatásához?** Egy ingyenes próba verzió fejlesztéshez elegendő; licenc szükséges a termeléshez.  
- **Hány sor kód?** Körülbelül 70 sor, világos lépésekre bontva.  
- **Használhatom ugyanazt a megközelítést PDF-ekhez?** Igen – az Aspose.Page több kimeneti formátumot támogat, köztük a PDF-et.

## Előfeltételek
- **Java fejlesztői környezet** – JDK 8 vagy újabb, valamint a választott IDE.  
- **Aspose.Page for Java könyvtár** – Töltsd le a legújabb JAR-t a hivatalos oldalról [here](https://releases.aspose.com/page/java/).  
- **Írási jogosultság** egy mappához, ahová a generált PostScript fájlt menteni fogod.

## Csomagok importálása
Először hozd be a szükséges osztályokat a projektedbe. Ezek az importok hozzáférést biztosítanak a rajzolási primitívekhez, a színkezeléshez és az Aspose.Page API-hoz.

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
Hozd létre a kimeneti adatfolyamot, állítsd be az oldal méretét (A4), és definiálj néhány elrendezési változót, amelyeket a hatch‑kitöltésű négyzetek rajzolásakor újra felhasználsz.

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

## 2. lépés: Grafikai állapot mentése és transzformálás
A grafikai állapot mentése lehetővé teszi, hogy később visszatérjünk az eredeti koordináta-rendszerhez, míg a `translate` a kiindulási pontot egy kényelmes helyre helyezi.

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## 3. lépés: Négyzet létrehozása minden mintához
Definiálj egy újrahasználható téglalapot, amely minden hatch‑kitöltésű cellát képvisel.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## 4. lépés: Toll beállítása a minta négyzet körvonalához
A 2 pont széles `BasicStroke` tiszta körvonalat ad minden négyzetnek.

```java
BasicStroke stroke = new BasicStroke(2);
```

## 5. lépés: Hatch-minták bejárása
Iterálj végig a `HatchStyle` enum minden értékén, töltsd ki minden négyzetet a megfelelő textúrával, majd rajzold meg a körvonalát. Ez a **hatch-minta hozzáadásának** funkciójának a magja.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## 6. lépés: Grafikai állapot visszaállítása
Térj vissza az eredeti koordináta-rendszerhez, miután befejeztük a négyzetek rácsának rajzolását.

```java
document.writeGraphicsRestore();
```

## 7. lépés: Szöveg kitöltése hatch-mintával
Itt bemutatjuk, hogyan lehet szöveget festeni hatch-textúrával. A példa az „ABC” szót egy átlós‑kereszt minta segítségével tölti ki.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## 8. lépés: Szöveg körvonalazása hatch-mintával
Most ugyanazt a szöveget körvonalazzuk, de ezúttal 70 %-os hatch stílust és vastagabb vonalat használva.

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## 9. lépés: Dokumentum lezárása és mentése
Fejezd be az oldalt, írd a fájlt a lemezre, és szabadítsd fel az erőforrásokat.

```java
document.closePage();
document.save();
```

Kövesd ezeket a lépéseket, és kapsz egy PostScript fájlt, amely teljes hatch-mintakészletet mutat be alakzatokra és szövegre egyaránt – mindezt a **aspose page java** biztosítja.

## Miért használjunk hatch-mintákat az Aspose.Page Java-val?
- **Vizualis megkülönböztetés** – A hatch kitöltések akkor is működnek, ha a nyomtatók csak monokróm kimenetet támogatnak.  
- **Teljesítmény** – A textúrák futás közben generálódnak, így elkerülheted a nagy képfájlok használatát.  
- **Kereszt‑formátum támogatás** – Ugyanaz a kód célozhat PDF-et, EPS-t vagy SVG-t minimális módosítással.

## Gyakori hibák és tippek
- **Fájlútvonal hibák** – Győződj meg arról, hogy a `dataDir` a megfelelő fájlelválasztóval (`/` vagy `\`) végződik.  
- **Nem támogatott színek** – Egyes régebbi PostScript értelmezők nem kezelhetnek bizonyos színtereket; a maximális kompatibilitás érdekében maradj az alap RGB-nél.  
- **Licenc figyelmeztetések** – A minta érvényes licenc nélkül történő futtatása vízjelet helyez el a kimenetben.

## Összegzés
A hatch-minták beépítése drámaian javíthatja a technikai rajzok, térképek vagy bármely Java által generált grafika olvashatóságát és esztétikáját. A **Aspose.Page Java** segítségével egy tömör API-t kapsz, amely elrejti az alacsony szintű PostScript parancsokat, így a tervezésre koncentrálhatsz a fájlformátum részletei helyett.

## Gyakran Ismételt Kérdések

**Q: Használhatom az Aspose.Page Java-t más Java keretrendszerekkel?**  
A: Igen, a könyvtár keretrendszer‑független, és működik Spring, Jakarta EE, Android (korlátozottan) és tiszta Java SE esetén.

**Q: Elérhető próba verzió az Aspose.Page Java-hoz?**  
A: Természetesen. Tölts le egy ingyenes 30‑napos próbát [here](https://releases.aspose.com/).

**Q: Hogyan szerezhetek ideiglenes licencet fejlesztéshez?**  
A: Kérj ideiglenes licencet [here](https://purchase.aspose.com/temporary-license/). Ez eltávolítja a kiértékelési vízjeleket.

**Q: Hol találok további útmutatókat és közösségi támogatást?**  
A: Látogasd meg a hivatalos fórumot [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) további példák és kérdések‑válaszokért.

**Q: Van átfogó dokumentáció minden osztályról és metódusról?**  
A: Igen, a teljes API referencia elérhető [here](https://reference.aspose.com/page/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-08  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose