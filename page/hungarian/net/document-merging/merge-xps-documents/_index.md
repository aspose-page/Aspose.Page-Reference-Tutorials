---
date: 2026-01-15
description: Ismerje meg, hogyan lehet XPS dokumentumokat egyesíteni az Aspose.Page
  for .NET használatával – egy lépésről‑lépésre útmutató a zökkenőmentes dokumentumösszevonáshoz.
linktitle: Merge XPS Documents
second_title: Aspose.Page .NET API
title: Hogyan egyesítsünk XPS dokumentumokat az Aspose.Page .NET-hez
url: /hu/net/document-merging/merge-xps-documents/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan egyesítsünk XPS dokumentumokat az Aspose.Page for .NET segítségével

## Bevezetés

Megbízható módot keresel arra, hogy **hogyan egyesíts XPS** fájlokat programozottan? Ebben az útmutatóban lépésről lépésre bemutatjuk, hogyan lehet XPS dokumentumokat egyesíteni az Aspose.Page for .NET használatával. Akár jelentéseket, számlákat vagy bármilyen más XPS‑alapú anyagot kell összevonnod, a folyamat egyszerű és teljesen automatizált. Merüljünk el, és nézzük meg, hogyan érhetsz el tiszta, egyesített XPS kimenetet csak néhány C# sorral.

## Gyors válaszok
- **Melyik könyvtár kezeli az XPS egyesítést?** Aspose.Page for .NET  
- **Mennyi időt vesz igénybe a megvalósítás?** Általában 10 perc alatt  
- **Szükségem van licencre?** Licenc szükséges a termelési használathoz; ingyenes próba elérhető  
- **Támogatott .NET verziók?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Egyesíthetek titkosított XPS fájlokat?** Igen – az Aspose.Page képes kezelni a titkosított dokumentumokat

## Mi az XPS dokumentum egyesítés?
Az XPS (XML Paper Specification) egy Microsoft által létrehozott rögzített elrendezésű dokumentumformátum. Az XPS fájlok egyesítése azt jelenti, hogy több XPS dokumentumot egyetlen, folyamatos fájlba fűzünk össze, miközben megőrzik az eredeti elrendezést, betűtípusokat és grafikákat.

## Miért használjuk az Aspose.Page for .NET-et?
- **Teljes irányítás** az egyesítési folyamat felett Microsoft XPS Viewer nélkül  
- **Nincs külső függőség** – minden a .NET alkalmazásodban fut  
- **Magas teljesítmény** – nagy dokumentumok esetén is hatékonyan működik  
- **Keresztplatformos** – kompatibilis a .NET Framework, .NET Core és .NET 5+ verziókkal  

## Előkövetelmények

Mielőtt elkezdenéd, győződj meg róla, hogy rendelkezel:
- Alapvető C# és .NET ökoszisztéma ismeretekkel.  
- **Aspose.Page for .NET** telepítve – letöltheted [itt](https://releases.aspose.com/page/net/).  
- Egy vagy több XPS fájl, amelyet össze szeretnél vonni.

## Névterek importálása

A C# projektedben importáld azt a névteret, amely hozzáférést biztosít az XPS API-hoz:

```csharp
using Aspose.Page.XPS;
```

## 1. lépés: Projekt beállítása

Hozz létre egy új C# konzol- vagy könyvtárprojektet a Visual Studio, Rider vagy a kedvenc IDE-dben. Adj hozzá hivatkozást az Aspose.Page DLL-hez (vagy telepítsd a NuGet csomagot `Aspose.Page`). Ez hozzáférést biztosít a később használt `XpsDocument` osztályhoz.

## 2. lépés: Stream-ek inicializálása

Nyisd meg a forrás XPS fájlokat bemeneti stream-ként, és hozz létre egy kimeneti stream-et az egyesített dokumentumhoz. A `using` utasítások biztosítják, hogy a művelet után minden stream helyesen lezáródjon.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Initialize XPS output stream
using (System.IO.Stream outStream = System.IO.File.Open(dataDir + "mergedXPSfiles.xps", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream inStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

## 3. lépés: XPS dokumentum betöltése

Hozz létre egy `XpsDocument` példányt az elsődleges bemeneti stream-ből. A `XpsLoadOptions` objektum lehetővé teszi a betöltési viselkedés testreszabását, ha szükséges.

```csharp
XpsDocument document = new XpsDocument(inStream, new XpsLoadOptions());
```

## 4. lépés: XPS fájlok tömbjének létrehozása

Készíts egy string tömböt, amely felsorolja az összes egyesíteni kívánt XPS fájlt. A tömb sorrendje határozza meg a végső dokumentum sorrendjét.

```csharp
string[] filesToMerge = new string[] { dataDir + "Demo.xps", dataDir + "sample.xps" };
```

## 5. lépés: XPS fájlok egyesítése

Hívd meg a `Merge` metódust, átadva a fájlútvonalak tömbjét és a kimeneti stream-et. Az Aspose.Page elvégzi a nehéz munkát – egyesíti az oldalakat, megőrzi az erőforrásokat, és írja a végleges XPS fájlt.

```csharp
document.Merge(filesToMerge, outStream);
```

## Gyakori problémák és tippek
- **Fájl nem található** – Ellenőrizd újra a `filesToMerge` útvonalakat. A `Path.Combine` használata segíthet elkerülni az útvonal‑elválasztó hibákat.  
- **Memóriahasználat** – Sok fájl egyesítésekor fontold meg a kötegelt feldolgozást a memóriaigény alacsonyan tartása érdekében.  
- **Titkosított dokumentumok** – Ha valamely forrás XPS jelszóval védett, töltsd be a megfelelő hitelesítő adatokkal az egyesítés előtt.

## Gyakran ismételt kérdések

**Q1: Egyesíthetek különböző oldalméretű XPS fájlokat?**  
A: Igen. Az Aspose.Page automatikusan normalizálja az oldalméreteket az egyesítés során.

**Q2: Van korlát arra, hogy hány XPS fájlt tudok összevonni?**  
A: Nincs szigorú korlát, de nagyon nagy gyűjtemények befolyásolhatják a teljesítményt; figyeld a memóriahasználatot.

**Q3: Szükségem van speciális licencre a titkosított XPS dokumentumok egyesítéséhez?**  
A: Teljes Aspose.Page licenc szükséges minden termelési szintű funkcióhoz, beleértve a titkosított dokumentumok kezelését is.

**Q4: Hogyan adhatok egyedi láblécet minden oldalhoz az egyesítés után?**  
A: Az egyesítés után újra megnyithatod a keletkezett XPS-t `XpsDocument`‑tel, és a rajzoló API‑val beszúrhatod a lábléceket.

**Q5: Támogatja az Aspose.Page a .NET Core‑t?**  
A: Természetesen. A könyvtár kompatibilis a .NET Core 3.1 és újabb verzióival, valamint a .NET 5/6/7‑tel.

## Következtetés

Most már megtanultad, **hogyan egyesíts XPS** dokumentumokat hatékonyan az Aspose.Page for .NET segítségével. A fenti lépések követésével automatizálhatod a dokumentumok összevonását bármely .NET alkalmazásban, időt takarítva meg és csökkentve a manuális munkát. Fedezd fel tovább az API‑t, hogy vízjeleket adj hozzá, titkosítsd a végső fájlt, vagy szükség szerint egyes oldalakat manipulálj.

---

**Legutóbb frissítve:** 2026-01-15  
**Tesztelve:** Aspose.Page for .NET (legújabb verzió)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}