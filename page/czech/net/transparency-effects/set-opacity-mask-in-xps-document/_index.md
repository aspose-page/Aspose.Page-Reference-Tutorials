---
title: Nastavte masku krytí v dokumentu XPS pomocí Aspose.Page pro .NET
linktitle: Nastavte masku krytí v dokumentu XPS
second_title: Aspose.Page .NET API
description: Naučte se nastavit masky krytí v dokumentech XPS pomocí Aspose.Page for .NET. Vylepšete estetiku dokumentu bez námahy.
type: docs
weight: 12
url: /cs/net/transparency-effects/set-opacity-mask-in-xps-document/
---
## Úvod

Masky krytí jsou nezbytné, když chcete vytvářet vizuálně přitažlivé dokumenty s různou úrovní průhlednosti. Aspose.Page for .NET tento proces zjednodušuje a nabízí vývojářům komplexní sadu nástrojů pro vylepšení dokumentů XPS. V tomto tutoriálu prozkoumáme, jak nastavit masku krytí v podrobném průvodci.

## Předpoklady

Než se ponoříte do výukového programu, ujistěte se, že máte následující předpoklady:

-  Aspose.Page for .NET: Ujistěte se, že máte nainstalovanou knihovnu. Pokud ne, můžete si jej stáhnout z[webová stránka](https://releases.aspose.com/page/net/).

- Adresář dokumentů: Nastavte adresář pro ukládání dokumentů XPS.

## Import jmenných prostorů

Ve svém projektu .NET začněte importováním potřebných jmenných prostorů:

```csharp
using Aspose.Page.Xps;
using Aspose.Page.Xps.XpsModel;
using Aspose.Page.Xps.XpsModel.Shapes;
using Aspose.Page.Xps.XpsModel.Text;
using System.Drawing;
```

## Krok 1: Vytvořte nový dokument XPS

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";
// Vytvořte nový dokument XPS
XpsDocument doc = new XpsDocument();
```

Začněte vytvořením nového dokumentu XPS pomocí Aspose.Page for .NET.

## Krok 2: Přidejte plátno do instance XpsDocument

```csharp
// Přidejte plátno do instance XpsDocument
XpsCanvas canvas = doc.AddCanvas();
```

Nyní přidejte plátno k dokumentu XPS. Plátno poslouží jako kontejner pro různé grafické prvky.

## Krok 3: Přidejte obdélník s maskou krytí

```csharp
// Obdélník s neprůhledností maskovaný ImageBrush
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.OpacityMask = doc.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)path.OpacityMask).TileMode = XpsTileMode.Tile;
```

 Přidejte na plátno obdélník a nastavte jeho neprůhlednost pomocí`OpacityMask`vlastnictví. V tomto příkladu používáme jako masku krytí obrázek.

## Krok 4: Uložte výsledný dokument XPS

```csharp
// Uložte výsledný dokument XPS
doc.Save(dataDir + "OpacityMask_out.xps");
```

Nakonec uložte upravený dokument XPS s aplikovanou maskou krytí.

## Závěr

Gratulujeme! Úspěšně jste se naučili, jak nastavit masky krytí v dokumentech XPS pomocí Aspose.Page for .NET. Tato funkce otevírá říši kreativních možností pro navrhování sofistikovaných a vizuálně přitažlivých dokumentů.

## FAQ

### Q1: Mohu použít masky krytí na jiné tvary kromě obdélníků?

Odpověď 1: Ano, Aspose.Page for .NET umožňuje aplikovat masky krytí na různé tvary, včetně kruhů, mnohoúhelníků a vlastních cest.

### Q2: Je maska krytí omezena na obrázky?

Odpověď 2: Ne, zatímco tento kurz používal obrázek jako masku krytí, můžete použít plné barvy, přechody nebo dokonce vzory.

### Otázka 3: Existují pokročilé možnosti pro jemné doladění úrovní krytí?

A3: Absolutně, Aspose.Page for .NET poskytuje podrobnou kontrolu nad nastavením krytí, což vám umožňuje dosáhnout přesných efektů průhlednosti.

### Q4: Mohu použít více masek krytí na jeden prvek?

A4: Ano, můžete navrstvit více masek krytí a vytvořit tak složité efekty průhlednosti.

### Q5: Je Aspose.Page kompatibilní s jinými formáty dokumentů?

A5: Aspose.Page se primárně zaměřuje na dokumenty XPS, ale Aspose poskytuje řadu produktů pro práci s různými formáty.