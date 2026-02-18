---
date: 2026-02-18
description: Naučte se, jak nastavit barvu kreslení a vytvořit elipsu v PostScriptu
  v Javě pomocí Aspose.Page. Tento průvodce ukazuje, jak vyplnit elipsu v Javě, nakreslit
  obrys elipsy a nastavit tloušťku tahu.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Nastavit barvu kresby pro vykreslení PostScriptové elipsy v Javě
url: /cs/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nastavte barvu kreslení pro vykreslení PostScript elipsy v Javě

## Úvod
Pokud potřebujete **nastavit barvu kreslení** při kreslení vektorové grafiky, knihovna Aspose.Page pro Java vám poskytuje plnou kontrolu nad každým tahem a výplní. V tomto tutoriálu se dozvíte, jak **nastavit barvu kreslení**, **vyplnit elipsu v Javě** a **nakreslit obrys elipsy** pomocí jednoduchého, krok za krokem přístupu. Na konci budete schopni přidat vysoce kvalitní PostScript elipsy do faktur, reportů nebo jakéhokoli tisknutelného dokumentu.

## Rychlé odpovědi
- **Která knihovna je nejlepší pro kreslení PostScript grafiky v Javě?** Aspose.Page for Java.  
- **Mohu vyplnit elipsu plnou barvou?** Yes – use `document.setPaint(Color.YOUR_COLOR)` before `fill`.  
- **Jak nakreslím pouze obrys elipsy?** Set the paint and stroke, then call `document.draw(...)`.  
- **Potřebuji licenci pro produkční použití?** A commercial license is required; a temporary license is available for testing.  
- **Jaká verze Javy je podporována?** Any Java 8+ runtime works with the current Aspose.Page release.

## Co je PostScript elipsa?
PostScript elipsa je vektorový tvar definovaný ohraničujícím obdélníkem. Na rozdíl od rastrových obrázků se škáluje bez ztráty kvality, což ji činí ideální pro tisk ve vysokém rozlišení a konverzi do PDF.

## Proč použít Aspose.Page k vytvoření PostScript elipsy?
- **Plná kontrola** nad kreslicími primitivy (čáry, křivky, elipsy).  
- **Cross‑platform** – funguje na Windows, Linuxu i macOS.  
- **Žádné externí závislosti** – čisté Java API, žádný nativní kód.  
- **Snadná integrace** s existujícími Java aplikacemi a nástroji pro sestavení.

## Požadavky
Než začnete, ujistěte se, že máte:

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

## Jak nastavit barvu kreslení pro elipsu
Nastavení barvy kreslení je prvním krokem před jakoukoliv operací výplně nebo tahu. Metoda `setPaint` určuje barvu, která bude použita pro následující kreslicí příkaz.

### Krok 1: Nastavte PostScript dokument
Vytvořte výstupní stream, nastavte velikost stránky a vytvořte instanci `PsDocument`.

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

### Krok 2: Jak vyplnit elipsu – použijte nastavení barvy
Pro **vyplnění elipsy** musíte nejprve zavolat `setPaint` s požadovanou barvou výplně a poté zavolat `fill` s instancí `Ellipse2D`.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Krok 3: Nakreslete obrys elipsy a nastavte tloušťku tahu
Po vyplnění můžete změnit barvu kreslení na jinou, definovat `BasicStroke` pro kontrolu šířky čáry a nakreslit obrys elipsy.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Krok 4: Uzavřete a uložte dokument
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
- **Barva se neaplikuje** – Pamatujte, že `document.setPaint(...)` musíte nastavit *před* každým voláním `fill` nebo `draw`; nastavení barvy se automaticky nepřenáší mezi samostatnými operacemi.

## Často kladené otázky

**Q: Mohu používat Aspose.Page pro Java s jinými Java knihovnami?**  
A: Ano, Aspose.Page pro Java je navržena tak, aby se bez problémů integrovala s dalšími Java knihovnami.

**Q: Jak mohu získat dočasnou licenci pro Aspose.Page pro Java?**  
A: Získejte dočasnou licenci **[zde](https://purchase.aspose.com/temporary-license/)** pro testovací účely.

**Q: Je Aspose.Page vhodná pro komerční projekty?**  
A: Rozhodně! Navštivte **[zde](https://purchase.aspose.com/buy)** a prozkoumejte licenční možnosti pro komerční použití.

**Q: Kde mohu získat pomoc nebo diskutovat o dotazech souvisejících s Aspose.Page?**  
A: Připojte se ke komunitě na **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** pro diskuze a podporu.

**Q: Existují nějaké bezplatné zdroje pro další učení o Aspose.Page pro Java?**  
A: Využijte **[bezplatnou zkušební verzi](https://releases.aspose.com/)** a prozkoumejte příklady v dokumentaci.

## Závěr
Aspose.Page pro Java usnadňuje **nastavit barvu kreslení**, **vyplnit elipsu** a **nakreslit obrys elipsy** – ať už potřebujete jednoduchý vyplněný tvar nebo složitou grafiku s tahy. Pomocí výše uvedených kroků můžete rychle přidat profesionální vektorovou grafiku do jakéhokoli tisknutelného dokumentu. Pro podrobnější průzkum – například kombinování více tvarů, aplikaci gradientů nebo konverzi do PDF – se podívejte na oficiální **[dokumentaci](https://reference.aspose.com/page/java/)**.

---

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}