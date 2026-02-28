---
date: 2026-02-28
description: Naučte se, jak přidat obrázek do dokumentu PostScript pomocí Aspose.Page
  pro .NET. Tento průvodce také popisuje, jak vložit bitmapu do PS a jak v případě
  potřeby extrahovat obrázky z PS.
linktitle: Add Image to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Jak přidat obrázek do dokumentu PostScript (PS) pomocí Aspose.Page
url: /cs/net/image-management/add-image-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat obrázek do dokumentu PostScript (PS) pomocí Aspose.Page

## Jak přidat obrázek do dokumentu PostScript (PS)

V tomto tutoriálu se naučíte **jak přidat obrázek** do dokumentu PostScript (PS) pomocí výkonné knihovny Aspose.Page pro .NET. Ať už připravujete tiskové letáky, technické výkresy nebo vlastní zprávy, vložení grafiky přímo do PS souborů může dramaticky zlepšit vizuální kvalitu. Provedeme vás každým krokem, vysvětlíme, proč je každý řádek důležitý, a poskytneme tipy, které můžete znovu použít v budoucích projektech.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.Page pro .NET (nejnovější verze)
- **Mohu vložit bitmapu do ps?** Ano – použijte `DrawImage` s objektem `Bitmap`
- **Jak dlouho trvá implementace?** Obvykle méně než 10 minut pro základní obrázek
- **Potřebuji licenci?** Zkušební verze funguje pro hodnocení; pro produkci je vyžadována komerční licence
- **Mohu později extrahovat obrázky z ps?** Rozhodně – Aspose.Page také poskytuje API pro extrakci

## Předpoklady

Než se pustíme do kódu, ujistěte se, že máte následující předpoklady připravené:

- Knihovna Aspose.Page pro .NET: Stáhněte a nainstalujte knihovnu Aspose.Page pro .NET z [here](https://releases.aspose.com/page/net/).
- Adresář dokumentu: Vytvořte adresář ve svém systému, kde budete ukládat dokumenty a soubory obrázků.

## Importovat jmenné prostory

Začněte importováním potřebných jmenných prostorů do svého projektu. Tyto jmenné prostory vám umožní využívat funkce Aspose.Page ve vaší .NET aplikaci:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Krok 1: Nastavit adresář dokumentu

Ujistěte se, že máte vyhrazený adresář pro své dokumenty. Nahraďte `"Your Document Directory"` v níže uvedeném úryvku kódu cestou k vašemu adresáři dokumentů.

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: Vytvořit výstupní stream pro PS dokument

Nastavte výstupní stream pro dokument PostScript. Tento stream bude použit k uložení upraveného dokumentu.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddImage_outPS.ps", FileMode.Create))
```

## Krok 3: Vytvořit možnosti uložení

Vytvořte možnosti uložení pro PS dokument, kde specifikujete požadovaná nastavení, jako je velikost stránky.

```csharp
PsSaveOptions options = new PsSaveOptions();
```

## Krok 4: Vytvořit PS dokument

Inicializujte nový jednopage PS dokument a připravte se na grafické operace.

```csharp
PsDocument document = new PsDocument(outPsStream, options, false);
document.WriteGraphicsSave();
document.Translate(100, 100);
```

## Krok 5: Vložit bitmapu do PS dokumentu

Načtěte objekt `Bitmap` ze souboru obrázku a aplikujte transformace. Toto je jádro **jak přidat obrázek** – nakreslíme bitmapu na PS plátno.

```csharp
using (Bitmap image = new Bitmap(dataDir + "TestImage Format24bppRgb.jpg"))
{
    System.Drawing.Drawing2D.Matrix transform = new System.Drawing.Drawing2D.Matrix();
    transform.Translate(35, 300);
    transform.Scale(3, 3);
    transform.Rotate(-45);
    
    document.DrawImage(image, transform, Color.Empty);
}
```

> **Tip:** Upravte hodnoty `Translate`, `Scale` a `Rotate`, abyste obrázek umístili a změnili jeho velikost přesně tam, kde jej potřebujete.

## Krok 6: Dokončit grafické operace

Ukončete grafické operace a zavřete aktuální stránku.

```csharp
document.WriteGraphicsRestore();
document.ClosePage();
```

## Krok 7: Uložit dokument

Uložte upravený PS dokument.

```csharp
document.Save();
```

## Jak extrahovat obrázky z PS dokumentů

Pokud později potřebujete získat grafiku, Aspose.Page poskytuje metody pro extrakci, například `PsDocument.ExtractImages`. Zatímco tento tutoriál se zaměřuje na vkládání, stejná knihovna vám umožní **extrahovat obrázky z ps** souborů pro opětovné použití nebo analýzu.

## Časté problémy a řešení

| Problém | Proč se to děje | Řešení |
|---------|----------------|--------|
| Obrázek se zobrazuje deformovaně | Nesprávná škálovací matice | Zkontrolujte hodnoty `Scale`; použijte jednotné škálování (např. `Scale(1,1)`) pro původní velikost |
| Výstupní soubor je prázdný | Stream není vyprázdněn | Ujistěte se, že `document.Save()` je voláno uvnitř bloku `using` |
| Nepodporovaný formát obrázku | Bitmap nemůže načíst soubor | Převeďte obrázek do podporovaného formátu jako JPEG, PNG, BMP nebo GIF |

## Závěr

Gratulujeme! Úspěšně jste se naučili **jak přidat obrázek** do dokumentu PostScript pomocí Aspose.Page pro .NET. Nyní máte pevný základ pro vkládání grafiky a také víte, jak **extrahovat obrázky z ps** a **vložit bitmapu do ps**, když to bude potřeba. Nebojte se experimentovat s více obrázky, různými transformacemi nebo dokonce vlastními kreslícími příkazy pro vytvoření bohatého, tisknutelného obsahu.

## Často kladené otázky

### Q1: Mohu přidat více obrázků do jednoho PS dokumentu pomocí Aspose.Page?

A1: Ano, můžete. Jednoduše opakujte kroky přidání obrázku v rámci dokumentu.

### Q2: Jaké formáty obrázků jsou podporovány knihovnou Aspose.Page pro .NET?

A2: Aspose.Page pro .NET podporuje různé formáty obrázků, včetně JPEG, PNG, BMP a GIF.

### Q3: Existuje limit velikosti pro obrázky, které lze přidat?

A3: Limit velikosti závisí na specifikacích PS dokumentu a systémových zdrojích. Aspose.Page zvládá širokou škálu velikostí obrázků.

### Q4: Mohu na obrázky aplikovat další efekty, jako filtry nebo překryvy?

A4: Ano, Aspose.Page umožňuje aplikovat různé transformace a efekty na obrázky před jejich přidáním do dokumentu.

### Q5: Jak mohu extrahovat obrázky z PS dokumentu?

A5: Aspose.Page pro .NET poskytuje metody pro extrakci obrázků z PS dokumentů. Viz dokumentace pro podrobnosti.

---

**Poslední aktualizace:** 2026-02-28  
**Testováno s:** Aspose.Page pro .NET (nejnovější vydání)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}