---
date: 2026-04-03
description: Naučte se, jak přidat průhledný obdélník a aplikovat Grid Visual Brush
  v .NET pomocí Aspose.Page pro úchvatné XPS dokumenty.
keywords:
- add transparent rectangle
- grid visual brush
- Aspose.Page .NET
linktitle: Použít vizuální štětec mřížky
second_title: Aspose.Page .NET API
title: Přidat průhledný obdélník pomocí Grid Visual Brush (.NET)
url: /cs/net/visual-brushes/apply-grid-visual-brush/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání průhledného obdélníku pomocí Grid Visual Brush (.NET)

## Úvod

Pokud chcete **přidat průhledný obdélník** do XPS dokumentu a zároveň použít stylový Grid Visual Brush, jste na správném místě. V tomto tutoriálu vás provedeme přesnými kroky potřebnými s Aspose.Page pro .NET, abyste mohli vytvářet vizuálně bohaté dokumenty, které vynikají. Na konci budete mít kompletní, spustitelný příklad, který demonstruje obě techniky v jednom snadno sledovatelném pracovním postupu.

## Rychlé odpovědi
- **Co dělá průhledný obdélník?** Přidává poloprůhlednou vrstvu, která umožňuje zobrazit obsah v pozadí.  
- **Které API vytváří štětec?** `XpsDocument.CreateVisualBrush` vytváří Grid Visual Brush.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro testování; pro produkci je vyžadována komerční licence.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní příklad.

## Co je průhledný obdélník v XPS?
Průhledný obdélník je jednoduše tvar, jehož barva výplně obsahuje alfa komponentu menší než 1,0, což umožňuje částečně viditelné podkladové grafiky. Je to ideální pro zvýraznění částí bez úplného zakrytí pozadí.

## Proč použít Grid Visual Brush?
Grid Visual Brush vám umožňuje dlaždicovat malý vektorový grafický prvek přes větší oblast, čímž vytváří vzory jako mřížky, šrafování nebo vlastní textury. Kombinací s průhledným obdélníkem získáte vrstvené vizuální efekty, které jsou lehké a nezávislé na rozlišení.

## Požadavky

Před ponořením se do kódu se ujistěte, že máte:

- **Aspose.Page pro .NET** – můžete jej stáhnout [zde](https://releases.aspose.com/page/net/).
- Vývojové prostředí .NET (Visual Studio, VS Code nebo jakékoli IDE, které preferujete).
- Složka, do které budou ukládány vygenerované XPS soubory.

## Importovat jmenné prostory

Ve vašem souboru C# importujte požadované jmenné prostory:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Nyní rozdělíme řešení do jasných, číslovaných kroků.

## Krok 1: Inicializace XpsDocument

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

Začínáme vytvořením instance `XpsDocument`, která bude obsahovat všechny následné kreslicí operace.

## Krok 2: Vytvoření magenta geometrie mřížky

```csharp
// ExStart:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExEnd:4
```

Tato geometrie definuje obrys mřížky, kterou bude vizuální štětec vyplňovat.

## Krok 3: Návrh magenta Grid VisualBrush

```csharp
// ExStart:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExEnd:5
```

Zde kreslíme malou fialovou (magenta) dlaždici, která bude opakována po celé mřížce.

## Krok 4: Použití VisualBrush na mřížku

```csharp
// ExStart:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExEnd:6
```

Volání `CreateVisualBrush` spojuje magenta dlaždici s geometrií mřížky a umožňuje její opakování.

## Krok 5: Přidání mřížky na plátno

```csharp
// ExStart:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExEnd:7
```

Umístíme dlaždicovou mřížku na plátno a použijeme transformační posun, aby se zobrazila na požadovaném místě.

## Krok 6: Přidání průhledného obdélníku

```csharp
// ExStart:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f; // This opacity makes the rectangle transparent
// ExEnd:8
```

V tomto kroku **přidáme průhledný obdélník** (červený tvar s `Opacity = 0.7f`). Upravením hodnoty opacity můžete řídit, jak průhledný obdélník bude.

## Krok 7: Uložení dokumentu

```csharp
// ExStart:9
doc.Save(dataDir + "AddGrid_out.xps");
// ExEnd:9
```

Soubor XPS je zapsán do složky, kterou jste dříve určili.

## Běžné případy použití

- **Zvýraznění v reportu:** Překrytí poloprůhledným obdélníkem pro zdůraznění grafu nebo tabulky.  
- **Vodoznakové efekty:** Kombinace dlaždicové mřížky s průhledným překryvem pro jemné značení.  
- **Interaktivní PDF/XPS:** Použijte vzor jako pozadí pro formulářová pole při zachování čitelnosti uživatelského rozhraní.

## Tipy pro řešení problémů

- **Opacity neviditelná?** Ujistěte se, že váš prohlížeč podporuje průhlednost v XPS; některé starší prohlížeče mohou ignorovat vlastnost `Opacity`.  
- **Nesprávná velikost dlaždice?** Ověřte, že zdrojový obdélník (`new RectangleF(0f, 0f, 10f, 10f)`) odpovídá rozměrům vektorové dlaždice.  
- **Soubor nebyl uložen?** Zkontrolujte, že `dataDir` ukazuje na existující adresář s právy zápisu.

## Často kladené otázky

**Q: Mohu použít Aspose.Page pro .NET jak ve webových, tak desktopových aplikacích?**  
A: Ano, knihovna funguje ve všech typech .NET aplikací.

**Q: Je k dispozici zkušební verze před zakoupením?**  
A: Samozřejmě, můžete získat bezplatnou zkušební verzi [zde](https://releases.aspose.com/).

**Q: Kde mohu najít další podporu nebo komunitní diskuze?**  
A: Navštivte [Aspose.Page Forum](https://forum.aspose.com/c/page/39) pro pomoc od komunity a inženýrů Aspose.

**Q: Jak mohu získat dočasnou licenci pro hodnocení?**  
A: Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

**Q: Jaká další dokumentace je k dispozici pro Aspose.Page pro .NET?**  
A: Prozkoumejte komplexní dokumentaci [zde](https://reference.aspose.com/page/net/).

---

**Poslední aktualizace:** 2026-04-03  
**Testováno s:** Aspose.Page 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}