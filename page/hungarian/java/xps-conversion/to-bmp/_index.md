---
date: 2026-03-08
description: Ismerje meg, hogyan konvertálhat XPS-t BMP-re Java-ban, és állíthatja
  be a BMP felbontását az Aspose.Page Java képkonvertáló könyvtár segítségével. Ez
  az útmutató a magas minőségű kimenetet és a memóriahatékony tippeket tárgyalja.
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: XPS konvertálása BMP-re Java-ban – Felbontás beállítása a magas minőségű kimenethez
url: /hu/java/xps-conversion/to-bmp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS konvertálása BMP-re Java-ban

## Bevezetés
Üdvözöljük ebben a lépésről‑lépésre útmutatóban, amely bemutatja, hogyan **konvertálhat XPS‑t BMP‑re** Java‑ban, és hogyan állíthatja be a felbontást az optimális képminőség érdekében az Aspose.Page segítségével. Akár nyomtatási folyamatot épít, bélyegképeket generál, vagy nagy felbontású grafikára van szüksége, a DPI szabályozása rugalmasságot biztosít minden követelmény teljesítéséhez.

## Gyors válaszok
- **Melyik könyvtárat használjam?** Az Aspose.Page for Java a legteljesebb **java image conversion library** XPS → BMP konvertáláshoz.  
- **Szabályozhatom a képminőséget?** Igen – használja a `BmpSaveOptions`‑t a **BMP felbontás** és a simítási mód beállításához.  
- **Hogyan kerülhetem el az OutOfMemoryError Java‑t nagy XPS fájlok feldolgozásakor?** Renderelje az oldalakat partíciókban, vagy növelje a JVM heap‑et (`-Xmx`).  
- **Csak bizonyos oldalakat kell konvertálnom?** Természetesen, az `options.setPageNumbers()` lehetővé teszi a pontos oldalak kiválasztását.  
- **Mely Java verziók támogatottak?** Minden modern Java verzió (8 és újabb) zökkenőmentesen működik.

## Miért fontos a felbontás beállítása?
A felbontás meghatározza a generált BMP‑kép hüvelykenkénti pontszámát (DPI). A magasabb DPI élesebb képeket eredményez, ami nyomtatás vagy részletes grafikai munka esetén elengedhetetlen. A felbontás beállítása teljes irányítást ad a **convert xps to bmp** munkafolyamat kimeneti minősége felett.

## Miért használjuk az Aspose.Page‑t XPS → BMP konvertáláshoz?
- **Magas hűség** – megőrzi az eredeti XPS vektoros minőségét.  
- **Finomhangolt vezérlés** – beállíthatja a DPI‑t, a simítást, és még a konvertálandó oldalakat is kiválaszthatja.  
- **Nincs külső függőség** – tisztán Java, natív könyvtárak nélkül.  
- **Skálázható** – működik egyoldalas dokumentumoknál és nagy, többoldalas XPS fájloknál egyaránt.  

## Előfeltételek
A konvertálási folyamat megkezdése előtt győződjön meg a következő előfeltételek meglétéről:
- **Java fejlesztői környezet** – Java 8 vagy újabb telepítve a gépén.  
- **Aspose.Page for Java könyvtár** – Töltse le és vegye fel a projektjébe az Aspose.Page for Java könyvtárat. A könyvtárat megtalálja [itt](https://releases.aspose.com/page/java/).  
- **Minta XPS fájl** – Készítsen elő egy XPS dokumentumot, amelyet BMP‑re szeretne konvertálni.

## Csomagok importálása
Tegye bele a szükséges Aspose.Page csomagokat a Java kódjába:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Hogyan állítsuk be a felbontást XPS‑ről BMP‑re konvertáláskor
Az alábbi tömör, számozott útmutató pontosan megmutatja, hol és hogyan állítható be a felbontás, valamint hogyan **konvertálhatók konkrét oldalak**.

### 1. lépés: XPS dokumentum betöltése
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### 2. lépés: Opciók inicializálása (felbontás és oldalválasztás)
```java
// Initialize options object with necessary parameters.
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);

// Primary setting – this is the **how to set resolution** part.
options.setResolution(300);               // 300 DPI for high‑quality output

// Optional: convert specific pages only (e.g., pages 1, 2, and 6)
options.setPageNumbers(new int[]{1, 2, 6});
```

### 3. lépés: Renderelő eszköz létrehozása
```java
// Create rendering device for BMP format
ImageDevice device = new ImageDevice();
```

### 4. lépés: Dokumentum mentése az opciókkal
```java
// Save XPS document to BMP using options and device
document.save(device, options);
```

### 5. lépés: Renderelt képek bejárása és fájlok írása
```java
// Iterate through document partitions
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoBMP" + "_" + (i + 1) + "_" + (j + 1) + ".bmp");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```

Ismételje meg ezeket a lépéseket minden további testreszabás vagy módosítás esetén, amelyre a konvertálási folyamat során szüksége lehet.

## Hogyan kerülhető el az OutOfMemoryError Java nagy XPS fájlok konvertálásakor
- **Feldarabolásban történő feldolgozás** – A példa már a dokumentumot partíciókban rendereli (`device.getResult()`), ami csökkenti a memória terhelését.  
- **JVM heap növelése** – Használja a `-Xmx` kapcsolót (pl. `-Xmx2g`) a nagy dokumentumok számára több memória lefoglalásához.  
- **Erőforrások felszabadítása** – Hívja meg a `document.close()`‑t a munka befejezésekor a natív erőforrások felszabadításához.

## Gyakori problémák és megoldások
| Probléma | Megoldás |
|----------|----------|
| **Alacsony minőségű BMP kimenet** | Ellenőrizze, hogy az `options.setResolution()` értéke ≥ 300 DPI‑re van állítva. |
| **A dokumentum csak részben konvertálódik** | Győződjön meg róla, hogy az `options.setPageNumbers()` tartalmazza az összes kívánt oldal indexét. |
| **OutOfMemoryError nagy XPS fájloknál** | Feldarabolja a dokumentumot kisebb részekre, vagy növelje a JVM heap méretét (`-Xmx`). |
| **Fájl nem található** | Ellenőrizze a `dataDir` útvonalat, és hogy a bemeneti XPS fájl létezik-e. |

## Gyakran feltett kérdések
### K: Testreszabhatom a BMP képek felbontását?
V: Igen, a `options.setResolution()` paraméter módosításával állíthatja be a felbontást a kódban.

### K: Az Aspose.Page kompatibilis különböző Java verziókkal?
V: Igen, az Aspose.Page széles körű Java verziót támogat. Győződjön meg róla, hogy kompatibilis verziót használ.

### K: Hogyan konvertálhatok XPS fájlokat egy adott oldaltartományból?
V: Használja az `options.setPageNumbers()` metódust a konvertálandó oldalszámok megadásához.

### K: Vannak-e más kimeneti formátumok, amelyeket az Aspose.Page támogat?
V: Igen, az Aspose.Page számos kimeneti formátumot támogat. Tekintse meg a dokumentációt a teljes listáért.

### K: Hol találok további segítséget vagy támogatást?
V: Látogassa meg az [Aspose.Page Fórumot](https://forum.aspose.com/c/page/39) a közösségi támogatásért és megbeszélésekért.

---

**Utoljára frissítve:** 2026-03-08  
**Tesztelve a következővel:** Aspose.Page for Java 24.12  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}