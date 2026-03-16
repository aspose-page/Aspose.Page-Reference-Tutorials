---
date: 2026-03-16
description: Naučte se, jak ořezávat EPS obrázky a měnit velikost EPS souborů v .NET
  pomocí Aspose.Page. Postupujte podle tohoto krok‑za‑krokem průvodce a snadno ořízněte
  EPS a změňte jeho velikost.
linktitle: Crop EPS Images
second_title: Aspose.Page .NET API
title: Jak oříznout EPS obrázky pomocí Aspose.Page pro .NET
url: /cs/net/image-manipulation/crop-eps-images/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak oříznout EPS obrázky pomocí Aspose.Page pro .NET

## Úvod

Pokud potřebujete vědět **jak oříznout EPS** obrázky v .NET aplikaci, jste na správném místě. V tomto tutoriálu vás provedeme ořezáváním a změnou velikosti EPS souborů pomocí výkonné knihovny Aspose.Page pro .NET. Ať už vylepšujete nástroj pro reportování nebo připravujete grafiku pro webovou službu, zvládnutí této techniky vám ušetří čas a poskytne pixel‑dokonalé výsledky.

## Rychlé odpovědi
- **Jaká knihovna zpracovává ořezávání EPS?** Aspose.Page for .NET  
- **Primární metoda?** `doc.CropEps(outputStream, newBoundingBox)`  
- **Mohu také změnit velikost EPS?** Ano – použijte `ResizeEps` s palci, milimetry nebo procenty.  
- **Požadavky?** .NET (Framework 4.5+ / .NET Core 3.1+), nainstalovaný Aspose.Page, EPS soubor.  
- **Typická doba implementace?** Přibližně 10 minut pro základní workflow ořezání‑a‑změny velikosti.

## Požadavky

Než se ponoříte do kódu, ujistěte se, že máte:

- Znalost vývoje v .NET.  
- Knihovnu Aspose.Page pro .NET nainstalovanou. Pokud ne, můžete ji stáhnout [zde](https://releases.aspose.com/page/net/).  
- Ukázkový EPS obrázek (nahraďte `"input.eps"` v kódu vaším skutečným souborem).

## Importování jmenných prostorů

Začněme importováním jmenných prostorů, které nám poskytují přístup ke třídám pro práci s EPS.

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

## Jak oříznout EPS obrázky – krok za krokem průvodce

### Krok 1: Inicializace `PsDocument`

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

Vytvoříme instanci `PsDocument` ze vstupního EPS proudu. Tento objekt představuje EPS soubor v paměti a poskytuje přístup k metodám ořezávání a změny velikosti.

### Krok 2: Získání původního ohraničujícího rámečku

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

Ohraničující rámeček udává aktuální rozměry EPS plátna. Znalost těchto hodnot vám pomůže definovat bezpečný ořezávací obdélník.

### Krok 3: Vytvoření výstupního proudu

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

Otevřeme zapisovatelný proud, kam bude oříznutý EPS uložen. Použití bloku `using` zaručuje, že proud bude řádně uzavřen.

### Krok 4: Definování nového ohraničujícího rámečku

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

Nahraďte čísla souřadnicemi, které chcete zachovat. Ujistěte se, že nové hodnoty zůstávají uvnitř původního ohraničujícího rámečku; jinak operace selže.

### Krok 5: Oříznutí a uložení EPS

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

Tento jediný řádek provede ořez a zapíše výsledek do `output_crop.eps`. Metoda upravuje dokument v paměti, takže můžete v případě potřeby řetězit další operace.

## Změna velikosti EPS obrázku

Po oříznutí často chcete změnit velikost EPS pro zobrazení nebo tisk. Aspose.Page podporuje tři jednotky měření.

### Změna velikosti v palcích

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

### Změna velikosti v milimetrech

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

### Změna velikosti v procentech

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

Každé volání přepíše předchozí výstup, takže pokud potřebujete samostatné soubory pro každou velikost, vytvořte nový proud.

## Časté problémy a řešení

| Příznak | Pravděpodobná příčina | Oprava |
|---------|-----------------------|--------|
| **Hodnoty ohraničujícího rámečku mimo rozsah** | Nový rámeček překračuje původní rozměry | Ověřte hodnoty `initialBoundingBox` a vyberte souřadnice uvnitř tohoto rozsahu. |
| **Výstupní soubor je prázdný** | Výstupní proud není vyprázdněn nebo uzavřen | Zajistěte, aby blok `using` byl dokončen před přístupem k souboru, nebo zavolejte `outputEpsStream.Flush()`. |
| **Neočekávané škálování** | Míchání jednotek (např. palce vs. milimetry) | Vždy zadejte správný enum `Units`, který odpovídá vašim hodnotám velikosti. |

## Často kladené otázky

### Q1: Mohu použít Aspose.Page pro .NET s jinými formáty obrázků?

A1: Aspose.Page se primárně zaměřuje na EPS obrázky, ale Aspose poskytuje různé knihovny pro různé formáty. Podívejte se do jejich dokumentace pro konkrétní formáty.

### Q2: Jak mohu získat dočasnou licenci pro Aspose.Page pro .NET?

A2: Navštivte [tento odkaz](https://purchase.aspose.com/temporary-license/) a získejte dočasnou licenci pro testování.

### Q3: Existují nějaká omezení velikosti obrázku, který mohu zpracovat pomocí Aspose.Page pro .NET?

A3: Aspose.Page je navržena tak, aby zvládala obrázky různých velikostí. Výkon se však může lišit v závislosti na složitosti obrázku.

### Q4: Existuje komunitní fórum pro diskuse o Aspose.Page?

A5: Ano, můžete se zapojit do komunity Aspose.Page [zde](https://forum.aspose.com/c/page/39).

### Q5: Kde najdu podrobnou dokumentaci pro Aspose.Page pro .NET?

A5: Odkazujte na dokumentaci [zde](https://reference.aspose.com/page/net/).

---

**Poslední aktualizace:** 2026-03-16  
**Testováno s:** Aspose.Page 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}