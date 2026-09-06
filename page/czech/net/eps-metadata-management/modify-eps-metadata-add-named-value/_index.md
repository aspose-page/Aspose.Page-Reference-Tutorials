---
date: 2026-08-08
description: Naučte se, jak vytvořit EPS s metadaty XMP a přidat pojmenované hodnoty
  pomocí Aspose.Page pro .NET. Průvodce krok za krokem s ukázkovým kódem.
keywords:
- create eps with xmp
- add named value eps
- aspose.page metadata
lastmod: 2026-08-08
linktitle: Přidat pojmenovanou hodnotu
og_description: Vytvořte EPS s metadaty XMP v .NET pomocí Aspose.Page. Tento průvodce
  ukazuje, jak rychle a spolehlivě přidat pojmenované hodnoty do EPS souborů.
og_image_alt: Guide showing how to add XMP named value to an EPS file with Aspose.Page
og_title: Vytvořte EPS s XMP – přidejte pojmenovanou hodnotu pomocí Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to create EPS with XMP metadata and add named values using
    Aspose.Page for .NET. Step‑by‑step guide with code placeholders.
  headline: Create EPS with XMP – add named value using Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page supports EPS versions 3.0 through 3.3, ensuring broad compatibility
      with legacy and modern files.
    question: Is Aspose.Page compatible with different EPS file versions?
  - answer: Yes, a commercial license is required for production use. You can purchase
      a license **[Aspose.Page license purchase page](https://purchase.aspose.com/buy)**.
    question: Can I use Aspose.Page for commercial projects?
  - answer: Yes, a fully functional trial can be downloaded **[Aspose.Page free trial
      download page](https://releases.aspose.com/)**.
    question: Is there a free trial available?
  - answer: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**
      to ask questions and share experiences.
    question: How can I get support or join the community?
  - answer: A temporary license lets you evaluate the product for a short period.
      You can request one **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: What is a temporary license and how do I obtain one?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: Vytvořte EPS s XMP – přidejte pojmenovanou hodnotu pomocí Aspose.Page
url: /cs/net/eps-metadata-management/modify-eps-metadata-add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořte EPS s XMP – přidejte pojmenovanou hodnotu pomocí Aspose.Page

## Úvod

V tomto tutoriálu se naučíte, jak **vytvořit EPS s XMP** metadata a vložit pojmenovanou hodnotu pomocí knihovny Aspose.Page pro .NET. Ať už budujete dávkový zpracovatelský kanál nebo potřebujete obohatit EPS soubory o vlastní XMP značky, níže uvedené kroky vás provedou vším od nastavení projektu až po uložení upraveného souboru. Aspose.Page dokáže zpracovat EPS dokumenty až do **500 stránek** bez načítání celého souboru do paměti, což jej činí vhodným pro scénáře s vysokým objemem.

## Rychlé odpovědi
- **Jaký je hlavní cíl?** Přidat pojmenovanou XMP hodnotu do existujícího EPS souboru.  
- **Která knihovna je vyžadována?** Aspose.Page for .NET.  
- **Potřebuji licenci?** Pro produkční použití je vyžadována komerční licence; k dispozici je bezplatná zkušební verze.  
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Jak dlouho trvá implementace?** Přibližně 10–15 minut pro základní případ použití.

## Jak vytvořit EPS s XMP metadaty v .NET?

Načtěte cílový EPS soubor, získejte (nebo vytvořte) jeho objekt XMP metadata, přidejte požadovanou pojmenovanou hodnotu a nakonec dokument uložte zpět na disk. Tento pracovní postup vyžaduje jen několik volání metod a funguje konzistentně napříč všemi podporovanými verzemi EPS. Přístup také zachovává existující obsah stránek a další XMP struktury, takže můžete bezpečně řetězit více aktualizací metadat.

## Požadavky

- Základní znalost C# a struktury .NET projektu.  
- Visual Studio 2022 (nebo jakékoli kompatibilní IDE).  
- Knihovna Aspose.Page pro .NET. Pokud ji ještě nemáte, stáhněte ji ze **stránky ke stažení Aspose.Page pro .NET**([Aspose.Page for .NET download page](https://releases.aspose.com/page/net/)).  

## Importujte jmenné prostory

Následující jmenné prostory poskytují přístup k třídám pro práci s EPS v Aspose.Page, výstupem zařízení a XMP metadaty.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Krok 1: inicializujte vstupní stream EPS souboru

Vytvořte `FileStream` pro zdrojový EPS soubor a vytvořte objekt `PsDocument` pro práci s dokumentem.

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Krok 2: získejte XMP metadata

Získejte objekt `XmpMetadata` z dokumentu; tento objekt představuje vložený XMP paket.

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## Krok 3: změňte hodnoty XMP metadata

Použijte metodu `AddNamedValue` třídy `XmpMetadata` k vložení nové pojmenované hodnoty do určené XMP struktury.

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## Krok 4: uložte EPS soubor se změněnými XMP metadaty

Uložte upravený dokument zápisem do nového `FileStream`.

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## Proč použít Aspose.Page pro EPS metadata?

Aspose.Page podporuje **50+ XMP schémat** a může zpracovat EPS soubory až do **500 stránek**, přičemž spotřeba paměti zůstává pod **30 MB** pro typické dokumenty. Knihovna nevyužívá externí nástroje ani nativní kód, což zaručuje konzistentní chování napříč prostředí Windows, Linux a macOS.

## Běžné problémy a řešení

- **Chybějící XMP paket:** Pokud `GetXmpMetadata()` vrátí `null`, EPS soubor neobsahuje XMP blok. Knihovna jej automaticky vytvoří, ale ujistěte se, že soubor není poškozen.  
- **Konflikty jmenných prostorů:** Při přidávání vlastních pojmenovaných hodnot použijte jedinečnou URI jmenného prostoru, aby nedocházelo ke kolizím s existujícími schématy.  
- **Velké soubory:** U EPS souborů větších než 200 MB zvažte streamování výstupu, aby nedošlo k nadměrné spotřebě paměti.

## Často kladené otázky

**Q: Je Aspose.Page kompatibilní s různými verzemi EPS souborů?**  
A: Aspose.Page podporuje EPS verze 3.0 až 3.3, což zajišťuje širokou kompatibilitu se staršími i moderními soubory.

**Q: Mohu použít Aspose.Page pro komerční projekty?**  
A: Ano, pro produkční použití je vyžadována komerční licence. Licenci můžete zakoupit na **[Aspose.Page license purchase page](https://purchase.aspose.com/buy)**.

**Q: Je k dispozici bezplatná zkušební verze?**  
A: Ano, plně funkční zkušební verzi lze stáhnout na **[Aspose.Page free trial download page](https://releases.aspose.com/)**.

**Q: Jak získám podporu nebo se připojím ke komunitě?**  
A: Navštivte **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**, kde můžete klást otázky a sdílet zkušenosti.

**Q: Co je dočasná licence a jak ji získám?**  
A: Dočasná licence vám umožní produkt vyzkoušet po omezenou dobu. Můžete ji požádat na **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.

---

**Poslední aktualizace:** 2026-08-08  
**Testováno s:** Aspose.Page 24.11 pro .NET  
**Autor:** Aspose

## Související tutoriály

- [Přidat metadata do EPS dokumentu pomocí Aspose.Page pro .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Změnit pojmenovanou hodnotu pomocí Aspose.Page pro .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)
- [Extrahovat metadata z EPS dokumentu pomocí Aspose.Page pro .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}