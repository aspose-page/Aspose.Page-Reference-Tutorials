---
date: 2026-05-05
description: Naučte se, jak přidávat texturové dlaždicové vzory do dokumentů PostScript
  pomocí Aspose.Page pro Javu. Tento průvodce ukazuje, jak efektivně přidávat texturu
  a objevovat kreativní možnosti.
keywords:
- how to add texture
- fill shape with texture
- fill rectangle with texture
linktitle: Přidat texturovaný vzor pro dlaždicování v Java PostScriptu
second_title: Aspose.Page Java API
title: Jak přidat texturovaný vzor dlaždicování v Java PostScriptu
url: /cs/java/postscript-texture-patterns/add-texture-tiling-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat texturovaný dlaždicový vzor v Java PostScriptu

## Úvod
V oblasti vývoje v Javě je učení **jak přidat texturu** do PostScript dokumentů běžnou požadavkem. Aspose.Page pro Java tuto úlohu usnadňuje, takže se můžete soustředit na design místo na nízkoúrovňovou PostScript syntaxi. V tomto tutoriálu projdeme každý krok potřebný k přidání texturovaného dlaždicového vzoru, vyplnění tvarů a dokonce i textu texturou v Java PostScript dokumentu.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.Page pro Java  
- **Na jaké hlavní klíčové slovo se tento průvodce zaměřuje?** *how to add texture*  
- **Potřebuji licenci pro testování?** K dispozici je bezplatná zkušební verze; licence je vyžadována pro produkční nasazení.  
- **Jaká verze Javy je podporována?** Java 8 nebo vyšší.  
- **Mohu znovu použít texturovaný štětec pro více tvarů?** Ano – vytvořte `TexturePaint` jednou a aplikujte jej na libovolný tvar.  
- **Jak vyplním obdélník texturou?** Použijte `document.fill(shape)` po nastavení `TexturePaint` jako aktuálního štětce.

## Co je texturovaný dlaždicový vzor?
Texturovaný dlaždicový vzor opakuje malý obrázek (dlaždici) přes větší oblast, což vám umožní **vyplnit tvar texturou** bez ručního kreslení každé dlaždice. Tato technika je ideální pro pozadí, výplně a dekorativní textové efekty v PostScriptu.

## Proč použít Aspose.Page pro Java?
- **Renderování bez závislostí** – není potřeba externí interpretery PostScriptu.  
- **Plná kontrola nad grafikou** – kombinujte vektorové tvary, text a bitmapové textury.  
- **Cross‑platform** – funguje na jakémkoli OS, který podporuje Javu.  

## Předpoklady
Předtím, než se ponoříte do tutoriálu, ujistěte se, že máte následující předpoklady:
- Základní znalost programovacího jazyka Java.  
- Znalost struktury dokumentu PostScript.  
- Knihovna Aspose.Page pro Java nainstalována. Můžete si ji stáhnout [zde](https://releases.aspose.com/page/java/).

## Import balíčků
Začněte importováním potřebných balíčků pro váš Java projekt:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Jak přidat texturovaný dlaždicový vzor v Java PostScriptu
Níže je průvodce krok za krokem. Každý krok obsahuje krátké vysvětlení následované přesným kódem, který je třeba zkopírovat.

### Krok 1: Vytvořit PostScript dokument
Začněte vytvořením nového PostScript dokumentu, specifikací výstupního proudu a možností uložení. Ujistěte se, že máte nastavené potřebné cesty.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTextureTilingPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Krok 2: Nastavit grafické prostředí
Přesuňte počátek do vhodné polohy a načtěte bitmapu, která bude sloužit jako texturová dlaždice.

```java
document.writeGraphicsSave();
document.translate(200, 100);
// Create a BufferedImage object from image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestTexture.bmp"));
```

### Krok 3: Vytvořit texturovaný štětec
Definujte `TexturePaint`, který opakuje bitmapu přes oblast tvaru. Upravte velikost obdélníku, pokud chcete, aby se dlaždice zobrazovala větší nebo menší.

```java
// Create image area doubled in width
Rectangle2D.Float imageArea = new Rectangle2D.Float(0, 0, image.getWidth() * 2, image.getHeight());
// Create texture brush from the image
TexturePaint paint = new TexturePaint(image, imageArea);
```

### Krok 4: Kreslit a vyplňovat tvary
Vytvořte obdélník a **vyplňte obdélník texturou** pomocí štětce. Poté obrysujte tvar, aby byl výsledek vizuálně odlišný.

```java
// Create rectangle
Rectangle2D.Float shape = new Rectangle2D.Float(0, 0, 200, 100);
// Set this texture brush as current paint
document.setPaint(paint);
// Fill rectangle
document.fill(shape);
document.setPaint(Color.RED);
document.setStroke(new BasicStroke(2));
document.draw(shape);
```

### Krok 5: Přidat text s texturovaným vzorem
Můžete také aplikovat stejnou texturu na textové glyfy. To ukazuje **jak vyplnit texturou** znaky, přičemž je stále možné je obkreslit.

```java
// Fill the text with the texture pattern
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
// Outline the text with the texture pattern
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

### Krok 6: Uložit a zavřít
Nakonec zavřete stránku, uložte dokument a uvolněte prostředky.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Časté problémy a tipy
- **Chybějící soubor textury** – Ověřte, že cesta k `TestTexture.bmp` je správná a soubor je přístupný.  
- **Nesprávné rozměry obrázku** – Pokud se textura zdá natažená, upravte `imageArea` tak, aby odpovídala původní velikosti obrázku.  
- **Výkon** – Znovu použijte stejnou instanci `TexturePaint` pro více tvarů, abyste se vyhnuli zbytečnému vytváření objektů.  
- **Profesionální tip:** Použijte bitmapu s vysokým rozlišením pro dlaždici, aby textura zůstala ostrá při škálování.

## Často kladené otázky

**Q: Je Aspose.Page pro Java vhodný pro začátečníky?**  
A: Rozhodně! Aspose.Page pro Java poskytuje komplexní dokumentaci, což jej činí přístupným pro vývojáře všech úrovní.

**Q: Mohu integrovat Aspose.Page pro Java do svého existujícího Java projektu?**  
A: Ano, můžete snadno integrovat Aspose.Page pro Java do svého projektu podle poskytnuté dokumentace [zde](https://reference.aspose.com/page/java/).

**Q: Kde mohu najít podporu nebo diskutovat o dotazech souvisejících s Aspose.Page?**  
A: Navštivte [forum Aspose.Page](https://forum.aspose.com/c/page/39), kde můžete komunikovat s komunitou a požádat o pomoc.

**Q: Je k dispozici bezplatná zkušební verze Aspose.Page pro Java?**  
A: Ano, můžete si vyzkoušet bezplatnou verzi [zde](https://releases.aspose.com/).

**Q: Jak mohu získat dočasnou licenci pro Aspose.Page pro Java?**  
A: Navštivte [tento odkaz](https://purchase.aspose.com/temporary-license/), kde získáte dočasnou licenci.

## Závěr
Gratulujeme! Úspěšně jste se naučili **jak přidat texturu** pomocí dlaždicových vzorů do Java PostScript dokumentu pomocí Aspose.Page pro Java. Neváhejte experimentovat s různými bitmapovými dlaždicemi, měřítky a kompozitními operacemi, abyste odhalili plný tvůrčí potenciál texturovaných výplní.

---

**Poslední aktualizace:** 2026-05-05  
**Testováno s:** Aspose.Page pro Java 24.12 (nejnovější)  
**Autor:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}