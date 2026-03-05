---
date: 2025-12-28
description: Tanulja meg, hogyan hozhat létre XPS dokumentumot Java-ban az Aspose.Page
  segítségével, és adjon hozzá könnyedén csempézett képet ezzel a lépésről‑lépésre
  útmutatóval.
linktitle: Add Tiled Image in Java XPS
second_title: Aspose.Page Java API
title: Hogyan készítsünk XPS-dokumentumot csempézett képpel Java-ban
url: /hu/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS dokumentum létrehozása és csempézett kép hozzáadása Java-ban

## Bevezetés
A modern Java fejlesztésben az **XPS dokumentum** fájlok programozott létrehozásának képessége értékes tudás, különösen akkor, ha grafikai elemekkel, például csempézett képekkel szeretnénk gazdagítani őket. Az Aspose.Page for Java egyszerűvé teszi ezt a folyamatot, lehetővé téve, hogy a vizuális tervezésre koncentráljunk a low‑level fájlkezelés helyett. Ebben az útmutatóban megtanulod, hogyan hozhatsz létre XPS dokumentumot, **csempézett képet adhatsz hozzá**, és mentheted az eredményt, mindezt világos, lépésről‑lépésre példakódokkal.

## Gyors válaszok
- **Mit csinál az Aspose.Page?** Egy magas szintű API-t biztosít XPS dokumentumok generálásához és manipulálásához Java-ban.  
- **Csempézhetek képet?** Igen – használja az `XpsImageBrush`-t a `XpsTileMode.Tile` beállítással.  
- **Szükségem van licencre?** Ideiglenes vagy kereskedelmi licenc szükséges a termelésben való használathoz.  
- **Mely Java verzió támogatott?** Bármely JDK 8+ kompatibilis.  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 10–15 perc egy alap csempézett‑kép szcenárióhoz.

## Mi az a „create XPS document”?
Az XPS (XML Paper Specification) fájl egy rögzített elrendezésű dokumentumformátum, amely a PDF-hez hasonló. Az XPS dokumentum programozott létrehozása lehetővé teszi nyomtatható, eszköz‑független fájlok generálását közvetlenül Java kódból.

## Miért adjunk hozzá csempézett képet?
A kép csempézése a grafikát egy meghatározott területen ismétli, ami tökéletes háttérképekhez, vízjelekhez vagy mintázott kitöltésekhez. Az Aspose.Page `XpsTileMode.Tile` használatával ezt néhány sor kóddal elérheted.

## Előfeltételek
Mielőtt belevágnál, győződj meg róla, hogy a következők rendelkezésre állnak:

1. **Java Development Kit (JDK)** – telepített JDK 8 vagy újabb.  
2. **Aspose.Page for Java** – letölthető a [weboldalról](https://releases.aspose.com/page/java/).  
3. **Írható könyvtár** – ahol a generált XPS fájl mentésre kerül.

## Importálás
A Java projektedben importáld a szükséges osztályokat:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Lépés‑ről‑lépésre útmutató

### 1. lépés: Projekt beállítása
Add hozzá az Aspose.Page JAR fájlokat a projekt classpath‑éhez, és ellenőrizd, hogy az importálások hibamentesen fordulnak.

### 2. lépés: XPS dokumentum létrehozása
Hozz létre egy új `XpsDocument` objektumot. Ez a fő tároló, amely az összes oldalt, útvonalat és erőforrást tartalmazza.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### 3. lépés: A csempézett kép útvonalának meghatározása
Helyezd el a csempézni kívánt képet (pl. `R08LN_NN.jpg`) a `dataDir` által hivatkozott könyvtárban. A kép a brush mintájaként lesz használva.

### 4. lépés: Csempézett kép hozzáadása
Hozz létre egy téglalap alakú útvonalat, és töltsd ki egy `XpsImageBrush`‑szal. A tile mód `Tile` beállításával a kép ismétlődik a téglalapon.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### 5. lépés: Dokumentum mentése
Írd ki az XPS fájlt a lemezre. A kimeneti fájl tartalmazni fogja a most definiált csempézett képet.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Ismételd meg ezeket a lépéseket, amikor **csempézett képet** szeretnél hozzáadni más oldalakhoz vagy alakzatokhoz ugyanabban az XPS dokumentumban.

## Gyakori problémák és megoldások
| Probléma | Megoldás |
|----------|----------|
| A kép nem jelenik meg | Ellenőrizd, hogy a fájl útvonal (`dataDir + "R08LN_NN.jpg"`) helyes‑e, és a kép elérhető. |
| A csempe minta nyújtott | Állítsd be a forrás és a cél `Rectangle2D` értékeket a csempe méretének szabályozásához. |
| Az átlátszóság nem hat | Győződj meg róla, hogy a brush átlátszósága **a** tile mód konfigurációja után van beállítva. |

## Gyakran ismételt kérdések

### Az Aspose.Page kompatibilis minden Java verzióval?
Az Aspose.Page úgy lett tervezve, hogy különböző Java verziókkal működjön. A kompatibilitás ellenőrzéséhez tekintsd meg a dokumentációt [itt](https://reference.aspose.com/page/java/).

### Használhatom az Aspose.Page‑t kereskedelmi projektekben?
Igen, az Aspose.Page kereskedelmi licenceket kínál. Vásárolhatsz licenceket [itt](https://purchase.aspose.com/buy).

### Van ingyenes próba verzió?
Igen, az Aspose.Page funkcióit ingyenes próba verzióval is kipróbálhatod [itt](https://releases.aspose.com/).

### Hol találok közösségi támogatást és megbeszéléseket?
Csatlakozz az Aspose.Page közösséghez a [fórumban](https://forum.aspose.com/c/page/39).

### Hogyan szerezhetek ideiglenes licencet az Aspose.Page‑hez?
Ideiglenes licencet kaphatsz [itt](https://purchase.aspose.com/temporary-license/).

---

**Utoljára frissítve:** 2025-12-28  
**Tesztelve a következővel:** Aspose.Page for Java 24.12 (legújabb)  
**Szerző:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
