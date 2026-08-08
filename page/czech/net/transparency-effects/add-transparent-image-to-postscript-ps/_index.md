---
date: 2026-03-26
description: Naučte se, jak vytvořit dokument PostScript v .NET a přidat průhledný
  obrázek pomocí Aspose.Page. Tento krok‑za‑krokem průvodce zahrnuje předpoklady,
  kód a tipy.
linktitle: Add Transparent Image to PostScript (PS)
second_title: Aspose.Page .NET API
title: Vytvořit dokument PostScript v .NET s průhledným obrázkem (Aspose.Page)
url: /cs/net/transparency-effects/add-transparent-image-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořit PostScript dokument .NET s průhledným obrázkem (Aspose.Page)

## Úvod

V tomto tutoriálu se naučíte **jak vytvořit PostScript dokument .NET** a vložit průhledný PNG pomocí Aspose.Page pro .NET. Přidání průhledných obrázků vám umožní vytvářet bohatší, vrstvenou grafiku – ideální pro vodoznaky, překryvy nebo UI mock‑upy uvnitř PS souboru. Provedeme vás každým krokem, od nastavení prostředí až po vykreslení jak neprůhledných, tak průhledných obrázků.

## Rychlé odpovědi
- **Co dělá Aspose.Page?** Poskytuje plnohodnotné API pro generování, úpravu a vykreslování dokumentů PostScript (PS) a XPS v .NET.  
- **Mohu přidat průhledné PNG?** Ano—použijte `DrawTransparentImage` k řízení průhlednosti.  
- **Které verze .NET jsou podporovány?** Všechny aktuální verze .NET Framework, .NET Core a .NET 5/6.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro hodnocení; licence je vyžadována pro produkci.  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní příklad.

## Požadavky

- **Aspose.Page for .NET** – stáhněte jej z [download link](https://releases.aspose.com/page/net/).  
- Složka, kde budete uchovávat PS dokument a obrázek, který chcete vložit.  
- Průhledný PNG (např. `mask1.png`), který bude použit pro průhlednou vrstvu.

## Importovat jmenné prostory

Nejprve importujte jmenné prostory, které obsahují třídy, jež budeme potřebovat. To nám poskytne přístup k modelu PS dokumentu, grafickým utilitám a základním .NET typům kreslení.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Krok 1: Nastavte adresář dokumentu

Definujte cestu, kde budou umístěny zdrojový obrázek a výstupní PS soubor. Nahraďte zástupný text skutečnou cestou na vašem počítači.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Krok 2: Vytvořte výstupní stream pro PostScript dokument

Budeme zapisovat vygenerovaný PS obsah do souborového streamu. Tento stream je později předán konstruktoru `PsDocument`.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTransparentImage_outPS.ps", FileMode.Create))
{
    // Your code for the next steps will go here.
}
```

## Krok 3: Nastavte možnosti uložení a barvu pozadí

Nakonfigurujte `PsSaveOptions`, aby definovaly, jak je soubor uložen. Nastavení barvy pozadí je užitečné, když chcete mít pevné plátno za průhlednými prvky.

```csharp
PsSaveOptions options = new PsSaveOptions();
options.BackgroundColor = Color.FromArgb(211, 8, 48);
```

## Krok 4: Vytvořte nový 1‑stránkový PS dokument

Vytvořte dokument pomocí streamu a možností definovaných výše. Příznak `false` říká Aspose.Page, aby automaticky nezavíral stream.

```csharp
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Krok 5: Uložit stav grafiky a přeložit

Před kreslením uložíme aktuální stav grafiky a posuneme počátek, aby se naše obrázky objevily na požadované pozici na stránce.

```csharp
document.WriteGraphicsSave();
document.Translate(20, 100);
```

## Jak přidat průhledný obrázek do PostScript dokumentu

### Krok 6: Přidat neprůhledný RGB obrázek

Nejprve přidáme stejný PNG jako běžný neprůhledný obrázek. To ukazuje vizuální rozdíl, když později použijeme průhlednost.

```csharp
using (Bitmap image = new Bitmap(dataDir + "mask1.png"))
{
    document.DrawImage(image, new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 100, 0), Color.Empty);
}
```

### Krok 7: Přidat průhledný obrázek

Nyní použijeme `DrawTransparentImage` k vykreslení PNG s hodnotou opacity. Třetí parametr (`255`) představuje plnou neprůhlednost; nižší hodnoty zvyšují průhlednost. Zde **nastavujeme průhlednost obrázku .NET**.

```csharp
using (Bitmap image = new Bitmap(dataDir + "mask1.png"))
{
    document.DrawTransparentImage(image, new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 350, 0), 255);
}
```

> **Pro tip:** Pro nastavení 50 % průhlednosti předávejte `128` místo `255`.

## Krok 8: Obnovit stav grafiky a zavřít stránku

Po kreslení obnovíme předchozí stav grafiky a zavřeme stránku, aby byl obsah finalizován.

```csharp
document.WriteGraphicsRestore();
document.ClosePage();
```

## Krok 9: Uložit dokument

Nakonec uložíme PS soubor na disk.

```csharp
document.Save();
```

Postupem podle těchto kroků jste **vytvořili PostScript dokument .NET**, který obsahuje jak neprůhledný, tak průhledný obrázek, a ukazuje, jak **kreslit průhledný obrázek C#** s Aspose.Page.

## Proč použít Aspose.Page pro efekty průhlednosti?

- **Plná kontrola** nad stavem grafiky, maticemi a úrovněmi průhlednosti.  
- **Žádné externí závislosti**—vše běží v čistém .NET kódu.  
- **Cross‑platform** podpora vám umožní generovat PS soubory na Windows, Linuxu nebo macOS.

## Časté problémy a řešení

| Problém | Řešení |
|-------|----------|
| Obrázek se zobrazuje úplně neprůhledně i po použití `DrawTransparentImage` | Ujistěte se, že alfa hodnota (třetí argument) je menší než `255`. |
| Soubor PS zobrazuje prázdnou stránku | Ověřte, že je nastavena barva pozadí a že cesta ke streamu je správná. |
| Výjimka „File not found“ | Zkontrolujte dvakrát `dataDir` a že `mask1.png` existuje v této složce. |

## Často kladené otázky

**Q: Mohu použít jiné formáty obrázků než PNG pro průhlednost?**  
A: Ano—Aspose.Page podporuje PNG, GIF a TIFF pro průhledné vykreslování.

**Q: Je Aspose.Page kompatibilní s nejnovějším .NET frameworkem?**  
A: Rozhodně. Knihovna je pravidelně aktualizována pro .NET 6, .NET 7 a novější.

**Q: Mohu aplikovat průhlednost na existující PS dokument?**  
A: Ano. Otevřete dokument pomocí `PsDocument`, přidejte novou stránku nebo upravte existující a použijte stejný přístup `DrawTransparentImage`.

**Q: Jaké výhody nabízí Aspose.Page oproti obecnějším grafickým knihovnám?**  
A: Je navržena speciálně pro PS/XPS, poskytuje přesnou kontrolu nad vektorovou grafikou, fonty a manipulací s obrázky bez potřeby kompletního renderovacího enginu.

**Q: Existují limity pro úroveň průhlednosti, kterou mohu nastavit?**  
A: Ne. Můžete zadat libovolnou alfa hodnotu od `0` (zcela průhledná) po `255` (zcela neprůhledná).

## Závěr

Ukázali jsme, jak **vytvořit PostScript dokument .NET** a vložit jak neprůhledné, tak průhledné obrázky pomocí Aspose.Page. Tato technika otevírá možnosti pro sofistikované rozvržení dokumentů, vodoznaky a vrstvenou grafiku—vše generováno programově z C#.

---

**Poslední aktualizace:** 2026-03-26  
**Testováno s:** Aspose.Page 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}