---
date: 2026-01-20
description: Könnyedén adjon hozzá oldalszámokat a PDF-hez, miközben XPS dokumentumokat
  egyesít magas minőségű PDF-ekbe az Aspose.Page for .NET segítségével. Kövesse lépésről‑lépésre
  útmutatónkat az XPS PDF‑vé konvertálásához.
linktitle: Merge XPS Documents into PDF
second_title: Aspose.Page .NET API
title: Oldalszámok hozzáadása PDF-hez – XPS összevonása PDF-be az Aspose.Page használatával
url: /hu/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Oldalszámok hozzáadása PDF-hez – XPS összevonása PDF-be az Aspose.Page használatával

## Bevezetés

Ha **oldalszámok hozzáadására PDF-hez** van szüksége XPS fájlok összevonása közben, az Aspose.Page for .NET gondtalan megoldást nyújt. Ebben az útmutatóban egy teljes, termelés‑kész példán keresztül mutatjuk be, hogyan konvertálhat egy XPS dokumentumot magas minőségű PDF‑be, hogyan szabályozhatja a képtömörítést, és hogyan szúrhat be automatikusan oldalszámokat a végső PDF‑be. A végére egy újrahasználható kódrészletet kap, amelyet bármely C# projektbe beilleszthet.

## Gyors válaszok
- **Hozzáadhatok oldalszámokhoz XPS PDF‑be való összevonásakor?** Igen – a `PdfSaveOptions.PageNumbers` tulajdonság pontosan ezt teszi.  
- **Melyik könyvtár kezeli a konverziót?** Aspose.Page for .NET.  
- **Szükség van licencre a termelési használathoz?** Érvényes Aspose.Page licenc szükséges; ideiglenes licenc is elérhető teszteléshez.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, valamint .NET 5/6+.  
- **Lehetséges a magas minőségű képkimenet?** Teljesen – állítsa be a `JpegQualityLevel` értékét 100-ra, és válassza a `PdfImageCompression.Jpeg` opciót.

## Előfeltételek

Mielőtt elkezdené a gyakorlati példát, győződjön meg róla, hogy az alábbiak rendelkezésre állnak:

- Aspose.Page for .NET: Győződjön meg róla, hogy az Aspose.Page könyvtár telepítve van. Letöltheti **[innen](https://releases.aspose.com/page/net/)**.  
- Dokumentumfájlok: Legyen a XPS dokumentum (`input.xps`) a megadott könyvtárban.

## Névterek importálása

A .NET projektjében vegye fel a szükséges névtereket az Aspose.Page használatához:

```csharp
using Aspose.Page.XPS;
```

Ez a lépés biztosítja, hogy hozzáférjen a dokumentumkonverzióhoz szükséges osztályokhoz és metódusokhoz.

## Hogyan adjunk hozzá oldalszámokat PDF-hez XPS dokumentumok összevonásakor

A `PdfSaveOptions.PageNumbers` gyűjtemény lehetővé teszi, hogy pontosan megadja, mely oldalak (vagy oldaltartományok) jelenjenek meg a kimeneti PDF‑ben. Ha feltölti a kívánt oldalszámokkal, az Aspose.Page automatikusan beilleszti a megfelelő számozást.

### 1. lépés: Stream-ek inicializálása

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

Ez a lépés az XPS és PDF fájlok bemeneti és kimeneti stream‑jeinek beállítását jelenti. Ügyeljen a helyes útvonalakra és fájlnevekre.

### 2. lépés: XPS dokumentum betöltése

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

Itt betöltjük az XPS dokumentumot az `XpsDocument` objektumba, felkészítve a további feldolgozásra.

### 3. lépés: Mentési beállítások inicializálása (XPS PDF‑be összevonása)

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }   // <-- adds page numbers PDF
};
// ExEnd:5
```

Testreszabhatja a `PdfSaveOptions` objektumot igényei szerint, megadva például a képtömörítést, szövegtömörítést és a **oldalszámokat**, amelyeket a végső PDF‑ben szeretne látni. A `JpegQualityLevel` 100‑ra állítása garantálja a **magas minőségű PDF‑képeket**.

### 4. lépés: Renderelő eszköz létrehozása

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

A `PdfDevice` felelős az XPS dokumentum PDF formátumba történő rendereléséért.

### 5. lépés: Dokumentum mentése (C# XPS PDF‑be)

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

Végül mentse a dokumentumot a renderelő eszközzel és a megadott beállításokkal. A kimeneti PDF a kiválasztott oldalakat tartalmazni fogja automatikusan hozzáadott oldalszámokkal.

## Miért használjuk az Aspose.Page‑t ehhez a konverzióhoz?

- **Megbízhatóság** – Kezeli a komplex XPS funkciókat hűségvesztés nélkül.  
- **Teljesítmény** – Stream‑alapú feldolgozás elkerüli a teljes fájlok memóriába töltését.  
- **Rugalmasság** – Finomhangolt vezérlés a képminőség, tömörítés és oldalszámozás felett.  
- **Keresztplatformos** – Windows, Linux és macOS rendszereken működik .NET Core‑dal.

## Gyakori problémák és megoldások

| Probléma | Megoldás |
|----------|----------|
| **A kimeneti PDF üres** | Ellenőrizze, hogy az XPS fájl útvonala helyes‑e, és a fájl nem sérült. |
| **Az oldalszámok nem jelennek meg** | Győződjön meg róla, hogy a `PageNumbers` a megfelelő null‑alapú oldalindexeket tartalmazza (pl. `new int[] {1,2,6}`). |
| **Alacsony minőségű képek** | Növelje a `JpegQualityLevel` értékét, és válassza a `PdfImageCompression.Jpeg` opciót. |
| **Nagy XPS fájlok memória‑nyomást okoznak** | Dolgozza fel az XPS‑t kisebb darabokban, vagy növelje az alkalmazás memória‑korlátját. |

## Gyakran Ismételt Kérdések

### Q1: Több XPS fájlt összevonhatok egyetlen PDF‑be?

Igen. Egyszerűen állítsa be a `PageNumbers` paramétert a `PdfSaveOptions`‑ban, hogy tartalmazza a kívánt oldalakat a különböző XPS fájlokból, vagy töltse be sorban az egyes XPS‑eket, és hívja meg a `document.Save`‑t ugyanazzal a `PdfDevice`‑del.

### Q2: Elérhető ideiglenes licenc az Aspose.Page for .NET‑hez?

Igen, ideiglenes licencet szerezhet **[itt](https://purchase.aspose.com/temporary-license/)** tesztelési célokra.

### Q3: Vannak korlátozások a fájlméretre az Aspose.Page dokumentumkonverzió során?

Az Aspose.Page for .NET nem szab szigorú méretkorlátot, de a legjobb teljesítmény elérhető ésszerű méretű fájlokkal. Nagyon nagy XPS dokumentumok esetén javasolt stream‑alapú feldolgozást alkalmazni a memóriahasználat csökkentése érdekében.

### Q4: Testreszabhatom a kimeneti PDF‑et, például vízjelek vagy megjegyzések hozzáadásával?

Igen, az Aspose.Page for .NET kiterjedt PDF‑manipulációs funkciókat kínál. A konverzió után használhatja az Aspose.PDF könyvtárat vízjelek, megjegyzések vagy egyéb kiegészítések hozzáadásához.

### Q5: Támogatja az Aspose.Page for .NET a keresztplatformos fejlesztést?

Igen, az Aspose.Page for .NET úgy lett tervezve, hogy zökkenőmentesen működjön különböző platformokon, beleértve a Windows, Linux és macOS rendszereket, ha .NET Core‑dal vagy .NET 5/6‑tal használják.

**Last Updated:** 2026-01-20  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}