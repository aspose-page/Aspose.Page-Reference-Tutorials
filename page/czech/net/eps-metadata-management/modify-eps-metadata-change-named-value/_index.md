---
date: 2026-01-25
description: Naučte se, jak nastavit XMP a změnit pojmenovanou hodnotu v souborech
  EPS pomocí Aspose.Page pro .NET. Přizpůsobte metadata XMP snadno pro individuální
  zpracování dokumentů.
linktitle: Change Named Value
second_title: Aspose.Page .NET API
title: Jak nastavit XMP a změnit pojmenovanou hodnotu pomocí Aspose.Page pro .NET
url: /cs/net/eps-metadata-management/modify-eps-metadata-change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak nastavit XMP a změnit pojmenovanou hodnotu pomocí Aspose.Page pro .NET

## Úvod

Pokud potřebujete **nastavit XMP** informace uvnitř souboru EPS a také **změnit pojmenovanou hodnotu** v jeho metadatech, jste na správném místě. V tomto tutoriálu projdeme reálný scénář, kde upravujete XMP metadata pomocí Aspose.Page pro .NET, což vám poskytne plnou kontrolu nad vlastnostmi dokumentu, značkováním a následným zpracováním.

## Rychlé odpovědi
- **Co je XMP?** Standardizovaný formát pro vkládání metadat do grafických a dokumentových souborů.  
- **Proč měnit pojmenovanou hodnotu?** Pro aktualizaci konkrétních polí metadat, jako je velikost stránky nebo vlastní značky, aniž byste přepisovali celý soubor.  
- **Která knihovna pomáhá?** Aspose.Page pro .NET poskytuje jednoduché API pro oba úkoly.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro testování; pro produkci je vyžadována komerční licence.  
- **Podporované platformy?** .NET Framework, .NET Core a .NET 5/6+.

## Předpoklady

Než se ponoříte do tutoriálu, ujistěte se, že máte následující předpoklady připravené:

- Aspose.Page pro .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Page pro .NET. Pokud ne, můžete ji stáhnout [zde](https://releases.aspose.com/page/net/).
- Dokumentový adresář: Mějte určený adresář pro vaše soubory EPS, kde můžete provádět změny pojmenovaných hodnot.

## Importujte jmenné prostory

Ve vašem .NET projektu musíte importovat potřebné jmenné prostory, abyste získali přístup k funkcionalitě poskytované Aspose.Page. Přidejte následující jmenné prostory do svého kódu:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Nyní rozdělíme kód do několika kroků pro komplexní pochopení:

## Krok 1: Inicializace vstupního streamu EPS souboru

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// ExEnd:1
```

V tomto kroku nastavíme vstupní stream pro EPS soubor, který chcete upravit. Ujistěte se, že nahradíte „Your Document Directory“ skutečnou cestou k vašemu dokumentovému adresáři.

## Krok 2: Získání XMP metadat

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

Získá existující XMP metadata z EPS souboru. Pokud EPS soubor neobsahuje XMP metadata, bude vytvořeno nové s hodnotami z PS metadatových komentářů.

## Krok 3: Změna hodnot XMP metadat

```csharp
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

Zde ukazujeme, jak **změnit pojmenované hodnoty** v rámci struktury `xmpTPg:MaxPageSize`. Můžete přizpůsobit názvy vlastností a hodnoty podle svých požadavků na metadata.

## Krok 4: Uložení EPS souboru se změněnými XMP metadaty

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

Uložte upravený EPS soubor do výstupního streamu. Soubor nyní bude odrážet provedené změny v XMP metadatech.

## Časté problémy a řešení

- **Chybí sekce XMP** – Pokud zdrojový EPS neobsahuje žádné XMP, Aspose.Page automaticky vytvoří minimální XMP blok. Poté můžete přidat své vlastní pojmenované hodnoty, jak je uvedeno výše.
- **Nesprávná předpona jmenného prostoru** – Ujistěte se, že jmenný prostor (např. `xmpTPg`) odpovídá tomu, který je přítomen v původních metadatech; jinak API bude považovat za novou vlastnost.
- **Chyby přístupu k souboru** – Ověřte, že aplikace má oprávnění ke čtení/zápisu do adresáře, který specifikujete v `dataDir`.

## Často kladené otázky

**Q: Mohu používat Aspose.Page pro .NET s jinými formáty dokumentů?**  
A: Ano, Aspose.Page podporuje různé formáty dokumentů, včetně EPS, XPS a PDF.

**Q: Je k dispozici zkušební verze pro Aspose.Page pro .NET?**  
A: Ano, můžete získat bezplatnou zkušební verzi [zde](https://releases.aspose.com/).

**Q: Kde mohu najít další dokumentaci k Aspose.Page pro .NET?**  
A: Odkazujte se na dokumentaci [zde](https://reference.aspose.com/page/net/).

**Q: Jak mohu získat dočasnou licenci pro Aspose.Page pro .NET?**  
A: Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

**Q: Jaké možnosti podpory jsou k dispozici pro uživatele Aspose.Page pro .NET?**  
A: Navštivte komunitní fórum [zde](https://forum.aspose.com/c/page/39) pro podporu a diskuze.

---

**Poslední aktualizace:** 2026-01-25  
**Testováno s:** Aspose.Page 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}