---
date: 2026-01-05
description: Naučte se ořezávat XPS dokumenty pomocí Aspose.Page pro .NET. Tento krok‑za‑krokem
  průvodce vám ukáže, jak efektivně vytvářet, manipulovat a ukládat XPS soubory.
linktitle: Clipping XPS
second_title: Aspose.Page .NET API
title: Jak oříznout XPS pomocí Aspose.Page pro .NET
url: /cs/net/canvas-manipulation/clippingxps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak oříznout XPS pomocí Aspose.Page pro .NET

## Úvod

Vítejte v tomto komplexním tutoriálu o **jak oříznout XPS** pomocí Aspose.Page pro .NET! V tomto průvodci vás provede procesem vytváření, manipulace a ukládání XPS dokumentů pomocí knihovny. XPS, neboli XML Paper Specification, je standardizovaný a otevřený formát dokumentů a Aspose.Page pro .NET poskytuje výkonné nástroje pro práci s XPS dokumenty ve vašich .NET aplikacích.

## Rychlé odpovědi
- **Co je ořezávání XPS?** Aplikace geometrické masky (clip) k omezení viditelné oblasti prvků plátna XPS.  
- **Která knihovna je pro to nejlepší?** Aspose.Page pro .NET nabízí plnohodnotné API pro tvorbu a ořezávání XPS.  
- **Požadavky?** Visual Studio, .NET runtime a knihovna Aspose.Page pro .NET.  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní scénář ořezávání.  
- **Mohu to použít v produkci?** Ano, s platnou licencí Aspose (k dispozici zkušební verze).

## Co je “jak oříznout XPS”?
Ořezávání v XPS funguje definováním **clip geometrie** (například kruhu nebo obdélníku) a přiřazením této geometrie k plátnu. Vše, co je nakresleno mimo tuto geometrii, není vykresleno, což vám umožní vytvářet sofistikované rozvržení stránek, jako jsou maskované obrázky, vlastní tvary nebo zaměřené oblasti obsahu.

## Proč použít Aspose.Page pro .NET k oříznutí XPS?
- **Plná kontrola** nad transformacemi plátna, geometrickými cestami a štětci.  
- **Žádné externí závislosti** – vše běží uvnitř vaší .NET aplikace.  
- **Cross‑platform** podpora pro .NET Framework, .NET Core a .NET 5/6+.  
- **Vysoký výkon** s lehkým API, které zapisuje platné XPS soubory.

## Požadavky

Než se pustíme dál, ujistěte se, že máte následující:

- Visual Studio nainstalované na vašem počítači.  
- Knihovna Aspose.Page pro .NET přidána do vašeho projektu. Můžete si ji stáhnout [zde](https://releases.aspose.com/page/net/).  
- Základní znalost programovacího jazyka C#.

## Importování jmenných prostorů

Aby bylo možné využívat funkce Aspose.Page pro .NET, musíte do svého projektu importovat požadované jmenné prostory. Postupujte podle těchto kroků:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Nyní rozdělíme ukázkový kód, který jste poskytli, do několika kroků.

## Krok 1: Nastavte cestu ke složce dokumentu.

```csharp
string dataDir = "Your Document Directory";
```

Ujistěte se, že nahradíte „Your Document Directory“ skutečnou cestou k vaší složce s dokumenty.

## Krok 2: Vytvořte nový XPS dokument.

```csharp
XpsDocument doc = new XpsDocument();
```

Tímto se vytvoří nový XPS dokument, se kterým budete pracovat.

## Krok 3: Vytvořte hlavní plátno.

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

Tento krok vytvoří hlavní plátno, které je společné pro všechny prvky stránky.

## Krok 4: Nastavte levý a horní posun v hlavním plátně.

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

Upravte levý a horní posun podle vašich požadavků.

## Krok 5: Vytvořte geometrický popis obdélníku.

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

Tímto se vytvoří geometrie cesty pro obdélník.

## Krok 6: Vytvořte výplň pro obdélníky.

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

Definujte barvu výplně pro obdélníky.

## Krok 7: Přidejte další plátno s ořezem do hlavního plátna.

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

Tento krok přidá další plátno do hlavního plátna.

## Krok 8: Vytvořte kruhovou geometrii pro ořez.

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

Tímto se vytvoří kruhová clip geometrie a aplikuje se na druhé plátno.

## Krok 9: Vytvořte obdélník ve druhém plátně a vyplňte jej.

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Tento krok vytvoří obdélník ve druhém plátně a vyplní jej.

## Krok 10: Přidejte druhé plátno s obrysem obdélníku do hlavního plátna.

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

Tím se přidá další plátno do hlavního plátna.

## Krok 11: Vytvořte obdélník ve třetím plátně a nakreslete jeho obrys.

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

Tímto se vytvoří obdélník ve třetím plátně a aplikuje se na něj obrys.

## Krok 12: Uložte výsledný XPS dokument.

```csharp
doc.Save(dataDir + "output2.xps");
```

Tím se XPS dokument uloží do určené složky.

## Časté problémy a řešení
- **Neplatná cesta** – Ujistěte se, že `dataDir` končí zpětným lomítkem (`\\`) nebo použijte `Path.Combine`.  
- **Clip není aplikován** – Ověřte, že řetězec clip geometrie je správně vytvořen; chybějící mezera může způsobit, že bude clip ignorován.  
- **Výjimka licence** – V ne‑evaluační verzi přidejte platnou Aspose licenci před vytvořením dokumentu, aby nedošlo k výjimkám za běhu.

## Často kladené otázky

### Q1: Mohu použít Aspose.Page pro .NET s jinými formáty dokumentů?

A1: Aspose.Page pro .NET se primárně zaměřuje na XPS dokumenty, ale Aspose poskytuje další knihovny pro různé formáty dokumentů.

### Q2: Je Aspose.Page pro .NET vhodný pro začátečníky?

A2: Ano, Aspose.Page pro .NET je navržen tak, aby byl uživatelsky přívětivý, a začátečníci si mohou rychle osvojit jeho funkce s odpovídající dokumentací.

### Q3: Kde najdu více příkladů a zdrojů?

A3: Navštivte [dokumentaci](https://reference.aspose.com/page/net/) a [forum Aspose.Page](https://forum.aspose.com/c/page/39) pro rozsáhlé zdroje a příklady.

### Q4: Jak mohu získat dočasnou licenci pro Aspose.Page pro .NET?

A4: Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

### Q5: Je k dispozici bezplatná zkušební verze pro Aspose.Page pro .NET?

A5: Ano, bezplatnou zkušební verzi můžete prozkoumat [zde](https://releases.aspose.com/).

## Další často kladené otázky

**Q: Mohu kombinovat více ořezových geometrií na jednom plátně?**  
A: Ano, můžete přiřadit složitý `PathGeometry`, který obsahuje několik podcest, k vlastnosti `Clip`, což umožňuje vrstvené maskování.

**Q: Ovlivňuje ořezávání konverzi do PDF?**  
A: Při následné konverzi XPS do PDF pomocí Aspose.PDF se geometrie ořezu zachová, takže vizuální výsledek zůstane stejný.

**Q: Je možné animovat ořezávání v XPS?**  
A: XPS samotné nepodporuje animaci; můžete však vygenerovat sérii XPS stránek s různými tvary ořezu pro simulaci pohybu.

---

**Poslední aktualizace:** 2026-01-05  
**Testováno s:** Aspose.Page 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}