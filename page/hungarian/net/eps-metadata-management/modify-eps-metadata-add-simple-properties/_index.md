---
title: Egyszerű tulajdonságok hozzáadása a .NET Aspose.Page segítségével
linktitle: Egyszerű tulajdonságok hozzáadása
second_title: Aspose.Page .NET API
description: Javítsa az EPS-fájlokat az Aspose.Page for .NET segítségével. Egyszerű tulajdonságok könnyedén hozzáadhatók a személyre szabott dokumentum-metaadatokhoz.
weight: 14
url: /hu/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Egyszerű tulajdonságok hozzáadása a .NET Aspose.Page segítségével

## Bevezetés

A dokumentumkezelés és -fejlesztés terén az Aspose.Page for .NET hatékony eszközként jelenik meg, amely lehetővé teszi a fejlesztők számára az XMP metaadatok zökkenőmentes hozzáadását és módosítását az EPS-fájlokban. Ez az oktatóanyag végigvezeti az Aspose.Page for .NET segítségével egyszerű tulajdonságok EPS-fájlhoz való hozzáadásának folyamatán.

## Előfeltételek

Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételeket teljesítette:

1.  Aspose.Page for .NET: Győződjön meg arról, hogy az Aspose.Page for .NET telepítve van a fejlesztői környezetében. Ha nem, akkor letöltheti[itt](https://releases.aspose.com/page/net/).

2.  Dokumentumkönyvtár: Állítson be egy könyvtárat az EPS-fájlok tárolására. Frissítse a`dataDir` változót a megadott kódrészletben a dokumentumkönyvtár elérési útjával.

## Névterek importálása

Kezdésként importálja a szükséges névtereket, hogy lehetővé tegye az Aspose.Page for .NET-hez való kommunikációját. Adja hozzá a következő sorokat a kódfájl elejéhez:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## 1. lépés: Inicializálja az EPS fájlbeviteli adatfolyamot

```csharp
// ExStart:1
// A dokumentumok könyvtárának elérési útja.
string dataDir = "Your Document Directory";
// EPS-fájl beviteli adatfolyam inicializálása
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//PsDocument példány létrehozása adatfolyamból
PsDocument document = new PsDocument(psStream);
```

## 2. lépés: Szerezze be az XMP metaadatokat

```csharp
// Szerezze be az XMP metaadatokat. Ha az EPS-fájl nem tartalmaz XMP-metaadatokat, akkor egy újat kapunk, amely tele van a PS-metaadatok megjegyzéseiből származó értékekkel (%%Creator, %%CreateDate, %%Title stb.)
XmpMetadata xmp = document.GetXmpMetadata();
```

## 3. lépés: Az XMP metaadatértékek módosítása

```csharp
// Az XMP metaadatok értékeinek módosítása
DateTime now = DateTime.UtcNow;

// Integer tulajdonság hozzáadása
xmp.Add("xmp:Intg1", new XmpValue(111));

// Adja hozzá a DateTime tulajdonságot
xmp.Add("xmp:Date1", new XmpValue(now));

// Dupla tulajdonság hozzáadása
xmp.Add("xmp:Double1", new XmpValue(111.11D));

//String tulajdonság hozzáadása
xmp.Add("xmp:String1", new XmpValue("ABC"));
```

## 4. lépés: Mentse el az EPS-fájlt módosított XMP-metaadatokkal

```csharp
// Mentse az EPS-fájlt a megváltozott XMP-metaadatokkal

// Kimeneti adatfolyam létrehozása
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_simple_props_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // EPS fájl mentése
    document.Save(outPsStream);
}
```

## 5. lépés: Zárja be a FileStream szolgáltatást

```csharp
finally
{
    psStream.Close();
}
```

Ha követi ezeket a lépéseket, az Aspose.Page for .NET segítségével könnyedén építhet be egyszerű tulajdonságokat az EPS-fájlokba.

## Következtetés

Összefoglalva, az Aspose.Page for .NET felbecsülhetetlen értékű eszköznek bizonyul azon fejlesztők számára, akik az EPS-fájlokat egyéni XMP-metaadatokkal kívánják bővíteni. Egyszerű tulajdonságok hozzáadásával személyre szabhatja és gazdagíthatja dokumentumait, hogy megfeleljenek az egyedi követelményeknek, és ezzel a dokumentumok kezelésének lehetőségeinek világát nyitja meg.

## GYIK

### 1. kérdés: Az Aspose.Page for .NET kompatibilis az összes EPS-fájllal?

1. válasz: Az Aspose.Page for .NET támogatja az EPS-fájlok széles skáláját. A kompatibilitás azonban az egyes fájlok összetettségétől és szerkezetétől függően változhat.

### 2. kérdés: Módosíthatom a meglévő XMP metaadatokat az Aspose.Page for .NET segítségével?

A2: Abszolút! Amint az ebben az oktatóanyagban látható, egyszerűen módosíthatja a meglévő XMP-metaadat-értékeket, vagy újakat adhat hozzá az igényeinek megfelelően.

### 3. kérdés: Vannak-e korlátozások a hozzáadható tulajdonságok típusára vonatkozóan?

3. válasz: Az Aspose.Page for .NET különféle adattípusokat támogat a tulajdonságokhoz, beleértve az egész számokat, dátumokat, kettősöket és karakterláncokat. Rugalmasan választhatja ki a metaadatainak megfelelő típust.

### 4. kérdés: Hogyan szerezhetek technikai támogatást az Aspose.Page for .NET-hez?

 A4: Technikai segítségért keresse fel a[Aspose.Page fórum](https://forum.aspose.com/c/page/39) vagy fedezze fel a[dokumentáció](https://reference.aspose.com/page/net/) átfogó útmutatásért.

### 5. kérdés: Elérhető ingyenes próbaverzió az Aspose.Page számára .NET-hez?

 5. válasz: Igen, hozzáférhet az ingyenes próbaverzióhoz[itt](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
