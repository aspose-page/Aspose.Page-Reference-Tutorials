---
title: Použít měřenou licenci s Aspose.Page pro .NET
linktitle: Použít měřenou licenci
second_title: Aspose.Page .NET API
description: Prozkoumejte bezproblémovou integraci Aspose.Page for .NET pomocí tohoto podrobného průvodce aplikací měřené licence. Optimalizujte zpracování dokumentů bez námahy.
weight: 10
url: /cs/net/getting-started/apply-metered-license/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Použít měřenou licenci s Aspose.Page pro .NET

## Úvod

Odemkněte plný potenciál Aspose.Page for .NET použitím měřené licence. Tento tutoriál vás provede procesem nastavení a použití měřené licence a zajistí hladké a optimalizované používání této výkonné knihovny .NET.

## Předpoklady

Než se pustíte do kroků, ujistěte se, že máte splněny následující předpoklady:

-  Platná licence Aspose.Page for .NET: Můžete ji získat z[buy.aspose.com](https://purchase.aspose.com/buy).
-  Nainstalovaná knihovna Aspose.Page: Viz[dokumentace](https://reference.aspose.com/page/net/) pro pokyny k instalaci.
- Vývojové prostředí .NET: Ujistěte se, že máte na svém počítači nastaveno funkční prostředí .NET.

## Import jmenných prostorů

Ve svém projektu .NET importujte potřebné jmenné prostory pro přístup k funkcím Aspose.Page:

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

## Krok 1: Nastavte měřený veřejný a soukromý klíč

 Inicializujte`Aspose.Page.Metered` třídy a nastavte měřené veřejné a soukromé klíče. Nahradit`<type public key here>` a`<type private key here>` se svými skutečnými klíči.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

## Krok 2: Načtěte soubor EPS a vytvořte dokument

 Zadejte cestu k souboru EPS a vytvořte stream pro čtení jeho obsahu. Poté vytvořte instanci souboru`PsDocument` třídy ze streamu.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Krok 3: Převeďte obrázek EPS na obrázek PNG

 Vytvořit`ImageDevice` pro převod souboru EPS na obrázek PNG. Uložte soubor EPS jako obrázek pomocí`ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

## Krok 4: Načtení bajtů obrázku

Získejte bajty obrázku, kde každé pole bajtů představuje jednu stránku. V tomto případě máme jednu stránku.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

## Krok 5: Uložte bajty obrázku do souboru

Uložte bajty obrázku do souboru, čímž zajistíte úspěšnou konverzi z EPS do PNG.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

## Krok 6: Ověřte měřenou licenci

Vizuálně zkontrolujte, zda byla měřená licence úspěšně aplikována. Pokud výsledný obrázek neobsahuje červenou hodnotící zprávu, znamená to, že měřená licence je aplikována bez problémů.

Nyní jste připraveni využít plné schopnosti Aspose.Page for .NET s měřenou licencí!

## Závěr

Tento podrobný průvodce vás vybavil znalostmi pro bezproblémové použití měřené licence pomocí Aspose.Page for .NET. Vylepšete své možnosti zpracování dokumentů a prozkoumejte rozsáhlé funkce, které tato výkonná knihovna nabízí.

## FAQ

### Q1: Jak získám měřenou licenci pro Aspose.Page for .NET?

 A1: Návštěva[buy.aspose.com](https://purchase.aspose.com/buy) získat platnou licenci.

### Q2: Kde najdu dokumentaci pro Aspose.Page for .NET?

 A2: Viz[Aspose.Page .NET](https://reference.aspose.com/page/net/) pro komplexní dokumentaci.

### Q3: Existuje fórum pro diskuse a podporu Aspose.Page?

 A3: Ano, navštivte[Fórum](https://forum.aspose.com/c/page/39) zapojit se do komunity a vyhledat pomoc.

### Q4: Mohu vyzkoušet Aspose.Page for .NET před nákupem?

 A4: Rozhodně! Přístup k bezplatné zkušební verzi na[tady](https://releases.aspose.com/).

### Q5: Jak mohu získat dočasnou licenci pro Aspose.Page for .NET?

 A5: Návštěva[dočasná licence/](https://purchase.aspose.com/temporary-license/) získat dočasnou licenci.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
