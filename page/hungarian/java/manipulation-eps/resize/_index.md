---
date: 2026-02-07
description: Ismerje meg, hogyan lehet átméretezni az EPS fájlokat Java-ban, és módosítani
  az EPS méreteket az Aspose.Page használatával. Ez a lépésről‑lépésre útmutató megmutatja,
  hogyan lehet EPS-t átméretezni pontok, hüvelyk, milliméter vagy százalékok szerint.
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: Hogyan méretezzünk EPS fájlokat Java-ban az Aspose.Page segítségével
url: /hu/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan méretezhetünk át EPS fájlokat Java-ban az Aspose.Page segítségével

## Bevezetés
Ha megbízható módot keres **hogyan méretezzen át EPS** fájlokat programozottan, jó helyen jár. Ebben az útmutatóban végigvezetjük az EPS képek átméretezését Java-ban az Aspose.Page könyvtár használatával. Akár a méretet duplázni szeretné, akár egy meghatározott méretre csökkenteni, vagy százalékos arányban dolgozni, az alábbi lépések teljes irányítást adnak a kimeneti méretek felett. A **hogyan méretezzen át eps** megértése elengedhetetlen, ha grafikai elemeket kell különböző nyomtatási elrendezésekhez vagy képernyőfelbontásokhoz igazítani.

## Gyors válaszok
- **Melyik könyvtár szükséges?** Aspose.Page for Java  
- **Átméretezhetők pontokban, hüvelykben vagy milliméterben?** Igen – az API támogatja mindhárom egységet, valamint a százalékos értékeket.  
- **Szükséges licenc a fejlesztéshez?** Egy ingyenes próba verzió elegendő a teszteléshez; licenc szükséges a termeléshez.  
- **Melyik Java verzió szükséges?** Java 8 vagy újabb.  
- **A kód szálbiztos?** Minden `PsDocument` példány izolált, így a fájlok párhuzamosan feldolgozhatók.  

## Mi az EPS és miért kell átméretezni?
Az Encapsulated PostScript (EPS) egy népszerű vektorgrafikus formátum, amelyet kiadványszerkesztésben és nyomtatásban használnak. Néha az eredeti EPS fájlt olyan méretben hozták létre, amely nem felel meg a célkimenetnek – például egy 72 pts méretű logót 144 pts-re kell növelni egy nagyobb brosúrához. A **hogyan méretezzen át eps** ismerete lehetővé teszi, hogy a vektoros minőséget megtartva alkalmazkodjon a méretekhez bármely munkafolyamatban.

## Miért használjuk az Aspose.Page‑t EPS átméretezéshez?
- **Teljes kontroll az egységek felett** – pontok, hüvelyk, milliméter vagy százalék.  
- **Nincs külső függőség** – tiszta Java API, natív könyvtárak nélkül.  
- **Magas teljesítmény** – alkalmas kötegelt feldolgozásra szervereken.  
- **Megőrzi a vektor pontosságát** – a kimenet skálázható marad rasterizáció nélkül.

## Előfeltételek
Mielőtt a kódba merülnénk, győződjön meg róla, hogy a következők rendelkezésre állnak:

- Java Development Kit (JDK) telepítve van a gépén.  
- Aspose.Page for Java könyvtár. Letöltheti **[itt](https://releases.aspose.com/page/java/)**.  
- Alapvető Java programozási ismeretek.

## Importálás
A Java projektjében adja hozzá a szükséges importokat, hogy dolgozhasson az Aspose.Page objektumokkal és a szabványos I/O streamekkel.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## EPS méretek módosítása különböző egységekkel
A könyvtár lehetővé teszi a **eps méretek módosítását** egyszerűen a megfelelő `Units` enum kiválasztásával. Az alábbiakban ugyanazt az öt lépéses mintát mutatjuk be pontok, hüvelyk, milliméter és százalék esetén. Az egyetlen változó az, hogy melyik egységet adja át a `resizeEps`‑nek.

## EPS átméretezése pontokkal
Az alábbi teljes, lépésről‑lépésre példakód duplázza meg egy EPS fájl méretét pontokban mérve.

### 1. lépés: Bemeneti stream beállítása
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### 2. lépés: A `PsDocument` objektum inicializálása
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### 3. lépés: Az EPS kép aktuális méretének lekérdezése
```java
Dimension oldSize = doc.extractEpsSize();
```

### 4. lépés: Kimeneti stream létrehozása a méretezett fájlhoz
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### 5. lépés: Méretezés és mentés pontokkal
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## EPS átméretezése hüvelykben
Ugyanez az öt lépéses minta alkalmazható; csak cserélje le a `Units.Points`‑t `Units.Inches`‑re, és állítsa be a kívánt hüvelyk értéket.

## EPS átméretezése milliméterben
Ismét kövesse ugyanazokat a lépéseket, a `Units.Millimeters`‑re cserélve az egységet. Ez akkor hasznos, ha metrikus méretekre van szükség a nyomtatási munkafolyamatokban.

## EPS átméretezése százalékban
Százalékos skálázáshoz használja a `Units.Percent` egységet. Szorozza meg az eredeti szélességet és magasságot a kívánt százalékkal (pl. `0.5` a 50 % csökkentéshez).

## Gyakori hibák és tippek
- **Mindig zárja le a streameket** – Gyártási kódban csomagolja a streameket `try‑with‑resources`‑ba, hogy elkerülje a fájlzárakat.  
- **Tartsa meg az arányt** – Szorozza meg a szélességet és a magasságot ugyanazzal a tényezővel, hacsak nem akar szándékosan torzítást.  
- **Ellenőrizze a DPI‑t** – Az átméretezés nem változtatja meg a DPI‑t; ha más DPI‑ra van szükség, azt külön kell beállítani az átméretezés után.  
- **Szálbiztonság** – Hozzon létre egy új `PsDocument`‑ot szálanként; ugyanazon példány megosztása váratlan eredményeket okozhat.  

## Gyakran feltett kérdések

**K: Használható ez a könyvtár más képformátumokhoz is?**  
V: Nem, az Aspose.Page kizárólag PostScript és EPS fájlokra specializálódott.

**K: Elérhető ingyenes próba verzió az Aspose.Page for Java‑hoz?**  
V: Igen, a ingyenes próbát **[itt](https://releases.aspose.com/)** tekintheti meg.

**K: Hol találok további segítséget és megbeszéléseket?**  
V: Látogassa meg az **[Aspose.Page fórumot](https://forum.aspose.com/c/page/39)** a közösségi támogatásért.

**K: Hogyan szerezhetek ideiglenes licencet?**  
V: Ideiglenes licencet **[itt](https://purchase.aspose.com/temporary-license/)** kaphat.

**K: Vannak elérhető példaprojektek?**  
V: Igen, a dokumentációt **[itt](https://reference.aspose.com/page/java/)** találja.

---

**Utolsó frissítés:** 2026-02-07  
**Tesztelt verzió:** Aspose.Page for Java 24.12 (a cikk írásakor legújabb)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}