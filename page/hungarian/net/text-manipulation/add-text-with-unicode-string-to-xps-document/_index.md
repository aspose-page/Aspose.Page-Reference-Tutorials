---
date: 2026-03-21
description: Tanulja meg, hogyan adhat hozzá Unicode szöveget egy XPS dokumentumhoz
  az Aspose.Page for .NET használatával. Ez az útmutató megmutatja, hogyan hozhat
  létre XPS dokumentumot C#-ban, és hogyan adhat szöveget Unicode karakterláncokkal
  az Aspose.Page segítségével.
linktitle: Add Text with Unicode String to XPS Document
second_title: Aspose.Page .NET API
title: Unicode szöveg hozzáadása XPS dokumentumhoz az Aspose.Page segítségével
url: /hu/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Unicode szöveg hozzáadása XPS dokumentumhoz az Aspose.Page segítségével

## Bevezetés

Ha **how to add unicode** karaktereket kell hozzáadni egy XPS fájlhoz, jó helyen jársz. Ebben az útmutatóban végigvezetünk a pontos lépéseken, amelyek szükségesek egy **create XPS document C#**‑stílusú XPS dokumentum létrehozásához az Aspose.Page for .NET használatával, és bemutatjuk az **aspose page add text** képességet egy Unicode karakterlánccal. A végére egy teljesen működő XPS dokumentumot kapsz, amely helyesen jeleníti meg a jobbról balra (RTL) irányú Unicode szöveget.

## Gyors válaszok
- **Mire terjed ki az útmutató?** Unicode szöveg hozzáadása egy XPS dokumentumhoz az Aspose.Page for .NET segítségével.  
- **Melyik nyelvet használják?** C# (kompatibilis a .NET Framework és a .NET Core platformokkal).  
- **Szükségem van licencre?** Az ingyenes próba verzió fejlesztéshez használható; a termeléshez kereskedelmi licenc szükséges.  
- **Módosíthatom a betűtípust vagy a méretet?** Igen – a példában az Arial 20 pt van használva, de bármely telepített betűtípus működik.  
- **Támogatott a RTL?** `BidiLevel = 1` beállítása engedélyezi a jobbról balra (RTL) megjelenítést Unicode karakterláncok esetén.

## Mi az a “how to add unicode” az XPS-ben?

Unicode szöveg hozzáadása azt jelenti, hogy bármely nyelv karaktereit – arab, héber, kínai stb. – beillesztjük egy XPS dokumentumba. Az Aspose.Page `XpsGlyphs` osztálya kezeli az alacsony szintű glif elhelyezést, míg a `BidiLevel` tulajdonság szabályozza a szöveg irányát RTL szkriptek esetén.

## Miért használjuk az Aspose.Page-t szöveg hozzáadásához?

- **Full .NET integration** – működik a .NET Framework, .NET Core, .NET 5/6+ környezetekkel.  
- **No external dependencies** – tiszta managed kód, nincs COM interop.  
- **Rich typography support** – betűtípusok, stílusok, színek és kétirányú szöveg.  
- **High performance** – gyorsan hoz létre és ment XPS fájlokat, ideális szerveroldali generáláshoz.

## Előfeltételek

- Alapvető C# és .NET fejlesztési ismeretek.  
- Visual Studio (bármely friss verzió).  
- Aspose.Page for .NET könyvtár – töltsd le innen: [here](https://releases.aspose.com/page/net/).

## Névtér importálása

Először importáld a névtereket, amelyek hozzáférést biztosítanak az XPS modellhez és a rajzolási segédeszközökhöz.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 1. lépés: Dokumentum előkészítése – create XPS document C#

Hozz létre egy új XPS dokumentumot, amely a Unicode szöveget fogja tartalmazni.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

## 2. lépés: Unicode szöveg hozzáadása – aspose page add text

Most hozzáadjuk a tényleges Unicode karakterláncot. Ebben a példában az Arial betűtípust, 20-as méretet használjuk, és a szöveget a (400 f, 200 f) pozícióba helyezzük. Az `BidiLevel` értéke 1 azt mondja a renderelőnek, hogy a karakterláncot jobbról balra (RTL) kezelje.

```csharp
// Add Text
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## 3. lépés: Dokumentum mentése

Végül mentsd el az XPS fájlt a lemezre.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Gratulálunk! Sikeresen **how to add unicode** szöveget adtál hozzá egy XPS dokumentumhoz az Aspose.Page for .NET használatával.

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| A szöveg eltorzult | A betűtípus nem támogatja az Unicode tartományt | Használj olyan betűtípust, amely tartalmazza a szükséges glifeket (pl. Arial Unicode MS). |
| Az RTL szöveg még mindig balról jobbra | `BidiLevel` nincs beállítva vagy 0-ra van állítva | Győződj meg róla, hogy `glyphs.BidiLevel = 1;` van beállítva RTL szkriptekhez. |
| A fájl nem mentődik | Érvénytelen `dataDir` útvonal | Ellenőrizd, hogy a könyvtár létezik-e, és az alkalmazásnak van-e írási jogosultsága. |

## Gyakran feltett kérdések

**K: Kompatibilis az Aspose.Page a legújabb .NET keretrendszerekkel?**  
A: Igen, az Aspose.Page rendszeresen frissül, hogy támogassa a .NET Framework, .NET Core és a .NET 5/6+ verziókat.

**K: Testreszabhatom a betűtípus stílusát és méretét szöveg hozzáadásakor?**  
A: Természetesen! Az `AddGlyphs` metódus lehetővé teszi bármely betűcsalád, méret és `FontStyle` megadását.

**K: Hol találok további dokumentációt az Aspose.Page-hez?**  
A: A dokumentációt [here](https://reference.aspose.com/page/net/) tekintheted meg a részletes API leírásért.

**K: Vannak ingyenes források az Aspose.Page megismeréséhez?**  
A: Igen, tekintsd meg a közösségi fórumot a [Aspose.Page forum](https://forum.aspose.com/c/page/39) címen tippek, példák és felhasználói támogatás céljából.

**K: Elérhető próba verzió a vásárlás előtt?**  
A: Természetesen! Töltsd le az ingyenes próbaverziót [here](https://releases.aspose.com/) címen a könyvtár kipróbálásához.

---

**Utoljára frissítve:** 2026-03-21  
**Tesztelve:** Aspose.Page 24.11 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}