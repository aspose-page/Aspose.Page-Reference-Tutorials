---
date: 2026-01-28
description: Naučte se, jak převést EPS na PNG pomocí Aspose.Page pro .NET a použít
  licenci s měřeným poplatkem pro bezproblémové zpracování dokumentů.
linktitle: Apply Metered License
second_title: Aspose.Page .NET API
title: Převod EPS na PNG a použití měřené licence s Aspose.Page pro .NET
url: /cs/net/getting-started/apply-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převod EPS na PNG a aplikace měřené licence pomocí Aspose.Page pro .NET

## Úvod

Odemkněte plný potenciál Aspose.Page pro .NET **převodem EPS na PNG** a aplikací měřené licence. Tento tutoriál vás provede každým krokem – od načtení souboru EPS po jeho uložení jako obrázek PNG – abyste mohli efektivně zpracovávat dokumenty bez hodnotících vodoznaků.

## Rychlé odpovědi
- **Co tento tutoriál pokrývá?** Převod souborů EPS na obrázky PNG a aplikace měřené licence s Aspose.Page pro .NET.  
- **Potřebuji licenci?** Ano, pro produkční použití je vyžadována měřená licence.  
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Jak dlouho trvá implementace?** Přibližně 10–15 minut pro základní převod.  
- **Mohu to spustit na Linuxu/macOS?** Rozhodně – Aspose.Page je multiplatformní.

## Co je „převod EPS na PNG“?
Převod EPS na PNG znamená rasterizaci vektorového souboru Encapsulated PostScript (EPS) do bitmapového obrázku PNG. To je užitečné, když potřebujete zobrazit nebo vložit grafiku do webových stránek, reportů nebo UI komponent, které EPS nepodporují.

## Proč použít měřenou licenci pro převod EPS na obrázek?
Měřená licence vám umožní platit jen za stránky, které zpracujete, což je ideální pro pracovní zátěže s proměnlivým objemem. Navíc odstraňuje červený hodnotící banner, který se objevuje při používání bezplatné zkušební verze, a zajišťuje čistý výstup pro koncové uživatele.

## Předpoklady

Předtím, než se pustíte do kroků, ujistěte se, že máte následující:

- Platná licence Aspose.Page pro .NET: Můžete ji získat na [purchase.aspose.com](https://purchase.aspose.com/buy).
- Knihovna Aspose.Page nainstalována: Pro pokyny k instalaci se podívejte na [dokumentaci](https://reference.aspose.com/page/net/).
- Vývojové prostředí .NET: Ujistěte se, že máte na svém počítači nastavené funkční .NET prostředí.

## Importování jmenných prostorů

Ve vašem .NET projektu importujte potřebné jmenné prostory pro přístup k funkcionalitám Aspose.Page:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

## Jak převést EPS na PNG s měřenou licencí?

Níže je podrobný průvodce, který pokrývá vše, co potřebujete vědět.

### Krok 1: Nastavte veřejný a soukromý klíč měřené licence

Inicializujte třídu `Aspose.Page.Metered` a nastavte veřejný a soukromý klíč. Nahraďte `<type public key here>` a `<type private key here>` vašimi skutečnými klíči.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

### Krok 2: Načtěte soubor EPS a vytvořte dokument

Zadejte cestu k vašemu souboru EPS a vytvořte stream pro načtení jeho obsahu. Poté vytvořte instanci třídy `PsDocument` ze streamu.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

### Krok 3: Převod EPS na PNG obrázek

Vytvořte `ImageDevice` pro převod souboru EPS na PNG obrázek. Uložte EPS soubor jako obrázek pomocí `ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

### Krok 4: Získání bajtů obrázku

Získejte bajty obrázku, kde každý pole bajtů představuje jednu stránku. V tomto případě máme jednu stránku.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

### Krok 5: Uložení bajtů obrázku do souboru

Uložte bajty obrázku do souboru, čímž zajistíte úspěšný převod z EPS na PNG.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

### Krok 6: Ověření měřené licence

Vizuelně zkontrolujte, zda je měřená licence úspěšně aplikována. Pokud výsledný obrázek neobsahuje červenou hodnotící zprávu, licence byla aplikována bez problémů.

Nyní jste připraveni využít plný potenciál Aspose.Page pro .NET s měřenou licencí!

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|---------|---------|--------|
| Červený hodnotící banner se stále zobrazuje | Licence není nastavena nebo jsou špatné klíče | Zkontrolujte veřejný/soukromý klíč a ujistěte se, že `SetMeteredKey` je voláno před jakýmkoli zpracováním dokumentu |
| Nebyl vytvořen výstupní soubor | Nesprávná cesta `dataDir` nebo oprávnění k souborům | Ověřte, že adresář existuje a aplikace má oprávnění k zápisu |
| Více stránek nebylo uloženo | Byla zapsána pouze první stránka | Procházejte `imagesBytes` a každé pole uložte do samostatného PNG souboru |

## Často kladené otázky

**Q: Mohu použít měřenou licenci v CI/CD pipeline?**  
A: Ano, můžete klíče bezpečně uložit (např. do proměnných prostředí) a volat `SetMeteredKey` během procesu sestavení.

**Q: Podporuje Aspose.Page zachování barevného profilu při převodu do PNG?**  
A: Výstup PNG zachovává původní barevné informace, ale můžete jej dále přizpůsobit pomocí `ImageSaveOptions`.

**Q: Je možné převést EPS do jiných rastrových formátů (JPEG, BMP)?**  
A: Rozhodně – stačí změnit `ImageSaveOptions` na požadovaný formát.

**Q: Jaká je maximální velikost podporovaného souboru EPS?**  
A: Aspose.Page zvládá velké soubory, ale spotřeba paměti roste s rozlišením obrázku. Pro velmi velké dokumenty zvažte zpracování jednotlivých stránek.

**Q: Jak mohu programově zjistit počet stránek v souboru EPS?**  
A: Použijte `document.PagesCount` po načtení `PsDocument`.

## FAQ's

### Q1: Jak získat měřenou licenci pro Aspose.Page pro .NET?

A1: Navštivte [purchase.aspose.com](https://purchase.aspose.com/buy) a získejte platnou licenci.

### Q2: Kde najdu dokumentaci pro Aspose.Page pro .NET?

A2: Podívejte se na [Aspose.Page .NET](https://reference.aspose.com/page/net/) pro komplexní dokumentaci.

### Q3: Existuje fórum pro diskuse a podporu Aspose.Page?

A3: Ano, navštivte [forum](https://forum.aspose.com/c/page/39) a zapojte se do komunity a požádejte o pomoc.

### Q4: Můžu vyzkoušet Aspose.Page pro .NET před zakoupením?

A4: Rozhodně! Získejte bezplatnou zkušební verzi na [zde](https://releases.aspose.com/).

### Q5: Jak získat dočasnou licenci pro Aspose.Page pro .NET?

A5: Navštivte [temporary license/](https://purchase.aspose.com/temporary-license/) a získejte dočasnou licenci.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

---

**Poslední aktualizace:** 2026-01-28  
**Testováno s:** Aspose.Page 24.12 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}