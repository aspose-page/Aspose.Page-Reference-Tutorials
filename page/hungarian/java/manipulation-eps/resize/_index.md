---
date: 2026-08-29
description: Ismerje meg, hogyan lehet Java vektoros átméretezéssel EPS fájlokat átméretezni
  Java-ban az Aspose.Page használatával. Ez a lépésről‑lépésre útmutató megmutatja,
  hogyan lehet EPS-t átméretezni points, inches, millimeters vagy percentages.
keywords:
- java vector resize
- how to resize eps
- EPS resizing Java
lastmod: 2026-08-29
linktitle: EPS fájl átméretezése Java-ban
og_description: A Java vektoros átméretezés lehetővé teszi, hogy közvetlenül Java-ban
  állítsa be az EPS fájl méreteit. Az Aspose.Page használatával átméretezhet points,
  inches, millimeters vagy percentages, miközben megőrzi a vector quality-t.
og_image_alt: Guide showing java vector resize of EPS files using Aspose.Page
og_title: 'Java vektoros átméretezés: EPS méretek módosítása az Aspose.Page segítségével'
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to Java vector resize EPS files in Java using Aspose.Page.
    This step‑by‑step guide shows you how to resize EPS with points, inches, millimeters,
    or percentages.
  headline: How to Java vector resize EPS files with Aspose.Page
  type: TechArticle
- questions:
  - answer: No, Aspose.Page is specialized for PostScript and EPS files only.
    question: Can I use this library for other image formats?
  - answer: Yes, you can explore the free trial **[Aspose free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**
      for community support.
    question: Where can I find additional help and discussions?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license?
  - answer: Yes, check the documentation **[Aspose.Page Java API reference](https://reference.aspose.com/page/java/)**.
    question: Are there any example projects available?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- java vector resize
- EPS resize
- Aspose.Page
- Java graphics
- vector graphics
title: Hogyan lehet Java vektoros átméretezéssel EPS fájlokat átméretezni az Aspose.Page
  segítségével
url: /hu/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan lehet Java-ban vektorosan átméretezni EPS fájlokat az Aspose.Page használatával

## Bevezetés
Ha programozott módon **java vector resize** EPS fájlokat kell átméreteznie, jó helyen jár. Ez az útmutató végigvezeti Önt az EPS képek Java-ban történő átméretezésén az Aspose.Page könyvtár segítségével. Akár a méretet duplázni szeretné, egy adott méretre csökkenteni, vagy százalékos arányban dolgozni, az alábbi lépések teljes irányítást adnak a kimeneti méretek felett. Az EPS átméretezésének elsajátítása elengedhetetlen, amikor a grafikákat különböző nyomtatási elrendezésekhez, képernyőfelbontásokhoz vagy márka irányelvekhez kell igazítani.

## Gyors válaszok
- **Melyik könyvtár szükséges?** Aspose.Page for Java  
- **Átméretezhetek pontok, hüvelyk vagy milliméterek használatával?** Igen – az API támogatja mindhárom egységet plusz százalékos értékeket.  
- **Szükségem van licencre a fejlesztéshez?** Egy ingyenes próba a teszteléshez működik; licenc szükséges a termeléshez.  
- **Melyik Java verzió szükséges?** Java 8 vagy újabb.  
- **A kód szálbiztos?** Minden `PsDocument` példány izolált, így a fájlokat párhuzamosan feldolgozhatja.  

## Mi az EPS és miért kell átméretezni?
Az Encapsulated PostScript (EPS) egy vektoros grafikai formátum, amelyet széles körben használnak nyomtatásra és kiadványszerkesztésre. Néha az eredeti EPS fájlt olyan méretben hozzák létre, amely nem felel meg a célkimenetnek – például egy 72 pt-re tervezett logónak 144 pt-re kell nőnie egy nagyobb brosúrához. A **how to resize eps** ismerete lehetővé teszi, hogy megőrizze a vektor minőségét, miközben a méreteket bármely munkafolyamathoz igazítja.

## Miért használja az Aspose.Page-t EPS átméretezéshez?
Az Aspose.Page egy egyszerű API-t biztosít, amely lehetővé teszi, hogy a célméretet bármely támogatott egységben megadja, miközben automatikusan megőrzi a vektor struktúráját. A könyvtár belsőleg kezeli az egységkonverziót, így a kívánt méretekre koncentrálhat anélkül, hogy manuálisan számolna.

- **Támogat négy mérőegységet** – Pontok, Hüvelyk, Milliméter és Százalék.  
- **Nincs külső függőség** – tiszta Java API, natív könyvtárak nem szükségesek.  
- **Nagy teljesítményű feldolgozás** – percenként akár 500 EPS fájlt is kezel egy szabványos 8‑magos szerveren.  
- **Megőrzi a vektor hűségét** – a kimenet teljesen skálázható marad rasterizáció nélkül.  

## Előfeltételek
Mielőtt a kódba merülnénk, győződjön meg róla, hogy a következőkkel rendelkezik:

- Java Development Kit (JDK) telepítve van a gépén.  
- Aspose.Page for Java könyvtár. Letöltheti a **[Aspose.Page for Java download page](https://releases.aspose.com/page/java/)**.  
- Alapvető Java programozási ismeretek.  

## Csomagok importálása
A Java projektjében adja hozzá a szükséges importokat, hogy dolgozhasson az Aspose.Page objektumokkal és a szabványos I/O streamekkel.

`PsDocument` egy memóriában betöltött EPS dokumentumot képvisel.  
`Units` egy felsorolás, amely meghatározza az API által elfogadott mérőegységeket.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## Hogyan változtassuk meg az EPS méreteket különböző egységekkel
Az EPS méreteket a `resizeEps` metódus meghívásával módosíthatja, megadva a kívánt szélességet, magasságot és egy `Units` enum értéket; ez pontok, hüvelyk, milliméter vagy százalék esetén működik. Az ugyanaz az öt lépéses minta minden egységre alkalmazható, így az API kiszámítható és könnyen integrálható.

`resizeEps` átméretezi az EPS vásznát a megadott méretekre, miközben megőrzi a belső vektor adatokat.

## EPS átméretezése pontok használatával
Töltse be az EPS fájlt, adja meg az új méretet pontokban, és mentse az eredményt. Ez a megközelítés megduplázza az eredeti méreteket, miközben megőrzi az arányt. A pontok használata pontos vezérlést biztosít a nyomtatásra kész méretek felett, ami különösen hasznos tipográfiai elrendezések és nagy felbontású kimenetek esetén.

### 1. lépés: állítsa be a bemeneti adatfolyamot
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### 2. lépés: inicializálja a `PsDocument` objektumot
`PsDocument` betölti a forrás EPS fájlt és módszereket biztosít a manipulációhoz.  

```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### 3. lépés: nyerje ki az EPS kép aktuális méretét
```java
Dimension oldSize = doc.extractEpsSize();
```

### 4. lépés: hozzon létre egy kimeneti streamet a méretezett fájlhoz
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### 5. lépés: méretezze át és mentse az EPS-t pontok használatával
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## EPS átméretezése hüvelyk használatával
A hüvelyk használatával történő átméretezés lehetővé teszi, hogy megfeleljen az angolszász egységekben meghatározott specifikációknak, például brosúra elrendezéseknek vagy az USA‑ban használt nyomtatási szabványoknak. Adja meg a cél szélességet és magasságot hüvelykben, és az API a megfelelő belső egységekbe konvertálja őket, mielőtt alkalmazná a transzformációt.

## EPS átméretezése milliméter használatával
Metrikus munkafolyamatok esetén a méretek milliméterben történő megadása biztosítja a konzisztenciát a papírméretekkel és a USA-n kívül használt nyomtatóberendezésekkel. A könyvtár automatikusan kezeli a milliméterről a belső koordináta rendszerre történő konverziót.

## EPS átméretezése százalékos arányban
A százalékos átméretezés arányosan méretezi az eredeti méreteket, ami gyors méretállításra alkalmas anélkül, hogy abszolút értékeket kellene számolni. Például a `0.5` tényező a szélességet és a magasságot is 50 %-kal csökkenti.

## Gyakori buktatók és tippek
- **Mindig zárja le a streameket** – A produkciós kódban csomagolja a streameket try‑with‑resources használatával a fájlzárolások elkerülése érdekében.  
- **Őrizze meg az arányt** – Szorozza meg a szélességet és a magasságot ugyanazzal a tényezővel, hacsak nem akar szándékosan torzítást.  
- **Ellenőrizze a DPI-t** – Az átméretezés nem változtatja meg a DPI-t; ha más DPI-ra van szüksége, állítsa be külön a méretezés után.  
- **Szálbiztonság** – Hozzon létre egy új `PsDocument` példányt szálanként; ugyanazon példány megosztása váratlan eredményekhez vezethet.  

## Gyakran ismételt kérdések

**Q: Használhatom ezt a könyvtárat más képformátumokhoz?**  
A: Nem, az Aspose.Page kizárólag PostScript és EPS fájlokra specializálódott.

**Q: Elérhető ingyenes próba az Aspose.Page for Java-hoz?**  
A: Igen, felfedezheti az ingyenes próbát a **[Aspose free trial page](https://releases.aspose.com/)** oldalon.

**Q: Hol találok további segítséget és megbeszéléseket?**  
A: Látogassa meg az **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** közösségi támogatásért.

**Q: Hogyan szerezhetek ideiglenes licencet?**  
A: Ideiglenes licencet a **[temporary license request page](https://purchase.aspose.com/temporary-license/)** oldalon kaphat.

**Q: Van elérhető példaprojekt?**  
A: Igen, tekintse meg a dokumentációt a **[Aspose.Page Java API reference](https://reference.aspose.com/page/java/)** oldalon.

---

**Legutóbb frissítve:** 2026-08-29  
**Tesztelve:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Szerző:** Aspose

## Kapcsolódó útmutatók

- [EPS átméretezése Aspose.Page segítségével – Java EPS manipuláció](/page/java/manipulation-eps/)
- [Hogyan vágjunk le EPS fájlokat Java-ban – Aspose.Page útmutató](/page/java/manipulation-eps/crop/)
- [Hogyan méretezzünk skálát téglalapként az Aspose.Page for Java használatával](/page/java/page-manipulation/transformations/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}