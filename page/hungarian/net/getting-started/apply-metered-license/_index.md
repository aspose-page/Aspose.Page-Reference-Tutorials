---
title: Alkalmazza a mért licencet az Aspose.Page segítségével .NET-hez
linktitle: Alkalmazza a mért licencet
second_title: Aspose.Page .NET API
description: Fedezze fel az Aspose.Page .NET-hez való zökkenőmentes integrációját ezzel a lépésről-lépésre szóló útmutatóval a korlátos licencek alkalmazásáról. Optimalizálja a dokumentumfeldolgozást könnyedén.
type: docs
weight: 10
url: /hu/net/getting-started/apply-metered-license/
---
## Bevezetés

Kihasználja az Aspose.Page teljes potenciálját .NET-hez egy mért licenc alkalmazásával. Ez az oktatóanyag végigvezeti a mért licenc beállításának és alkalmazásának folyamatán, biztosítva ennek a nagy teljesítményű .NET-könyvtárnak a zökkenőmentes és optimalizált használatát.

## Előfeltételek

Mielőtt belevágna a lépésekbe, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

-  Érvényes Aspose.Page .NET-licenchez: beszerezheti innen[buy.aspose.com](https://purchase.aspose.com/buy).
-  Aspose.Page könyvtár telepítve: Lásd a[dokumentáció](https://reference.aspose.com/page/net/) telepítési utasításokért.
- .NET fejlesztői környezet: Győződjön meg arról, hogy működő .NET környezet van beállítva a gépen.

## Névterek importálása

A .NET-projektben importálja a szükséges névtereket az Aspose.Page funkciók eléréséhez:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

## 1. lépés: Állítsa be a mért nyilvános és privát kulcsokat

 Inicializálja a`Aspose.Page.Metered` osztályba, és állítsa be a mért nyilvános és privát kulcsokat. Cserélje ki`<type public key here>` és`<type private key here>` a valódi kulcsaiddal.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

## 2. lépés: Töltse be az EPS-fájlt és hozzon létre dokumentumot

 Adja meg az EPS-fájl elérési útját, és hozzon létre egy adatfolyamot a tartalmának olvasásához. Ezután hozzon létre egy példányt a`PsDocument` osztály a patakból.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## 3. lépés: Konvertálja az EPS-t PNG képpé

 Hozzon létre egy`ImageDevice` az EPS fájl PNG képpé konvertálásához. Mentse az EPS fájlt képként a`ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

## 4. lépés: Töltse le a képbájtokat

Szerezze meg a kép bájtjait, ahol minden bájttömb egy oldalt jelent. Ebben az esetben egy oldalunk van.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

## 5. lépés: Mentse a képbájtokat fájlba

Mentse el a kép bájtjait egy fájlba, így biztosítva a sikeres konvertálást EPS-ről PNG-re.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

## 6. lépés: Ellenőrizze a mért licencet

Vizuálisan ellenőrizze, hogy a mért licencet sikeresen alkalmazta-e. Ha az eredményül kapott kép nem tartalmazza a piros értékelő üzenetet, az azt jelzi, hogy a mért licencet probléma nélkül alkalmazták.

Most már készen áll, hogy kihasználja az Aspose.Page for .NET teljes képességét egy mért licenccel!

## Következtetés

Ez a részletes útmutató felvértezi Önt azokkal a tudással, amelyek segítségével zökkenőmentesen alkalmazhatja a mért licencet az Aspose.Page for .NET használatával. Növelje dokumentumfeldolgozási képességeit, és fedezze fel a nagy teljesítményű könyvtár által kínált hatalmas szolgáltatásokat.

## GYIK

### 1. kérdés: Hogyan szerezhetek fizetős licencet az Aspose.Page számára .NET-hez?

 A1: Látogassa meg[buy.aspose.com](https://purchase.aspose.com/buy) érvényes engedély megszerzéséhez.

### 2. kérdés: Hol találom az Aspose.Page for .NET dokumentációját?

 A2: Lásd[Aspose.Page .NET](https://reference.aspose.com/page/net/) átfogó dokumentációhoz.

### 3. kérdés: Létezik fórum az Aspose.Page vitáihoz és támogatásához?

 A3: Igen, látogassa meg[fórum](https://forum.aspose.com/c/page/39) kapcsolatba lépni a közösséggel és segítséget kérni.

### 4. kérdés: Kipróbálhatom az Aspose.Page-t .NET-hez a vásárlás előtt?

 A4: Abszolút! Az ingyenes próbaverzió elérése a címen[itt](https://releases.aspose.com/).

### 5. kérdés: Hogyan szerezhetek ideiglenes licencet az Aspose.Page for .NET számára?

 A5: Látogassa meg[ideiglenes engedély/](https://purchase.aspose.com/temporary-license/) ideiglenes engedély megszerzéséhez.