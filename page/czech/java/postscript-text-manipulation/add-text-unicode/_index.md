---
date: 2025-12-13
description: Naučte se, jak přidat text na ASP stránku v Javě, nastavit styl písma
  v Javě a jak přidat Unicode text pomocí Aspose.Page. Postupujte podle našeho krok‑za‑krokem
  průvodce.
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: asp stránka přidat text – Unicode v Java PostScriptu
url: /cs/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# asp page add text – Unicode v Java PostScript

## Úvod
Pokud potřebujete **asp page add text** v pracovním postupu Java PostScript a zároveň zachovat Unicode znaky, jste na správném místě. V tomto tutoriálu si projdeme přidání Unicode textu, nastavení stylu písma a uložení výsledku pomocí **Aspose.Page for Java**. Na konci pochopíte, jak nastavit font style java a jak efektivně přidat unicode text ve svých projektech.

## Rychlé odpovědi
- **Která knihovna dokáže přidat Unicode text v Java PostScript?** Aspose.Page for Java.  
- **Která hlavní metoda přidává text?** `doc.addGlyphs(...)` s objektem `XpsGlyphs`.  
- **Potřebuji speciální písmo pro Unicode?** Jakékoli TrueType/OpenType písmo, které podporuje požadované kódy (např. Arial).  
- **Mohu změnit styl písma?** Ano, pomocí `XpsFontStyle` (Regular, Bold, Italic, atd.).  
- **Je licence vyžadována pro produkční použití?** Ano, pro ne‑zkušební použití je potřeba platná licence Aspose.Page.

## Co je asp page add text?
`asp page add text` označuje proces vkládání textových řetězců do PostScript nebo XPS dokumentu pomocí API Aspose.Page. API abstrahuje nízkoúrovňové PostScript příkazy a umožňuje pracovat s vysoceúrovňovými objekty jako `XpsGlyphs`.

## Proč použít Aspose.Page k nastavení font style java a přidání Unicode textu?
- **Plná podpora Unicode** – Zpracovává skripty zleva doprava i složité glyfy.  
- **Jednoduché API** – Jednořádkové volání pro přidání textu a aplikaci stylů.  
- **Cross‑platform** – Funguje v jakémkoli Java‑kompatibilním prostředí.  
- **Žádné externí závislosti** – Není potřeba další renderovací engine.

## Požadavky
Než se pustíme do tutoriálu, ujistěte se, že máte připravené následující:

1. **Java Development Kit (JDK)** – Ověřte, že je Java nainstalována na vašem počítači.  
2. **Aspose.Page for Java** – Stáhněte a nainstalujte knihovnu Aspose.Page z [download link](https://releases.aspose.com/page/java/).  
3. **Integrované vývojové prostředí (IDE)** – Vyberte si preferované Java IDE, např. IntelliJ IDEA nebo Eclipse.

## Import balíčků
Ve svém Java projektu importujte potřebné balíčky pro Aspose.Page. Přidejte následující řádky do kódu:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Krok 1: Nastavení projektu
Vytvořte nový Java projekt ve svém IDE a nastavte strukturu projektu. Ujistěte se, že knihovna Aspose.Page je zahrnuta v závislostech projektu.

## Krok 2: Inicializace XPS dokumentu
Začněte inicializací nového XPS dokumentu ve vašem projektu:

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Krok 3: Přidání Unicode textu
Nyní přidejme Unicode text do vašeho XPS dokumentu pomocí knihovny Aspose.Page. Použijte následující úryvek kódu:

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

Tento úsek kódu přidá Unicode text **"AVAJ rof SPX.esopsA"** do XPS dokumentu na souřadnice (400, 200) se zadaným písmem a stylem. Všimněte si, že volání `setBidiLevel(1)` umožňuje renderování zprava doleva pro správné zobrazení Unicode.

## Krok 4: Uložení dokumentu
Uložte výsledný XPS dokument pomocí následujícího kódu:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

## Závěr
Gratulujeme! Úspěšně jste provedli **asp page add text** a nastavili styl písma v Java PostScript scénáři pomocí Aspose.Page. Tato metoda vám poskytuje detailní kontrolu nad renderováním Unicode a stylizací, což je ideální pro internacionalizované zprávy, faktury a grafiku.

Prozkoumejte další funkce a možnosti Aspose.Page v [documentation](https://reference.aspose.com/page/java/).

## Často kladené otázky

**Q:** Můžu použít Aspose.Page pro Java i s jinými programovacími jazyky?  
**A:** Aspose.Page je primárně navržena pro Java, ale Aspose poskytuje knihovny pro různé programovací jazyky.

**Q:** Je k dispozici bezplatná zkušební verze?  
**A:** Ano, bezplatnou zkušební verzi Aspose.Page získáte [zde](https://releases.aspose.com/).

**Q:** Kde najdu podporu a diskuze o Aspose.Page?  
**A:** Navštivte [Aspose.Page forum](https://forum.aspose.com/c/page/39) pro podporu a diskuze.

**Q:** Jak získat dočasnou licenci pro Aspose.Page?  
**A:** Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

**Q:** Jaké styly písma jsou v Aspose.Page k dispozici?  
**A:** Aspose.Page podporuje styly písma jako Regular, Bold, Italic a BoldItalic.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-13  
**Tested With:** Aspose.Page for Java (latest)  
**Author:** Aspose  

---