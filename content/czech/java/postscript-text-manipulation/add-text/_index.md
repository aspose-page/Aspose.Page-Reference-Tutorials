---
title: Manipulace s textem Aspose.Page Java
linktitle: Přidejte text do jazyka Java PostScript
second_title: Aspose.Page Java API
description: Prozkoumejte sílu Aspose.Page for Java v našem tutoriálu o přidávání textu do PostScriptových dokumentů. Naučte se snadno používat systémová a vlastní písma.
type: docs
weight: 10
url: /cs/java/postscript-text-manipulation/add-text/
---
## Úvod
Vítejte v našem podrobném průvodci přidáváním textu do jazyka Java PostScript pomocí Aspose.Page for Java. Aspose.Page for Java je výkonná knihovna, která umožňuje vývojářům snadno manipulovat s PostScriptovými dokumenty. V tomto tutoriálu vás provedeme procesem přidávání textu, používání systémových a vlastních písem, obrysování textu a začleňování tahů pro vizuálně přitažlivý výsledek.
## Předpoklady
Než se ponoříte do výukového programu, ujistěte se, že máte následující předpoklady:
- Základní znalost programování v Javě.
-  Nainstalovaná knihovna Aspose.Page for Java. Můžete si jej stáhnout z[Aspose.Page for Java download page](https://releases.aspose.com/page/java/).
-  Nezbytná písma dostupná v zadané složce. Další informace najdete v[Aspose.Page pro dokumentaci Java](https://reference.aspose.com/page/java/).
## Importujte balíčky
Ve svém projektu Java importujte potřebné balíčky pro Aspose.Page for Java:
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
## Krok 1: Nastavte dokument
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Vytvořte výstupní proud pro dokument PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Vytvořte možnosti uložení s velikostí A4
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// Text, který se má zapsat do souboru PS
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Vytvořte nový 1stránkový dokument PS
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Krok 2: Použití systémového písma pro vyplnění textu
```java
// Použití systémového písma pro vyplňování textu
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Vyplňte text výchozí nebo již definovanou barvou (černá)
document.fillText(str, font, 50, 100);
// Vyplňte text modrou barvou
document.fillText(str, font, 50, 150, Color.BLUE);
```
## Krok 3: Použití vlastního písma pro vyplnění textu
```java
// Použití vlastního písma pro vyplnění textu
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Vyplňte text výchozí nebo již definovanou barvou (černá)
document.fillText(str, drFont, 50, 200);
// Vyplňte text modrou barvou
document.fillText(str, drFont, 50, 250, Color.BLUE);
```
## Krok 4: Nastínění textu pomocí systémového písma
```java
// Použití systémového písma pro obrysový text
document.outlineText(str, font, 50, 300);
// Obrysový text pomocí modrofialového pera o šířce 2 bodů
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Vyplňte text oranžovou barvou a přetáhněte modrým perem o šířce 2 bodů
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```
## Krok 5: Navrhování textu pomocí vlastního písma
```java
// Použití vlastního písma pro obrys textu
document.outlineText(str, drFont, 50, 450);
// Obrysový text pomocí modrofialového pera o šířce 2 bodů
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Vyplňte text oranžovou barvou a přetáhněte modrým perem o šířce 2 bodů
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```
## Krok 6: Uložte dokument
```java
// Zavřít aktuální stránku
document.closePage();
// Uložte dokument
document.save();
```
## Závěr
Gratulujeme! Úspěšně jste se naučili přidávat text do jazyka Java PostScript pomocí Aspose.Page for Java. Experimentujte s různými fonty, barvami a možnostmi obrysů, abyste svůj dokument dále vylepšili.
## Často kladené otázky
### Mohu používat svá vlastní písma s Aspose.Page for Java?
 Ano, můžete použít vlastní písma zadáním názvu a velikosti písma v souboru`DrFont` třída.
### Jak mohu změnit barvu textu?
 Požadovanou barvu můžete nastavit pomocí`Color` třídy při vyplňování nebo obrysování textu.
### Je možné přidat více stránek do dokumentu PostScript?
Absolutně! Opakováním kroků vytváření a ukládání dokumentu můžete vytvořit více stránek.
###  Jaký je účel`ExternalFontCache` class?
`ExternalFontCache` se používá k načítání vlastních písem, což zajišťuje, že jsou k dispozici pro manipulaci s textem.
### Mohu na vyznačený text použít různé tahy?
 Ano, můžete upravit šířku a barvu tahu pomocí`Stroke` třída a`Color` třídy, resp.