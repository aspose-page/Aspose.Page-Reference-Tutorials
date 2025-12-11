---
date: 2025-12-11
description: Ismerje meg, hogyan állíthat be egyedi oldalméretet és adhat hozzá oldalakat
  Java PostScript dokumentumokhoz az Aspose.Page használatával. Kövesse lépésről‑lépésre
  útmutatónkat a zökkenőmentes dokumentumműveletekhez.
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: Aspose.Page Java útmutató – egyedi oldalméret beállítása PostScript-ben oldalak
  hozzáadása közben
url: /hu/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java oktatóanyag – egyéni oldalméret beállítása PostScript oldalak hozzáadása során

## Bevezetés
A modern Java alkalmazásokban gyakran szükséges **egyéni oldalméret beállítása** a PostScript kimenethez – legyen szó számlák, jegyek vagy egyedi grafikák generálásáról. Az Aspose.Page for Java egyszerűvé teszi ezt a feladatot. Ebben az oktatóanyagban lépésről lépésre megtanulja, hogyan adjon hozzá oldalakat, és hogyan állítson be egyéni oldalméreteket egy PostScript dokumentumban, hogy minden alkalommal a tökéletes elrendezést kapja.

## Gyors válaszok
- **Beállíthatok különböző oldalméreteket minden egyes oldalra?** Igen, egyedi méretekkel nyithatja meg az oldalakat a `document.openPage(width, height)` metódussal.  
- **Szükség van licencre a termelési környezetben?** Érvényes Aspose.Page licenc szükséges a nem‑értékelő telepítésekhez.  
- **Mely Java verziók támogatottak?** A könyvtár a Java 8 és újabb verzióival működik.  
- **Az API szálbiztos?** A `PsDocument` példányok nem szálbiztosak; minden szálhoz hozzon létre külön `PsDocument`‑ot.  
- **Mekkora lehet egy PostScript fájl?** Az Aspose.Page hatékonyan kezeli a több megabájtos fájlokat; a memóriahasználat a tartalommal, nem az oldalak számával aránylik.

## Előfeltételek
Mielőtt elkezdenénk, győződjön meg róla, hogy rendelkezik:

- Alapvető Java programozási ismeretekkel.  
- Az Aspose.Page for Java könyvtár hozzáadva a projektjéhez (Maven/Gradle vagy manuális JAR).  
- Java fejlesztői környezettel (IDE, JDK 8+).  

## Csomagok importálása
A kezdéshez importálja a szükséges osztályokat az Aspose.Page könyvtárból.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 1. lépés: Többoldalas PostScript dokumentum létrehozása
Először hozzon létre egy új `PsDocument`‑et, amely több oldalt támogat. Ez beállítja a kimeneti streamet, és jelzi a könyvtárnak, hogy egy többoldalas fájlon dolgozunk.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddPages2_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Set variable that indicates if resulting PostScript document will be multipaged
boolean multiPaged = true;
// Create new multipaged PS Document with one page opened
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## 2. lépés: Tartalom hozzáadása az első oldalhoz
Miután a dokumentum készen áll, bármilyen tartalmat hozzáadhat az első oldalhoz. Amikor befejezte, zárja le az oldalt, hogy a tartalom rögzítve legyen.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## Hogyan állítsunk be egyéni oldalméretet
Ha az alapértelmezett oldalméret nem megfelelő, **egyéni oldalméretet** állíthat be egy új oldal megnyitásakor. Ez hasznos például nyugták, címkék vagy bármely nem szabványos elrendezés esetén.

## 3. lépés: Második oldal hozzáadása eltérő mérettel
Az alábbiakban megnyitunk egy második oldalt, és kifejezetten megadunk egy egyedi szélességet és magasságot (pontban). Ez bemutatja, hogyan állíthat be egyéni oldalméretet egyedi oldalakhoz.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## 4. lépés: Dokumentum mentése
Végül mentse a változtatásokat a dokumentum mentésével. Az összes oldal – beleértve az egyéni méretűeket is – ki lesz írva a kimeneti fájlba.

```java
// Save the document
document.save();
```

Ezeknek a lépéseknek a követésével zökkenőmentesen hozzáadhat oldalakat, és **egyéni oldalméreteket állíthat be** egy Java PostScript dokumentumban az Aspose.Page segítségével, teljes kontrollt biztosítva minden oldal elrendezése felett.

## Összegzés
Az Aspose.Page for Java robusztus, fejlesztőbarát API‑t kínál a PostScript dokumentumok kezeléséhez. Most már tudja, hogyan adjon hozzá több oldalt, alkalmazzon egyedi méreteket, és mentse az eredményt – ezáltal pontosan formázott kimenetet generálhat bármely Java‑alapú megoldáshoz.

## Gyakran Ismételt Kérdések
### Hozzáadhatok különböző méretű oldalakat egyetlen PostScript dokumentumban?
Igen, ahogy ebben az oktatóanyagban is bemutattuk, különböző méretű oldalakat adhat hozzá egy többoldalas PostScript dokumentumban.  
### Van korlátozás az oldalak számát illetően, amelyeket hozzáadhatok?
Az Aspose.Page gyakorlatilag korlátlan számú oldal hozzáadását támogatja egy dokumentumban.  
### Hozzáadhatok egyedi tartalmat, például képeket vagy grafikákat az oldalakhoz?
Természetesen! Az Aspose.Page lehetővé teszi különféle tartalmak, köztük szöveg, képek és egyéb grafikai elemek hozzáadását.  
### Az Aspose.Page alkalmas nagy dokumentumok kezelésére?
Igen, az Aspose.Page úgy lett tervezve, hogy hatékonyan kezelje mind a kis, mind a nagy méretű dokumentumokat.  
### Hol találok további forrásokat és támogatást az Aspose.Page‑hez?
Fedezze fel az [Aspose.Page dokumentációját](https://reference.aspose.com/page/java/), vagy látogassa meg az [Aspose.Page fórumot](https://forum.aspose.com/c/page/39) a közösségi támogatásért.  

**További kérdések‑válaszok**

**K:** *Milyen képformátumok támogatottak PostScript oldalra rajzoláskor?*  
**V:** PNG, JPEG, BMP és GIF képeket közvetlenül beágyazhat a rajzoló API‑val.  

**K:** *Hogyan változtathatom meg a dokumentum alapértelmezett DPI-jét?*  
**V:** Állítsa be a `PsSaveOptions.setResolution(int dpi)` metódust a `PsDocument` létrehozása előtt.  

**K:** *Titkosíthatok egy PostScript fájlt jelszóval?*  
**V:** A PostScript önmagában nem támogat titkosítást, de a kimenetet PDF‑be csomagolva alkalmazhat biztonsági beállításokat, ha szükséges.

---

**Utolsó frissítés:** 2025-12-11  
**Tesztelt verzió:** Aspose.Page for Java 24.10  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
