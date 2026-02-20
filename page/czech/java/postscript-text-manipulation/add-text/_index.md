---
date: 2026-02-20
description: Naučte se, jak nastavit barvu textu v Javě pomocí Aspose.Page pro Javu,
  změnit velikost písma v Javě, generovat soubor PostScript, vyplnit a obkreslit text
  a používat vlastní písma v Javě při vytváření dokumentu PostScript.
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: Nastavte barvu textu v Javě pomocí Aspose.Page – Průvodce manipulací s textem
url: /cs/java/postscript-text-manipulation/add-text/
weight: 10
---

 Font and Changing Text Size.

- Outlining (Stroke) Text – Apply Stroke Text.

- Outlining Text with Custom Font.

- Step 6: Save the Document.

- Why This Matters.

- Common Issues & Solutions table.

- Frequently Asked Questions with Q/A.

- Conclusion.

- Footer details.

Make sure to keep code block placeholders unchanged.

Also keep markdown formatting.

Let's translate each piece.

I'll produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení barvy textu v Javě s Aspose.Page – Průvodce manipulací s textem

## Úvod
Vítejte v našem krok‑za‑krokem průvodci, jak **nastavit barvu textu v Javě** při práci se soubory PostScript pomocí Aspose.Page pro Javu. Aspose.Page pro Javu je výkonná knihovna, která vývojářům umožňuje **vytvářet postscript dokumenty**, manipulovat s fonty a stylovat text s přesností. V tomto tutoriálu se naučíte, jak přidat text, změnit jeho barvu, **změnit velikost písma v Javě**, a dokonce **aplikovat výplň a obrys textu** pro profesionální vzhled.

## Rychlé odpovědi
- **Která knihovna mi umožní nastavit barvu textu v Javě?** Aspose.Page pro Javu.  
- **Mohu použít systémové fonty i vlastní fonty?** Ano, oba jsou podporovány a **použít vlastní fonty v Javě** je snadné.  
- **Jak změním velikost textu?** Zadáním velikosti písma při vytváření objektu `Font` nebo `DrFont`.  
- **Je možné najednou obrysovat a vyplnit text?** Rozhodně – použijte `fillAndStrokeText`.  
- **Jaký výstupní formát tento tutoriál vytváří?** Dokument PostScript (`.ps`), který můžete **programově generovat postscript soubor**.

## Co znamená „nastavit barvu textu v Javě“?
Nastavení barvy textu v Javě znamená definovat objekt `Color`, který vykreslovací engine (zde Aspose.Page) použije při kreslení znaků na stránku. Tato operace je nezbytná pro tvorbu vizuálně odlišných dokumentů, zejména když potřebujete **programově generovat postscript soubor**.

## Proč použít Aspose.Page pro Javu?
- **Úplná kontrola** nad generováním PostScriptu bez nutnosti nativního interpreteru.  
- **Podpora jak systémových, tak externích fontů**, což vám umožní vložit libovolnou typografii.  
- **Jednoduché API** pro výplň, obrys a **výplň s obrysem textu**, které poskytuje flexibilitu při stylování.  
- **Cross‑platform** kompatibilita – napište jednou, spusťte kdekoliv, kde běží Java.  

## Předpoklady
Předtím, než se pustíte do kódu, ujistěte se, že máte:

- Základní znalosti programování v Javě.  
- Knihovnu Aspose.Page pro Javu nainstalovanou. Můžete ji stáhnout ze [stránky ke stažení Aspose.Page pro Javu](https://releases.aspose.com/page/java/).  
- Potřebné fonty umístěné ve specifikované složce. Další podrobnosti najdete v [dokumentaci Aspose.Page pro Javu](https://reference.aspose.com/page/java/).  

## Import balíčků
Ve svém Java projektu importujte potřebné balíčky pro Aspose.Page pro Javu:

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
Nejprve vytvoříme nový **PostScript dokument** a nakonfigurujeme výstupní možnosti.

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
Nyní ukážeme **nastavení barvy textu v Javě** s fontem poskytovaným systémem.

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **Tip:** Metoda `fillText` automaticky používá aktuální barvu, pokud nepředáte argument `Color`, který je ve výchozím nastavení černý.

## Použití vlastního fontu a změna velikosti textu
Můžete také **změnit velikost písma v Javě** a použít vlastní font uložený ve vaší složce s fonty.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Obrysování (Stroke) textu – Aplikovat obrys textu
Obrysování textu mu dodá ostrý okraj. Zde **aplikujeme obrys textu** pomocí `BasicStroke`.

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

## Obrysování textu s vlastním fontem
Stejná technika funguje i s vlastními fonty.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Krok 6: Uložení dokumentu
Nakonec zavřeme stránku a zapíšeme soubor na disk.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Proč je to důležité
Schopnost **nastavit barvu textu v Javě** a kombinovat výplň s obrysem vám poskytuje plnou uměleckou kontrolu nad finálním výstupem PostScriptu. Ať už generujete faktury, certifikáty nebo vlastní grafiku, možnost **vytvářet postscript dokumenty** s přesným stylováním snižuje potřebu následné úpravy v grafických editorech.

## Časté problémy a řešení
| Problém | Řešení |
|-------|----------|
| **Font nebyl nalezen** | Ujistěte se, že soubor s fontem je umístěn ve složce `necessary_fonts` a že cesta ke složce je správně přidána pomocí `options.setAdditionalFontsFolders`. |
| **Barva se neaplikovala** | Ověřte, že voláte přetíženou verzi `fillText` nebo `outlineText`, která obsahuje argument `Color`. |
| **Obrys je příliš tenký** | Zvyšte šířku `BasicStroke` (např. `new BasicStroke(3)`). |
| **Dokument se neotevírá** | Zkontrolujte, že vygenerovaný soubor `.ps` má správnou příponu a že váš prohlížeč podporuje PostScript. |

## Často kladené otázky

**Q:** Mohu použít vlastní fonty s Aspose.Page pro Javu?  
**A:** Ano, můžete **použít vlastní fonty v Javě** zadáním názvu fontu a velikosti ve třídě `DrFont`.

**Q:** Jak mohu změnit barvu textu?  
**A:** Barvu nastavíte pomocí třídy `Color` při výplni nebo obrysování textu.

**Q:** Je možné přidat více stránek do PostScript dokumentu?  
**A:** Rozhodně! Můžete vytvořit více stránek opakováním kroků pro vytvoření a uložení dokumentu.

**Q:** K čemu slouží třída `ExternalFontCache`?  
**A:** `ExternalFontCache` slouží k načtení vlastních fontů, aby byly dostupné pro manipulaci s textem.

**Q:** Mohu aplikovat různé obrysy na obrysovaný text?  
**A:** Ano, šířku a barvu obrysu můžete přizpůsobit pomocí třídy `Stroke` a třídy `Color`.

## Závěr
Gratulujeme! Nyní víte, jak **nastavit barvu textu v Javě**, **změnit velikost písma v Javě**, **aplikovat výplň a obrys textu** a **vytvářet postscript dokumenty** pomocí Aspose.Page pro Javu. Experimentujte s různými fonty, barvami a styly obrysů a vytvořte profesionální výstup v PostScriptu.

---

**Poslední aktualizace:** 2026-02-20  
**Testováno s:** Aspose.Page pro Javu 23.12 (nejnovější)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}