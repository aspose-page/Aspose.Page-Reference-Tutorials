---
date: 2025-12-02
description: Ismerje meg, hogyan lehet könnyedén átméretezni az EPS fájlokat Java
  nyelven az Aspose.Page segítségével. Ez a lépésről‑lépésre útmutató megmutatja,
  hogyan lehet EPS‑t átméretezni pontok, hüvelyk, milliméter vagy százalékok használatával.
language: hu
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: Hogyan méretezhetünk át EPS fájlokat Java-ban az Aspose.Page segítségével
url: /java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan méretezhetünk át EPS fájlokat Java-ban az Aspose.Page segítségével

## Bevezetés
Ha megbízható módot keres **az EPS fájlok átméretezésére** programozottan, jó helyen jár. Ebben az útmutatóban végigvezetünk az EPS képek Java-ban történő átméretezésén az Aspose.Page könyvtár használatával. Akár a méretet duplázni szeretné, egy adott mé ellenőrzést biztosítanak a kimeneti méretek felett.

## Gyors válaszok
- **Milyen könyvtár szükséges?** Aspose.Page for Java  
- **Átméretezhetek pontok, hüvelyk vagy milliméter egységekben?** Igen – az API támogatja mindhárom egységet, valamint a százalékos értékeket.  
- **Szükségem van licencre a fejlesztéshez?** Egy ingyenes próba a teszteléshez megfelelő; a termeléshez licenc szükséges.  
- **Milyen Java verzió szükséges?** Java 8 vagy újabb.  
- **A kód szálbiztos?** Minden `PsDocument` példány izolált, így a fájlok párhuzamosatók.

## Előfeltételek
Mielőtt belemerülnénk a kódba, győződjön meg arról, hogy a következők rendelkezésre állnak:

- Java Development Kit (JDK) telepítve van a gépén.  
- Aspose.Page for Java könyvtár. Letöltheti **[itt](https://releases.aspose.com/page/java/)**.  
- Alapvető Java programozási ismeretek.  

## Csomagok importálása
A Java projektjében adja hozzá a szükséges importokat, hogy dolgozhasson az Aspose.Page objektumokkal és a szabványos I/O adatfolyamokkal.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## Hogyan méretezzen át EPS-t pontok használatával
Az alábbiakban egy teljes, lépésről‑lépésre példát láthat, amely pontok mérőegységként való használatával duplázza meg egy EPS fájl méretét.

### 1. lépés: Állítsa be a bemeneti adatfolyamot
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### 2. lépés: Inicializálja a `PsDocument` objektumot
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### 3. lépés: Olvassa ki az EPS kép aktuális méretét
```java
Dimension oldSize = doc.extractEpsSize();
```

### 4. lépés: Hozzon létre egy kimeneti adatfolyamot a méretezett fájlhoz
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### 5. lépés: Méretezze át és mentse az EPS-t pontok használatával
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## Hogyan méretezzen át EPS-t hüvelyk használatával
Ugyanez az öt lépéses minta alkalmazható; csak cserélje le a `Units.Points`-t `Units.Inches`-re, és szükség szerint állítsa be a méretezési tényezőt.

## Hogyan méretezzen át EPS-t milliméter használatával
Ismét kövesse ugyanazokat a lépéseket, a mértékegységet `Units.Millimeters`-re cserélve. Ez akkor hasznos, ha nyomtatási munkafolyamatokhoz metrikus méretekre van szükség.

## Hogyan méretezzen át EPS-t százalékos arányban
Százalékos méretezéshez tartsa meg az egységet `Units.Percent`-ként. Szorozza meg az eredeti szélességet és magasságot a kívánt százalékkal (pl. `0.5` a 50 % csökkentéshez).

## Gyakori hibák és tippek
- **Mindig zárja le az adatfolyamokat** – A termelési kódban csomagolja az adatfolyamokat try‑with‑resources blokkba a fájlzárolások elkerülése érdekében.  
- **Tartsa meg a képarányt** – Szorozza meg a szélességet és a magasságot ugyanazzal a tényezővel, hacsak nem akar szándékosan torzítást.  
- **Ellenőrizze a DPI-t** – Az átméretezés nem változtatja meg a DPI-t; ha más DPI-re van szüksége, azt külön kell beállítani az átméretezés után.

## Összegzés
Most már tudja, **hogyan méretezzen át EPS** fájlokat Java-ban az Aspose.Page segítségével, legyen szó pontokról, hüvelykről, milliméterekről vagy százalékos arányokról. Ez a rugalmasság lehetővé teszi az EPS manipuláció integrálását automatizált folyamatokba, asztali segédprogramokba vagy szerver‑oldali szolgáltatásokba.

## Gyakran Ismételt Kérdések

**K: Használhatom ezt a könyvtárat más képformátumokhoz?**  
V: Nem, az Aspose.Page kizárólag PostScript és EPS fájlokra specializálódott.

**K: Elérhető ingyenes próba az Aspose.Page for Java-hoz?**  
V: Igen, az ingyenes próbát **[itt](https://releases.aspose.com/)** tekintheti meg.

**K: Hol találok további segítséget és megbeszéléseket?**  
V: Látogassa meg az **[Aspose.Page fórumot](https://forum.aspose.com/c/page/39)** a közösségi támogatásért.

**K: Hogyan szerezhetek ideiglenes licencet?**  
V: Ideiglenes licencet **[itt](https://purchase.aspose.com/temporary-license/)** kaphat.

**K: Van elérhető példaprojekt?**  
V: Igen, a dokumentációt **[itt](https://reference.aspose.com/page/java/)** tekintheti meg.

---

**Utoljára frissítve:** 2025-12-02  
**Tesztelve:** Aspose.Page for Java 24.12 (a legújabb a írás időpontjában)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}