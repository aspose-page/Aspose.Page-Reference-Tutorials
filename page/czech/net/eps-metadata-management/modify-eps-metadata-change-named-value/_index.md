---
title: Změňte pojmenovanou hodnotu pomocí Aspose.Page pro .NET
linktitle: Změnit pojmenovanou hodnotu
second_title: Aspose.Page .NET API
description: Naučte se, jak změnit pojmenované hodnoty v souborech EPS pomocí Aspose.Page for .NET. Přizpůsobte si metadata XMP bez námahy pro zpracování dokumentů na míru.
weight: 16
url: /cs/net/eps-metadata-management/modify-eps-metadata-change-named-value/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Změňte pojmenovanou hodnotu pomocí Aspose.Page pro .NET

## Úvod

Ve světě zpracování dokumentů vyniká Aspose.Page for .NET jako výkonný nástroj pro manipulaci se soubory EPS. Jednou z klíčových funkcí, které nabízí, je možnost měnit pojmenované hodnoty v rámci metadat XMP. Tento tutoriál vás provede procesem změny pojmenované hodnoty pomocí Aspose.Page for .NET a umožní vám přizpůsobit soubory EPS podle vašich konkrétních potřeb.

## Předpoklady

Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:

-  Aspose.Page for .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Page for .NET. Pokud ne, můžete si jej stáhnout[tady](https://releases.aspose.com/page/net/).

- Adresář dokumentů: Mějte určený adresář pro soubory EPS, kde můžete provádět změny pojmenovaných hodnot.

## Import jmenných prostorů

Ve svém projektu .NET musíte importovat potřebné jmenné prostory pro přístup k funkcím poskytovaným Aspose.Page. Přidejte do svého kódu následující jmenné prostory:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Pojďme si nyní kód rozdělit do několika kroků pro komplexní pochopení:

## Krok 1: Inicializujte vstupní datový proud souboru EPS

```csharp
// Start: 1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// Rozšíření: 1
```

tomto kroku nastavíme vstupní proud pro soubor EPS, který chcete upravit. Nezapomeňte nahradit „Adresář vašich dokumentů“ skutečnou cestou k adresáři vašich dokumentů.

## Krok 2: Získejte metadata XMP

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

Načtěte existující metadata XMP ze souboru EPS. Pokud soubor EPS neobsahuje metadata XMP, vygeneruje se nová s hodnotami z komentářů metadat PS.

## Krok 3: Změňte hodnoty metadat XMP

```csharp
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

Zde demonstrujeme změnu dvou pojmenovaných hodnot ve struktuře "xmpTPg:MaxPageSize". To si můžete přizpůsobit podle svých konkrétních požadavků.

## Krok 4: Uložte soubor EPS se změněnými metadaty XMP

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

Uložte upravený soubor EPS do výstupního proudu. Soubor nyní bude odrážet změny provedené v metadatech XMP.

## Závěr

V tomto tutoriálu jste se naučili, jak využít Aspose.Page for .NET ke změně pojmenovaných hodnot v metadatech XMP v souborech EPS. Tato funkce otevírá svět možností přizpůsobení a přizpůsobení dokumentů tak, aby splňovaly specifické požadavky.

## FAQ

### Q1: Mohu použít Aspose.Page pro .NET s jinými formáty dokumentů?

Odpověď 1: Ano, Aspose.Page podporuje různé formáty dokumentů, včetně EPS, XPS a PDF.

### Q2: Je k dispozici zkušební verze pro Aspose.Page pro .NET?

 A2: Ano, máte přístup k bezplatné zkušební verzi[tady](https://releases.aspose.com/).

### Q3: Kde najdu další dokumentaci na Aspose.Page pro .NET?

 A3: Viz dokumentace[tady](https://reference.aspose.com/page/net/).

### Q4: Jak mohu získat dočasnou licenci pro Aspose.Page for .NET?

 A4: Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).

### Q5: Jaké možnosti podpory jsou k dispozici pro uživatele Aspose.Page pro .NET?

 A5: Navštivte fórum komunity[tady](https://forum.aspose.com/c/page/39) za podporu a diskuze.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
