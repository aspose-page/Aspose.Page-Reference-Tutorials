---
date: 2025-12-14
description: Naučte se, jak nastavit barvu textu v Javě pomocí Aspose.Page pro Javu,
  přidat text do PostScriptu a použít obrys textu pro bohaté formátování dokumentů.
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: Nastavení barvy textu v Javě s Aspose.Page – Průvodce manipulací s textem
url: /cs/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení barvy textu v Javě s Aspose.Page – Průvodce manipulací s textem

## Úvod
Vítejte v našem podrobném průvodci o **set text color java** při práci se soubory PostScript pomocí Aspose.Page pro Javu. Aspose.Page pro Javu je výkonná knihovna, která umožňuje vývojářům vytvářet a **generate postscript file** dokumenty, manipulovat s fonty a stylovat text s přesností. V tomto tutoriálu se naučíte, jak přidat text, změnit jeho barvu, upravit velikost a dokonce **apply stroke text** pro profesionální vzhled.

## Rychlé odpovědi
- **Která knihovna mi umožní nastavit barvu textu v Javě?** Aspose.Page for Java.
- **Mohu používat systémové fonty i vlastní fonty?** Yes, both are supported.
- **Jak změním velikost textu?** By specifying the font size when creating the `Font` or `DrFont`.
- **Je možné najednou obkreslit a vyplnit text?** Absolutely – use `fillAndStrokeText`.
- **Jaký výstupní formát tento tutoriál vytváří?** A PostScript (`.ps`) document.

## Co je “set text color java”?
Nastavení barvy textu v Javě znamená definování objektu `Color`, který vykreslovací engine (zde Aspose.Page) používá při kreslení znaků na stránku. Tato operace je nezbytná pro vytváření vizuálně odlišných dokumentů, zejména při programovém generování **postscript documents**.

## Proč používat Aspose.Page pro Javu?
- **Full control** nad generováním PostScriptu bez potřeby nativního interpretu PostScriptu.
- **Support for both system and external fonts**, umožňující vložit jakoukoliv typografii, kterou potřebujete.
- **Easy API** pro vyplnění, obkreslení a **fill and stroke text**, poskytující flexibilitu ve stylování.
- **Cross‑platform** kompatibilita – napište jednou, spusťte kdekoliv, kde běží Java.

## Požadavky
- Základní znalost programování v Javě.
- Knihovna Aspose.Page pro Javu nainstalována. Můžete si ji stáhnout ze [Aspose.Page for Java download page](https://releases.aspose.com/page/java/).
- Potřebné fonty jsou k dispozici ve specifikovaném adresáři. Další podrobnosti jsou v [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).

## Import balíčků
In your Java project, import the necessary packages for Aspose.Page for Java:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```

## Krok 1: Nastavení dokumentu
Nejprve vytvoříme nový **PostScript document** a nakonfigurujeme výstupní možnosti.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// A text to write to PS file
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Jak nastavit barvu textu v Javě pomocí systémového fontu
Nyní ukazujeme **set text color java** s fontem poskytnutým systémem.

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **Tip:** Metoda `fillText` automaticky používá aktuální barvu, pokud nepředáte argument `Color`, který ve výchozím nastavení je černý.

## Použití vlastního fontu a změna velikosti textu
Můžete také **change text size** a použít vlastní font uložený ve vaší složce s fonty.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Obkreslení (Stroke) textu – Apply Stroke Text
Obkreslení textu mu dává ostrý okraj. Zde **apply stroke text** pomocí `BasicStroke`.

```java
// Using system font for outlining text
document.outlineText(str, font, 50, 300);
// Outline text with blue‑violet colored 2‑points width pen
Stroke stroke = new BasicStroke(2);
Color strokeColor = new Color(138, 43, 226); // blue‑violet
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```

## Obkreslení textu s vlastním fontem
Stejná technika funguje s vlastními fonty.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Krok 6: Uložení dokumentu
Nakonec zavřete stránku a zapište soubor na disk.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Časté problémy a řešení
| Problém | Řešení |
|-------|----------|
| **Font nebyl nalezen** | Ensure the font file is placed in `necessary_fonts` and the folder path is correctly added via `options.setAdditionalFontsFolders`. |
| **Barva nebyla použita** | Verify you are calling the overload of `fillText` or `outlineText` that includes a `Color` argument. |
| **Obrys je příliš tenký** | Increase the `BasicStroke` width (e.g., `new BasicStroke(3)`). |
| **Dokument se neotevírá** | Confirm the generated `.ps` file is saved with the correct extension and that your viewer supports PostScript. |

## Často kladené otázky

**Q:** Can I use my own custom fonts with Aspose.Page for Java?  
A: Yes, you can use custom fonts by specifying the font name and size in the `DrFont` class.

**Q:** How can I change the color of the text?  
A: You can set the desired color using the `Color` class when filling or outlining the text.

**Q:** Is it possible to add multiple pages to a PostScript document?  
A: Absolutely! You can create multiple pages by repeating the document creation and saving steps.

**Q:** What is the purpose of the `ExternalFontCache` class?  
A: `ExternalFontCache` is used to fetch custom fonts, ensuring they are available for text manipulation.

**Q:** Can I apply different strokes to the outlined text?  
A: Yes, you can customize the width and color of the stroke using the `Stroke` class and `Color` class, respectively.

## Závěr
Gratulujeme! Nyní víte, jak **set text color java**, měnit velikosti fontů, **apply stroke text** a **create postscript document** soubory pomocí Aspose.Page pro Javu. Experimentujte s různými fonty, barvami a styly obrysů a vytvořte profesionální výstup ve formátu PostScript.

---

**Last Updated:** 2025-12-14  
**Tested With:** Aspose.Page for Java 23.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}