---
date: 2026-02-25
description: Naučte se, jak vytvořit XPS gradient s vodorovným vyplněním pomocí Aspose.Page
  pro .NET. Snadno zvýšte vizuální atraktivitu svých dokumentů.
linktitle: Add Horizontal Gradient to XPS
second_title: Aspose.Page .NET API
title: 'Vytvořte XPS gradient: vodorovné vyplnění pomocí Aspose.Page pro .NET'
url: /cs/net/gradient-fills/add-horizontal-gradient-to-xps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření XPS gradientu – Přidání horizontálního gradientu do XPS pomocí Aspose.Page pro .NET

## Úvod

V tomto tutoriálu **vytvoříte XPS gradient** výplně, které běží horizontálně napříč vašimi stránkami. Přidání horizontálního gradientu může okamžitě učinit XPS dokument vypadat profesionálněji a poutavěji, zejména pro zprávy, brožury nebo jakýkoli vizuálně bohatý výstup. Provedeme vás kompletním procesem pomocí Aspose.Page pro .NET, od nastavení prostředí až po uložení finálního XPS souboru.

## Rychlé odpovědi
- **Co tento tutoriál pokrývá?** Přidání horizontálního gradientu do XPS dokumentu pomocí Aspose.Page pro .NET.  
- **Která knihovna je vyžadována?** Aspose.Page pro .NET (jakákoli aktuální verze).  
- **Potřebuji licenci?** Zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Jak dlouho trvá implementace?** Přibližně 5–10 minut pro základní gradient.  
- **Mohu změnit směr gradientu?** Ano – upravte počáteční a koncové body `LinearGradientBrush`.

## Jak vytvořit XPS gradient pomocí Aspose.Page pro .NET

Níže najdete krok‑za‑krokem průvodce, který vysvětluje **proč** existuje každá řádka kódu, nejen **co** dělá. Klidně postupujte ve Visual Studio nebo ve svém oblíbeném .NET editoru.

## Požadavky

Než začneme, ujistěte se, že máte následující předpoklady připravené:

1. **Aspose.Page pro .NET Library:** Ujistěte se, že máte knihovnu Aspose.Page pro .NET nainstalovanou ve svém vývojovém prostředí. Můžete ji stáhnout z [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

2. **Vývojové prostředí:** Nastavte vhodné vývojové prostředí, včetně editoru kódu jako je Visual Studio.

## Importování jmenných prostorů

Začněte importováním potřebných jmenných prostorů do vašeho projektu. Tyto jmenné prostory jsou nezbytné pro práci s Aspose.Page pro .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Nyní si rozdělíme poskytnutý příklad do několika kroků.

## Krok 1: Nastavení cesty ke složce dokumentu

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Krok 2: Vytvoření nového XPS dokumentu

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Krok 3: Inicializace gradientových zastávek

```csharp
// ExStart:5
// Initialize List of XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## Krok 4: Vytvoření nové cesty

```csharp
// ExStart:6
// Create new path by defining geometry in abbreviation form
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Krok 5: Uložení výsledného XPS dokumentu

```csharp
// ExStart:7
// Save resultant XPS document
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

Nyní jste úspěšně přidali horizontální gradient do svého XPS dokumentu pomocí Aspose.Page pro .NET.

## Časté problémy a řešení

| Problém | Důvod | Řešení |
|-------|--------|-----|
| Gradient se zobrazuje jako jednobarevná výplň | Gradientové zastávky nebyly přidány správně | Ujistěte se, že je po nastavení štětce provedeno `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);`. |
| Uložený soubor je prázdný | `dataDir` ukazuje na neexistující složku | Ověřte, že složka existuje, nebo použijte absolutní cestu. |
| Chyba kompilace u `PointF` | Chybí odkaz na `System.Drawing` | Přidejte odkaz na `System.Drawing.Common` (pro .NET Core/5+). |

## Často kladené otázky

### Q1: Kde mohu najít dokumentaci k Aspose.Page pro .NET?

A1: Dokumentaci najdete [zde](https://reference.aspose.com/page/net/).

### Q2: Jak si mohu stáhnout Aspose.Page pro .NET?

A2: Knihovnu si můžete stáhnout ze [stránky pro stažení Aspose.Page pro .NET](https://releases.aspose.com/page/net/).

### Q3: Kde mohu zakoupit Aspose.Page pro .NET?

A3: Zakoupit můžete na [stránce nákupu](https://purchase.aspose.com/buy).

### Q4: Je k dispozici bezplatná zkušební verze?

A4: Ano, bezplatnou zkušební verzi získáte [zde](https://releases.aspose.com/).

### Q5: Jak získám dočasnou licenci pro Aspose.Page pro .NET?

A5: Dočasnou licenci můžete získat na [tomto odkazu](https://purchase.aspose.com/temporary-license/).

## Často kladené otázky

**Q: Mohu tuto techniku gradientu použít u XPS dokumentů, které již obsahují obrázky?**  
A: Rozhodně. Gradient se aplikuje na vrstvu cesty, takže existující obrázky zůstávají nedotčeny.

**Q: Je možné vytvořit místo toho vertikální gradient?**  
A: Ano. Změňte počáteční a koncové body `LinearGradientBrush` tak, aby měly různé Y‑souřadnice při zachování konstantního X.

**Q: Podporuje Aspose.Page .NET Core?**  
A: Knihovna je plně kompatibilní s .NET Core, .NET 5 a novějšími verzemi.

**Q: Jak mohu znovu použít stejný gradient na více stránkách?**  
A: Vytvořte `XpsLinearGradientBrush` jednou, uložte jej do proměnné a přiřaďte jej cestám na každé stránce.

## Závěr

Vylepšení vašich XPS dokumentů pomocí gradientů nejen zvyšuje vizuální přitažlivost, ale také poskytuje poutavější uživatelský zážitek. S Aspose.Page pro .NET můžete **vytvořit XPS gradient** výplně rychle a spolehlivě, čímž vašim zprávám, brožurám nebo e‑knihám dodáte profesionální lesk.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2026-02-25  
**Testováno s:** Aspose.Page for .NET 24.11  
**Autor:** Aspose