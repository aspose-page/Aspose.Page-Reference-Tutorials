---
date: 2026-01-10
description: Jednoduše převádějte XPS na PDF v .NET s Aspose.Page. Stáhněte knihovnu,
  prozkoumejte dokumentaci a získejte bezplatnou zkušební verzi.
linktitle: Convert XPS to PDF
second_title: Aspose.Page .NET API
title: Převést XPS na PDF pomocí Aspose.Page pro .NET
url: /cs/net/document-conversion/convert-xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převod XPS na PDF pomocí Aspose.Page pro .NET

## Úvod

V tomto tutoriálu se naučíte **jak převést XPS na PDF** pomocí knihovny Aspose.Page pro .NET. Převod XPS na PDF je častý požadavek, když potřebujete sdílet XPS dokumenty s uživateli, kteří mají pouze PDF čtečky, nebo když chcete vložit XPS obsah do větších PDF pracovních postupů. Provedeme vás každým krokem, vysvětlíme, proč je každé nastavení důležité, a ukážeme vám, jak jemně doladit výstup – například nastavením kvality JPEG a aplikací komprese obrázků v PDF.

## Rychlé odpovědi
- **Jaká knihovna je nejlepší pro převod XPS na PDF?** Aspose.Page pro .NET
- **Potřebuji licenci pro produkční nasazení?** Ano, je vyžadována komerční licence; k dispozici je bezplatná zkušební verze.
- **Mohu řídit kvalitu obrázků?** Rozhodně – použijte `JpegQualityLevel` a `PdfImageCompression`.
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Je možné převést více XPS souborů do jednoho PDF?** Ano, pomocí smyčky přes soubory a sloučením výsledků.

## Předpoklady

Než se pustíme do tohoto převodu, ujistěte se, že máte následující předpoklady:

- **Aspose.Page pro .NET Library** – Ujistěte se, že máte knihovnu Aspose.Page pro .NET nainstalovanou ve svém vývojovém prostředí. Můžete si ji stáhnout z [dokumentace Aspose.Page](https://reference.aspose.com/page/net/).
- **Vývojové prostředí** – Nastavte .NET vývojové prostředí s Visual Studiem nebo jiným kompatibilním IDE.
- **XPS dokument** – Připravte XPS dokument, který chcete převést na PDF. Může se jednat o váš ukázkový XPS soubor uložený v určeném adresáři.

## Import jmenných prostorů

Než se ponoříme do kódu, naimportujme potřebný jmenný prostor, aby byly funkce Aspose.Page pro .NET dostupné v našem projektu:

```csharp
using Aspose.Page.XPS;
```

## Průvodce krok za krokem

### Krok 1: Inicializace adresáře dokumentu

Definujte složku, která obsahuje váš zdrojový XPS soubor a kam bude uložen výsledný PDF.

```csharp
string dataDir = "Your Document Directory";
```

Nahraďte `"Your Document Directory"` absolutní nebo relativní cestou k složce obsahující váš XPS dokument.

### Krok 2: Otevření streamů pro výstup PDF a vstup XPS

Používáme dva souborové streamy – jeden pro čtení XPS souboru a druhý pro zápis vygenerovaného PDF.

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

> **Tip:** Ujistěte se, že cesty jsou správné a že aplikace má oprávnění číst/zapisovat do cílové složky.

### Krok 3: Načtení XPS dokumentu

Vytvořte instanci `XpsDocument` ze XPS streamu. Objekt `XpsLoadOptions` vám umožní specifikovat preference načítání, ale výchozí nastavení funguje ve většině scénářů.

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

### Krok 4: Konfigurace možností uložení PDF

Zde nastavujeme preference výstupu PDF. Všimněte si použití **komprese obrázků PDF** (`PdfImageCompression.Jpeg`) a **kvality JPEG** (`JpegQualityLevel = 100`). Tato nastavení přímo ovlivňují velikost souboru a vizuální věrnost.

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

- **`JpegQualityLevel`** – Řídí kvalitu JPEG obrázků vložených do PDF (vyšší = lepší kvalita, větší soubor).
- **`ImageCompression`** – Volí kompresní algoritmus; JPEG je ideální pro fotografické obrázky.
- **`TextCompression`** – Flate komprese snižuje velikost PDF bez ztráty kvality textu.
- **`PageNumbers`** – Umožňuje **uložit XPS jako PDF** pouze pro vybrané stránky.

### Krok 5: Vytvoření zařízení pro vykreslování PDF

`PdfDevice` funguje jako cílové zařízení, které zapisuje PDF data do streamu, který jsme otevřeli dříve.

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

### Krok 6: Uložení dokumentu do PDF

Nakonec zavolejte metodu `Save`, předáte vykreslovací zařízení a nakonfigurované možnosti.

```csharp
document.Save(device, options);
```

Po dokončení provádění kódu se v určeném adresáři objeví soubor `XPStoPDF_out.pdf`, obsahující převedené stránky s kompresí a nastavením kvality, které jste definovali.

## Proč převádět XPS na PDF?

- **Univerzální přístupnost** – PDF prohlížeče jsou nainstalovány prakticky na každém zařízení, zatímco XPS čtečky jsou vzácné.
- **Zachování rozvržení** – PDF zachovává přesné vizuální rozvržení, písma a grafiku původního XPS.
- **Další zpracování** – Jakmile je dokument v PDF, můžete jej sloučit, anotovat nebo digitálně podepsat pomocí dalších knihoven Aspose.

## Běžné případy použití

- **Podnikové reportování** – Generujte XPS reporty ze starších systémů a převádějte je na PDF pro distribuci.
- **Archivace** – Ukládejte dokumenty jako PDF pro dlouhodobou archivaci a zároveň je můžete vytvářet ze zdrojů XPS.
- **Webové služby** – Nabídněte API endpoint, který přijímá XPS nahrávky a vrací PDF soubory v reálném čase.

## Řešení problémů a tipy

- **Soubor nenalezen** – Zkontrolujte cestu `dataDir` a ujistěte se, že název XPS souboru přesně odpovídá.
- **Chyby oprávnění** – Spusťte Visual Studio jako administrátor nebo udělte oprávnění zápisu do výstupní složky.
- **Velké PDF** – Pokud je výsledné PDF příliš velké, snižte `JpegQualityLevel` nebo přepněte `ImageCompression` na `PdfImageCompression.Zip`.

## Často kladené otázky

### Q1: Mohu převést více XPS souborů do jednoho PDF pomocí Aspose.Page pro .NET?

A1: Ano, můžete smyčkou projít více XPS souborů a následovat stejné kroky pro jejich sloučení do jednoho PDF.

### Q2: Existují další výstupní formáty podporované Aspose.Page pro .NET?

A2: Ano, Aspose.Page pro .NET podporuje různé výstupní formáty, včetně TIFF, JPEG, PNG a dalších.

### Q3: Jak mohu přizpůsobit vzhled převedeného PDF dokumentu?

A3: Můžete upravit parametry objektu možností, jako je komprese obrázků a komprese textu, abyste dosáhli požadovaného vzhledu.

### Q4: Je k dispozici zkušební verze pro Aspose.Page pro .NET?

A4: Ano, můžete si vyzkoušet možnosti Aspose.Page pro .NET získáním bezplatné zkušební verze [zde](https://releases.aspose.com/).

### Q5: Kde mohu získat komunitní podporu pro Aspose.Page pro .NET?

A5: Navštivte [forum Aspose.Page](https://forum.aspose.com/c/page/39) pro komunitní diskuze a podporu.

## Často kladené otázky (AI‑přátelské)

**Q: Jak nastavit kvalitu JPEG při převodu XPS na PDF?**  
A: Použijte vlastnost `JpegQualityLevel` uvnitř `PdfSaveOptions`. Nastavení na 100 poskytuje maximální kvalitu.

**Q: Co znamená „pdf image compression“ v tomto kontextu?**  
A: Odkazuje na volbu `ImageCompression`, která určuje, jak jsou obrázky komprimovány uvnitř PDF (např. JPEG, Zip).

**Q: Mohu programově generovat PDF bez zdroje XPS?**  
A: Ano, Aspose.Page také podporuje **c# generate pdf** přímo z kreslicích příkazů, ale to přesahuje rozsah tohoto tutoriálu.

**Q: Existuje způsob, jak převést XPS na PDF bez ztráty vektorové grafiky?**  
A: Převod zachovává vektorová data; jen se vyhněte rasterizaci obrázků tím, že `ImageCompression` ponecháte nastaveno na JPEG nebo Zip podle potřeby.

**Q: Podporuje knihovna .NET Core?**  
A: Rozhodně – Aspose.Page pro .NET funguje s .NET Core, .NET 5, .NET 6 a novějšími verzemi.

**Poslední aktualizace:** 2026-01-10  
**Testováno s:** Aspose.Page 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}