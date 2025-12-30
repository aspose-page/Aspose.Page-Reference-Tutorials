---
date: 2025-12-30
description: Tanulja meg, hogyan hozhat létre XPS-dokumentumot Java-ban téglalapok
  hozzáadásával az Aspose.Page segítségével. Kövesse ezt a lépésről‑lépésre útmutatót
  a zökkenőmentes XPS-dokumentumkezeléshez.
linktitle: Create XPS Document Java – Add Rectangle
second_title: Aspose.Page Java API
title: XPS dokumentum létrehozása Java – Téglalap hozzáadása az Aspose.Page segítségével
url: /hu/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS dokumentum létrehozása Java – Téglalap hozzáadása

## Introduction
Ebben az átfogó útmutatóban **XPS dokumentum Java** fájlokat hozol létre, és megtanulod, hogyan adj hozzá téglalapokat az Aspose.Page könyvtár segítségével. Akár jelentéseket, számlákat vagy egyedi grafikákat készítesz, a téglalapok létrehozásának elsajátítása pontos irányítást biztosít az XPS elrendezés felett. Lépésről lépésre végigvezetünk, megmagyarázzuk minden kódsor mögötti okot, és megmutatjuk, hogyan testre szabhatod a színeket és vonalakat a professzionális eredményekért.

## Quick Answers
- **Melyik könyvtár ajánlott?** Aspose.Page for Java  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 10 perc egy alap téglalaphoz  
- **Szükség van licencre?** Fejlesztéshez egy ingyenes próba elegendő; a termeléshez kereskedelmi licenc szükséges  
- **Melyik Java verzió támogatott?** Java 8 és újabb  
- **Hozzáadhatok több alakzatot?** Igen – ismételd meg a lépéseket minden egyes alakzathoz

## Prerequisites
- Alapvető ismeretek a Java programozási nyelvről.  
- Telepített Aspose.Page könyvtár. Ha nincs, letöltheted a [Aspose.Page Java dokumentációból](https://reference.aspose.com/page/java/).  
- Működő Java fejlesztői környezet (IDE, JDK, valamint Maven/Gradle, ha azt részesíted előnyben).

## Import Packages
A kezdéshez importáld a szükséges csomagokat a Java projektedbe. Győződj meg róla, hogy az Aspose.Page könyvtár helyesen van hozzáadva az osztályútvonalhoz. Íme egy alap példa:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Most bontsuk le a megadott példát több lépésre, hogy téglalapot adjunk hozzá Java XPS-ben.

## Step 1: Set the Document Directory
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

Cseréld le a `"Your Document Directory"` értéket arra az útvonalra, ahová az XPS fájlokat szeretnéd menteni.

## Step 2: Create a New XPS Document
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Ez a sor **létrehozza** az új XPS dokumentumot, amelyet később alakzatokkal, szöveggel vagy képekkel tölthetsz fel.

## Step 3: Add a CMYK Solid Color Stroked Rectangle
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```

Ez a lépés egy CMYK szilárd színű vonallal rendelkező téglalapot ad hozzá. A geometriai karakterláncot (`"M 20,10 L 220,10 220,100 20,100 Z"`) módosíthatod a méret vagy pozíció változtatásához, és a `createColor` metódus színértékeit a tervezésednek megfelelően állíthatod be.

## Step 4: Save the Resultant XPS Document
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```

Végül mentsd el a módosított XPS dokumentumot, amely tartalmazza a hozzáadott téglalapot, a korábban megadott könyvtárba.

## Common Use Cases
- **Jelentésfejlécek** – Használj téglalapokat háttérblokként a címekhez.  
- **Számlatáblázatok** – Emeld ki a cellákat vagy szakaszokat színes keretekkel.  
- **Egyedi grafikák** – Több téglalapot kombinálva hozhatsz létre összetett alakzatokat.

## Troubleshooting Tips
- **File not found hiba:** Ellenőrizd, hogy a `dataDir` egy létező mappára mutat, és hogy az ICC profil (`uswebuncoated.icc`) jelen van.  
- **Helytelen színek:** Győződj meg arról, hogy az ICC profil megegyezik a használni kívánt színtérrel (CMYK vs. RGB).  
- **Váratlan méretek:** Állítsd be a geometriai karakterláncot a helyes koordináták tükrözésére.

## Conclusion
Gratulálunk! Sikeresen megtanultad, hogyan **hozz létre XPS dokumentum Java** fájlokat, és hogyan adj hozzá téglalapokat az Aspose.Page segítségével. Ez az alap lehetővé teszi, hogy gazdagabb XPS dokumentumokat építs, testre szabj grafikákat, és alakzatokat integrálj nagyobb munkafolyamatokba.

## FAQs
### Can I add multiple rectangles in a single XPS document?
Igen, annyi téglalapot adhatsz hozzá, amennyire szükséged van, a tutorialban leírt lépések ismétlésével.

### How can I change the color of the rectangle?
Módosítsd a `createColor` metódus színértékeit a kívánt szín eléréséhez.

### Is Aspose.Page suitable for handling complex XPS document manipulations?
Teljesen! Az Aspose.Page erős funkciókészletet biztosít az XPS dokumentumok különféle feladatainak kezeléséhez.

### Where can I find additional examples and support?
Fedezd fel az [Aspose.Page fórumot](https://forum.aspose.com/c/page/39) további példákért, és kérj segítséget a közösségtől.

### Can I try Aspose.Page before purchasing?
Igen, kipróbálhatsz egy [ingyenes próbaverziót](https://releases.aspose.com/), hogy megtapasztald az Aspose.Page képességeit.

## Frequently Asked Questions

**Q: Működik ez a megközelítés Java 11‑el vagy újabb verzióval?**  
A: Igen, az Aspose.Page könyvtár kompatibilis a Java 8‑al és újabb verziókkal, beleértve a Java 11‑et, 17‑et és későbbit is.

**Q: Be tudok ágyazni képeket a téglalap területére?**  
A: Hozzáadhatsz egy `XpsImage` elemet, és a ugyanazokkal a geometriai koordinátákkal elhelyezheted a téglalap fölött vagy belül.

**Q: Hogyan állíthatok be kitöltő színt a vonal helyett?**  
A: Hívd meg a `path.setFill(...)` metódust egy szilárd színű ecsettel, amelyet a `doc.createSolidColorBrush(...)` segítségével hozol létre.

**Q: Lehetőség van a téglalap elforgatására?**  
A: Alkalmazz transzformációs mátrixot a útra a `path.setTransform(...)` használatával, hogy elforgass vagy méretezzen.

**Q: Milyen licenc szükséges a termeléshez?**  
A: A telepítéshez kereskedelmi Aspose.Page licenc szükséges; az ingyenes próba korlátozott a kiértékelésre és fejlesztésre.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-30  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

---