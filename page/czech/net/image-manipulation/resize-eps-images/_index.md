---
date: 2026-03-03
description: Naučte se, jak změnit velikost EPS obrázků v .NET pomocí Aspose.Page
  – krok za krokem průvodce, jak měnit velikost EPS pomocí bodů, palců, milimetrů
  nebo procent.
linktitle: Resize EPS Images
second_title: Aspose.Page .NET API
title: Jak změnit velikost EPS obrázků pomocí Aspose.Page pro .NET
url: /cs/net/image-manipulation/resize-eps-images/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak změnit velikost EPS obrázků pomocí Aspose.Page pro .NET

## Úvod

Hledáte **jak změnit velikost EPS** obrázků snadno pomocí Aspose.Page pro .NET? Tento tutoriál je vaším komplexním průvodcem, jak bez námahy manipulovat s velikostí EPS obrázků v různých jednotkách, jako jsou body, palce, milimetry a procenta. Aspose.Page pro .NET poskytuje výkonný soubor nástrojů a v tomto tutoriálu vás provedeme procesem krok za krokem.

## Rychlé odpovědi
- **Která knihovna zpracovává změnu velikosti EPS?** Aspose.Page for .NET  
- **Jaké jednotky jsou podporovány?** Body, Palce, Milimetry a Procenta  
- **Potřebuji licenci pro produkci?** Ano – je vyžadována komerční licence  
- **Mohu změnit velikost více souborů najednou?** Rozhodně – stačí projít soubory ve smyčce  
- **Je podporován .NET Core?** Ano, API funguje s .NET Framework i .NET Core  

## Co je změna velikosti EPS?
Encapsulated PostScript (EPS) je vektorový grafický formát běžně používaný v tiskařských a designových pracovních postupech. Změna velikosti EPS souboru upraví jeho ohraničující rámeček bez rasterizace grafiky, čímž zachová ostrost při jakémkoli měřítku.

## Proč měnit velikost EPS obrázků?
- **Udržet kvalitu tisku:** Vektorové škálování zachovává ostré hrany.  
- **Splnit požadavky rozvržení:** Upravit rozměry tak, aby odpovídaly velikosti stránky nebo plátna.  
- **Automatizovat dávkové úlohy:** Programově změnit velikost desítek souborů během několika sekund.  

## Předpoklady

Než se ponoříte do magie změny velikosti, ujistěte se, že máte následující předpoklady připravené:

- Aspose.Page for .NET knihovna: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Page pro .NET. Můžete si ji stáhnout [zde](https://releases.aspose.com/page/net/).

- Adresář dokumentů: Vytvořte adresář, kde budete ukládat vstupní EPS soubor a výstupní soubory po změně velikosti.

Nyní, když máte vše připravené, přejděme k importu potřebných jmenných prostorů a ponořme se do podrobného průvodce.

## Import jmenných prostorů

Ve vašem .NET projektu začněte importovat potřebné jmenné prostory pro práci s Aspose.Page. Přidejte následující kód na začátek souboru:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

## Jak změnit velikost EPS v bodech

Body jsou standardní jednotkou měření v tiskařském průmyslu. Níže uvedený příklad zdvojnásobí původní šířku a výšku.

```csharp
public static void ResizeInPoints()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_points.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(oldSize.Width * 2, oldSize.Height * 2), Units.Points);
        }
    }
}
```

## Jak změnit velikost EPS v palcích

Palce jsou často používány grafickými designéry při přípravě materiálů pro tisk.

```csharp
public static void ResizeInInches()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_inches.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
        }
    }
}
```

## Jak změnit velikost EPS v milimetrech

Milimetry jsou běžné v regionech, které používají metrický systém.

```csharp
public static void ResizeInMillimeters()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_mms.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
        }
    }
}
```

## Jak změnit velikost EPS pomocí procent

Změna velikosti založená na procentech vám umožní škálovat obrázek relativně k jeho původní velikosti.

```csharp
public static void ResizeInPercents()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_percents.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
        }
    }
}
```

Neváhejte tyto metody začlenit do svého projektu a budete měnit velikost EPS obrázků bez námahy. Experimentujte s různými jednotkami, abyste dosáhli požadovaných rozměrů.

## Časté problémy a řešení
- **Soubor nenalezen:** Ověřte, že `dataDir` ukazuje na správný adresář a že `input.eps` existuje.  
- **Neočekávaná velikost:** Pamatujte, že `Units.Percents` očekává hodnoty jako 150 pro 150 % původní velikosti.  
- **Výjimka licence:** Pokud se zobrazí chyba licence, ujistěte se, že je načten platný soubor licence Aspose.Page před vytvořením `PsDocument`.

## Závěr

Gratulujeme! Ovládli jste **jak změnit velikost EPS** obrázků pomocí Aspose.Page pro .NET. Tato výkonná knihovna otevírá svět možností pro manipulaci s vektorovou grafikou. Ať už navrhujete pro tisk nebo digitální média, Aspose.Page vám umožní dosáhnout přesných a přizpůsobených výsledků.

## Často kladené otázky

### Q1: Mohu změnit velikost více EPS obrázků najednou?

A1: Ano, můžete projít kolekci EPS souborů a podle toho aplikovat metody změny velikosti.

### Q2: Je Aspose.Page kompatibilní s jinými formáty obrázků?

A2: Aspose.Page se primárně zaměřuje na formáty PostScript a EPS. Pro jiné formáty obrázků zvažte použití Aspose.Imaging.

### Q3: Existují licenční požadavky pro komerční projekty?

A3: Ano, ujistěte se, že máte platnou licenci. Navštivte [zde](https://purchase.aspose.com/buy) pro podrobnosti o licencování.

### Q4: Můžu vyzkoušet Aspose.Page před zakoupením?

A4: Rozhodně! Můžete získat bezplatnou zkušební verzi [zde](https://releases.aspose.com/).

### Q5: Kde mohu získat další pomoc nebo diskutovat o problémech?

A5: Navštivte [forum Aspose.Page](https://forum.aspose.com/c/page/39), kde se můžete spojit s komunitou a získat pomoc.

## Často kladené otázky

**Q: Funguje tento kód s .NET Core 6?**  
A: Ano. API je kompatibilní s .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ a .NET 6+.

**Q: Jak mohu zachovat původní barevný profil?**  
A: Metoda `ResizeEps` nemění barevná data; pouze mění ohraničující rámeček.

**Q: Je možné změnit velikost EPS bez načtení celého souboru do paměti?**  
A: Použití proudu, jak je ukázáno, udržuje nízkou spotřebu paměti; dokument je zpracováván za běhu.

**Q: Mohu řetězit více operací změny velikosti?**  
A: Rozhodně. Zavolejte `ResizeEps` postupně na stejném instanci `PsDocument`.

**Q: Co se stane s vloženými obrázky uvnitř EPS?**  
A: Jsou škálovány proporcionálně s vektorovým obsahem, zachovávají kvalitu.

---

**Poslední aktualizace:** 2026-03-03  
**Testováno s:** Aspose.Page 24.12 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}