---
date: 2026-10-31
description: Naučte se, jak nastavit paint color a vyplnit ellipse v Java PostScript
  pomocí Aspose.Page. Tento průvodce ukazuje, jak vyplnit ellipse, nakreslit outline
  ellipse a nastavit stroke thickness s jasnými kroky kódu.
keywords:
- how to fill ellipse
- how to set paint color
- Aspose.Page Java ellipse
- PostScript drawing Java
lastmod: 2026-10-31
linktitle: Přidat ellipse v Java PostScript
og_description: Naučte se, jak vyplnit ellipse a nastavit paint color v Java PostScript
  pomocí Aspose.Page. Postupujte krok za krokem kódem pro kreslení vyplněných a obrysových
  ellipse během několika sekund.
og_image_alt: Developer guide showing how to fill ellipse and set paint color in Java
  PostScript with Aspose.Page
og_title: Jak vyplnit ellipse a nastavit paint color v Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  headline: How to fill ellipse and set paint color in Java PostScript
  type: TechArticle
- description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  name: How to fill ellipse and set paint color in Java PostScript
  steps:
  - name: Set up the PostScript document
    text: Create an output stream, configure page size, and instantiate a `PsDocument`.
      `PsDocument` is the core class that represents a PostScript file in memory.
      All drawing commands are routed through this object, and it handles page layout,
      resource management, and final file generation.
  - name: Fill ellipse – use set paint color
    text: To **fill ellipse**, you must first call `setPaint` with the desired fill
      color, then invoke `fill` with an `Ellipse2D` instance. `setPaint` sets the
      current drawing color used for subsequent fill or stroke operations. `Ellipse2D`
      defines the geometric bounds of the ellipse; its constructor takes th
  - name: Draw ellipse outline and set stroke thickness
    text: After filling, you can change the paint to a different color, define a `BasicStroke`
      to control line width, and draw the ellipse outline. `BasicStroke` specifies
      line width, dash pattern, and end‑cap style for drawing outlines. By adjusting
      its `width` property you control how bold the ellipse borde
  - name: Close and save the document
    text: Finalize the page and write the PostScript file to disk. Calling `document.close()`
      flushes all pending drawing commands and releases resources. The resulting `.ps`
      file can be opened with any PostScript viewer or converted to PDF. You now have
      a PostScript file that contains two ellipses—one filled
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to seamlessly integrate with other
      Java libraries.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Obtain a temporary license **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)**
      for testing purposes.
    question: How can I get a temporary license for Aspose.Page for Java?
  - answer: Absolutely! Visit **[the Aspose purchase page](https://purchase.aspose.com/buy)**
      to explore licensing options for commercial use.
    question: Is Aspose.Page suitable for commercial projects?
  - answer: Join the community at the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for discussions and assistance.
    question: Where can I seek help or discuss Aspose.Page‑related queries?
  - answer: Utilize the **[Aspose free trial page](https://releases.aspose.com/)**
      and explore examples in the documentation.
    question: Are there any free resources to learn more about Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript ellipse
- vector drawing
title: Jak vyplnit ellipse a nastavit paint color v Java PostScript
url: /cs/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vyplnit elipsu a nastavit barvu malby v Java PostScript

## Úvod
Pokud potřebujete **nastavit barvu malby** při kreslení vektorové grafiky, knihovna Aspose.Page pro Java vám poskytuje plnou kontrolu nad každým tah a výplní. V tomto tutoriálu se dozvíte, jak **nastavit barvu malby**, **vyplnit elipsu** a **nakreslit obrys elipsy** pomocí jednoduchého, krok za krokem přístupu. Na konci budete schopni přidat vysoce kvalitní PostScript elipsy do faktur, zpráv nebo jakéhokoli tisknutelného dokumentu.

## Rychlé odpovědi
- **Jaká knihovna je nejlepší pro kreslení PostScript grafiky v Javě?** Aspose.Page for Java.  
- **Mohu vyplnit elipsu plnou barvou?** Yes – use `document.setPaint(Color.YOUR_COLOR)` before `fill`.  
- **Jak nakreslím pouze obrys elipsy?** Set the paint and stroke, then call `document.draw(...)`.  
- **Potřebuji licenci pro produkční použití?** A commercial license is required; a temporary license is available for testing.  
- **Jaká verze Javy je podporována?** Any Java 8+ runtime works with the current Aspose.Page release.

## Co je PostScript elipsa?
PostScript elipsa je vektorový tvar definovaný ohraničujícím obdélníkem. Na rozdíl od rastrových obrázků se škáluje bez ztráty kvality, což ji činí ideální pro tisk ve vysokém rozlišení a konverzi do PDF. Protože je tvar popsán matematicky, může být vykreslen v jakékoli velikosti nebo rozlišení při zachování ostrých hran a hladkých křivek.

## Proč použít Aspose.Page k vytvoření PostScript elipsy?
Aspose.Page vám poskytuje deterministickou kontrolu nad každým kreslicím primitivem. Podporuje **3 hlavní operační systémy (Windows, Linux, macOS)**, **0 nativních závislostí** a dokáže vykreslit **50+ vektorových primitiv** za sekundu na typickém serveru. Knihovna je čistě Java, takže ji můžete vložit do jakékoli aplikace Java 8+ bez dalších nativních knihoven.

## Požadavky
Než začnete, ujistěte se, že máte:

1. Funkční vývojové prostředí Java (JDK 8 nebo novější).  
2. Knihovnu Aspose.Page pro Java přidanou do vašeho projektu. Můžete ji stáhnout **[z stránky vydání Aspose.Page pro Java](https://releases.aspose.com/page/java/)**.  

## Import balíčků
Ve vašem Java zdrojovém souboru importujte třídy potřebné pro kreslení a ukládání PostScript obsahu.

Balíček `java.awt` poskytuje základní grafické typy jako `Color`, `Ellipse2D` a `BasicStroke`. Balíček `com.aspose.page` poskytuje třídu `PsDocument`, která zapisuje PostScript výstup.

- **`Color`** – představuje sRGB barvu používanou pro malování.  
- **`Ellipse2D`** – popisuje tvar elipsy definovaný ohraničujícím obdélníkem.  
- **`BasicStroke`** – určuje šířku čáry, vzor čárkování a styl koncové čepičky pro kreslení obrysů.  
- **`PsDocument`** – představuje PostScript dokument a poskytuje metody pro kreslení grafiky a správu stránek.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Jak nastavit barvu malby pro elipsu
Prvním krokem je říci dokumentu, kterou barvu použít pro následující kreslicí operaci. Metoda `setPaint` nastaví plnou barvu, která bude aplikována buď na výplň, nebo na tah, v závislosti na následujícím volání.

### Krok 1: Nastavení PostScript dokumentu
Vytvořte výstupní stream, nastavte velikost stránky a vytvořte instanci `PsDocument`.

`PsDocument` je hlavní třída, která představuje PostScript soubor v paměti. Všechny kreslicí příkazy jsou směrovány přes tento objekt a on zajišťuje rozvržení stránky, správu zdrojů a finální generování souboru.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Krok 2: Vyplnit elipsu – použít nastavení barvy
Pro **vyplnění elipsy** musíte nejprve zavolat `setPaint` s požadovanou barvou výplně, poté vyvolat `fill` s instancí `Ellipse2D`.

`setPaint` nastaví aktuální kreslicí barvu používanou pro následné operace výplně nebo tahu.  
`Ellipse2D` definuje geometrické ohraničení elipsy; její konstruktor přijímá souřadnice X‑Y levého horního rohu plus šířku a výšku.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Krok 3: Nakreslit obrys elipsy a nastavit tloušťku tahu
Po vyplnění můžete změnit barvu malby na jinou, definovat `BasicStroke` pro řízení šířky čáry a nakreslit obrys elipsy.

`BasicStroke` určuje šířku čáry, vzor čárkování a styl koncové čepičky pro kreslení obrysů. Úpravou jeho vlastnosti `width` řídíte, jak silná se border elipsy jeví.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Krok 4: Zavřít a uložit dokument
Dokončete stránku a zapište PostScript soubor na disk.

Volání `document.close()` vyprázdní všechny čekající kreslicí příkazy a uvolní zdroje. Výsledný soubor `.ps` lze otevřít v libovolném PostScript prohlížeči nebo převést do PDF.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Nyní máte PostScript soubor, který obsahuje dvě elipsy — jednu vyplněnou oranžovou barvou a druhou s červeným obrysem. Klidně experimentujte s různými souřadnicemi, velikostmi a barvami, aby vyhovovaly vašim návrhovým potřebám.

## Časté úskalí a řešení problémů
- **Nesprávná cesta k souboru** – Ujistěte se, že `dataDir` končí oddělovačem (`/` nebo `\\`) vhodným pro váš OS.  
- **Chybějící licence** – Bez platné licence knihovna běží v evaluačním režimu a může přidávat vodoznaky.  
- **Barva se nepoužije** – Pamatujte nastavit `document.setPaint(...)` *před* každým voláním `fill` nebo `draw`; nastavení barvy se automaticky nepřetrvává mezi samostatnými operacemi.

## Často kladené otázky

**Q: Můžu použít Aspose.Page pro Java s jinými Java knihovnami?**  
A: Ano, Aspose.Page pro Java je navržena tak, aby se bez problémů integrovala s ostatními Java knihovnami.

**Q: Jak mohu získat dočasnou licenci pro Aspose.Page pro Java?**  
A: Získejte dočasnou licenci **[z Aspose stránky s dočasnou licencí](https://purchase.aspose.com/temporary-license/)** pro testovací účely.

**Q: Je Aspose.Page vhodná pro komerční projekty?**  
A: Rozhodně! Navštivte **[stránku nákupu Aspose](https://purchase.aspose.com/buy)** a prozkoumejte licenční možnosti pro komerční použití.

**Q: Kde mohu získat pomoc nebo diskutovat o dotazech souvisejících s Aspose.Page?**  
A: Připojte se ke komunitě na **[Aspose.Page fóru](https://forum.aspose.com/c/page/39)** pro diskuze a podporu.

**Q: Existují nějaké bezplatné zdroje pro další učení o Aspose.Page pro Java?**  
A: Využijte **[stránku s bezplatnou zkušební verzí Aspose](https://releases.aspose.com/)** a prozkoumejte příklady v dokumentaci.

## Závěr
Aspose.Page pro Java usnadňuje **nastavit barvu malby**, **vyplnit elipsu** a **nakreslit obrys elipsy** — ať už potřebujete jednoduchý vyplněný tvar nebo složitou grafiku s tahy. S výše uvedenými kroky můžete rychle přidat profesionální vektorovou grafiku do libovolného tisknutelného dokumentu. Pro podrobnější zkoumání — například kombinování více tvarů, aplikaci gradientů nebo konverzi do PDF — se podívejte na oficiální **[dokumentaci Aspose.Page Java](https://reference.aspose.com/page/java/)**.

---

**Poslední aktualizace:** 2026-10-31  
**Testováno s:** Aspose.Page for Java 24.11  
**Autor:** Aspose

## Související tutoriály

- [Jak nakreslit obdélník v Java PostScript pomocí Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [Jak přidat Unicode text v Java PostScript pomocí Aspose.Page](/page/java/postscript-text-manipulation/add-text-unicode/)
- [Vytvořit radiální gradient v PostScript pomocí Aspose.Page pro Java](/page/java/postscript-gradient-addition/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}