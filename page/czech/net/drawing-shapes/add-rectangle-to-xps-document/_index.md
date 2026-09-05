---
date: 2026-07-19
description: Naučte se, jak vytvořit XPS dokument .NET a přidat obdélník pomocí Aspose.Page
  pro .NET v stručném průvodci krok za krokem.
keywords:
- create xps document .net
- add rectangle xps
- aspose.page .net
lastmod: 2026-07-19
linktitle: Přidat obdélník do XPS dokumentu
og_description: Rychle vytvořte XPS dokument .NET. Tento tutoriál ukazuje, jak přidat
  obdélník do XPS souboru pomocí Aspose.Page pro .NET, s přehledným kódem a tipy.
og_image_alt: Guide to adding a rectangle to an XPS document using Aspose.Page for
  .NET
og_title: Vytvořte XPS dokument .NET – Přidejte obdélník pomocí Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  headline: Create XPS Document .NET – Add Rectangle with Aspose.Page
  type: TechArticle
- description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  name: Create XPS Document .NET – Add Rectangle with Aspose.Page
  steps:
  - name: Create a New XPS Document
    text: The `XpsDocument` class represents the XPS file you are building and provides
      methods to add pages, graphics, and other resources.
  - name: Add a Rectangle
    text: '`XpsPath` defines a drawable path object within the XPS document, allowing
      you to set geometry, stroke, fill, and other visual properties.'
  - name: Save the Document
    text: The `Save` method writes the constructed XPS document to the specified file
      path on disk. Congratulations! You have successfully added a rectangle to an
      XPS document using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works seamlessly with desktop, web, and cloud .NET applications.
    question: Is Aspose.Page compatible with all .NET applications?
  - answer: The full API reference is available [here](https://reference.aspose.com/page/net/).
    question: Where can I find the documentation for Aspose.Page for .NET?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Can I try Aspose.Page for .NET for free before purchasing?
  - answer: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain
      a temporary license.
    question: How can I obtain a temporary license for Aspose.Page for .NET?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support.
    question: Where can I seek community support or ask questions related to Aspose.Page
      for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- xps document
- aspose.page
- .net drawing
title: Vytvořte XPS dokument .NET – Přidejte obdélník pomocí Aspose.Page
url: /cs/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření XPS dokumentu .NET – Přidání obdélníku pomocí Aspose.Page

## Úvod

V tomto tutoriálu se naučíte, jak **vytvořit XPS dokument .NET** a nakreslit v něm obdélník pomocí Aspose.Page pro .NET. Ať už vytváříte reportingový engine, tisknutelnou fakturu nebo vlastní grafickou vrstvu, schopnost programově generovat XPS soubory vám poskytuje plnou kontrolu nad rozvržením a věrností. Postupujte podle níže uvedených kroků a během několika minut budete mít připravený XPS soubor k použití.

## Rychlé odpovědi
- **Jaký je hlavní cíl?** Vytvořit XPS dokument .NET a přidat tvar obdélníku.  
- **Která knihovna je vyžadována?** Aspose.Page pro .NET (ke stažení z oficiálního webu).  
- **Potřebuji licenci pro testování?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.  
- **Jak dlouho trvá implementace?** Přibližně 5‑10 minut pro základní obdélník.

## Co je Aspose.Page pro .NET?
Aspose.Page pro .NET je vysoce výkonná, plně spravovaná API, která umožňuje vývojářům programově vytvářet, upravovat a vykreslovat XPS (XML Paper Specification) dokumenty bez závislosti na externích komponentách. Nabízí bohatý objektový model pro kreslení tvarů, textu a obrázků a podporuje pokročilé funkce, jako je správa barev, komprese a konverze do PDF, což ji činí vhodnou pro širokou škálu scénářů generování dokumentů.

## Proč použít Aspose.Page k vytvoření XPS dokumentu .NET?
Aspose.Page podporuje **více než 30 funkcí XPS** — včetně vektorové grafiky, rozvržení textu a správy barev — a dokáže generovat soubory až do **500 MB** bez načítání celého dokumentu do paměti. Tato kvantifikovaná schopnost zajišťuje plynulý výkon i při velkých tiskových úlohách.

## Předpoklady

Než začnete s tímto tutoriálem, ujistěte se, že máte následující předpoklady připravené:

1. Knihovna Aspose.Page pro .NET: Ujistěte se, že máte knihovnu Aspose.Page pro .NET nainstalovanou ve svém vývojovém prostředí. Můžete si ji stáhnout [zde](https://releases.aspose.com/page/net/).
2. Adresář dokumentů: Vytvořte adresář, kam chcete ukládat své XPS dokumenty.

## Importování jmenných prostorů

Ve své .NET aplikaci zahrňte potřebné jmenné prostory pro využití funkcí Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Jak přidat obdélník do XPS dokumentu v .NET?

Načtěte XPS dokument, vytvořte objekt `Graphics`, definujte `RectangleF` s požadovanou velikostí a zavolejte `DrawRectangle`. Tento postup nakreslí obdélník jedním řádkem kódu a automaticky zpracuje škálování DPI. Pro typické stránky formátu A4 se obdélník o rozměrech 200 × 100 pt zobrazí uprostřed bez dalších výpočtů.

### Krok 1: Nastavte adresář dokumentů

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

### Krok 2: Vytvořte nový XPS dokument

Třída `XpsDocument` představuje XPS soubor, který vytváříte, a poskytuje metody pro přidávání stránek, grafiky a dalších zdrojů.

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

### Krok 3: Přidejte obdélník

`XpsPath` definuje kreslitelný objekt cesty v rámci XPS dokumentu, který vám umožňuje nastavit geometrii, obrys, výplň a další vizuální vlastnosti.

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

### Krok 4: Uložte dokument

Metoda `Save` zapíše vytvořený XPS dokument na určenou cestu souboru na disku.

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Gratulujeme! Úspěšně jste přidali obdélník do XPS dokumentu pomocí Aspose.Page pro .NET.

## Časté problémy a tipy

- **Chybějící písma:** Ujistěte se, že písma, na která odkazujete, jsou nainstalována na serveru; jinak Aspose.Page nahradí výchozím písmem, což může změnit rozvržení.  
- **Velké dokumenty:** Při generování souborů větších než 200 MB zvažte volání `document.SaveOptions.Compress = true` pro snížení využití paměti.  
- **Souřadnicový systém:** XPS používá body (1/72 palce). Nezapomeňte převést pixely na body, pokud pracujete s rozměry založenými na obrazovce.

## Často kladené otázky

**Q: Je Aspose.Page kompatibilní se všemi .NET aplikacemi?**  
A: Ano, Aspose.Page funguje bez problémů s desktopovými, webovými i cloudovými .NET aplikacemi.

**Q: Kde najdu dokumentaci pro Aspose.Page pro .NET?**  
A: Kompletní reference API je k dispozici [zde](https://reference.aspose.com/page/net/).

**Q: Můžu si Aspose.Page pro .NET vyzkoušet zdarma před zakoupením?**  
A: Ano, můžete získat bezplatnou zkušební verzi [zde](https://releases.aspose.com/).

**Q: Jak mohu získat dočasnou licenci pro Aspose.Page pro .NET?**  
A: Navštivte [tento odkaz](https://purchase.aspose.com/temporary-license/) a získejte dočasnou licenci.

**Q: Kde mohu získat komunitní podporu nebo klást otázky související s Aspose.Page pro .NET?**  
A: Navštivte [forum Aspose.Page](https://forum.aspose.com/c/page/39) pro komunitní podporu.

---

**Poslední aktualizace:** 2026-07-19  
**Testováno s:** Aspose.Page for .NET 24.9  
**Autor:** Aspose

## Související tutoriály

- [Vytvoření XPS dokumentu pomocí Aspose.Page pro .NET](/page/net/document-creation/create-xps-document/)
- [Aspose.Page .NET – Kreslení tvarů](/page/net/drawing-shapes/)
- [Přidání textu do XPS dokumentu pomocí Aspose.Page pro .NET](/page/net/text-manipulation/add-text-to-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}