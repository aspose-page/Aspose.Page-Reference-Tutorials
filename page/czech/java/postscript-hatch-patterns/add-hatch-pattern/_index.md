---
date: 2025-12-08
description: Naučte se, jak přidávat šrafovací vzory do dokumentů Java PostScript
  pomocí Aspose.Page Java. Tento krok‑za‑krokem průvodce vám ukáže, jak efektivně
  přidávat grafiku se šrafovacími vzory.
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: 'Aspose.Page Java: Přidat šrafovací vzor v Java PostScriptu'
url: /cs/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání šachovnicového vzoru v Java PostScriptu

## Úvod
Pokud pracujete s **Aspose.Page Java** a potřebujete obohatit výstup PostScriptu o texturovanou grafiku, šachovnicové vzory jsou rychlé a flexibilní řešení. V tomto tutoriálu vás provedeme **tím, jak přidat šachovnicové** návrhy do dokumentu PostScript, vysvětlíme, proč jsou užitečné, a poskytneme kompletní, připravený k běhu ukázkový kód. Na konci budete schopni vytvořit vizuálně atraktivní tvary a text vyplněné šachovnicovým vzorem pomocí několika řádků Java.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.Page pro Java (SDK „aspose page java“).  
- **Jaký vizuální efekt přidáváme?** Šachovnicové vzory (např. úhlopříčné čáry, křížové šachovnice).  
- **Potřebuji licenci pro spuštění ukázky?** Pro vývoj stačí bezplatná zkušební verze; pro produkci je licence vyžadována.  
- **Kolik řádků kódu?** Přibližně 70 řádků, rozdělených do přehledných kroků.  
- **Lze stejný přístup použít i pro PDF?** Ano — Aspose.Page podporuje více výstupních formátů, včetně PDF.

## Požadavky
Než začnete, ujistěte se, že máte:

- **Vývojové prostředí Java** — JDK 8 nebo novější a IDE dle vašeho výběru.  
- **Knihovnu Aspose.Page pro Java** — Stáhněte nejnovější JAR z oficiálního webu [​zde​](https://releases.aspose.com/page/java/).  
- **Zápisová práva** do složky, kam bude vygenerovaný soubor PostScript uložen.

## Import balíčků
Nejprve přidejte požadované třídy do svého projektu. Tyto importy vám umožní pracovat s kreslícími primitivy, správou barev a API Aspose.Page.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Krok 1: Nastavení počátečních parametrů
Vytvořte výstupní stream, nastavte velikost stránky (A4) a definujte několik proměnných rozvržení, které budou znovu použity při kreslení každého čtverce vyplněného šachovnicí.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## Krok 2: Uložení grafického stavu a translace
Uložení grafického stavu nám umožní později se vrátit k původnímu souřadnicovému systému, zatímco `translate` posune počátek na pohodlný výchozí bod.

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Krok 3: Vytvoření čtverce pro každý vzor
Definujte znovupoužitelný obdélník, který bude představovat každou buňku vyplněnou šachovnicí.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Krok 4: Nastavení pera pro obrys čtverce vzoru
`BasicStroke` o tloušťce 2 body poskytne ostrý obrys kolem každého čtverce.

```java
BasicStroke stroke = new BasicStroke(2);
```

## Krok 5: Procházení šachovnicových vzorů
Projděte všechny hodnoty výčtu `HatchStyle`, vyplňte každý čtverec odpovídající texturou a poté vykreslete jeho obrys. Toto je jádro **přidávání šachovnicového vzoru**.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Krok 6: Obnovení grafického stavu
Vraťte se k původnímu souřadnicovému systému po dokončení kreslení mřížky čtverců.

```java
document.writeGraphicsRestore();
```

## Krok 7: Vyplnění textu šachovnicovým vzorem
Zde ukazujeme, jak namalovat text pomocí šachovnicové textury. Příklad vyplní slovo „ABC“ úhlopříčným křížovým vzorem.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Krok 8: Obrys textu šachovnicovým vzorem
Nyní obkreslíme stejný text, tentokrát s 70 % šachovnicovým stylem a silnějším perem.

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Krok 9: Uzavření a uložení dokumentu
Dokončete stránku, zapište soubor na disk a uvolněte prostředky.

```java
document.closePage();
document.save();
```

Postupujte podle těchto kroků a získáte soubor PostScript, který předvádí kompletní sadu šachovnicových vzorů aplikovaných jak na tvary, tak na text — vše poháněno **aspose page java**.

## Proč používat šachovnicové vzory s Aspose.Page Java?
- **Vizuelní odlišení** — Šachovnicové výplně fungují i při tisku černobílým výstupem.  
- **Výkon** — Textury se generují za běhu, takže se vyhnete velkým souborům obrázků.  
- **Podpora napříč formáty** — Stejný kód může cílit na PDF, EPS nebo SVG s minimálními úpravami.

## Časté problémy a tipy
- **Chyby v cestě k souboru** — Ujistěte se, že `dataDir` končí správným oddělovačem souborů (`/` nebo `\`).  
- **Není podporována barva** — Starší interprety PostScriptu nemusí zvládat některé barevné prostory; pro maximální kompatibilitu používejte základní RGB.  
- **Upozornění na licenci** — Spuštění ukázky bez platné licence vloží vodoznak do výstupu.

## Závěr
Začlenění šachovnicových vzorů může výrazně zlepšit čitelnost a estetiku technických výkresů, map nebo jakékoli grafiky generované v Javě. S **Aspose.Page Java** získáte stručné API, které abstrahuje nízkoúrovňové příkazy PostScriptu, takže se můžete soustředit na design místo na drobnosti formátu souboru.

## Často kladené otázky

**Q: Mohu použít Aspose.Page Java s jinými Java frameworky?**  
A: Ano, knihovna je nezávislá na frameworku a funguje se Spring, Jakarta EE, Android (omezeně) i čistým Java SE.

**Q: Je k dispozici zkušební verze Aspose.Page Java?**  
A: Samozřejmě. Stáhněte si bezplatnou 30‑denní zkušební verzi [​zde​](https://releases.aspose.com/).

**Q: Jak získám dočasnou licenci pro vývoj?**  
A: Požádejte o dočasnou licenci [​zde​](https://purchase.aspose.com/temporary-license/). Odstraní vodotisk z evaluace.

**Q: Kde najdu další tutoriály a podporu komunity?**  
A: Navštivte oficiální fórum [​forum Aspose.Page pro Java​](https://forum.aspose.com/c/page/39) pro další příklady a otázky‑odpovědi.

**Q: Existuje komplexní dokumentace ke všem třídám a metodám?**  
A: Ano, úplná reference API je k dispozici [​zde​](https://reference.aspose.com/page/java/).

---

**Poslední aktualizace:** 2025-12-08  
**Testováno s:** Aspose.Page pro Java 24.12 (nejnovější v době psaní)  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
