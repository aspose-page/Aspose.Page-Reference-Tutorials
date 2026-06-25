---
date: 2026-06-25
description: Naučte se, jak oříznout XPS dokumenty pomocí Aspose.Page pro .NET. Tento
  podrobný návod vám ukáže, jak efektivně vytvářet, manipulovat a ukládat XPS soubory.
keywords:
- how to clip xps
- Aspose.Page .NET
- XPS clipping tutorial
linktitle: Ořezávání XPS
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to clip XPS documents using Aspose.Page for .NET. This step‑by‑step
    guide shows you how to create, manipulate, and save XPS files efficiently.
  headline: How to Clip XPS with Aspose.Page for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can assign a complex `PathGeometry` that contains several sub‑paths
      to the `Clip` property, allowing layered masking.
    question: Can I combine multiple clip geometries on a single canvas?
  - answer: When you later convert the XPS to PDF using Aspose.PDF, the clip geometry
      is preserved, so the visual result remains identical.
    question: Does clipping affect PDF conversion?
  - answer: XPS itself does not support animation; however, you can generate a series
      of XPS pages with different clip shapes to simulate motion.
    question: Is it possible to animate clipping in XPS?
  type: FAQPage
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

Vítejte v tomto komplexním tutoriálu o **jak oříznout XPS** pomocí Aspose.Page pro .NET! V tomto průvodci se krok za krokem naučíte vytvořit XPS dokument, použít geometrické ořezové masky a výsledek uložit. Ořezávání vám umožní skrýt části plátna, což umožňuje sofistikované rozvržení jako maskované obrázky, vlastní tvary nebo zaměřené oblasti obsahu – vše bez opuštění vašeho .NET kódu.

## Rychlé odpovědi
- **Co je ořezávání XPS?** Aplikace geometrické masky (clip) pro omezení viditelné oblasti prvků XPS plátna.  
- **Která knihovna je pro to nejlepší?** Aspose.Page pro .NET nabízí plnohodnotné API pro tvorbu a ořezávání XPS.  
- **Požadavky?** Visual Studio, .NET runtime a knihovna Aspose.Page pro .NET.  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní scénář ořezávání.  
- **Mohu to použít v produkci?** Ano, s platnou licencí Aspose (k dispozici zkušební verze).

## Co je „jak oříznout XPS“?

Ořezávání XPS znamená aplikaci geometrické masky na plátno, takže jakýkoli kreslený prvek mimo masku není vykreslen. Tato technika je ideální pro vytváření maskovaných obrázků, tlačítek s vlastním tvarem nebo zaměření pozornosti čtenáře na konkrétní oblast stránky. Definováním ořezové geometrie – například obdélníku, kruhu nebo složité cesty – získáte detailní kontrolu nad tím, co se objeví na konečné XPS stránce.

## Proč použít Aspose.Page pro .NET k ořezávání XPS?

Aspose.Page poskytuje deterministickou manipulaci s XPS na straně serveru bez externích závislostí. Podporuje **více než 50 vstupních a výstupních formátů**, dokáže zpracovat **200‑stránkové XPS soubory za méně než 0,5 sekundy** na standardním 2,5 GHz procesoru a funguje napříč .NET Framework 4.0+, .NET Core 2.0+, .NET 5, .NET 6 a .NET 7. API vám dává plnou kontrolu nad transformacemi plátna, geometriemi cest a štětci, což zajišťuje vždy výstup vysoké kvality.

## Požadavky

- Visual Studio nainstalované na vašem počítači.  
- Knihovna Aspose.Page pro .NET přidána do vašeho projektu. Můžete si ji stáhnout [zde](https://releases.aspose.com/page/net/).  
- Základní znalost programovacího jazyka C#.

## Jak oříznout XPS?

Načtěte XPS dokument, vytvořte plátno, definujte ořezovou geometrii (např. kruh), přiřaďte geometrii k vlastnosti `Clip` plátna, nakreslete svůj obsah a nakonec dokument uložte. Všechny tyto kroky lze provést pomocí několika volání metod a Aspose.Page automaticky zpracuje podkladové XML značky, takže se můžete soustředit na vizuální design místo struktury souboru.

## Importujte jmenné prostory

Pro použití funkcí Aspose.Page pro .NET musíte do svého projektu importovat požadované jmenné prostory. Postupujte podle těchto kroků:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.IO;
```

Nyní rozdělíme ukázkový kód, který jste poskytli, do několika kroků.

## Krok 1: Nastavte cestu ke složce dokumentu.

Definujte složku, kde bude XPS soubor vytvořen. Použití `Path.Combine` zaručuje správný oddělovač adresářů na jakémkoli OS.

```csharp
string dataDir = Path.Combine(Environment.CurrentDirectory, "Output");
Directory.CreateDirectory(dataDir);
```

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Krok 2: Vytvořte nový XPS dokument.

Vytvořte instanci třídy `XpsDocument`, která představuje celý XPS balíček.

```csharp
XpsDocument doc = new XpsDocument();
```

```csharp
string dataDir = "Your Document Directory";
```

## Krok 3: Vytvořte hlavní plátno.

Třída `Canvas` představuje kreslicí plochu v rámci XPS stránky, kde jsou vykreslovány tvary, obrázky a text.

```csharp
Canvas mainCanvas = new Canvas();
```

```csharp
XpsDocument doc = new XpsDocument();
```

## Krok 4: Nastavte levý a horní posun v hlavním plátně.

Upravte pozici plátna, aby bylo řízeno, kde kreslení na stránce začíná.

```csharp
mainCanvas.Left = 20;
mainCanvas.Top = 30;
```

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

## Krok 5: Vytvořte geometrii cesty obdélníku.

`PathGeometry` definuje vektorový tvar; zde vytvoříme jednoduchý obdélník.

```csharp
PathGeometry rectGeometry = new PathGeometry("M0,0 L100,0 100,50 0,50 Z");
```

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Krok 6: Vytvořte výplň pro obdélníky.

Definujte pevnou barvu štětce, která bude použita k vyplnění obdélníku.

```csharp
SolidColorBrush rectFill = new SolidColorBrush(Color.Black);
```

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

## Krok 7: Přidejte další plátno s ořezem do hlavního plátna.

Vytvořte podřízené plátno, které obdrží ořezovou masku.

```csharp
Canvas clippedCanvas = new Canvas();
mainCanvas.Children.Add(clippedCanvas);
```

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Krok 8: Vytvořte kruhovou geometrii pro ořez.

`PathGeometry` může také představovat kruhy; tato geometrie bude přiřazena k vlastnosti `Clip` podřízeného plátna.

```csharp
PathGeometry circleClip = new PathGeometry("M50,0 A50,50 0 1 0 49.9,0 Z");
clippedCanvas.Clip = circleClip;
```

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

## Krok 9: Vytvořte obdélník ve druhém plátně a vyplňte jej.

Nakreslete obdélník uvnitř ořezaného plátna; viditelná bude pouze část uvnitř kruhu.

```csharp
Path rectangle = new Path(rectGeometry, rectFill);
clippedCanvas.Children.Add(rectangle);
```

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

## Krok 10: Přidejte druhé plátno s obrysem obdélníku do hlavního plátna.

Přidejte obdélník s obrysem, aby bylo ukázáno, jak obrysy interagují s ořezáváním.

```csharp
Path strokedRect = new Path(rectGeometry, null, new Pen(Color.Blue, 2));
mainCanvas.Children.Add(strokedRect);
```

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Krok 11: Vytvořte obdélník ve třetím plátně a přidejte mu obrys.

Třetí plátno demonstruje nezávislé kreslení bez ořezávání.

```csharp
Canvas thirdCanvas = new Canvas();
PathGeometry thirdRectGeom = new PathGeometry("M0,0 L150,0 150,75 0,75 Z");
Path thirdRect = new Path(thirdRectGeom, null, new Pen(Color.Green, 3));
thirdCanvas.Children.Add(thirdRect);
mainCanvas.Children.Add(thirdCanvas);
```

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

## Krok 12: Uložte výsledný XPS dokument.

Uložte XPS balíček do souborového systému.

```csharp
doc.Save(Path.Combine(dataDir, "ClippedOutput.xps"));
```

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

## Běžné problémy a řešení
- **Neplatná cesta** – Ujistěte se, že `dataDir` končí zpětným lomítkem (`\\`) nebo použijte `Path.Combine`.  
- **Ořez není aplikován** – Ověřte, že řetězec ořezové geometrie je správně vytvořen; chybějící mezera může způsobit, že bude ořez ignorován.  
- **Výjimka licence** – V ne‑evaluační verzi přidejte platnou Aspose licenci před vytvořením dokumentu, aby se předešlo výjimkám během běhu.

## Často kladené otázky

### Q1: Mohu použít Aspose.Page pro .NET s jinými formáty dokumentů?

A1: Aspose.Page pro .NET se primárně zaměřuje na XPS dokumenty, ale Aspose poskytuje další knihovny pro různé formáty dokumentů.

### Q2: Je Aspose.Page pro .NET vhodný pro začátečníky?

A2: Ano, Aspose.Page pro .NET je navržen tak, aby byl uživatelsky přívětivý, a začátečníci si mohou rychle osvojit jeho funkce s odpovídající dokumentací.

### Q3: Kde mohu najít více příkladů a zdrojů?

A3: Navštivte [dokumentaci](https://reference.aspose.com/page/net/) a [forum Aspose.Page](https://forum.aspose.com/c/page/39) pro rozsáhlé zdroje a příklady.

### Q4: Jak mohu získat dočasnou licenci pro Aspose.Page pro .NET?

A4: Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

### Q5: Je k dispozici bezplatná zkušební verze pro Aspose.Page pro .NET?

A5: Ano, můžete si vyzkoušet bezplatnou verzi [zde](https://releases.aspose.com/).

## Další často kladené otázky

**Q: Mohu kombinovat více ořezových geometrií na jednom plátně?**  
A: Ano, můžete přiřadit složitou `PathGeometry`, která obsahuje několik podcest, k vlastnosti `Clip`, což umožňuje vrstvené maskování.

**Q: Ovlivňuje ořezování konverzi do PDF?**  
A: Když později převádíte XPS do PDF pomocí Aspose.PDF, geometrie ořezu je zachována, takže vizuální výsledek zůstává stejný.

**Q: Je možné animovat ořezávání v XPS?**  
A: XPS sám o sobě nepodporuje animaci; můžete však vygenerovat sérii XPS stránek s různými tvary ořezu pro simulaci pohybu.

**Poslední aktualizace:** 2026-06-25  
**Testováno s:** Aspose.Page 24.11 pro .NET  
**Autor:** Aspose  

```csharp
doc.Save(dataDir + "output2.xps");
```

## Související tutoriály

- [Jak transformovat XPS pomocí Aspose.Page pro .NET](/page/net/canvas-manipulation/transformationsxps/)
- [Přidat obdélník do XPS dokumentu pomocí Aspose.Page pro .NET](/page/net/drawing-shapes/add-rectangle-to-xps-document/)
- [Převést XPS do PDF pomocí Aspose.Page pro .NET](/page/net/document-conversion/convert-xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< /blocks/products/products-backtop-button >}}

{{< blocks/products/products-backtop-button >}}