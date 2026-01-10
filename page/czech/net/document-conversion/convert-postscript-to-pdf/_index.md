---
date: 2026-01-10
description: Bez námahy převádějte PostScript do PDF pomocí Aspose.Page pro .NET.
  Robustní, spolehlivý a vývojářsky přívětivý.
linktitle: Convert PostScript to PDF
second_title: Aspose.Page .NET API
title: Převod PostScriptu na PDF pomocí Aspose.Page pro .NET
url: /cs/net/document-conversion/convert-postscript-to-pdf/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převod PostScriptu do PDF pomocí Aspose.Page pro .NET

## Úvod

Pokud potřebujete **převést PostScript do PDF** rychle a spolehlivě, Aspose.Page pro .NET nabízí čisté, code‑first API, které za vás provádí těžkou práci. V tomto tutoriálu projdeme reálným příkladem, který přesně ukazuje **jak převést soubory PostScript**, přidat vlastní fonty a uložit výsledek jako PDF dokument, který můžete distribuovat nebo archivovat.  
Uvidíte, proč vývojáři volí Aspose.Page pro dávkové úlohy, práci s vlastními fonty a renderování s vysokou věrností — vše bez opuštění .NET ekosystému.

## Rychlé odpovědi
- **Jaká knihovna provádí převod?** Aspose.Page pro .NET  
- **Mohu přidat vlastní fonty?** Ano – použijte možnost `AdditionalFontsFolders`  
- **Je možný dávkový převod?** Rozhodně, stačí iterovat přes více souborů  
- **Potřebuji licenci pro produkci?** Je vyžadována komerční licence; je k dispozici bezplatná zkušební verze  
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## Co je převod PostScriptu do PDF?

Převod PostScriptu do PDF znamená převzít jazyk pro popis stránky (PostScript) a vykreslit jej do přenosného, široce podporovaného formátu PDF. To je užitečné, když obdržíte staré tiskové soubory, potřebujete archivovat dokumenty nebo je chcete zobrazit v prohlížečích bez dalších pluginů.

## Proč použít Aspose.Page pro .NET?

- **Žádné externí závislosti** – není potřeba Ghostscript ani nativní binární soubory.  
- **Plná kontrola nad fonty** – můžete dodat vlastní složky s fonty (`add custom fonts pdf`).  
- **Robustní zpracování chyb** – potlačte menší chyby a přesto získáte použitelné PDF (`save postscript as pdf`).  
- **Škálovatelné pro dávkové zpracování** – API je thread‑safe a dobře funguje v serverových prostředích.

## Předpoklady

Než se ponoříte do tutoriálu, ujistěte se, že máte následující předpoklady připravené:

1. Knihovna Aspose.Page pro .NET: Ujistěte se, že máte knihovnu Aspose.Page pro .NET nainstalovanou ve svém vývojovém prostředí. Můžete si ji stáhnout [zde](https://releases.aspose.com/page/net/).
2. Vývojové prostředí: Nastavte funkční vývojové prostředí s Visual Studio nebo jiným kompatibilním IDE.

Nyní, když máte předpoklady pokryté, pojďme prozkoumat kroky k **převodu PostScriptu do PDF** pomocí Aspose.Page pro .NET.

## Název importu jmenných prostorů

Na začátku musíte importovat potřebné jmenné prostory, abyste získali přístup k funkcionalitě poskytované Aspose.Page pro .NET. Umístěte následující kód na začátek svého souboru C#:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Krok 1: Inicializace streamů

Začněte inicializací vstupních a výstupních streamů pro soubory PostScript a PDF. Ujistěte se, že nahradíte „Your Document Directory“ skutečnou cestou k vašemu adresáři s dokumenty.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize PDF output stream
System.IO.FileStream pdfStream = new System.IO.FileStream(dataDir + "outputPDF_out.pdf", System.IO.FileMode.Create, System.IO.FileAccess.Write);
// Initialize PostScript input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "input.ps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Krok 2: Nastavení možností převodu

Pro řízení procesu převodu inicializujte objekt možností s potřebnými parametry. V tomto příkladu můžete nastavit příznak pro potlačení menších chyb během převodu.

```csharp
// If you want to convert Postscript file despite of minor errors set this flag
bool suppressErrors = true;
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions(suppressErrors);
// If you want to add a special folder where fonts are stored. Default fonts folder in OS is always included.
options.AdditionalFontsFolders = new string[] { @"{FONT_FOLDER}" };
```

> **Tip:** Použijte vlastnost `AdditionalFontsFolders` vždy, když potřebujete **přidat vlastní PDF fonty**, které nejsou nainstalovány v hostitelském OS.

## Krok 3: Inicializace PDF zařízení

Vytvořte PDF zařízení pro zpracování procesu převodu. V případě potřeby můžete specifikovat velikost stránky a formát obrazu.

```csharp
// Default page size is 595x842 and it is not mandatory to set it in PdfDevice
Aspose.Page.EPS.Device.PdfDevice device = new Aspose.Page.EPS.Device.PdfDevice(pdfStream);
// But if you need to specify size and image format use the following line
//Aspose.Page.EPS.Device.PdfDevice device = new Aspose.Page.EPS.Device.PdfDevice(pdfStream, new System.Drawing.Size(595, 842));
```

## Krok 4: Uložení dokumentu

Pokus se uložit dokument pomocí zadaného zařízení a možností.

```csharp
try
{
    document.Save(device, options);
}
finally
{
    psStream.Close();
    pdfStream.Close();
}
```

## Krok 5: Kontrola chyb

Po převodu je důležité zkontrolovat případné chyby. Pokud je nastaven příznak `suppressErrors`, projděte výjimky a vytiskněte chybové zprávy.

```csharp
// Review errors
if (suppressErrors)
{
    foreach (Exception ex in options.Exceptions)
    {
        Console.WriteLine(ex.Message);
    }
}
```

### Časté úskalí a jak se jim vyhnout

| Problém | Proč se to děje | Řešení |
|---------|----------------|--------|
| Fonty se nezobrazují | Vlastní fonty nejsou ve složce fontů OS | Přidejte cestu ke složce do `options.AdditionalFontsFolders` |
| Chybějící stránky | Vstupní PostScript obsahuje chyby | Nastavte `suppressErrors = true` pro pokračování v převodu a zkontrolujte `options.Exceptions` |
| Výstupní soubor je uzamčen | Stream není řádně uzavřen | Vždy uzavřete oba `psStream` a `pdfStream` v bloku `finally` (jak je ukázáno) |

## Často kladené otázky

**Q1: Je Aspose.Page pro .NET vhodný pro dávkové převody?**  
A1: Ano, Aspose.Page pro .NET podporuje dávkové převody, což vám umožní zpracovávat více souborů PostScript najednou.

**Q2: Mohu přizpůsobit složky s fonty používané během převodu?**  
A2: Rozhodně. Jak je ukázáno v tutoriálu, můžete specifikovat další složky s fonty podle vašich konkrétních požadavků.

**Q3: Je k dispozici zkušební verze pro Aspose.Page pro .NET?**  
A3: Ano, můžete získat bezplatnou zkušební verzi [zde](https://releases.aspose.com/).

**Q4: Kde mohu najít další podporu a komunitní diskuse?**  
A4: Navštivte [forum Aspose.Page](https://forum.aspose.com/c/page/39) pro komunitní diskuse a podporu.

**Q5: Jak mohu získat dočasnou licenci pro Aspose.Page pro .NET?**  
A5: Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

## Závěr

Na závěr, Aspose.Page pro .NET zjednodušuje složitý úkol **převodu postscriptu do pdf**. Díky intuitivnímu API a robustním funkcím mohou vývojáři bez problémů zpracovávat konverze dokumentů, což zajišťuje efektivitu a spolehlivost v jejich aplikacích. Ať už převádíte jeden soubor nebo zpracováváte tisíce, knihovna vám poskytuje flexibilitu **přidat vlastní PDF fonty**, elegantně spravovat chyby a **uložit PostScript jako PDF** pomocí jen několika řádků kódu.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

---