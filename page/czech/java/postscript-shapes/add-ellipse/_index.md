---
date: 2025-12-11
description: Naučte se, jak vytvořit elipsu v PostScriptu v Javě pomocí Aspose.Page.
  Tento krok‑za‑krokem průvodce vám ukáže, jak vyplnit elipsu barvou a jak ji nakreslit
  v Javě.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Jak vytvořit elipsu v PostScriptu v Javě pomocí Aspose.Page
url: /cs/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit elipsu PostScript v Javě s Aspose.Page

## Úvod
Vytvoření **PostScript elipsy** programově vám poskytuje detailní kontrolu nad vektorovou grafikou v reportech, fakturách nebo jakémkoli tisknutelném dokumentu. V tomto tutoriálu se naučíte, jak **vytvořit PostScript elipsu** pomocí knihovny Aspose.Page pro Java, vyplnit elipsu barvou a nakreslit obrys elipsy. Na konci budete připraveni vložit vlastní grafiku přímo do výstupu PostScript.

## Rychlé odpovědi
- **Jaká knihovna je nejlepší pro kreslení PostScript grafiky v Javě?** Aspose.Page for Java.  
- **Mohu vyplnit elipsu plnou barvou?** Ano – použijte `document.setPaint(Color.YOUR_COLOR)` před `fill`.  
- **Jak nakreslím pouze obrys elipsy?** Nastavte barvu a tah (stroke), pak zavolejte `document.draw(...)`.  
- **Potřebuji licenci pro produkční použití?** Je vyžadována komerční licence; dočasná licence je k dispozici pro testování.  
- **Jaká verze Javy je podporována?** Jakékoli prostředí Java 8+ funguje s aktuálním vydáním Aspose.Page.

## Co je PostScript elipsa?
PostScript elipsa je vektorový tvar definovaný ohraničujícím obdélníkem. Na rozdíl od rastrových obrázků se škáluje bez ztráty kvality, což ji činí ideální pro tisk ve vysokém rozlišení a konverzi do PDF.

## Proč použít Aspose.Page k vytvoření PostScript elipsy?
- **Plná kontrola** nad kreslením primitiv (čáry, křivky, elipsy).  
- **Cross‑platform** – funguje na Windows, Linuxu i macOS.  
- **Žádné externí závislosti** – čisté Java API, žádný nativní kód.  
- **Snadná integrace** s existujícími Java aplikacemi a nástroji pro sestavování.

## Požadavky
Před zahájením se ujistěte, že máte:

1. Funkční vývojové prostředí Java (JDK 8 nebo novější).  
2. Knihovnu Aspose.Page pro Java přidanou do vašeho projektu. Můžete ji stáhnout **[zde](https://releases.aspose.com/page/java/)**.  

## Import balíčků
Ve vašem Java zdrojovém souboru importujte třídy potřebné pro kreslení a ukládání PostScript obsahu.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Postupný průvodce

### Krok 1: Nastavení PostScript dokumentu
Vytvořte výstupní stream, nakonfigurujte velikost stránky a vytvořte instanci `PsDocument`.

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

### Krok 2: Vyplnění elipsy barvou
Nastavte barvu (paint) na požadovanou výplňovou barvu a zavolejte `fill` s instancí `Ellipse2D`.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Krok 3: Obrys elipsy tahy
Přepněte barvu (paint) na barvu tahu, definujte `BasicStroke` pro tloušťku čáry a nakreslete obrys elipsy.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Krok 4: Uzavření a uložení dokumentu
Dokončete stránku a zapište soubor PostScript na disk.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Nyní máte soubor PostScript, který obsahuje dvě elipsy – jednu vyplněnou oranžovou barvou a druhou s červeným obrysem. Klidně experimentujte s různými souřadnicemi, velikostmi a barvami, aby odpovídaly vašim návrhovým potřebám.

## Časté problémy a řešení
- **Nesprávná cesta k souboru** – Ujistěte se, že `dataDir` končí oddělovačem (`/` nebo `\\`) vhodným pro váš OS.  
- **Chybějící licence** – Bez platné licence knihovna běží v evaluačním režimu a může přidávat vodoznaky.  
- **Barva se neaplikuje** – Pamatujte nastavit `document.setPaint(...)` *před* každým voláním `fill` nebo `draw`; nastavení barvy se automaticky neuchovává mezi samostatnými operacemi.

## Často kladené otázky

**Q: Mohu použít Aspose.Page pro Java s dalšími Java knihovnami?**  
A: Ano, Aspose.Page pro Java je navržena tak, aby se bez problémů integrovala s dalšími Java knihovnami.

**Q: Jak mohu získat dočasnou licenci pro Aspose.Page pro Java?**  
A: Získejte dočasnou licenci **[zde](https://purchase.aspose.com/temporary-license/)** pro testovací účely.

**Q: Je Aspose.Page vhodná pro komerční projekty?**  
A: Rozhodně! Navštivte **[zde](https://purchase.aspose.com/buy)** a prozkoumejte licenční možnosti pro komerční použití.

**Q: Kde mohu získat pomoc nebo diskutovat o dotazech souvisejících s Aspose.Page?**  
A: Připojte se ke komunitě na **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** pro diskuze a podporu.

**Q: Existují nějaké bezplatné zdroje pro další učení o Aspose.Page pro Java?**  
A: Využijte **[free trial](https://releases.aspose.com/)** a prozkoumejte příklady v dokumentaci.

## Závěr
Aspose.Page pro Java umožňuje snadno **vytvořit PostScript elipsu** grafiku, ať už potřebujete jednoduchý vyplněný tvar nebo složitý obrys. S výše uvedenými kroky můžete rychle přidat profesionální vektorovou grafiku do libovolného tisknutelného dokumentu. Pro hlubší průzkum – například kombinování více tvarů, aplikaci gradientů nebo konverzi do PDF – se podívejte na oficiální **[documentation](https://reference.aspose.com/page/java/)**.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2025-12-11  
**Testováno s:** Aspose.Page for Java 24.11  
**Autor:** Aspose