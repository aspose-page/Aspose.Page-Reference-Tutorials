---
date: 2026-02-15
description: Naučte se, jak přidat šrafovací vzor do souborů Java PostScript pomocí
  Aspose.Page Java. Tento krok‑za‑krokem průvodce ukazuje kompletní kód a tipy.
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: Jak přidat šrafovací vzor v Java PostScript pomocí Aspose.Page
url: /cs/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat šrafovací vzor v Java PostScriptu

## Úvod
Pokud pracujete s **Aspose.Page Java** a zajímá vás **jak přidat šrafovací vzor** do vašeho výstupu PostScript, šrafovací vzory jsou rychlé a flexibilní řešení. V tomto tutoriálu vás provedeme **jak přidat šrafovací** návrhy do dokumentu PostScript, vysvětlíme, proč jsou užitečné, a poskytneme kompletní, připravený k spuštění ukázkový kód. Na konci budete schopni vytvořit vizuálně atraktivní tvary a text vyplněné šrafou pouhými několika řádky Java.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.Page pro Java (SDK „aspose page java“).  
- **Jaký vizuální efekt přidáváme?** Šrafovací vzory (např. úhlopříčné čáry, křížová šrafura).  
- **Je potřeba licence pro spuštění ukázky?** Pro vývoj stačí bezplatná zkušební verze; licence je vyžadována pro produkční nasazení.  
- **Kolik řádků kódu?** Přibližně 70 řádků, rozdělených do přehledných kroků.  
- **Mohu použít stejný přístup pro PDF?** Ano — Aspose.Page podporuje více výstupních formátů, včetně PDF.

## Jak přidat šrafovací vzor – Přehled
Šrafovací vzory jsou vektorové textury, které se vykreslují čistě při jakémkoli rozlišení a dobře fungují na monochromatických tiskárnách. Pomocí Aspose.Page Java můžete tyto vzory aplikovat na tvary, cesty i text bez nutnosti pracovat s nízkoúrovňovými příkazy PostScript.

## Požadavky
Než začnete, ujistěte se, že máte:

- **Vývojové prostředí Java** — JDK 8 nebo vyšší a IDE dle vašeho výběru.  
- **Knihovnu Aspose.Page pro Java** — Stáhněte si nejnovější JAR z oficiálního webu [zde](https://releases.aspose.com/page/java/).  
- **Zápisový přístup** ke složce, kam bude vygenerovaný soubor PostScript uložen.

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
Vytvořte výstupní stream, nastavte velikost stránky (A4) a definujte několik proměnných rozvržení, které budou znovu použity při kreslení každého čtverce vyplněného šrafou.

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
Definujte znovupoužitelný obdélník, který bude představovat každou buňku vyplněnou šrafou.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Krok 4: Nastavení pera pro obrys čtverce vzoru
`BasicStroke` o tloušťce 2 body poskytne ostrý obrys kolem každého čtverce.

```java
BasicStroke stroke = new BasicStroke(2);
```

## Krok 5: Procházení šrafovacích vzorů
Projděte všechny hodnoty v enumeraci `HatchStyle`, vyplňte každý čtverec odpovídající texturou a poté vykreslete jeho obrys. Toto je jádro funkčnosti **přidání šrafovacího vzoru**.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Krok 6: Obnovení grafického stavu
Vraťte se do původního souřadnicového systému po dokončení kreslení mřížky čtverců.

```java
document.writeGraphicsRestore();
```

## Krok 7: Vyplnění textu šrafovacím vzorem
Zde ukazujeme, jak namalovat text pomocí šrafovací textury. Příklad vyplní slovo „ABC“ vzorem diagonální křížové šrafy.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Krok 8: Obrys textu šrafovacím vzorem
Nyní obkreslíme stejný text, tentokrát s 70 % šrafovacím stylem a silnějším perem.

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

Postupujte podle těchto kroků a získáte soubor PostScript, který představuje kompletní sadu šrafovacích vzorů aplikovaných jak na tvary, tak na text — vše poháněno **aspose page java**.

## Proč používat šrafovací vzory s Aspose.Page Java?
- **Vizuelní odlišení** — Šrafované výplně fungují i při tisku na monochromatické výstupy.  
- **Výkon** — Textury se generují za běhu, takže se vyhnete velkým souborům s obrázky.  
- **Podpora napříč formáty** — Stejný kód může cílit na PDF, EPS nebo SVG s minimálními úpravami.

## Časté problémy a tipy
- **Chyby v cestě k souboru** — Ujistěte se, že `dataDir` končí správným oddělovačem souborů (`/` nebo `\`).  
- **Nesprávné barvy** — Některé starší interprety PostScriptu nemusí podporovat určité barevné prostory; pro maximální kompatibilitu používejte základní RGB.  
- **Upozornění na licenci** — Spuštění ukázky bez platné licence vloží vodoznak do výstupu.

## Závěr
Začlenění šrafovacích vzorů může výrazně zlepšit čitelnost a estetiku technických výkresů, map nebo jakékoli grafiky generované v Javě. S **Aspose.Page Java** získáte stručné API, které abstrahuje nízkoúrovňové příkazy PostScript, takže se můžete soustředit na design místo na detaily formátu souboru. Nyní už víte, **jak přidat šrafovací vzor** do svých dokumentů PostScript — experimentujte s různými hodnotami `HatchStyle` a vytvořte přesně ten vzhled, který potřebujete.

## Často kladené otázky

**Q: Mohu použít Aspose.Page Java s jinými Java frameworky?**  
A: Ano, knihovna je nezávislá na frameworku a funguje se Spring, Jakarta EE, Android (omezeně) i čistým Java SE.

**Q: Je k dispozici zkušební verze Aspose.Page Java?**  
A: Samozřejmě. Stáhněte si bezplatnou 30‑denní zkušební verzi [zde](https://releases.aspose.com/).

**Q: Jak získám dočasnou licenci pro vývoj?**  
A: Požádejte o dočasnou licenci [zde](https://purchase.aspose.com/temporary-license/). Odstraní vodotisk z výstupu.

**Q: Kde najdu další tutoriály a podporu komunity?**  
A: Navštivte oficiální fórum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) pro další příklady a otázky‑odpovědi.

**Q: Existuje komplexní dokumentace ke všem třídám a metodám?**  
A: Ano, úplná reference API je k dispozici [zde](https://reference.aspose.com/page/java/).

**Q: Mohu renderovat stejný šrafovací vzor do PDF místo PostScriptu?**  
A: Rozhodně. Změňte `PsSaveOptions` na `PdfSaveOptions` (nebo ekvivalent) a zbytek kódu zůstane beze změny.

**Q: Co dělat, když je vygenerovaný soubor prázdný?**  
A: Ověřte, že výstupní stream ukazuje na zapisovatelný adresář a že je po všech kreslících operacích zavoláno `document.save()`.

---

**Poslední aktualizace:** 2026-02-15  
**Testováno s:** Aspose.Page pro Java 24.12 (nejnovější v době psaní)  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}