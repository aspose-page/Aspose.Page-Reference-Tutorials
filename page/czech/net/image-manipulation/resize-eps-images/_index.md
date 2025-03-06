---
title: Změna velikosti obrázků EPS pomocí Aspose.Page pro .NET
linktitle: Změna velikosti obrázků EPS
second_title: Aspose.Page .NET API
description: Prozkoumejte bezproblémový proces změny velikosti obrázků EPS v .NET pomocí Aspose.Page. Bez námahy dosáhněte přesnosti v bodech, palcích, milimetrech a procentech.
weight: 11
url: /cs/net/image-manipulation/resize-eps-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Změna velikosti obrázků EPS pomocí Aspose.Page pro .NET

## Úvod

Hledáte bezproblémovou změnu velikosti obrázků EPS pomocí Aspose.Page for .NET? Tento výukový program je vaším komplexním průvodcem, jak bez námahy manipulovat s velikostí obrázků EPS v různých jednotkách, jako jsou body, palce, milimetry a procenta. Aspose.Page for .NET poskytuje výkonnou sadu nástrojů a v tomto tutoriálu vás provedeme procesem krok za krokem.

## Předpoklady

Než se ponoříte do magie změny velikosti, ujistěte se, že máte splněny následující předpoklady:

-  Knihovna Aspose.Page for .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Page for .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/page/net/).

- Adresář dokumentů: Vytvořte adresář, kam budete ukládat vstupní soubor EPS a výstupní soubory se změněnou velikostí.

Nyní, když máte vše nastaveno, přistoupíme k importu potřebných jmenných prostorů a ponoříme se do podrobného průvodce.

## Import jmenných prostorů

Ve svém projektu .NET začněte importem jmenných prostorů nezbytných pro práci s Aspose.Page. Na začátek souboru přidejte následující kód:

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

## Krok 1: Změna velikosti v bodech

Začněme změnou velikosti obrázku EPS v bodech. Body jsou standardní měrnou jednotkou v polygrafickém průmyslu.

```csharp
public static void ResizeInPoints()
{
    // Váš adresář dokumentů
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

## Krok 2: Změna velikosti v palcích

Nyní změňme velikost obrázku EPS v palcích, což je běžná jednotka používaná v grafickém designu.

```csharp
public static void ResizeInInches()
{
    // Váš adresář dokumentů
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

## Krok 3: Změna velikosti v milimetrech

Nyní změňme velikost obrázku EPS v milimetrech, což je další široce používaná jednotka v designu a tisku.

```csharp
public static void ResizeInMillimeters()
{
    // Váš adresář dokumentů
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

## Krok 4: Změna velikosti v procentech

Nakonec změňme velikost obrázku EPS pomocí procent, což poskytuje flexibilní přístup k úpravě velikosti obrázku.

```csharp
public static void ResizeInPercents()
{
    // Váš adresář dokumentů
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

Neváhejte a integrujte tyto metody do svého projektu a velikost obrázků EPS budete bez námahy měnit. Experimentujte s různými jednotkami, abyste dosáhli požadovaných rozměrů.

## Závěr

Gratulujeme! Zvládli jste umění změny velikosti obrázků EPS pomocí Aspose.Page for .NET. Tato výkonná knihovna otevírá svět možností pro manipulaci s vektorovou grafikou. Ať už navrhujete pro tisk nebo digitální média, Aspose.Page vám umožňuje dosáhnout přesných a přizpůsobených výsledků.

## FAQ

### Q1: Mohu změnit velikost více obrázků EPS současně?

Odpověď 1: Ano, můžete procházet kolekcí souborů EPS a odpovídajícím způsobem použít metody změny velikosti.

### Q2: Je Aspose.Page kompatibilní s jinými formáty obrázků?

A2: Aspose.Page se primárně zaměřuje na formáty PostScript a EPS. Pro jiné formáty obrázků zvažte použití Aspose.Imaging.

### Q3: Existují nějaké licenční úvahy pro komerční projekty?

 A3: Ano, ujistěte se, že máte platnou licenci. Návštěva[tady](https://purchase.aspose.com/buy) pro podrobnosti o licencích.

### Q4: Mohu vyzkoušet Aspose.Page před nákupem?

 A4: Rozhodně! Můžete získat bezplatnou zkušební verzi[tady](https://releases.aspose.com/).

### Q5: Kde mohu vyhledat další pomoc nebo prodiskutovat problémy?

 A5: Navštivte[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) spojit se s komunitou a získat pomoc.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
