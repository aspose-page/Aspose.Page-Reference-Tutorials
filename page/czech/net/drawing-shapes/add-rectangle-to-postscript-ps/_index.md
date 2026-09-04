---
date: 2026-06-30
description: Naučte se, jak vytvořit dokument postscript .NET a přidat obdélníky pomocí
  Aspose.Page pro .NET. Průvodce krok za krokem s ukázkami kódu.
keywords:
- create postscript document .net
- how to generate postscript file
- Aspose.Page rectangle
linktitle: Přidat obdélník do PostScriptu (PS)
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create postscript document .net and add rectangles using
    Aspose.Page for .NET. Step‑by‑step guide with code samples.
  headline: Create PostScript Document .NET – Add Rectangle Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page for .NET.
    question: What library do I need?
  - answer: Yes – the API lets you build PS files programmatically.
    question: Can I create a PostScript document from scratch?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: Typically under 10 minutes for basic shapes.
    question: How long does the implementation take?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Vytvořit dokument PostScript .NET – Přidat obdélník Aspose.Page
url: /cs/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání obdélníku do PostScriptu (PS) pomocí Aspose.Page pro .NET

## Úvod

Aspose.Page pro .NET je knihovna, která umožňuje programově vytvářet a manipulovat soubory PostScript, EPS a XPS. Pokud hledáte **create postscript document .net**, tento tutoriál vás provede přidáním obdélníků do dokumentu PostScript pomocí Aspose.Page a poskytne vám pevný základ pro tvorbu bohatší grafiky.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.Page for .NET.  
- **Mohu vytvořit dokument PostScript od nuly?** Yes – the API lets you build PS files programmatically.  
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Potřebuji licenci pro vývoj?** A free trial works for testing; a license is required for production.  
- **Jak dlouho trvá implementace?** Typically under 10 minutes for basic shapes.

## Co je vytváření postscript dokumentu .net?
Vytváření dokumentu PostScript v .NET znamená programově generovat soubor `.ps`, který popisuje obsah stránky — text, grafiku nebo tvary — pomocí API Aspose.Page. Tento přístup je ideální pro generování grafiky na straně serveru, automatizované vytváření reportů nebo jakýkoli scénář, kde potřebujete přesnou kontrolu nad výstupním formátem.

## Proč používat Aspose.Page pro .NET?
Aspose.Page podporuje **30+ grafických primitiv** a dokáže generovat soubory až do **500 MB** bez načítání celého dokumentu do paměti, což poskytuje vysoce výkonné vykreslování na Windows, Linuxu a macOS. Poskytuje vám plnou kontrolu nad tvary, barvami a tahy, aniž byste museli psát nízkoúrovňový kód PostScript.

- **Full control over graphics** – kreslete tvary, nastavujte barvy a aplikujte tahy, aniž byste se zabývali nízkoúrovňovou syntaxí PS.  
- **Cross‑platform** – funguje na runtime Windows, Linux a macOS.  
- **No external dependencies** – knihovna interně zpracovává veškeré generování PS.  
- **Rich documentation & examples** – rychle se rozjedete díky bohaté dokumentaci a příkladům.

## Požadavky

- **Aspose.Page for .NET Library** – stáhněte a nainstalujte z [here](https://releases.aspose.com/page/net/).  
- **Development Environment** – Visual Studio, VS Code nebo jakékoli IDE kompatibilní s .NET.

## Importujte jmenné prostory

Jmenný prostor `Aspose.Page` poskytuje základní třídy, které budete potřebovat, jako jsou `Document`, `Page`, `SolidBrush` a `Pen`. Importujte jej před zahájením kódování.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Nyní rozdělíme příklad na přehledné, číslované kroky.

## Krok 1: Nastavte adresář dokumentu

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Nahraďte `"Your Document Directory"` složkou, kam chcete uložit výsledný soubor PS.

## Krok 2: Vytvořte výstupní stream pro dokument PostScript

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Tento stream ukazuje na **AddRectangle_outPS.ps**. Klidně soubor přejmenujte nebo změňte umístění podle potřeby.

## Krok 3: Nastavte možnosti uložení a vytvořte PS dokument

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Zde říkáme Aspose.Page, aby použil velikost stránky A4 a vytvořil jednostránkový dokument.

## Krok 4: Přidejte vyplněný obdélník

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

Definujeme obdélník na souřadnicích (250, 100) s šířkou 150 a výškou 100, nastavíme oranžový štětec a vyplníme tvar.

## Krok 5: Přidejte obdélník s obrysem

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

Druhý obdélník je vytvořen níže na stránce, tentokrát s červeným tahy o šířce 3 body.

## Krok 6: Zavřete stránku a uložte dokument

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Zavřením stránky dokončíte kreslení a `Save()` zapíše soubor PS na disk.

## Jak vytvořit postscript dokument .net?
`Document` je hlavní třída představující soubor PostScript v Aspose.Page. `SaveOptions` určuje nastavení jako velikost stránky a výstupní formát dokumentu. Načtěte objekt `Document`, nakonfigurujte `SaveOptions` pro stránku A4, kreslete tvary pomocí `SolidBrush` nebo `Pen` a poté zavolejte `document.Save()` — celý postup vyžaduje jen několik řádků kódu a běží na libovolném podporovaném .NET runtime. Tento vzor vám umožní generovat plně kompatibilní soubory PostScript bez nutnosti manipulovat s čistým PS kódem.

## Jak generovat soubor postscript
Použijte třídu `SaveOptions` z Aspose.Page k určení výstupního formátu jako PostScript (`SaveFormat.PS`). Knihovna streamuje obsah přímo do souboru nebo paměťového streamu, což vám umožní efektivně generovat velké dokumenty bez nadměrné spotřeby paměti.

## Časté problémy a tipy

- **Incorrect file path** – Ujistěte se, že `dataDir` končí oddělovačem cesty (`\\` nebo `/`) nebo použijte `Path.Combine`.  
- **Missing license** – V produkčním prostředí aplikujte svou Aspose licenci před vytvořením dokumentu, aby se předešlo vodoznakům z evaluační verze.  
- **Color visibility** – Pokud se obdélník zobrazuje prázdně, ověřte, že barvy štětce nebo pera kontrastují s pozadím stránky.

## Často kladené otázky

**Q:** Mohu přizpůsobit barvy obdélníků?  
**A:** Rozhodně. Změňte hodnoty `Color.Orange` nebo `Color.Red` v konstruktorech `SolidBrush` a `Pen` na libovolnou `System.Drawing.Color`, kterou preferujete.

**Q:** Je Aspose.Page kompatibilní s jinými formáty dokumentů?  
**A:** Ano. Kromě PostScriptu Aspose.Page také podporuje generování XPS a EPS.

**Q:** Jak mohu přidat text do stejného dokumentu?  
**A:** Použijte třídu `TextFragment` k umístění textu na požadované souřadnice a poté zavolejte `document.Draw(textFragment)`.

**Q:** Kde najdu další příklady a kompletní referenci API?  
**A:** Prozkoumejte dokumentaci [here](https://reference.aspose.com/page/net/) a připojte se ke komunitě na [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q:** Můžu vyzkoušet Aspose.Page před zakoupením?  
**A:** Ano, stáhněte si bezplatnou zkušební verzi [here](https://releases.aspose.com/). Pro rozšířené hodnocení zvažte [dočasnou licenci](https://purchase.aspose.com/temporary-license/).

**Poslední aktualizace:** 2026-06-30  
**Testováno s:** Aspose.Page 24.12 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Jak vytvořit dokument PostScript s Aspose.Page pro .NET](/page/net/document-creation/create-postscript-document/)
- [Přidat obrázek do dokumentu PostScript (PS) s Aspose.Page](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Přidat text do dokumentu PostScript (PS) s Aspose.Page](/page/net/text-manipulation/add-text-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}