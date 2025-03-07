---
title: Změňte hodnoty pomocí Aspose.Page pro .NET
linktitle: Změnit hodnoty
second_title: Aspose.Page .NET API
description: Zvládněte manipulaci se soubory EPS pomocí Aspose.Page pro .NET. Měňte hodnoty metadat XMP bez námahy.
weight: 17
url: /cs/net/eps-metadata-management/modify-eps-metadata-change-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Změňte hodnoty pomocí Aspose.Page pro .NET

## Úvod

V dynamickém světě zpracování dokumentů vyniká Aspose.Page for .NET jako výkonný nástroj, který vývojářům nabízí možnost bez námahy manipulovat se soubory EPS. V tomto tutoriálu se ponoříme do procesu změny hodnot v souborech EPS pomocí Aspose.Page for .NET. Ať už jste zkušený vývojář nebo zvědavý začátečník, tento podrobný průvodce vás vybaví dovednostmi potřebnými k efektivní úpravě metadat XMP ve vašich souborech EPS.

## Předpoklady

Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:

### 1. Aspose.Page for .NET Library

Ujistěte se, že máte ve svém vývojovém prostředí nainstalovanou knihovnu Aspose.Page for .NET. Pokud ne, můžete si jej stáhnout[tady](https://releases.aspose.com/page/net/).

### 2. Adresář dokumentů

Nastavte adresář pro vaše dokumenty. Toto bude umístění, kde jsou uloženy vaše soubory EPS.

Nyní, když máme naše předpoklady seřazeny, přejděme k dalším zásadním krokům.

## Import jmenných prostorů

V každém projektu .NET je nezbytné importovat potřebné jmenné prostory, aby bylo možné využívat funkce Aspose.Page. Můžete to udělat takto:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Krok 1: Inicializujte vstupní proud souboru EPS

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";
// Inicializujte vstupní proud souboru EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

## Krok 2: Vytvořte instanci PsDocument ze streamu

```csharp
//Vytvořte instanci PsDocument ze streamu
PsDocument document = new PsDocument(psStream);
```

Nyní, když jsme připravili scénu, pojďme k jádru našeho tutoriálu – změně hodnot metadat XMP v souboru EPS.

## Krok 3: Získejte metadata XMP

```csharp
// Získejte metadata XMP. Pokud soubor EPS neobsahuje metadata XMP, získáme nový soubor vyplněný hodnotami z komentářů k metadatům PS (%%Creator, %%CreateDate, %%Title atd.)
XmpMetadata xmp = document.GetXmpMetadata();
```

## Krok 4: Upravte hodnoty metadat XMP

Nyní změňme některé klíčové hodnoty v metadatech XMP:

### Krok 4.1: Změňte hodnotu ModifyDate

```csharp
// Změňte hodnotu ModifyDate
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

### Krok 4.2: Změňte hodnotu Creator

```csharp
// Změňte hodnotu Creator
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### Krok 4.3: Změňte hodnotu titulku

```csharp
// Změňte hodnotu názvu
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

Po provedených změnách přejdeme k poslednímu kroku – uložení upraveného souboru EPS.

## Krok 5: Uložte soubor EPS se změněnými metadaty XMP

### Krok 5.1: Vytvořte výstupní proud

```csharp
// Vytvořte výstupní proud
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

### Krok 5.2: Uložte soubor EPS

```csharp
// Uložit soubor EPS
document.Save(outPsStream);
```

Nakonec zavřete vstupní stream:

```csharp
finally
{
    psStream.Close();
}
```

Gratulujeme! Úspěšně jste upravili hodnoty metadat XMP v souboru EPS pomocí Aspose.Page for .NET.

## Závěr

V tomto tutoriálu jsme prozkoumali bezproblémový proces změny hodnot v souborech EPS pomocí Aspose.Page for .NET. Jako vývojář máte nyní k dispozici výkonný nástroj pro efektivní manipulaci s dokumenty.

## FAQ

### Q1: Mohu použít Aspose.Page pro .NET s jinými formáty souborů?

A1: Aspose.Page se primárně zaměřuje na manipulaci se soubory EPS. Pro další formáty prozkoumejte rozmanitou řadu produktů Aspose.

### Q2: Je k dispozici zkušební verze?

 A2: Ano, můžete vyzkoušet Aspose.Page for .NET s dostupnou bezplatnou zkušební verzí[tady](https://releases.aspose.com/).

### Q3: Kde najdu podrobnou dokumentaci?

 A3: Komplexní dokumentaci lze nalézt[tady](https://reference.aspose.com/page/net/).

### Q4: Jak získám dočasnou licenci?

 A4: Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).

### Q5: Mohu zakoupit Aspose.Page pro .NET?

 A5: Rozhodně! Navštivte stránku nákupu[tady](https://purchase.aspose.com/buy) pro licenční možnosti.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
