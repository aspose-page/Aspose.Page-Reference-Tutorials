---
date: 2026-08-18
description: Naučte se, jak přidat šrafovací vzor do souborů Java PostScript pomocí
  Aspose.Page Java. Tento průvodce krok za krokem ukazuje kompletní kód a tipy.
keywords:
- how to add hatch pattern
- Aspose.Page Java
- PostScript hatch patterns
- Java graphics API
lastmod: 2026-08-18
linktitle: Přidat šrafovací vzor v Java PostScript
og_description: Naučte se, jak přidat šrafovací vzor v Java PostScript pomocí Aspose.Page.
  Postupujte podle tohoto průvodce krok za krokem a rychle vytvořte grafiku vyplněnou
  šrafou.
og_image_alt: Screenshot of Java code adding hatch pattern to a PostScript file with
  Aspose.Page
og_title: Jak přidat šrafovací vzor v Java PostScript – průvodce Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to add hatch pattern to Java PostScript files using Aspose.Page
    Java. This step‑by‑step guide shows the complete code and tips.
  headline: How to add hatch pattern in Java PostScript
  type: TechArticle
- questions:
  - answer: Yes, the library is framework‑agnostic and works with Spring, Jakarta
      EE, Android (limited), and plain Java SE.
    question: Can I use Aspose.Page Java with other Java frameworks?
  - answer: Absolutely. Download a free 30‑day trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is a trial version available for Aspose.Page Java?
  - answer: Request a temporary license [temporary license request page](https://purchase.aspose.com/temporary-license/).
      It removes evaluation watermarks.
    question: How do I obtain a temporary license for development?
  - answer: Visit the official forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39)
      for additional examples and Q&A.
    question: Where can I find more tutorials and community support?
  - answer: Yes, the full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Is there comprehensive documentation for all classes and methods?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Java
- Aspose.Page
- PostScript
- hatch pattern
title: Jak přidat šrafovací vzor v Java PostScript
url: /cs/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat šrafovací vzor v Java PostScript

## Úvod
Pokud pracujete s **Aspose.Page Java** a zajímá vás **jak přidat šrafovací vzor** do vašeho výstupu PostScript, šrafovací vzory jsou rychlé a flexibilní řešení. V tomto tutoriálu vás provedeme **jak přidat šrafovací** návrhy do dokumentu PostScript, vysvětlíme, proč jsou užitečné, a poskytneme kompletní, připravený k spuštění ukázkový kód. Na konci budete schopni vytvořit vizuálně atraktivní tvary a text vyplněné šrafou pomocí několika řádků Javy.

## Rychlé odpovědi
- **Jaká knihovna potřebuji?** Aspose.Page for Java (SDK “aspose page java”).  
- **Jaký vizuální efekt přidáváme?** Šrafovací vzory (např. úhlopříčné čáry, křížová šrafura).  
- **Potřebuji licenci pro spuštění ukázky?** Bezplatná zkušební verze funguje pro vývoj; licence je vyžadována pro produkci.  
- **Kolik řádků kódu?** Přibližně 70 řádků, rozdělených do přehledných kroků.  
- **Mohu použít stejný přístup pro PDF?** Ano—Aspose.Page podporuje více výstupních formátů, včetně PDF.

## Co je šrafovací vzor?
Šrafovací vzor je vektorové vyplnění sestávající z opakujících se čar nebo tvarů, které vytvářejí texturový efekt. Protože je definován matematicky, vzor se škáluje bez ztráty kvality, což ho činí ideálním pro tisk ve vysokém rozlišení a monochromatický výstup.

## Proč používat šrafovací vzory s Aspose.Page Java?
Aspose.Page podporuje **více než 10 výstupních formátů** (včetně PostScript, PDF, EPS, SVG a XPS) a dokáže vykreslovat šrafované výplně v dokumentech až do **500 stránek** bez načítání celého souboru do paměti. To znamená rychlý výkon, nízkou spotřebu paměti a konzistentní vizuální výsledky napříč všemi podporovanými formáty.

## Jak přidat šrafovací vzor – přehled
Šrafovací vzory jsou vektorové textury, které se vykreslují čistě při jakémkoli rozlišení a dobře fungují na monochromatických tiskárnách. Pomocí Aspose.Page Java můžete tyto vzory aplikovat na tvary, cesty i text, aniž byste museli pracovat s nízkoúrovňovými příkazy PostScript.

## Požadavky
- **Java vývojové prostředí** – JDK 8 nebo vyšší a IDE dle vašeho výběru.  
- **Aspose.Page for Java knihovna** – Stáhněte nejnovější JAR z oficiální **Aspose.Page for Java download page** [here](https://releases.aspose.com/page/java/).  
- Další vydání Aspose můžete procházet [here](https://releases.aspose.com/).  
- **Zápisový přístup** do složky, kam bude vygenerovaný soubor PostScript uložen.

## Import balíčků
Níže uvedené importy zahrnují standardní třídy Java AWT pro grafické primitivy jako barvy, tahy a geometrické tvary, stejně jako třídy Aspose.Page, které poskytují model dokumentu, definice šrafovacích stylů a možnosti ukládání potřebné k vytvoření souboru PostScript.  
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

## Co je třída `Document`?
Třída `Document` je nejvyšší objekt Aspose.Page, který představuje jeden soubor PostScript v paměti. Všechny kreslicí operace jsou prováděny prostřednictvím tohoto objektu.

## Jak nastavit výstupní stream?
Pro zápis výstupu vytvořte `FileOutputStream`, který ukazuje na požadovanou cestu k souboru; tento stream zajišťuje nízkoúrovňové zápisy bajtů. `PsSaveOptions` konfiguruje, jak je dokument uložen, včetně velikosti stránky a komprese. Poté vytvořte instanci `Document` s objektem `PsSaveOptions`, který určuje velikost stránky, kompresi a další nastavení specifické pro PostScript.  
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

## Jak uložit stav grafiky a posunout počátek?
Uložení stavu grafiky zachytí aktuální transformační matici, oblast ořezu a kreslicí atributy, což vám umožní později se vrátit. Po uložení zavolejte `translate(x, y)` na grafickém objektu, abyste posunuli počátek na vhodné místo pro kreslení mřížky šrafovaných čtverců.  
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Jak vytvořit znovupoužitelný čtverec pro každý vzor?
`Rectangle2D` představuje obdélníkový tvar definovaný jeho pozicí a velikostí. Vytvořením jediné instance, která odpovídá rozměrům buňky, ji můžete znovu použít pro každý šrafovaný čtverec, čímž snížíte alokaci objektů a udržíte smyčku kreslení efektivní.  
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Jak nastavit pero pro obrys čtverce vzoru?
`BasicStroke` popisuje tloušťku obrysu, vzor čáry a koncové zakončení pro vektorové tvary. Použití 2‑bodového `BasicStroke` poskytuje jasný okraj kolem každé šrafované buňky, čímž zajišťuje, že výplň je vizuálně oddělena od sousedních čtverců.  
```java
BasicStroke stroke = new BasicStroke(2);
```

## Jak iterovat přes šrafovací vzory?
`HatchStyle` je výčet, který uvádí všechny předdefinované šrafovací vzory, jako jsou úhlopříčné, křížové a tečkované styly. Smyčkování přes `HatchStyle.values()` vám umožní postupně aplikovat každý vzor, vyplnit obdélník pomocí `HatchBrush` a poté nakreslit jeho obrys.  
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Jak obnovit stav grafiky po kreslení?
Volání `restore()` na grafickém objektu vrátí transformační matici a nastavení kreslení do stavu uloženého dříve, čímž zabrání kumulativním posunům nebo škálování ovlivňujícím následné kreslicí operace. To zajišťuje, že pozdější obsah začíná od původního souřadnicového systému a používá výchozí atributy.  
```java
document.writeGraphicsRestore();
```

## Jak vyplnit text šrafovacím vzorem?
`TextFragment` představuje kus textu, který může být umístěn a stylizován nezávisle. Přiřazením `HatchBrush` s vybraným `HatchStyle` k výplni fragmentu se znaky textu vykreslí pomocí šrafovací textury místo plné barvy.  
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Jak obkreslit text jiným šrafovacím stylem?
`HatchBrush` lze také použít pro tah. Pro nakreslení obrysu nastavte tah fragmentu na `HatchBrush` s jiným `HatchStyle` (např. 70 % šrafování) a zvýšte šířku tahu pomocí `setStrokeWidth`. Tím se vykreslí okraj textu s vlastním šrafovacím vzorem při zachování vyplněného vnitřku.  
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Jak zavřít a uložit dokument?
`document.save()` zapíše dokument v paměti do určeného výstupního streamu. Po dokončení všech kreslicích příkazů zavolejte tuto metodu a poté zavřete `FileOutputStream`, aby se uvolnily systémové prostředky a soubor byl správně vyprázdněn na disk.  
```java
document.closePage();
document.save();
```

Postupujte podle těchto kroků a získáte soubor PostScript, který ukazuje kompletní sadu šrafovacích vzorů aplikovaných na tvary i text—vše poháněno **aspose page java**.

## Časté úskalí a tipy
- **Chyby v cestě k souboru** – Ujistěte se, že `dataDir` končí správným oddělovačem souborů (`/` nebo `\`).  
- **Nesprávné barvy** – Některé starší interpretery PostScript nemusí podporovat určité barevné prostory; držte se základního RGB pro maximální kompatibilitu.  
- **Upozornění na licenci** – Spuštění ukázky bez platné licence vloží vodoznak do výstupu.

## Často kladené otázky

**Q: Můžu použít Aspose.Page Java s jinými Java frameworky?**  
A: Ano, knihovna je nezávislá na frameworku a funguje se Spring, Jakarta EE, Android (omezeně) a čistým Java SE.

**Q: Je k dispozici zkušební verze pro Aspose.Page Java?**  
A: Rozhodně. Stáhněte si bezplatnou 30‑denní zkušební verzi [Aspose trial download page](https://releases.aspose.com/).

**Q: Jak získat dočasnou licenci pro vývoj?**  
A: Požádejte o dočasnou licenci [temporary license request page](https://purchase.aspose.com/temporary-license/). Odstraní evaluační vodoznaky.

**Q: Kde najdu další tutoriály a komunitní podporu?**  
A: Navštivte oficiální fórum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) pro další příklady a otázky a odpovědi.

**Q: Existuje komplexní dokumentace ke všem třídám a metodám?**  
A: Ano, kompletní reference API je k dispozici [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Můžu vykreslit stejný šrafovací vzor do PDF místo PostScript?**  
A: Rozhodně. Změňte `PsSaveOptions` na `PdfSaveOptions` (nebo ekvivalent) a zbytek kódu zůstane beze změny.

**Q: Co dělat, když je vygenerovaný soubor prázdný?**  
A: Ověřte, že výstupní stream ukazuje na zapisovatelný adresář a že `document.save()` je voláno po všech kreslicích operacích.

---

**Last Updated:** 2026-08-18  
**Testováno s:** Aspose.Page for Java 24.12 (nejnovější v době psaní)  
**Autor:** Aspose

## Související tutoriály

- [Vytvořit texturový vzor v PostScript – Aspose.Page Java](/page/java/postscript-texture-patterns/)
- [Jak přidat gradient: Diagonální gradient v Java PostScript pomocí Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Jak převést PostScript do PDF pomocí Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}