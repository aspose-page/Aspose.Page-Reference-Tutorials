---
date: 2026-01-12
description: Naučte se, jak vytvářet dokumenty PostScript v .NET pomocí Aspose.Page.
  Tento krok‑za‑krokem průvodce ukazuje, jak vytvořit soubory PostScript, nastavit
  velikost stránky PostScript a přizpůsobit okraje pro bezproblémovou integraci.
linktitle: Create PostScript Document
second_title: Aspose.Page .NET API
title: Jak vytvořit dokument PostScript pomocí Aspose.Page pro .NET
url: /cs/net/document-creation/create-postscript-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit dokument PostScript pomocí Aspose.Page pro .NET

## Úvod

Vítejte! V tomto komplexním tutoriálu se dozvíte **jak programově vytvořit dokumenty PostScript** pomocí Aspose.Page pro .NET. Ať už generujete faktury, přepravní štítky nebo jakýkoli vektorový tiskový výstup, tento průvodce vás provede každým krokem – od nastavení prostředí až po uložení finálního souboru *.ps*. Ponořme se a uvidíme, jak snadno lze vytvořit vysoce kvalitní soubor PostScript pomocí několika řádků C#.

## Rychlé odpovědi
- **Jaká knihovna potřebuji?** Aspose.Page for .NET  
- **Mohu nastavit velikost stránky?** Ano – použijte `options.PageSize` (viz „nastavit velikost stránky PostScript“).  
- **Potřebuji licenci pro vývoj?** Pro testování stačí bezplatná zkušební verze; pro produkci je licence vyžadována.  
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Jak dlouho trvá implementace?** Obvykle méně než 10 minut pro základní dokument.

## Co je „jak vytvořit PostScript“ v .NET?
Aspose.Page poskytuje bohaté API, které abstrahuje nízkoúrovňovou syntaxi EPS/PostScript, takže se můžete soustředit na rozvržení stránky, grafiku a text. Použitím knihovny se vyhnete ručnímu PS kódu a získáte podporu pro fonty, obrázky a přesná měření.

## Proč použít Aspose.Page pro tvorbu PostScriptu?
- **Plná kontrola** nad rozměry stránky, okraji a kreslicími primitivy.  
- **Žádné externí závislosti** – vše běží uvnitř vašeho .NET procesu.  
- **Cross‑platform** podpora pro Windows, Linux a macOS.  
- **Robustní správa fontů**, včetně vlastních složek s fonty.

## Požadavky

- Aspose.Page for .NET Library: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Page for .NET. Můžete ji stáhnout [zde](https://releases.aspose.com/page/net/).
- .NET Environment: Zajistěte, aby byl na vašem počítači nastaven funkční .NET environment.
- Text Editor nebo IDE: Použijte svůj oblíbený textový editor nebo integrované vývojové prostředí (IDE) pro psaní kódu.

Nyní, když máme vše připravené, začněme vytvářet dokument.

## Importovat jmenné prostory

Nejprve importujte jmenné prostory, které poskytují přístup k základním třídám Aspose.Page.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.IO;
```

Tyto jmenné prostory zpřístupňují třídy `PsDocument`, `PsSaveOptions` a pomocné třídy používané v celém tutoriálu.

## Krok 1: Nastavit adresář dokumentu

```csharp
string dir = "Your Document Directory";
```

Nahraďte `"Your Document Directory"` absolutní nebo relativní cestou, kam chcete uložit finální soubor **PostScript**.

## Krok 2: Vytvořit výstupní stream

```csharp
using (Stream outPsStream = new FileStream(dir + "document.ps", FileMode.Create))
```

`FileStream` otevře zapisovatelný stream s názvem **document.ps**. Všechny následující kreslicí příkazy budou do tohoto streamu zapisovány.

## Krok 3: Vytvořit možnosti uložení

```csharp
PsSaveOptions options = new PsSaveOptions();
```

`PsSaveOptions` vám umožňuje nastavit, jak bude dokument vykreslen a uložen.

## Krok 4: Nastavit velikost stránky PostScript a okraje

```csharp
options.PageSize = PageConstants.GetSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT);
options.Margins = PageConstants.GetMargins(PageConstants.MARGINS_ZERO);
```

Zde **nastavujeme velikost stránky PostScript** na formát A4 na výšku a odstraňujeme všechny okraje. Můžete nahradit `SIZE_A4` jinými konstantami (např. `SIZE_LETTER`) podle požadavků na rozvržení.

## Krok 5: Nastavit další složky s fonty

```csharp
options.AdditionalFontsFolders = new string[] { dir };
```

Pokud váš dokument používá vlastní fonty, které nejsou nainstalovány v systému, nasměrujte Aspose.Page na složku obsahující tyto soubory fontů.

## Krok 6: Vytvořit vícestránkový dokument

```csharp
bool multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

Instance `PsDocument` představuje dokument PostScript. Nastavením `multiPaged` na `false` vytvoříte jednostránkový dokument (pro vícestránkový výstup můžete nastavit `true`).

## Krok 7: Zavřít a uložit

```csharp
document.ClosePage();
document.Save();
```

Volání `ClosePage()` dokončí obsah stránky a `Save()` zapíše kompletní PostScript stream na disk.

Gratulujeme! Právě jste se naučili **jak vytvořit PostScript** dokumenty pomocí Aspose.Page pro .NET.

## Časté problémy a řešení

- **Chyby v cestě souboru** – Ujistěte se, že proměnná `dir` končí oddělovačem cesty (`\` nebo `/`) nebo použijte `Path.Combine`.
- **Chybějící fonty** – Pokud se text zobrazuje výchozími fonty, ověřte, že `options.AdditionalFontsFolders` ukazuje na správný adresář.
- **Nesprávná velikost stránky** – Zkontrolujte konstanty předávané do `PageConstants.GetSize`; můžete také zadat vlastní rozměry pomocí `new SizeF(width, height)`.

## Často kladené otázky

### Q1: Kde najdu dokumentaci k Aspose.Page pro .NET?
A1: Dokumentace je k dispozici [zde](https://reference.aspose.com/page/net/).

### Q2: Jak si mohu stáhnout Aspose.Page pro .NET?
A2: Můžete si ji stáhnout z [tohoto odkazu](https://releases.aspose.com/page/net/).

### Q3: Kde mohu zakoupit licenci pro Aspose.Page pro .NET?
A3: Licenci můžete zakoupit [zde](https://purchase.aspose.com/buy).

### Q4: Je k dispozici bezplatná zkušební verze Aspose.Page pro .NET?
A4: Ano, bezplatnou zkušební verzi najdete [zde](https://releases.aspose.com/).

### Q5: Jak získám dočasnou licenci pro Aspose.Page pro .NET?
A5: Dočasnou licenci získáte [zde](https://purchase.aspose.com/temporary-license/).

### Q6: Mohu generovat vícestránkové soubory PostScript?
A6: Rozhodně. Nastavte `bool multiPaged = true` při konstrukci `PsDocument` a voláním `document.NewPage()` vytvoříte další stránky.

### Q7: Podporuje Aspose.Page správu barev?
A7: Ano, můžete vložit ICC profily pomocí `PsSaveOptions.ColorProfile`, pokud je to potřeba.

---

**Poslední aktualizace:** 2026-01-12  
**Testováno s:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}