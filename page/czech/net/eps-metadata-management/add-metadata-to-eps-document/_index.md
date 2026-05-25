---
date: 2026-01-20
description: Naučte se, jak používat metadata EPS v Aspose.Page pro .NET k vylepšení
  organizace EPS dokumentů. Přidejte metadata snadno pro lepší přístupnost a vyhledávání
  informací.
linktitle: Add Metadata to EPS Document
second_title: Aspose.Page .NET API
title: Přidejte EPS metadata pomocí Aspose.Page pro .NET – aspose page eps metadata
url: /cs/net/eps-metadata-management/add-metadata-to-eps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání EPS metadat pomocí Aspose.Page pro .

V neustále se vyvíjejícím prostředí. Aspován kompletní stažení vyžadována pro produkci.  
- **Mohu zpracovávat více EPS souborů najednou?** Ano – jednoduše projděte své soubory a použijte verze .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co je aspose page eps metadata?

`aspose page eps metadata` odkazuje na XMP (Extensible Metadata Platform) paket, který Aspose.Page vkládá do EPS dokumentu. Tento paket ukládá standardní Dublin Core a XMP vlastnosti jako tvůrce, datum vytvoření, formát, název a vlastní pole, která můžete přidat.

## Proč použít Aspose.Page pro EPS metadata?

- **Vyhledatelnost:** Metadata umožňují rychlé vyhledání ve velkých úložištích dokumentů.  
- **Soulad:** Ukládejte informace o autorovi a z [zde](https://releasesboryena výstupní verze (`add_output.eps`).  

## Importování jmenných prostorů

Ve vašem .NET projektu zahrňte potřebné jmenné prostory, abyste mohli pracovat se soubory EPS a XMP metadaty.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Průvodce krok za krokem

### Krok 1: Inicializace vstupního proudu EPS souboru

Otevřete zdrojový EPS soubor jako proud a vytvořte instanci `PsDocument`.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// ExEnd:3
```

### Krok 2: Získání XMP metadat

Získejte existující XMP paket (nebo prázdný) z dokumentu.

```csharp
// ExStart:4
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

### Krok 3: Kontrola a nastavení hodnot metadat

Můžete přečíst existující hodnoty a v případě potřeby je upravit nebo přidat nové. Níže jsou běžné vlastnosti, které můžete chtít zkontrolovat.

#### Získání hodnoty CreatorTool

```csharp
// ExStart:5
if (xmp.Contains("xmp:CreatorTool"))
    Console.WriteLine("CreatorTool: " + xmp["xmp:CreatorTool"].ToStringValue());
// ExEnd:5
```

#### Získání hodnoty CreateDate

```csharp
// ExStart:6
if (xmp.Contains("xmp:CreateDate"))
    Console.WriteLine("CreateDate: " + xmp["xmp:CreateDate"].ToStringValue());
// ExEnd:6
```

#### Získání hodnoty Format

```csharp
// ExStart:7
if (xmp.Contains("dc:format"))
    Console.WriteLine("Format: " + xmp["dc:format"].ToStringValue());
// ExEnd:7
```

#### Získání hodnoty Title

```csharp
// ExStart:8
if (xmp.Contains("dc:title"))
    Console.WriteLine("Title: " + xmp["dc:title"].ToArray()[0].ToStringValue());
// ExEnd:8
```

#### Získání hodnoty Creator

```csharp
// ExStart:9
if (xmp.Contains("dc:creator"))
    Console.WriteLine("Creator: " + xmp["dc:creator"].ToArray()[0].ToStringValue());
// ExEnd:9
```

#### Získání hodnoty MetadataDate

```csharp
// ExStart:10
if (xmp.Contains("xmp:MetadataDate"))
    Console.WriteLine("MetadataDate: " + xmp["xmp:MetadataDate"].ToStringValue());
// ExEnd:10
```

> **Tip:** Pro přidání nové vlastnosti stačí přiřadit ji do slovníku `xmp`, např. `xmp["dc:description"] = new XmpValue("Sample EPS fileaty

Po aktualizaci metadat zapište dokument zpět na disk.

```csharp
// ExStart:11
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
// ExEnd:11
```

## Časté problémy a řešení

x přístupu k souboru** | Vstupní nebo výstupní soubor je uzamčen jiným procesem. | Zavřete všechny prohlížeče/editor, které mohou mít EPS soubor otevřený. |
| **Hodnoty metadat jsou prázdné** | Původní EPS soubor neobsahuje tyto XMP značky. | Přidejte chybějící značky ručně pomocí `xmp["tag"] = new XmpValue("value");`. |

## Často kladené otázky

### Q1: Mohu přidat metadata do více EPS dokumentů najednou?

**A:** Ano. Projděte kolekci cest k souborům, aplikujte stejné kroky na každý `PsDocument` a uložte výsledky.

### Q2: Existují nějaká omezení velikosti EPS dokumentů, které Aspose.Page pro .NET dokáže zpracovat?

**A:** Knihovna podporuje EPS soubory prakticky jakékoli velikosti, ale extrémně velké soubory mohou vyžadovat více paměti. Sledujte využití paměti vaší aplikace při zpracování obrovských dokumentů.

### Q3: Je XMP metadata standardizována pro všechny EPS dokumenty?

**A:** XMP používá standard přizpůsobit pole metadat pro specifickéhodně. Slovník `XmpMetadata` vám umožní přidávat, upravovat nebo odstraňovat jakoukoliádat chyby během procesu přidávání metadat?

**A:** Zabalte logiku zpracování do bloku `try…catch` a zaznamenejte `IOException`, `AsposeException` nebo jiné relevantní výjimky, aby bylo zajištěno elegantní selhání.

---

**Poslední aktualizace:** 2026-01-20  
**Testováno s:** Aspose.Page for .NET 24.11 (nejnovější)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}