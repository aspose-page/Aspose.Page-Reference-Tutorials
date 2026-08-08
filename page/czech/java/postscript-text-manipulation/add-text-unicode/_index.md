---
date: 2026-05-20
description: Naučte se, jak přidat Unicode text v Java PostScript pomocí Aspose.Page
  – krok za krokem průvodce, jak snadno přidávat Unicode řetězce.
keywords:
- how to add unicode
- java add arabic text
- java add chinese text
linktitle: Přidat text pomocí Unicode řetězce v Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add Unicode text in Java PostScript using Aspose.Page
    – a step‑by‑step guide on how to add unicode strings effortlessly.
  headline: How to Add Unicode Text in Java PostScript with Aspose.Page
  type: TechArticle
- description: Learn how to add Unicode text in Java PostScript using Aspose.Page
    – a step‑by‑step guide on how to add unicode strings effortlessly.
  name: How to Add Unicode Text in Java PostScript with Aspose.Page
  steps:
  - name: '**Java Development Kit (JDK)** – Any recent version (8 or newer).'
    text: '**Java Development Kit (JDK)** – Any recent version (8 or newer).'
  - name: '**Aspose.Page for Java** – Download and install the library from the [download
      link](https://releases.aspose.com/page/java/). You can also browse all releases
      [here](https://releases.aspose.com/).'
    text: '**Aspose.Page for Java** – Download and install the library from the [download
      link](https://releases.aspose.com/page/java/). You can also browse all releases
      [here](https://releases.aspose.com/).'
  - name: '**IDE of your choice** – IntelliJ IDEA, Eclipse, or any other Java IDE
      you prefer.'
    text: '**IDE of your choice** – IntelliJ IDEA, Eclipse, or any other Java IDE
      you prefer.'
  type: HowTo
- questions:
  - answer: Aspose.Page is built specifically for Java, but Aspose offers equivalent
      libraries for .NET, C++, and Python if you need cross‑language support.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can access a free trial of Aspose.Page [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      help, samples, and troubleshooting tips.
    question: Where can I find support and community discussions?
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for testing?
  - answer: The API supports Regular, Bold, Italic, and BoldItalic styles for any
      TrueType or OpenType font you load.
    question: What font styles does Aspose.Page support?
  type: FAQPage
second_title: Aspose.Page Java API
title: Jak přidat Unicode text v Java PostScript pomocí Aspose.Page
url: /cs/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat Unicode text v Java PostScript s Aspose.Page

## Úvod
Pokud se ptáte, **jak přidat Unicode** znaky do Java‑založeného PostScript (nebo XPS) workflow, jste na správném místě. V tomto tutoriálu projdeme přesné kroky potřebné k vložení Unicode řetězců pomocí knihovny Aspose.Page pro Java. Na konci průvodce budete schopni vložit libovolný jazyk‑specifický text — arabštinu, čínštinu, emoji, cokoliv — přímo do vašeho PostScript výstupu.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.Page for Java  
- **Mohu přidat skripty zprava doleva?** Ano, nastavte úroveň Bidi, jak je ukázáno v kódu  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; pro produkci je vyžadována komerční licence  
- **Které IDE je nejlepší?** Jakékoli Java IDE (IntelliJ IDEA, Eclipse, NetBeans)  
- **Je kód multiplatformní?** Ano – můžete jej spustit na Windows, macOS nebo Linuxu  

## Co znamená „jak přidat Unicode“ v kontextu PostScriptu?
Přidání Unicode textu znamená vložení znaků, jejichž kódové body leží mimo základní ASCII rozsah — například arabština, čínština nebo emoji — do PostScript (nebo XPS) dokumentu pomocí Aspose.Page. Knihovna automaticky mapuje tyto kódové body na odpovídající glyfy ve vybraném písmu, zajišťuje složité tvarování, ligatury a pořadí zprava doleva bez nutnosti ručního kódování.

## Proč použít Aspose.Page pro Unicode text?
Aspose.Page vám poskytuje spolehlivé, 100 % čistě‑Java řešení, které podporuje **více než 50 vstupních a výstupních formátů** a dokáže vykreslit vícejazyčný text v dokumentech až do 1 000 stran, aniž by načítalo celý soubor do paměti. Eliminujete tak potřebu externích utilit pro správu fontů, zkrátíte vývojový čas o 70 % a garantujete konzistentní vizuální výstup napříč Windows, macOS a Linux prostředími.

## Předpoklady
Než se pustíme dál, ujistěte se, že máte připravené následující položky:

1. **Java Development Kit (JDK)** – Jakákoli aktuální verze (8 nebo novější).  
2. **Aspose.Page for Java** – Stáhněte a nainstalujte knihovnu z [odkazu ke stažení](https://releases.aspose.com/page/java/). Všechny verze můžete procházet také [zde](https://releases.aspose.com/).  
3. **IDE podle vašeho výběru** – IntelliJ IDEA, Eclipse nebo jakékoli jiné Java IDE, které preferujete.

## Importovat balíčky
Přidejte požadované třídy Aspose.Page do vašeho Java zdrojového souboru:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Krok 1: Nastavte svůj projekt
Vytvořte nový Java projekt, přidejte Aspose.Page JAR do cesty sestavení projektu a vytvořte složku, kam bude uložen generovaný XPS soubor. Tato složka bude později odkazována jako `dataDir`.

## Krok 2: Inicializovat XPS dokument
Třída `XpsDocument` představuje XPS soubor v paměti a poskytuje plátno pro všechny kreslicí operace.

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Krok 3: Přidat Unicode text
Nyní skutečně přidáme Unicode řetězec. Níže uvedený příklad zapisuje obrácenou frázi „AVAJ rof SPX.esopsA“, která obsahuje jen ASCII znaky, ale můžete ji nahradit libovolným Unicode textem (např. arabsky „مرحبا“ nebo čínsky „你好“). Takto **java add arabic text** nebo **java add chinese text** do vašeho dokumentu.

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

> **Tip:** Pro správné vykreslení jazyků zprava doleva nastavte `glyphs.setBidiLevel(1);`. Pro jazyky zleva doprava můžete tento řádek vynechat.

## Krok 4: Uložit dokument
Uložte XPS soubor na disk:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

Po spuštění programu otevřete vygenerovaný `AddEncodingText_out.xps` v libovolném XPS prohlížeči a uvidíte Unicode text vykreslený na zadaných souřadnicích.

## Běžné problémy a řešení
| Problém | Důvod | Řešení |
|-------|--------|-----|
| Text se zobrazuje jako čtverečky | Písmo nebylo nalezeno nebo nepodporuje znaky | Použijte písmo, které obsahuje požadované glyfy (např. „Arial Unicode MS“) |
| Text zprava doleva se zobrazuje zleva doprava | Úroveň Bidi není nastavena | Zavolejte `glyphs.setBidiLevel(1);` |
| Soubor nebyl uložen | Cesta `dataDir` je neplatná nebo chybí oprávnění k zápisu | Ujistěte se, že adresář existuje a aplikace má oprávnění k zápisu |

## Často kladené otázky
**Q: Mohu použít Aspose.Page pro Java s jinými programovacími jazyky?**  
A: Aspose.Page je vytvořeno speciálně pro Java, ale Aspose nabízí ekvivalentní knihovny pro .NET, C++ a Python, pokud potřebujete podporu napříč jazyky.

**Q: Je k dispozici bezplatná zkušební verze?**  
A: Ano, můžete získat bezplatnou zkušební verzi Aspose.Page [zde](https://releases.aspose.com/).

**Q: Kde najdu podporu a diskuse komunity?**  
A: Navštivte [forum Aspose.Page](https://forum.aspose.com/c/page/39) pro pomoc, ukázky a tipy na řešení problémů.

**Q: Jak získám dočasnou licenci pro testování?**  
A: Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

**Q: Jaké styly písem Aspose.Page podporuje?**  
A: API podporuje styly Regular, Bold, Italic a BoldItalic pro jakékoli TrueType nebo OpenType písmo, které načtete.

## Závěr
Nyní ovládáte **jak přidat Unicode** text do Java PostScript (XPS) dokumentu pomocí Aspose.Page. Tato schopnost otevírá dveře k vícejazyčným reportům, internacionalizovaným fakturám a jakémukoli scénáři, kde jsou potřeba ne‑ASCII znaky. Neváhejte prozkoumat další funkce, jako je rotace textu, ořezové cesty nebo vložení vlastních fontů — detaily najdete v oficiální [dokumentaci](https://reference.aspose.com/page/java/).

---

**Poslední aktualizace:** 2026-05-20  
**Testováno s:** Aspose.Page for Java 23.12 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Jak přidat text v PostScriptu s Aspose.Page pro Java](/page/java/postscript-text-manipulation/)
- [Nastavit barvu textu v Javě s Aspose.Page – Průvodce manipulací s textem](/page/java/postscript-text-manipulation/add-text/)
- [Přidat stránky v PostScriptu Java – Bezproblémový průvodce s Aspose.Page](/page/java/postscript-page-manipulation/add-pages1/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}