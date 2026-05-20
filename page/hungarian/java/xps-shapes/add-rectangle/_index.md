---
date: 2026-04-24
description: Tanulja meg, hogyan állíthatja be a téglalap színét, és hogyan adhat
  hozzá téglalapot Java XPS-ben az Aspose.Page használatával. Ez az útmutató a téglalap
  Java‑ban való hozzáadását és a téglalap körvonalának módosítását mutatja be.
keywords:
- set rectangle color
- add rectangle java
- change rectangle stroke
linktitle: Téglalap hozzáadása Java XPS-ben
second_title: Aspose.Page Java API
title: Téglalap színének beállítása és téglalap hozzáadása Java XPS-ben
url: /hu/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Téglalap szín beállítása és téglalap hozzáadása Java XPS-ben

## Bevezetés
Ebben az útmutatóban megtanulja, hogyan **állítsa be a téglalap színét** és **adjon hozzá egy téglalapot** Java XPS-ben az Aspose.Page könyvtár segítségével. Akár egyszerű alakzatokat kell rajzolnia egy jelentéshez, akár összetett vektorgrafikákat hoz létre, a téglalap stílusának elsajátítása pontos irányítást biztosít az XPS dokumentumok felett.  

## Gyors válaszok
- **Melyik könyvtár szükséges?** Aspose.Page for Java  
- **Módosíthatom a téglalap körvonalát?** Igen, a `setStroke` és a `setStrokeThickness` használatával  
- **Támogatott a CMYK színprofil?** Teljesen – betöltheti az ICC profilokat, ahogy látható  
- **Szükség van licencre a termeléshez?** Igen, kereskedelmi licenc szükséges a nem‑értékelő használathoz  
- **Mennyi időt vesz igénybe a megvalósítás?** Általában 10 perc alatt egy egyszerű téglalap esetén

## Mi a **set rectangle color**?
A téglalap színének beállítása azt jelenti, hogy meghatározzuk a kitöltés vagy a körvonal színét, amelyet az alakzat a végső XPS dokumentumban megjelenít. Az Aspose.Page segítségével RGB, CMYK vagy akár egyedi ICC színprofilokat is használhat a pontos színilleszkedéshez.

## Miért használja az Aspose.Page-t a **add rectangle java** és **change rectangle stroke** műveletekhez?
- **Teljes körű API** – támogatja a szilárd színeket és a színátmeneteket.  
- **Keresztplatformos** – bármely Java futtatókörnyezetben működik natív függőségek nélkül.  
- **Gazdag geometriai támogatás** – összetett útvonalak létrehozása, transzformációk alkalmazása és a körvonal vastagságának egyszerű kezelése.  

## Előfeltételek
Mielőtt a kódba merülnénk, győződjön meg róla, hogy rendelkezik:

- Alapvető Java programozási ismeretekkel.  
- Az Aspose.Page könyvtár telepítve. Ha nincs, töltse le a [Aspose.Page Java dokumentációból](https://reference.aspose.com/page/java/).  
- Működő Java fejlesztői környezet (IDE, JDK, stb.).  

## Csomagok importálása
A kezdéshez importálja a szükséges csomagokat a Java projektjébe. Győződjön meg róla, hogy az Aspose.Page könyvtár helyesen van hozzáadva az osztályútvonalhoz. Íme egy alap példa:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Most bontsuk le a megadott példát több lépésre, hogy **téglalapot adjunk hozzá** és **beállítsuk a színét** Java XPS-ben.

## 1. lépés: A dokumentum könyvtár beállítása
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
`"Your Document Directory"` cserélje le arra a abszolút útvonalra, ahol XPS fájlokat szeretne olvasni/írni.

## 2. lépés: Új XPS dokumentum létrehozása
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```
Ez a sor inicializál egy új XPS dokumentumot, amely a formáinkat fogja tartalmazni.

## 3. lépés: CMYK szilárd színű körvonalas téglalap hozzáadása
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
Ez a lépés egy **körvonalas téglalapot** ad hozzá CMYK szilárd színnel. A `setStroke` metódus meghatározza a téglalap körvonalának színét, míg a `setStrokeThickness` szabályozza a vonalvastagságot – tökéletes a **téglalap körvonalának módosításához**.

### Praktikus tipp:
Ha RGB színt szeretne, cserélje le a `createColor` hívást `doc.createColor(0, 0, 255)`-re egy szilárd kék kitöltéshez.

## 4. lépés: Az eredmény XPS dokumentum mentése
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```
Végül mentse az XPS dokumentumot a lemezre. A `AddRectangle_out.xps` fájl most már tartalmaz egy téglalapot, amelynek színét és körvonalát Ön definiálta.

## Gyakori problémák és megoldások
| Probléma | Ok | Megoldás |
|----------|----|----------|
| **A téglalap nem látható** | Helytelen útvonal geometria vagy a körvonal vastagsága 0-ra van állítva | Ellenőrizze az útvonal karakterláncot (`"M 20,10 L 220,10 220,100 20,100 Z"`) és győződjön meg róla, hogy a `setStrokeThickness` nagyobb, mint 0. |
| **Helytelen szín** | ICC profil használata, amely nem egyezik a kívánt színtérrel | Használja a `doc.createColor(r, g, b)`-t RGB-hez, vagy ellenőrizze újra az ICC fájl útvonalát. |
| **A fájl nem lett mentve** | `dataDir` egy nem létező mappára mutat, vagy nincs írási jogosultsága | Hozza létre a mappát előre, vagy válasszon egy írható helyet. |

## Gyakran ismételt kérdések

**K:** *Hozzáadhatok több téglalapot egyetlen XPS dokumentumban?*  
A: Igen. Egyszerűen ismételje meg a geometria létrehozását és a stílus beállítását minden szükséges téglalaphoz.

**K:** *Hogyan változtathatom meg a téglalap kitöltő színét a körvonal helyett?*  
A: Használja a `path.setFill(...)`-t egy szilárd színű ecsettel, hasonlóan ahhoz, ahogy a `setStroke`-ot használja.

**K:** *Alkalmas-e az Aspose.Page összetett XPS dokumentum manipulációkra?*  
A: Teljesen. A könyvtár támogatja a fejlett funkciókat, mint például a színátmenetek, transzformációk és beágyazott betűtípusok.

**K:** *Hol találok további példákat és közösségi támogatást?*  
A: Fedezze fel az [Aspose.Page fórumot](https://forum.aspose.com/c/page/39) további kódrészletek és közösségi segítségért.

**K:** *Próbálhatom-e az Aspose.Page-t vásárlás előtt?*  
A: Igen, egy [ingyenes próbaverziót](https://releases.aspose.com/) is kipróbálhat, hogy felmérje az API képességeit.

---

**Utolsó frissítés:** 2026-04-24  
**Tesztelve:** Aspose.Page for Java 24.12  
**Szerző:** Aspose

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}