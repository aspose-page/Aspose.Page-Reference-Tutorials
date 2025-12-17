---
date: 2025-12-17
description: Naučte se, jak přidávat Unicode text v Java PostScript pomocí Aspose.Page
  – krok za krokem průvodce, jak snadno přidávat Unicode řetězce.
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: Jak přidat Unicode text v Java PostScriptu pomocí Aspose.Page
url: /cs/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat Unicode text v Java PostScript pomocí Aspose.Page

## Úvod
Pokud se ptáte **jak přidat Unicode** znaky do workflow PostScript (nebo XPS) založeného na Javě, jste na správném místě. V tomto tutoriálu projdeme přesné kroky potřebné k vložení Unicode řetězců pomocí knihovny Aspose.Page pro Java. Na konci průvodce budete schopni vložit text v jakémkoli jazyce — arabštinu, čínštinu, emoji, cokoli — přímo do výstupu PostScript.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.Page for Java  
- **Mohu přidat skripty zprava doleva?** Ano, nastavte úroveň Bidi, jak je ukázáno v kódu  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; pro produkci je vyžadována komerční licence  
- **Které IDE je nejlepší?** Jakékoli Java IDE (IntelliJ IDEA, Eclipse, NetBeans)  
- **Je kód multiplatformní?** Naprosto — spusťte jej na Windows, macOS nebo Linuxu

## Co znamená „jak přidat Unicode“ v kontextu PostScriptu?
Přidání Unicode znamená vložení znaků, které jsou reprezentovány kódovými body mimo základní ASCII rozsah. Aspose.Page abstrahuje nízkoúrovňové detaily kódování, takže se můžete soustředit na samotný text a jeho vizuální umístění.

## Proč použít Aspose.Page pro Unicode text?
- **Plná podpora Unicode** – Zpracovává složité skripty, ligatury a jazyky zprava doleva.  
- **Žádné externí závislosti** – Není nutné ručně spravovat soubory fontů; API pracuje se systémovými fonty.  
- **Jednoduché API** – Stačí několik volání metod k vykreslení vícejazyčného textu.

## Předpoklady
Než se pustíme dál, ujistěte se, že máte připravené následující položky:

1. **Java Development Kit (JDK)** – Jakákoli recentní verze (8 nebo novější).  
2. **Aspose.Page for Java** – Stáhněte a nainstalujte knihovnu z [odkazu ke stažení](https://releases.aspose.com/page/java/).  
3. **IDE podle vašeho výběru** – IntelliJ IDEA, Eclipse nebo jakékoli jiné Java IDE, které preferujete.

## Import balíčků
Přidejte požadované třídy Aspose.Page do vašeho Java zdrojového souboru:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Krok 1: Nastavte svůj projekt
Vytvořte nový Java projekt, přidejte JAR Aspose.Page do cesty sestavení projektu a vytvořte složku, kam bude uložen vygenerovaný XPS soubor. Tato složka je později odkazována jako `dataDir`.

## Krok 2: Inicializujte XPS dokument
Vytvořte prázdný XPS dokument, který bude obsahovat obsah:

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Krok 3: Přidejte Unicode text
Nyní skutečně přidáme Unicode řetězec. Níže uvedený příklad zapisuje obrácenou frázi „AVAJ rof SPX.esopsA“, která obsahuje pouze ASCII znaky, ale můžete ji nahradit libovolným Unicode textem (např. arabské „مرحبا“ nebo čínské „你好”).

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

> **Tip:** Pro správné vykreslení jazyků zprava doleva nastavte `glyphs.setBidiLevel(1);`. Pro jazyky zleva doprava můžete tento řádek vynechat.

## Krok 4: Uložte dokument
Uložte XPS soubor na disk:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

Po spuštění programu otevřete vygenerovaný `AddEncodingText_out.xps` v libovolném XPS prohlížeči a uvidíte Unicode text vykreslený na zadaných souřadnicích.

## Časté problémy a řešení
| Problém | Důvod | Řešení |
|-------|--------|-----|
| Text se zobrazuje jako čtverečky | Font nebyl nalezen nebo nepodporuje znaky | Použijte font, který obsahuje požadované glyfy (např. “Arial Unicode MS”) |
| Text zprava doleva se zobrazuje zleva doprava | Úroveň Bidi není nastavena | Zavolejte `glyphs.setBidiLevel(1);` |
| Soubor se neuloží | Cesta `dataDir` je neplatná nebo chybí oprávnění k zápisu | Ujistěte se, že adresář existuje a aplikace má právo zapisovat |

## Často kladené otázky
### Mohu použít Aspose.Page pro Java s jinými programovacími jazyky?
Aspose.Page je primárně navržena pro Java, ale Aspose poskytuje knihovny pro různé programovací jazyky.

### Je k dispozici bezplatná zkušební verze?
Ano, bezplatnou zkušební verzi Aspose.Page získáte [zde](https://releases.aspose.com/).

### Kde mohu najít podporu a diskuze o Aspose.Page?
Navštivte [forum Aspose.Page](https://forum.aspose.com/c/page/39) pro podporu a diskuze.

### Jak mohu získat dočasnou licenci pro Aspose.Page?
Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

### Jaké jsou dostupné styly fontů v Aspose.Page?
Aspose.Page podporuje styly fontů jako Regular, Bold, Italic a BoldItalic.

## Závěr
Nyní ovládáte **jak přidat Unicode** text do Java PostScript (XPS) dokumentu pomocí Aspose.Page. Tato schopnost otevírá dveře k vícejazyčným reportům, internacionalizovaným fakturám a jakémukoli scénáři, kde jsou potřeba ne‑ASCII znaky. Neváhejte prozkoumat další funkce, jako je rotace textu, ořezové cesty nebo vkládání vlastních fontů — detaily najdete v oficiální [dokumentaci](https://reference.aspose.com/page/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2025-12-17  
**Testováno s:** Aspose.Page for Java 23.12 (nejnovější v době psaní)  
**Autor:** Aspose  

---