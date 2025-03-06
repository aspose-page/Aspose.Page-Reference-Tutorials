---
title: Méretezze át az EPS-képeket az Aspose.Page segítségével .NET-hez
linktitle: EPS képek átméretezése
second_title: Aspose.Page .NET API
description: Fedezze fel az EPS-képek átméretezésének zökkenőmentes folyamatát a .NET-ben az Aspose.Page használatával. Pontosan, hüvelykben, milliméterben és százalékban könnyedén elérheti a pontosságot.
weight: 11
url: /hu/net/image-manipulation/resize-eps-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Méretezze át az EPS-képeket az Aspose.Page segítségével .NET-hez

## Bevezetés

Az Aspose.Page for .NET használatával zökkenőmentesen szeretné átméretezni az EPS-képeket? Ez az oktatóanyag átfogó útmutató az EPS-képek méretének könnyű manipulálásához különböző mértékegységekben, például pontokban, hüvelykekben, milliméterekben és százalékokban. Az Aspose.Page for .NET hatékony eszközkészletet kínál, és ebben az oktatóanyagban lépésről lépésre végigvezetjük a folyamaton.

## Előfeltételek

Mielőtt belemerülne az átméretezési varázslatba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

-  Aspose.Page for .NET Library: Győződjön meg arról, hogy az Aspose.Page for .NET könyvtár telepítve van. Letöltheti innen[itt](https://releases.aspose.com/page/net/).

- Dokumentumkönyvtár: Hozzon létre egy könyvtárat, ahol tárolja a bemeneti EPS-fájlt és a kimeneti átméretezett fájlokat.

Most, hogy minden be van állítva, folytassuk a szükséges névterek importálását, és mélyedjünk el a lépésenkénti útmutatóban.

## Névterek importálása

A .NET-projektben kezdje az Aspose.Page használatához szükséges névterek importálásával. Adja hozzá a következő kódot a fájl elejéhez:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

## 1. lépés: Méretezés pontokban

Kezdjük azzal, hogy átméretezzük az EPS-képet pontokban. A pontok szabványos mértékegységek a nyomdaiparban.

```csharp
public static void ResizeInPoints()
{
    // Az Ön dokumentumkönyvtára
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_points.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(oldSize.Width * 2, oldSize.Height * 2), Units.Points);
        }
    }
}
```

## 2. lépés: Átméretezés hüvelykben

Most pedig méretezzünk át egy EPS-képet hüvelykben, amely a grafikai tervezésben használatos mértékegység.

```csharp
public static void ResizeInInches()
{
    // Az Ön dokumentumkönyvtára
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_inches.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
        }
    }
}
```

## 3. lépés: Átméretezés milliméterben

Most pedig méretezzünk át egy EPS-képet milliméterben, ami egy másik széles körben használt egység a tervezésben és a nyomtatásban.

```csharp
public static void ResizeInMillimeters()
{
    // Az Ön dokumentumkönyvtára
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_mms.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
        }
    }
}
```

## 4. lépés: Átméretezés százalékban

Végül méretezzünk át egy EPS-képet százalékos arányokkal, rugalmas megközelítést biztosítva a képméret beállításához.

```csharp
public static void ResizeInPercents()
{
    // Az Ön dokumentumkönyvtára
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_percents.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
        }
    }
}
```

Nyugodtan integrálhatja ezeket a módszereket projektjébe, és könnyedén átméretezheti az EPS-képeket. Kísérletezzen különböző egységekkel a kívánt méretek eléréséhez.

## Következtetés

Gratulálunk! Elsajátította az EPS-képek átméretezésének művészetét az Aspose.Page for .NET segítségével. Ez a nagy teljesítményű könyvtár a lehetőségek világát nyitja meg a vektorgrafikák manipulálására. Akár nyomtatott, akár digitális médiára tervez, az Aspose.Page segítségével precíz és testreszabott eredményeket érhet el.

## GYIK

### 1. kérdés: Átméretezhetek több EPS-képet egyszerre?

1. válasz: Igen, az EPS-fájlok gyűjteményén keresztül folytathatja az átméretezési módszereket.

### 2. kérdés: Az Aspose.Page kompatibilis más képformátumokkal?

2. válasz: Az Aspose.Page elsősorban a PostScript és EPS formátumokra összpontosít. Más képformátumok esetén fontolja meg az Aspose.Imaging használatát.

### 3. kérdés: Vannak-e kereskedelmi projektek engedélyezési szempontjai?

 V3: Igen, győződjön meg arról, hogy rendelkezik érvényes engedéllyel. Látogatás[itt](https://purchase.aspose.com/buy) az engedély részleteiért.

### 4. kérdés: Kipróbálhatom az Aspose.Page oldalt vásárlás előtt?

 A4: Abszolút! Ingyenes próbaverziót kaphat[itt](https://releases.aspose.com/).

### 5. kérdés: Hol kérhetek további segítséget vagy vitathatom meg a problémákat?

 A5: Látogassa meg a[Aspose.Page fórum](https://forum.aspose.com/c/page/39) kapcsolatba lépni a közösséggel és segítséget kapni.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
