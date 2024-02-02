---
title: Oříznutí XPS pomocí Aspose.Page pro .NET
linktitle: Výstřižek XPS
second_title: Aspose.Page .NET API
description: Prozkoumejte sílu Aspose.Page for .NET v tomto podrobném průvodci ořezáváním dokumentů XPS. Vytvářejte, manipulujte a ukládejte soubory XPS bez námahy.
type: docs
weight: 11
url: /cs/net/canvas-manipulation/clippingxps/
---
## Úvod

Vítejte v tomto komplexním tutoriálu o ořezávání XPS pomocí Aspose.Page pro .NET! V této příručce vás provedeme procesem vytváření, manipulace a ukládání dokumentů XPS pomocí Aspose.Page for .NET. XPS nebo XML Paper Specification je standardizovaný a otevřený formát dokumentu a Aspose.Page for .NET poskytuje výkonné nástroje pro práci s dokumenty XPS ve vašich aplikacích .NET.

## Předpoklady

Než se pustíme do výukového programu, ujistěte se, že máte následující předpoklady:

- Visual Studio nainstalované na vašem počítači.
-  Knihovna Aspose.Page for .NET byla přidána do vašeho projektu. Můžete si jej stáhnout[tady](https://releases.aspose.com/page/net/).
- Základní znalost programovacího jazyka C#.

## Import jmenných prostorů

Abyste mohli používat funkce Aspose.Page for .NET, musíte do svého projektu importovat požadované jmenné prostory. Následuj tyto kroky:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Nyní si rozeberme příklad kódu, který jste poskytli, do několika kroků.

## Krok 1: Nastavte cestu k adresáři dokumentu.

```csharp
string dataDir = "Your Document Directory";
```

Ujistěte se, že jste nahradili "Your Document Directory" skutečnou cestou k vašemu adresáři dokumentů.

## Krok 2: Vytvořte nový dokument XPS.

```csharp
XpsDocument doc = new XpsDocument();
```

Tím se vytvoří nový dokument XPS, se kterým budete pracovat.

## Krok 3: Vytvořte hlavní plátno.

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

Tento krok vytvoří hlavní plátno, které je společné pro všechny prvky stránky.

## Krok 4: Nastavte odsazení vlevo a nahoře na hlavním plátně.

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

Upravte levé a horní odsazení podle svých požadavků.

## Krok 5: Vytvořte obdélníkovou geometrii cesty.

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

Tím se vytvoří geometrie cesty pro obdélník.

## Krok 6: Vytvořte výplň pro obdélníky.

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

Definujte barvu výplně pro obdélníky.

## Krok 7: Přidejte další plátno s klipem na hlavní plátno.

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

Tento krok přidá k hlavnímu plátnu další plátno.

## Krok 8: Vytvořte geometrii kruhu pro klip.

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

Tím se vytvoří kruhová geometrie klipu a použije se na druhé plátno.

## Krok 9: Na druhém plátně vytvořte obdélník a vyplňte jej.

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Tento krok vytvoří na druhém plátně obdélník a vyplní ho.

## Krok 10: Přidejte druhé plátno s vytaženým obdélníkem na hlavní plátno.

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

Tím se k hlavnímu plátnu přidá další plátno.

## Krok 11: Vytvořte obdélník ve třetím plátně a potáhněte ho.

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

Tím se ve třetím plátně vytvoří obdélník a aplikuje se na něj tah.

## Krok 12: Uložte výsledný dokument XPS.

```csharp
doc.Save(dataDir + "output2.xps");
```

Tím se dokument XPS uloží do určeného adresáře.

## Závěr

Gratulujeme! Úspěšně jste se naučili, jak oříznout XPS pomocí Aspose.Page for .NET. Tato příručka poskytla podrobný návod kroků zahrnutých do procesu.

## FAQ

### Q1: Mohu použít Aspose.Page pro .NET s jinými formáty dokumentů?

A1: Aspose.Page for .NET se primárně zaměřuje na dokumenty XPS, ale Aspose poskytuje další knihovny pro různé formáty dokumentů.

### Q2: Je Aspose.Page for .NET vhodný pro začátečníky?

Odpověď 2: Ano, Aspose.Page for .NET je navržen tak, aby byl uživatelsky přívětivý a začátečníci mohou rychle pochopit jeho funkce pomocí správné dokumentace.

### Q3: Kde najdu další příklady a zdroje?

 A3: Navštivte[dokumentace](https://reference.aspose.com/page/net/) a[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) pro rozsáhlé zdroje a příklady.

### Q4: Jak mohu získat dočasnou licenci pro Aspose.Page for .NET?

 A4: Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).

### Q5: Je k dispozici bezplatná zkušební verze pro Aspose.Page pro .NET?

 A5: Ano, můžete prozkoumat bezplatnou zkušební verzi[tady](https://releases.aspose.com/).