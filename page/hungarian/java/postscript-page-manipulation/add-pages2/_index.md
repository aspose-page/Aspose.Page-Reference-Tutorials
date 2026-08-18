---
date: 2026-02-18
description: Tudja meg, hogyan állíthat be egyéni oldalméretet, és hogyan adhat hozzá
  oldalakat Java PostScript dokumentumokhoz az Aspose.Page segítségével. Kövesse lépésről‑lépésre
  útmutatónkat a zökkenőmentes dokumentumműveletekhez.
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: Aspose.Page Java oktatóanyag – egyéni oldalméret beállítása PostScriptben oldalak
  hozzáadása során
url: /hu/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java oktatóanyag – egyéni oldalméret beállítása oldalak hozzáadása közben PostScriptben

## Bevezetés
A modern Java‑alkalmazásokban gyakran szükséges **egyéni oldalméret beállítása** a PostScript kimenethez – legyen szó számlák, jegyek vagy egyedi grafikák generálásáról. Ebben az oktatóanyagban megtanulja, hogyan **állíthat be egyéni oldalméretet** minden egyes oldalra, hogyan adhat hozzá több oldalt, és végül hogyan **generálhat PostScript fájlt**, amely pontosan megfelel a kívánt elrendezésnek. A kódot lépésről‑lépésre bemutatjuk, hogy gyorsan alkalmazhassa a technikát saját projektjeiben.

## Gyors válaszok
- **Beállíthatok különböző oldalméreteket minden oldalra?** Igen, egyéni méretekkel nyithatja meg az oldalakat a `document.openPage(width, height)` használatával.  
- **Szükség van licencre a termeléshez?** Érvényes Aspose.Page licenc szükséges a nem‑értékelő telepítésekhez.  
- **Mely Java verziók támogatottak?** A könyvtár a Java 8‑as és újabb verziókkal működik.  
- **Az API szálbiztos?** A Document példányok nem szálbiztosak; minden szálnak hozzon létre külön `PsDocument`‑et.  
- **Mekkora lehet egy PostScript fájl?** Az Aspose.Page több megabájtos fájlokat is hatékonyan kezel; a memóriahasználat a tartalommal, nem az oldalak számával aránylik.  
- **Használhatom az open page width/height túlterhelést?** Természetesen – a `openPage(double width, double height)` lehetővé teszi bármilyen méret megadását pontban.

## Előfeltételek
Mielőtt elkezdenénk, győződjön meg róla, hogy rendelkezik:

- Alapvető Java programozási ismeretekkel.  
- Aspose.Page for Java integrálva a projektjébe (Maven/Gradle vagy manuális JAR).  
- Java fejlesztői környezettel (IDE, JDK 8+).  

## Csomagok importálása
A kezdéshez importálja a szükséges osztályokat az Aspose.Page könyvtárból.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 1. lépés: Többoldalas PostScript dokumentum létrehozása
Először hozzon létre egy új `PsDocument`‑et, amely több oldalt támogat. Ez beállítja a kimeneti streamet, és jelzi a könyvtárnak, hogy egy többoldalas fájllal dolgozunk.

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
Ha az alapértelmezett oldalméret nem megfelelő, **beállíthat egyéni oldalméretet** új oldal nyitásakor. Ez hasznos például nyugták, címkék vagy bármely nem szabványos elrendezés esetén.

## 3. lépés: Második oldal hozzáadása eltérő mérettel
Az alábbiakban megnyitunk egy második oldalt, és kifejezetten megadunk egy egyedi szélességet és magasságot (pontban). Ez bemutatja, hogyan állíthat be egyéni oldalméretet egyes oldalakhoz, lehetővé téve **különböző oldalméretek** használatát ugyanabban a dokumentumban.

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

Ezeknek a lépéseknek a követésével zökkenőmentesen adhat hozzá oldalakat és **állíthat be egyéni oldalméretet** egy Java PostScript dokumentumban az Aspose.Page segítségével, teljes irányítást biztosítva minden oldal elrendezése felett.

## Miért használjuk az Aspose.Page‑t egyéni oldalméret beállításához?
- **Pontosság:** A méretek pontban vannak definiálva, így pontos kontrollt kap az oldal szélessége és magassága felett.  
- **Rugalmasság:** Keverhet és párosíthat **különböző oldalméreteket** egyetlen PostScript fájlban.  
- **Teljesítmény:** A könyvtár közvetlenül a kimeneti fájlba streameli a tartalmat, így nagy‑léptékű **PostScript fájl generálás** esetén is megfelelő.  
- **Gazdag API:** Támogat grafika rajzolását, képek beágyazását és szöveg hozzáadását – mindezt a beállított egyéni méretek tiszteletben tartásával.

## Gyakori problémák és megoldások
| Probléma | Megoldás |
|----------|----------|
| **Az oldaldimenziók felcserélődnek** | Ne feledje, hogy az `openPage(width, height)` a szélességet várja először, majd a magasságot (mindkettő pontban). |
| **A tartalom túlnyúlik az oldalról** | Használja a `PsGraphics` koordináta‑rendszert az elemek elhelyezéséhez az egyéni határokon belül, vagy méretezze a rajzot. |
| **Memóriahiány hibák hatalmas dokumentumoknál** | Engedélyezze a streaminget úgy, hogy közvetlenül egy `FileOutputStream`‑ba ír, ahogy a példában látható, és kerülje el nagy képek egyszerre betöltését a memóriába. |

## Gyakran feltett kérdések
### Hozzáadhatok-e különböző méretű oldalakat egyetlen PostScript dokumentumban?
Igen, ahogy ebben az oktatóanyagban is bemutattuk, különböző méretű oldalakat adhat hozzá egy többoldalas PostScript dokumentumban.  

### Van-e korlátozás az oldalak számát illetően, amelyeket hozzáadhatok?
Az Aspose.Page gyakorlatilag korlátlan számú oldal hozzáadását támogatja egy dokumentumban.  

### Hozzáadhatok-e egyedi tartalmat, például képeket vagy grafikákat az oldalakhoz?
Természetesen! Az Aspose.Page lehetővé teszi különféle tartalmak, köztük szöveg, képek és egyéb grafikai elemek hozzáadását.  

### Az Aspose.Page alkalmas nagy dokumentumok kezelésére?
Igen, az Aspose.Page úgy van tervezve, hogy hatékonyan kezelje mind a kis, mind a nagy méretű dokumentumokat.  

### Hol találok további forrásokat és támogatást az Aspose.Page‑hez?
Tekintse meg az [Aspose.Page dokumentációt](https://reference.aspose.com/page/java/), vagy látogassa meg az [Aspose.Page fórumot](https://forum.aspose.com/c/page/39) a közösségi támogatásért.  

**További K&V**

**K:** *Milyen képformátumok támogatottak a PostScript oldalra rajzoláskor?*  
**V:** Közvetlenül beágyazhat PNG, JPEG, BMP és GIF képeket a rajzoló API‑val.  

**K:** *Hogyan változtathatom meg az alapértelmezett DPI‑t a dokumentumban?*  
**V:** Állítsa be a `PsSaveOptions.setResolution(int dpi)`‑t a `PsDocument` létrehozása előtt.  

**K:** *Titkosíthatok-e egy PostScript fájlt jelszóval?*  
**V:** A PostScript önmagában nem támogat titkosítást, de a kimenetet beágyazhatja PDF‑be, és szükség esetén alkalmazhat biztonsági beállításokat.

---

**Utoljára frissítve:** 2026-02-18  
**Tesztelve:** Aspose.Page for Java 24.10  
**Szerző:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}