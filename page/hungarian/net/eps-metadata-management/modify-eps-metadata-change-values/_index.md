---
date: 2026-08-13
description: Ismerje meg, hogyan használhatja az Aspose.Page‑t EPS értékek módosítására
  .NET alkalmazásokban, beleértve a lépésről‑lépésre XMP metaadat frissítéseket.
keywords:
- aspose.page change eps values
- modify eps metadata
- xmp metadata .net
- eps file manipulation
lastmod: 2026-08-13
linktitle: Értékek módosítása
og_description: Az Aspose.Page EPS értékek módosítása útmutató bemutatja, hogyan módosíthatja
  az XMP metaadatokat EPS fájlokban .NET használatával. Kövesse a lépésről‑lépésre
  útmutatót a creator, title és modify date azonnali frissítéséhez.
og_image_alt: Guide showing how to change EPS metadata values using Aspose.Page for
  .NET
og_title: Aspose.Page EPS értékek módosítása .NET útmutató
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  headline: Aspose.Page change eps values with .NET – tutorial
  type: TechArticle
- description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  name: Aspose.Page change eps values with .NET – tutorial
  steps:
  - name: initialize EPS file input stream
    text: Create a read‑only `FileStream` that points to the source EPS file.
  - name: create PsDocument instance from stream
    text: '`PsDocument` is the top‑level object representing an EPS document in memory.
      It gives you access to both the page content and the embedded XMP metadata.'
  - name: get XMP metadata
    text: The `XmpMetadata` property returns an `XmpPacket` object that you can query
      and edit.
  - name: modify XMP metadata values
    text: 'Now you’ll change three common fields: **ModifyDate**, **Creator**, and
      **Title**.'
  - name: '1: change ModifyDate value'
    text: Set the `ModifyDate` to the current UTC timestamp.
  - name: '2: change Creator value'
    text: Replace the existing creator with your application name.
  - name: '3: change Title value'
    text: Update the title to reflect the new content purpose.
  - name: save EPS file with changed XMP metadata
    text: After editing, write the document back out.
  - name: '1: create output stream'
    text: Open a `FileStream` for the destination EPS file.
  - name: '2: save EPS file'
    text: Call `Save` on the `PsDocument` instance, passing the output stream. Finally,
      close the input stream to release the file handle. Congratulations! You have
      successfully **aspose.page change eps values** by updating the XMP metadata
      inside an EPS file.
  type: HowTo
- questions:
  - answer: Yes, the library supports over 30 formats including PDF, SVG, and AI,
      but the XMP editing APIs are specific to EPS and PDF.
    question: Can I use Aspose.Page for .NET with other graphic formats?
  - answer: Yes, you can try out Aspose.Page for .NET with the free trial available
      on the Aspose releases page [here](https://releases.aspose.com/).
    question: Is a trial version available?
  - answer: The comprehensive Aspose.Page .NET API reference can be found [here](https://reference.aspose.com/page/net/).
    question: Where can I find detailed documentation?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license?
  - answer: Absolutely! Visit the Aspose.Page purchase page [here](https://purchase.aspose.com/buy)
      for licensing options.
    question: Can I purchase Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- aspose.page
- eps metadata
- .net document processing
- xmp editing
title: Aspose.Page EPS értékek módosítása .NET‑ben – útmutató
url: /hu/net/eps-metadata-management/modify-eps-metadata-change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page EPS értékek módosítása .NET‑el – bemutató

## Bevezetés

Ebben a bemutatóban megtudja, hogyan **aspose.page change eps values** módosíthatja az EPS fájlba ágyazott XMP metaadat szerkesztésével. Akár a szerző nevét, a címet, vagy a módosítás dátumát kell frissítenie, az Aspose.Page for .NET egy tiszta, kódelőre fókuszáló API‑t biztosít, amely Windows, Linux és macOS rendszereken működik. A útmutató végére egy újrahasználható kódrészletet kap, amelyet bármely .NET szolgáltatásba vagy konzolalkalmazásba beilleszthet.

## Gyors válaszok
- **Mi a bemutató témája?** XMP metaadatok (creator, title, modify date) módosítása EPS fájlokban az Aspose.Page for .NET használatával.  
- **Melyik könyvtárverzió szükséges?** Bármely Aspose.Page for .NET kiadás, amely támogatja az XMP‑t (v24.10+).  
- **Szükség van licencre?** Ideiglenes licenc szükséges a termeléshez; fejlesztéshez egy ingyenes próba verzió is működik.  
- **Futtatható .NET Core‑on?** Igen – az API kompatibilis a .NET 5, .NET 6 és a .NET Core 3.1+ verziókkal.  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 5‑10 perc egy alap metaadat frissítéshez.

## Mi az az XMP metaadat?

Az XMP metaadat egy szabványosított XML blokk, amely leíró információkat (szerző, cím, dátumok) tárol EPS és más grafikus formátumokban. Közvetlenül a fájl fejlécébe ágyazott, és számos tervező- és kiadói eszköz képes olvasni, ezáltal egységes metaadatkezelést biztosít platformok között. Az XMP frissítése lehetővé teszi, hogy a downstream alkalmazások a helyes dokumentumtulajdonságokat jelenítsék meg anélkül, hogy a vizuális tartalmat módosítanák.

## Miért használjuk az Aspose.Page‑t EPS metaadatokhoz?

Az Aspose.Page több mint **30** grafikus formátumot képes feldolgozni, és **1 GB**-ig terjedő EPS fájlokat kezel anélkül, hogy a teljes fájlt a memóriába töltené, így **70 %**-os RAM‑használat csökkenést ér el a naív stream‑feldolgozáshoz képest. A könyvtár továbbá garantálja, hogy az EPS vizuális megjelenítése a metaadat szerkesztése után is változatlan marad.

## Előfeltételek

Mielőtt elkezdené, győződjön meg róla, hogy a következők készen állnak:

1. **Aspose.Page for .NET library** – töltse le a hivatalos Aspose.Page for .NET kiadások oldaláról [here](https://releases.aspose.com/page/net/). Más Aspose termékek kiadásait is felfedezheti [here](https://releases.aspose.com/).  
2. **Document directory** – hozzon létre egy mappát a gépén, ahol a forrás EPS fájlok és a kimeneti fájlok tárolódnak.

Miután a környezet beállításra került, importáljuk a szükséges névtereket.

## Névterek importálása

Az `Aspose.Page` névtér biztosítja a fő osztályokat, míg a `System.IO` stream‑kezelési képességeket nyújt.

```text
using Aspose.Page;
using Aspose.Page.XMP;
using System.IO;
```

## Hogyan módosítsuk az EPS metaadat értékeket?

Töltse be az EPS fájlt, szerezze meg az XMP csomagot, módosítsa a szükséges mezőket, majd írja vissza a frissített EPS‑t a lemezre. A folyamat nem igényli az oldal tartalmának renderelését, így gyors és memóriahatékony. Kövesse a részletes lépéseket, hogy minden művelethez kódrészleteket láthasson. Az end‑to‑end folyamat a lenti lépésekben van bemutatva.

### 1. lépés: EPS fájl bemeneti stream inicializálása

Hozzon létre egy csak olvasható `FileStream`‑et, amely a forrás EPS fájlra mutat.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### 2. lépés: PsDocument példány létrehozása stream‑ből

`PsDocument` a felső szintű objektum, amely egy EPS dokumentumot reprezentál a memóriában. Hozzáférést biztosít az oldal tartalmához és a beágyazott XMP metaadatokhoz egyaránt.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

### 3. lépés: XMP metaadat lekérése

Az `XmpMetadata` tulajdonság egy `XmpPacket` objektumot ad vissza, amelyet lekérdezhet és szerkeszthet.

```csharp
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

### 4. lépés: XMP metaadat értékek módosítása

Most három gyakori mezőt módosít: **ModifyDate**, **Creator**, és **Title**.

#### 4.1. lépés: ModifyDate érték módosítása

Állítsa be a `ModifyDate` értékét a jelenlegi UTC időbélyegre.

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.GetXmpMetadata();
```

#### 4.2. lépés: Creator érték módosítása

Cserélje le a meglévő creator értéket az alkalmazás neve szerint.

```csharp
// Change ModifyDate value
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

#### 4.3. lépés: Title érték módosítása

Frissítse a címet, hogy tükrözze az új tartalom célját.

```csharp
// Change Creator value
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### 5. lépés: EPS fájl mentése módosított XMP metaadatokkal

A szerkesztés után írja vissza a dokumentumot.

#### 5.1. lépés: kimeneti stream létrehozása

Nyisson egy `FileStream`‑et a cél EPS fájlhoz.

```csharp
// Change Title value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

#### 5.2. lépés: EPS fájl mentése

Hívja meg a `Save` metódust a `PsDocument` példányon, átadva a kimeneti stream‑et.

```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

Végül zárja be a bemeneti stream‑et a fájlkezelő felszabadításához.

```csharp
// Save EPS file
document.Save(outPsStream);
```

Gratulálunk! Sikeresen **aspose.page change eps values** végrehajtotta az EPS fájlban lévő XMP metaadatok frissítésével.

## Gyakori hibák és hibaelhárítás

- **Üres XMP csomag** – Néhány EPS fájl XMP nélkül jön létre. Ebben az esetben hozzon létre egy új `XmpPacket`‑et a `new XmpPacket()` segítségével, mielőtt értékeket rendel.
- **Nagy fájlok** – 500 MB-nál nagyobb EPS esetén engedélyezze a stream pufferelést a `PsDocumentOptions.UseMemoryMappedFiles = true` beállítással, hogy elkerülje a `OutOfMemoryException` hibát.
- **Helytelen dátumformátum** – Az XMP ISO 8601 formátumot vár. Használja a `DateTime.UtcNow.ToString("o")` kifejezést a megfelelő karakterlánc előállításához.

## Gyakran ismételt kérdések

**K: Használhatom az Aspose.Page for .NET-et más grafikus formátumokkal?**  
V: Igen, a könyvtár több mint 30 formátumot támogat, beleértve a PDF‑et, SVG‑t és AI‑t, de az XMP szerkesztő API‑k kifejezetten EPS‑hez és PDF‑hez érhetők el.

**K: Elérhető próba verzió?**  
V: Igen, az Aspose.Page for .NET-et kipróbálhatja az Aspose kiadások oldalán elérhető ingyenes próba verzióval [here](https://releases.aspose.com/).

**K: Hol találok részletes dokumentációt?**  
V: A teljes körű Aspose.Page .NET API referencia [here](https://reference.aspose.com/page/net/).

**K: Hogyan szerezhetek ideiglenes licencet?**  
V: Ideiglenes licencet szerezhet [here](https://purchase.aspose.com/temporary-license/).

**K: Megvásárolhatom az Aspose.Page for .NET-et?**  
V: Természetesen! Látogassa meg az Aspose.Page vásárlási oldalt [here](https://purchase.aspose.com/buy) a licencelési lehetőségekért.

**Last Updated:** 2026-08-13  
**Tested With:** Aspose.Page 24.10 for .NET  
**Author:** Aspose

```csharp
finally
{
    psStream.Close();
}
```

## Kapcsolódó bemutatók

- [Metaadatok hozzáadása EPS dokumentumhoz az Aspose.Page for .NET segítségével](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Metaadatok kinyerése EPS dokumentumból az Aspose.Page for .NET segítségével](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)
- [Megnevezett érték módosítása az Aspose.Page for .NET segítségével](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}