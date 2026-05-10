---
date: 2026-03-19
description: Ismerje meg, hogyan adhat hozzá jegyet egyedi nyomtatási jegyek létrehozásával
  az Aspose.Page for .NET segítségével. Szabja testre nyomtatási élményét finomhangolt
  vezérléssel.
linktitle: Create Custom Print Ticket
second_title: Aspose.Page .NET API
title: 'Hogyan adjunk hozzá jegyet: Egyedi nyomtatási jegy létrehozása az Aspose.Page
  for .NET segítségével'
url: /hu/net/print-ticket-management/create-custom-print-ticket/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan adjunk hozzá jegyet: Egyedi nyomtatási jegy létrehozása az Aspose.Page for .NET segítségével

## Bevezetés

Ha **how to add ticket** funkcióra van szüksége egy .NET alkalmazásban, az Aspose.Page lehetővé teszi egyedi nyomtatási jegyek generálását közvetlenül a kódból. Ebben az útmutatóban végigvezetjük a teljes folyamaton – a környezet beállítását, egy XPS dokumentum létrehozását, egy egyedi munka nyomtatási jegy csatolását, és az eredmény mentését. A végére képes lesz jegy támogatást hozzáadni bármely nyomtatási munkafolyamathoz magabiztosan.

## Gyors válaszok
- **Mit jelent a „add ticket”?** Ez egy egyedi nyomtatási jegy (XPS metaadat) beágyazását jelenti, amely a nyomtató beállításait szabályozza.  
- **Melyik könyvtár szükséges?** Aspose.Page for .NET.  
- **Szükségem van licencre?** Az értékeléshez egy ideiglenes licenc elegendő; a termeléshez teljes licenc szükséges.  
- **Használhatom .NET Core‑dal?** Igen, az Aspose.Page támogatja a .NET Framework‑ot és a .NET Core‑t.  
- **Mennyi időt vesz igénybe a megvalósítás?** Általában 15 perc alatt elkészíthető egy alap jegy.

## Mi az egyedi nyomtatási jegy?
Az egyedi nyomtatási jegy egy XML‑alapú leírás a nyomtató beállításairól (például összeállítás, példányszám, színkezelés stb.), amely az XPS dokumentummal együtt utazik. Lehetővé teszi a fejlesztők számára, hogy programozottan határozzák meg, hogyan legyen egy dokumentum nyomtatva, ezzel kiküszöbölve a kliensoldali manuális konfigurációt.

## Miért adjunk hozzá jegy támogatást az Aspose.Page‑del?
- **Finomhangolt vezérlés:** Állítsa be az összeállítást, a példányszámot, a hordozótípust és egyebeket a kódból.  
- **Keresztplatformos konzisztencia:** Ugyanaz a jegy minden olyan nyomtatón működik, amely érti az XPS metaadatokat.  
- **Zökkenőmentes integráció:** Közvetlenül működik a meglévő .NET projektjeivel további szolgáltatások nélkül.

## Előfeltételek

Mielőtt belemerülnénk, győződjön meg róla, hogy rendelkezik:

- Alapvető jártasság C#‑ban és .NET fejlesztésben.  
- Telepített Visual Studio (bármely friss verzió).  
- Az Aspose.Page for .NET könyvtár hozzáadva a projektjéhez.  

Ha még nem adta hozzá a könyvtárat, letöltheti a [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/) oldalról. Közösségi segítségért látogassa meg az [Aspose.Page forum](https://forum.aspose.com/c/page/39) oldalt.

## Névterek importálása

Kezdje azzal, hogy betölti az XPS és metaadat osztályokat tartalmazó névtereket.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsMetadata;
using Aspose.Page.XPS.XpsModel;
using System;
using System.Drawing;
```

Most bontsuk le a megvalósítást lépésről lépésre.

## 1. lépés: Dokumentumkönyvtár beállítása

Határozza meg, hogy hová legyen mentve a generált XPS fájl.

```csharp
string dir = "Your Document Directory";
```

## 2. lépés: Új XPS dokumentum létrehozása

Hozzon létre egy új XPS dokumentumot, amely a lapokat és a jegyet fogja tartalmazni.

```csharp
XpsDocument xDocs = new XpsDocument();
```

## 3. lépés: Egyedi munka nyomtatási jegy hozzáadása

Csatoljon egy egyedi munka nyomtatási jegyet a dokumentumhoz. Ez a **how to add ticket** funkció magja – itt adja meg az összeállítást, a példányszámot, a renderelési szándékot, a színkezelést és minden egyéb szükséges beállítást.

```csharp
xDocs.JobPrintTicket = new JobPrintTicket(
    new PageDevModeSnaphot("SABlAGwAbABvACEAAAA="),
    new DocumentCollate(Collate.CollateOption.Collated),
    // Add other print settings as needed
);
```

> **Pro tip:** Cserélje le a helyőrző snapshot karakterláncot egy Base64‑kódolt DEVMODE struktúrára, amely megfelel a nyomtató képességeinek.

## 4. lépés: Dokumentum mentése

Mentse el az XPS dokumentumot (a beágyazott jeggyel együtt) a lemezre.

```csharp
xDocs.Save(dir + "output1.xps");
```

Amikor megnyitja a *output1.xps* fájlt egy olyan megjelenítőben, amely figyelembe veszi az XPS metaadatokat, a nyomtató automatikusan alkalmazni fogja a jegyben definiált beállításokat.

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| A jegy nem alkalmazódik | A megjelenítő figyelmen kívül hagyja az XPS metaadatokat | Használjon olyan nyomtatóillesztőt, amely támogatja az XPS nyomtatási jegyeket, vagy egy megjelenítőt, például a Microsoft XPS Viewer‑t. |
| Érvénytelen Base64 snapshot | Sérült DEVMODE adat | Generálja újra a snapshotot a nyomtatóillesztőből a `GetPrinter` API használatával. |
| Hiányzó jogosultságok | `dir` írási hozzáférése megtagadva | Győződjön meg róla, hogy az alkalmazás megfelelő fájlrendszer‑jogosultságokkal fut. |

## Gyakran feltett kérdések

**Q: Használhatom az Aspose.Page for .NET-et más .NET keretrendszerekkel?**  
A: Igen, az Aspose.Page működik a .NET Framework‑kel, a .NET Core‑ral, a .NET 5/6‑tal és későbbi verziókkal.

**Q: Hogyan szerezhetek ideiglenes licencet az Aspose.Page‑hez?**  
A: Látogassa meg [ezt a linket](https://purchase.aspose.com/temporary-license/), hogy ideiglenes licencet szerezzen az Aspose.Page‑hez.

**Q: Van közösségi fórum az Aspose.Page támogatásához?**  
A: Természetesen, hasznos beszélgetéseket és támogatást találhat az [Aspose.Page fórumon](https://forum.aspose.com/c/page/39).

**Q: Milyen hordozótípusok támogatottak az egyedi nyomtatási jegyekben?**  
A: Az Aspose.Page számos hordozótípust támogat, beleértve a sima papírt, a fényes papírt és az egyedi hordozódefiníciókat.

**Q: Van elérhető minta projekt az Aspose.Page for .NET‑hez?**  
A: Tekintse meg a [dokumentációt](https://reference.aspose.com/page/net/), ahol minta projekteket és kódrészleteket talál a fejlesztés elindításához.

## Összegzés

Áttekintettük a **how to add ticket** támogatást egy XPS dokumentumban az Aspose.Page for .NET segítségével. A lépések követésével közvetlenül a fájlokba ágyazhat be részletes nyomtatási utasításokat, így teljes irányítást kap a nyomtatási munkafolyamat felett .NET alkalmazásaiból. Nyugodtan kísérletezzen további jegybeállításokkal, hogy megfeleljenek a konkrét nyomtatási környezetének.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Utoljára frissítve:** 2026-03-19  
**Tesztelve:** Aspose.Page for .NET (legújabb stabil verzió)  
**Szerző:** Aspose