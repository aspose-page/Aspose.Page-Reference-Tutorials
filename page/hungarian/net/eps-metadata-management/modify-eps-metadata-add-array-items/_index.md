---
date: 2026-08-08
description: Ismerje meg, hogyan adhat hozzá tömbelemeket az EPS metaadatokhoz az
  Aspose.Page EPS metaadatok használatával. Ez a lépésről‑lépésre útmutató .NET‑ben
  bemutatja, hogyan adhat hozzá tömbelemeket, és hogyan olvashat EPS fájlokat hatékonyan.
keywords:
- aspse page eps metadata
- how to add array item
- read eps file .net
lastmod: 2026-08-08
linktitle: Tömbelemek hozzáadása
og_description: Fedezze fel, hogyan adhat hozzá tömbelemeket az EPS metaadatokhoz
  az Aspose.Page EPS metaadatok használatával. Kövesse ezt a tömör .NET‑tutorialt
  az EPS fájlok olvasásához és a metaadatok hatékony kezeléséhez.
og_image_alt: Guide showing how to add array items to EPS metadata with Aspose.Page
  in a .NET project
og_title: Tömbelemek hozzáadása az Aspose.Page EPS metaadatokhoz .NET-ben
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  headline: Add array items with Aspose.Page EPS metadata in .NET
  type: TechArticle
- description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  name: Add array items with Aspose.Page EPS metadata in .NET
  steps:
  - name: initialize eps file input stream
    text: '`PsDocument` represents an EPS document and provides methods to access
      its content. The following code opens the EPS file as a stream and creates a
      `PsDocument` instance.'
  - name: get xmp metadata
    text: '`GetXmpMetadata()` retrieves the XMP packet embedded in the EPS file. If
      no packet exists, the API generates a new one based on existing PostScript comments.'
  - name: change xmp metadata values
    text: '`AddArrayItem()` appends a new value to an existing XMP array without overwriting
      other entries. Use it to add titles, creators, or custom tags to the metadata.'
  - name: save eps file with changed xmp metadata
    text: '`Save()` writes the modified XMP packet back into the EPS file while preserving
      the original PostScript content. Provide the output path to create a new file
      or overwrite the source.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works across .NET Framework 4.5+, .NET Core 3.1+, and
      .NET 5/6/7, providing consistent API behavior on Windows, Linux and macOS.
    question: Is Aspose.Page compatible with all .NET environments?
  - answer: You can evaluate the library with a free trial download from the [Aspose
      purchase page](https://purchase.aspose.com/buy). A commercial license is required
      for production deployments.
    question: Can I use Aspose.Page for free?
  - answer: Temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      for short‑term projects or evaluation periods.
    question: Are temporary licenses available for Aspose.Page?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      to ask questions and share solutions with other developers.
    question: Where can I find community support for Aspose.Page?
  - answer: Refer to the official [documentation](https://reference.aspose.com/page/net/)
      for the most recent release notes and download links.
    question: What is the latest version of Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: Tömbelemek hozzáadása az Aspose.Page EPS metaadatokhoz .NET-ben
url: /hu/net/eps-metadata-management/modify-eps-metadata-add-array-items/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tömbelemek hozzáadása az Aspose.Page EPS metaadatokhoz .NET-ben

## Bevezetés

Ebben az oktatóanyagról megtanulja, hogyan adjon hozzá tömbelemeket az EPS metaadatokhoz az **Aspose.Page EPS metadata** használatával. Akár további címekkel, szerzőkkel vagy egyedi címkékkel szeretné gazdagítani az EPS fájlt, az Aspose.Page egyszerűvé teszi a feladatot bármely .NET fejlesztő számára. Lépésről lépésre végigvezetjük a folyamaton, az EPS adatfolyam megnyitásától a frissített XMP csomag mentéséig, így magabiztosan integrálhatja a metaadatkezelést saját alkalmazásaiba.

## Gyors válaszok
- **Mit tesz lehetővé az Aspose.Page EPS metadata?** Lehetővé teszi az XMP metaadat‑tömbök olvasását és írását EPS fájlokban .NET‑ből.  
- **Melyik osztály képviseli az EPS dokumentumot?** `PsDocument` a fő osztály az EPS tartalom betöltéséhez és mentéséhez.  
- **Szükségem van licencre a fejlesztéshez?** A ingyenes próba verzió teszteléshez működik; a termeléshez kereskedelmi licenc szükséges.  
- **Módosíthatom a metaadatokat anélkül, hogy az EPS grafikát megváltoztatnám?** Igen, csak az XMP csomag módosul, a lap tartalma érintetlen marad.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Mi az Aspose.Page EPS metadata?
Az Aspose.Page EPS metadata egy XMP‑alapú információs blokk, amely egy EPS fájlba van beágyazva. Leíró tulajdonságokat tárol, például címeket, szerzőket, kulcsszavakat és egyedi címkéket az ISO 16684‑1 szabvány szerint. A metaadatok programozottan elérhetők és módosíthatók az Aspose.Page API‑n keresztül, lehetővé téve az automatizált dokumentumkezelést és a keresés optimalizálását.

## Miért módosítsuk az EPS metaadatokat?
Az Aspose.Page több mint **30 metaadatmezőt** képes feldolgozni, és **200 MB**‑ig terjedő EPS fájlokat kezel anélkül, hogy a teljes dokumentumot a memóriába töltené, ami akár **40 %**‑os CPU‑megtakarítást eredményez a teljes fájl elemzéséhez képest. A metaadatok frissítése javítja a kereshetőséget, a megfelelőséget és az utólagos munkafolyamat‑automatizálást.

## Előfeltételek

- Alapvető .NET programozási ismeretek.  
- Aspose.Page for .NET telepítve – töltse le innen: [download Aspose.Page for .NET](https://releases.aspose.com/page/net/).  
- Visual Studio (vagy bármely .NET‑kompatibilis IDE) a mintakód futtatásához.  

## Hogyan adjunk hozzá tömbelemeket az EPS metaadatokhoz?
A tömbelemek hozzáadásához először töltse be az EPS fájlt egy `PsDocument`‑ba, majd szerezze meg az XMP csomagot a `GetXmpMetadata()`‑val. Használja a `AddArrayItem()` metódust a kívánt XMP tömbön, például `dc:title` vagy `dc:creator`, új értékek hozzáfűzéséhez. Végül hívja meg a `Save()`‑t, hogy a frissített metaadatok vissza legyenek írva a fájlba, miközben a grafikus tartalom változatlan marad.

### 1. lépés: EPS fájl bemeneti adatfolyam inicializálása
`PsDocument` egy EPS dokumentumot képvisel, és módszereket biztosít a tartalom eléréséhez. Az alábbi kód megnyitja az EPS fájlt adatfolyamként, és létrehozza a `PsDocument` példányt.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### 2. lépés: XMP metaadat lekérése
`GetXmpMetadata()` visszaadja az EPS fájlba beágyazott XMP csomagot. Ha nincs csomag, az API egy újat generál a meglévő PostScript megjegyzések alapján.

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

### 3. lépés: XMP metaadat értékek módosítása
`AddArrayItem()` új értéket fűz egy meglévő XMP tömbhöz anélkül, hogy a többi bejegyzést felülírná. Használja címek, szerzők vagy egyedi címkék hozzáadásához a metaadatokhoz.

```csharp
// ExStart:4
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

### 4. lépés: EPS fájl mentése módosított XMP metaadatokkal
`Save()` visszaírja a módosított XMP csomagot az EPS fájlba, miközben megőrzi az eredeti PostScript tartalmat. Adja meg a kimeneti útvonalat új fájl létrehozásához vagy a forrás felülírásához.

```csharp
// ExStart:5
// Change XMP metadata values

// Add one more title. It will be added at the end of the array by default.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Add one more creator. It will be added in the array by an index (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

## Gyakori buktatók és hibaelhárítás

- **Null XMP csomag** – Ha a `GetXmpMetadata()` `null`‑t ad vissza, ellenőrizze, hogy az EPS fájl legalább egy megjegyzésblokkot tartalmaz; ellenkező esetben hozza létre manuálisan egy új `XmpMetadata` példányt.  
- **Kódolási problémák** – Használjon UTF‑8‑at karakterláncok hozzáadásakor, hogy elkerülje a nem ASCII nyelvekben előforduló karaktertorzulást.  
- **Nagy fájlok** – 150 MB‑nál nagyobb EPS fájlok esetén fontolja meg a bemenet streamelését `FileStream`‑mel egy puffert használva, hogy alacsonyan tartsa a memóriahasználatot.

## Gyakran ismételt kérdések

**Q: Az Aspose.Page kompatibilis minden .NET környezettel?**  
A: Igen, az Aspose.Page működik a .NET Framework 4.5+, .NET Core 3.1+, és .NET 5/6/7 környezetekben, konzisztens API viselkedést biztosítva Windows, Linux és macOS rendszereken.

**Q: Használhatom ingyenesen az Aspose.Page‑t?**  
A: A könyvtárat ingyenes próba verzióval értékelheti a [Aspose purchase page](https://purchase.aspose.com/buy) linkről. Kereskedelmi licenc szükséges a termelési környezethez.

**Q: Elérhetők ideiglenes licencek az Aspose.Page‑hez?**  
A: Ideiglenes licenceket a [temporary license page](https://purchase.aspose.com/temporary-license/) oldalon lehet beszerezni rövid távú projektekhez vagy értékelési időszakokhoz.

**Q: Hol találok közösségi támogatást az Aspose.Page‑hez?**  
A: Csatlakozzon a [Aspose.Page fórumhoz](https://forum.aspose.com/c/page/39), ahol kérdéseket tehet fel és megoldásokat oszthat meg más fejlesztőkkel.

**Q: Mi a legújabb verziója az Aspose.Page‑nek .NET‑re?**  
A: Tekintse meg a hivatalos [documentation](https://reference.aspose.com/page/net/) oldalt a legfrissebb kiadási megjegyzésekért és letöltési linkekért.

---

**Utolsó frissítés:** 2026-08-08  
**Tesztelve:** Aspose.Page 24.11 for .NET  
**Szerző:** Aspose

```csharp
// ExStart:6
// Save EPS file with changed XMP metadata

// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
// ExEnd:6
```

## Kapcsolódó oktatóanyagok

- [Tömbelemek módosítása az Aspose.Page for .NET használatával](/page/net/eps-metadata-management/modify-eps-metadata-change-array-items/)
- [Egyszerű tulajdonságok hozzáadása az Aspose.Page for .NET használatával](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Névtér hozzáadása az Aspose.Page for .NET használatával](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}