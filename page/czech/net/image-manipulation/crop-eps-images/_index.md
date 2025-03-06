---
title: Oříznout obrázky EPS pomocí Aspose.Page pro .NET
linktitle: Oříznout obrázky EPS
second_title: Aspose.Page .NET API
description: Prozkoumejte bezproblémový svět manipulace s obrázky EPS v .NET pomocí Aspose.Page. Bez námahy ořízněte a změňte velikost obrázků pro úžasné výsledky.
weight: 10
url: /cs/net/image-manipulation/crop-eps-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Oříznout obrázky EPS pomocí Aspose.Page pro .NET

## Úvod

Potýkáte se s manipulací s obrázky EPS ve svých aplikacích .NET? Už nehledejte! V tomto tutoriálu vás provedeme procesem oříznutí obrázků EPS pomocí výkonné knihovny Aspose.Page for .NET. Ať už jste zkušený vývojář nebo teprve začínáte, tento podrobný průvodce vám pomůže dosáhnout přesného oříznutí obrázku bez námahy.

## Předpoklady

Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:

- Pracovní znalost vývoje .NET.
-  Nainstalovaná knihovna Aspose.Page for .NET. Pokud ne, můžete si jej stáhnout[tady](https://releases.aspose.com/page/net/).
- Ukázkový obrázek EPS (nahraďte "input.eps" v kódu skutečným souborem).

## Import jmenných prostorů

Začněme importem potřebných jmenných prostorů, aby náš kód fungoval hladce. 

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

Nyní si tutoriál rozdělíme do několika kroků.

## Krok 1: Inicializujte PsDocument

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

 Inicializovat a`PsDocument` objekt se vstupním tokem EPS.

## Krok 2: Vytáhněte ohraničovací rámeček

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

Načtěte počáteční ohraničovací rámeček obrázku EPS.

## Krok 3: Vytvořte výstupní proud

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

Vytvořte výstupní proud pro oříznutý obrázek EPS.

## Krok 4: Definujte nový ohraničující rámeček

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

Definujte nový ohraničovací rámeček pro oříznutí. Ujistěte se, že nové hodnoty jsou v rámci počátečního ohraničovacího rámečku.

## Krok 5: Ořízněte a uložte

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

Ořízněte obrázek EPS pomocí nového ohraničovacího rámečku a uložte jej do výstupního proudu.

Opakujte tyto kroky pro různé scénáře změny velikosti.

## Změna velikosti obrázků EPS

### Změna velikosti v palcích

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

Změňte velikost obrázku EPS a uložte jej se zadanými rozměry v palcích.

### Změna velikosti v milimetrech

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

Změňte velikost obrázku EPS a uložte jej se zadanými rozměry v milimetrech.

### Změna velikosti v procentech

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

Změňte velikost obrázku EPS a uložte jej se zadanými rozměry v procentech.

## Závěr

Gratulujeme! Úspěšně jste se naučili, jak oříznout a změnit velikost obrázků EPS pomocí Aspose.Page for .NET. Nyní vylepšete své možnosti manipulace s obrázky a posuňte své aplikace .NET na další úroveň.

## Nejčastější dotazy

### Q1: Mohu použít Aspose.Page pro .NET s jinými formáty obrázků?

A1: Aspose.Page se primárně zaměřuje na obrázky EPS, ale Aspose poskytuje různé knihovny pro různé formáty. Zkontrolujte jejich dokumentaci pro konkrétní formáty.

### Q2: Jak mohu získat dočasnou licenci pro Aspose.Page for .NET?

 A2: Návštěva[tento odkaz](https://purchase.aspose.com/temporary-license/) získat dočasnou licenci pro testování.

### Otázka 3: Existují nějaká omezení velikosti obrázku, který mohu zpracovat pomocí Aspose.Page for .NET?

A3: Aspose.Page je navržen tak, aby zpracovával obrázky různých velikostí. Výkon se však může lišit v závislosti na složitosti obrázku.

### Q4: Existuje komunitní fórum pro diskuse Aspose.Page?

 A4: Ano, můžete se zapojit do komunity Aspose.Page[tady](https://forum.aspose.com/c/page/39).

### Q5: Kde najdu podrobnou dokumentaci pro Aspose.Page for .NET?

 A5: Viz dokumentace[tady](https://reference.aspose.com/page/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
