---
title: Adja hozzá a Circle Ellipse-t a PostScript-hez (PS) az Aspose.Page segítségével
linktitle: Körellipszis hozzáadása a PostScript-hez (PS)
second_title: Aspose.Page .NET API
description: Ismerje meg, hogyan adhat hozzá könnyedén körellipsziseket PostScript (PS) dokumentumokhoz az Aspose.Page for .NET használatával. Kövesse lépésenkénti útmutatónkat a zökkenőmentes integráció érdekében.
weight: 10
url: /hu/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adja hozzá a Circle Ellipse-t a PostScript-hez (PS) az Aspose.Page segítségével

## Bevezetés

Üdvözöljük ebben az átfogó oktatóanyagban, amely a PostScript (PS) dokumentumokhoz körellipszisek hozzáadásával foglalkozik az Aspose.Page for .NET használatával. Az Aspose.Page egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy zökkenőmentesen dolgozzanak PostScript- és más dokumentumformátumokkal. Ebben az útmutatóban végigvezetjük a kör ellipszisek PS-dokumentumaiba való könnyű beépítésének folyamatán.

## Előfeltételek

Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

1.  Aspose.Page for .NET Library: Töltse le és telepítse az Aspose.Page for .NET könyvtárat innen:[itt](https://releases.aspose.com/page/net/).

2. Fejlesztői környezet: Győződjön meg arról, hogy működő .NET fejlesztői környezet van beállítva a gépén.

Most pedig kezdjük a lépésről lépésre bemutatott útmutatóval.

## Névterek importálása

Első lépésben importálnia kell a szükséges névtereket, hogy elérhetővé tegye az Aspose.Page funkciót a kódban.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Most bontsuk fel a példát több lépésre, amelyek végigvezetik Önt a körellipszisek PostScript-dokumentumhoz való hozzáadásának folyamatán.

## 1. lépés: Állítsa be a dokumentumkönyvtárat

```csharp
// ExStart:1
// A dokumentumok könyvtárának elérési útja.
string dataDir = "Your Document Directory";
```

Győződjön meg arról, hogy a „Saját dokumentumkönyvtár” helyett a dokumentumkönyvtár tényleges elérési útja szerepel.

## 2. lépés: Hozzon létre kimeneti adatfolyamot a PostScript-dokumentumhoz

```csharp
//Kimeneti adatfolyam létrehozása PostScript-dokumentumhoz
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

Itt egy FileStream jön létre a PostScript-dokumentum írásához, és a fájlmód úgy van beállítva, hogy új fájlt hozzon létre.

## 3. lépés: Hozzon létre mentési opciókat és PS-dokumentumot

```csharp
//Hozzon létre mentési beállításokat A4-es méretben
PsSaveOptions options = new PsSaveOptions();

// Hozzon létre új 1 oldalas PS-dokumentumot
PsDocument document = new PsDocument(outPsStream, options, false);
```

Ez a lépés magában foglalja az A4-es méretű mentési beállítások létrehozását és egy új, egyoldalas PS-dokumentum inicializálását.

## 4. lépés: Hozzon létre grafikus útvonalat az első ellipszishez

```csharp
//Grafikus útvonal létrehozása az első ellipszisből
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

Az első ellipszishez létrejön egy grafikus útvonal, megadva annak helyzetét és méreteit.

## 5. lépés: Állítsa be a festéket és töltse ki az ellipszist

```csharp
//Állítsa be a festéket
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//Töltse ki az ellipszist
document.Fill(path);
```

Itt a festék be van állítva, és az első ellipszis meg van töltve a megadott színnel.

## 6. lépés: Hozzon létre grafikus útvonalat a második ellipszishez

```csharp
//Hozzon létre grafikus útvonalat a második ellipszisből
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

Hasonlóképpen a második ellipszishez grafikus útvonalat készítenek, amely meghatározza annak helyzetét és méreteit.

## 7. lépés: Állítsa be a körvonalat és rajzolja meg az ellipszist

```csharp
//Állítsa be a löketet
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//Az ellipszist körvonalazzuk (vázoljuk).
document.Draw(path);
```

Ebben a lépésben beállítja a körvonalat, és a második ellipszis körvonalait a megadott színnel és vonalvastagsággal körvonalazza.

## 8. lépés: Zárja be az aktuális oldalt, és mentse el a dokumentumot

```csharp
//Az aktuális oldal bezárása
document.ClosePage();

//Mentse el a dokumentumot
document.Save();
```

Végül az aktuális oldal bezárul, és a teljes dokumentum mentésre kerül, ezzel befejezve a folyamatot.

## Következtetés

Gratulálunk! Sikeresen megtanulta, hogyan kell körellipsziseket hozzáadni PostScript-dokumentumokhoz az Aspose.Page for .NET használatával. Ez az oktatóanyag egy részletes, lépésről lépésre haladó útmutatót tartalmaz, amely segít zökkenőmentesen integrálni ezt a funkciót a projektekbe.

## GYIK

### 1. kérdés: Használhatom az Aspose.Page for .NET oldalt más dokumentumformátumokkal?

 1. válasz: Az Aspose.Page elsősorban a PostScript-re összpontosít, de az Aspose más könyvtárakat is kínál különféle dokumentumformátumokhoz. Ellenőrizd a[Aspose dokumentáció](https://reference.aspose.com/page/net/) további részletekért.

### 2. kérdés: Hol találhatok további támogatást és közösségi megbeszéléseket?

 A2: Látogassa meg a[Aspose.Page fórum](https://forum.aspose.com/c/page/39) közösségi megbeszélésekre és támogatásra.

### 3. kérdés: Elérhető ingyenes próbaverzió az Aspose.Page számára .NET-hez?

 V3: Igen, hozzáférhet a[ingyenes próbaverzió](https://releases.aspose.com/)az Aspose.Page for .NET szolgáltatásainak felfedezéséhez.

### 4. kérdés: Hogyan szerezhetek ideiglenes licencet az Aspose.Page számára?

 V4: Szerezzen ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/) tesztelési és értékelési célokra.

### 5. kérdés: Hol vásárolhatom meg az Aspose.Page-t .NET-hez?

 5. válasz: Vásárolja meg az Aspose.Page oldalt a .NET számára a webhelyről[oldal vásárlása](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
