---
date: 2026-02-07
description: Naučte se, jak škálovat obdélník pomocí Aspose.Page pro Javu, jak přesunout
  tvar a aplikovat afinní transformaci k vytvoření dokumentů PostScript.
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Jak škálovat obdélník pomocí Aspose.Page pro Javu
url: /cs/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak škálovat obdélník pomocí Aspose.Page pro Java

## Úvod
Vítejte v komplexním průvodci využíváním výkonných funkcí **Aspose.Page for Java** k provádění různých transformací stránek. V tomto tutoriálu se naučíte **jak škálovat obdélník**, přesouvat tvary, otáčet objekty a **aplikovat afinní transformaci** při vytváření **PostScript dokumentu**. Tyto možnosti vám umožní vytvářet bohaté, graficky náročné Java aplikace bez nutnosti pracovat s nízkoúrovňovým renderovacím kódem.

## Rychlé odpovědi
- **Jak mohu v Javě se Aspose.Page škálovat obdélník?** Použijte metodu `document.scale()` před vykreslením tvaru.  
- **Mohu přesunout (přeložit) tvar, aniž by to ovlivnilo ostatní grafiku?** Ano—uložte stav grafiky, zavolejte `document.translate(x, y)`, vykreslete a poté obnovte stav.  
- **Jaká třída vytváří soubor PostScript?** `PsDocument` spolu s `PsSaveOptions`.  
- **Potřebuji licenci pro produkční použití?** Platná licence Aspose.Page je vyžadována pro komerční nasazení.  
- **Která verze Javy je podporována?** Aspose.Page funguje s Java 8 a novějšími.

## Požadavky
Než se pustíme do podrobného návodu, ujistěte se, že máte následující předpoklady:

- Základní znalost programování v Javě.  
- Knihovna Aspose.Page pro Java nainstalována. Můžete si ji stáhnout z [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- Integrované vývojové prostředí (IDE) pro Javu nastavené na vašem počítači.

## Import balíčků
Ve vašem Java projektu importujte potřebné balíčky pro využití Aspose.Page for Java:

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Co je „jak škálovat obdélník“ v Aspose.Page?
Škálování obdélníku mění jeho velikost podél os X a Y při zachování tvaru. Aspose.Page poskytuje metodu `scale(float sx, float sy)`, která aplikuje **afinní transformaci** na aktuální stav grafiky. Toto je hlavní technika stojící za klíčovým slovem **how to scale rectangle**.

## Jak přesunout tvar pomocí Aspose.Page
Překlad (translation) přesouvá tvar na nové místo, aniž by změnil jeho rozměry. To je podstata **how to translate shape**. Uložením stavu grafiky, aplikací `translate(dx, dy)`, vykreslením a následným obnovením stavu zajistíte, že ostatní objekty zůstanou nedotčeny.

## Příklad 1: Žádné transformace
První příklad vykresluje jednoduchý obdélník bez jakékoli aplikované transformace. Slouží jako výchozí bod pro srovnání s následujícími příklady.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## Příklad 2: Překlad
Zde demonstrujeme **how to translate shape** přesunutím grafického kontextu o 250 jednotek doprava před vykreslením druhého obdélníku.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Příklad 3: Škálování
Tento příklad odpovídá na hlavní otázku **how to scale rectangle**. Zmenšíme obdélník na 50 % původní šířky a 75 % výšky.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Jak otáčet tvar v Javě (rotate shape java)
Rotace je další běžná afinní operace. Kódové úryvky pro rotaci jsou vynechány z důvodu stručnosti, ale postup je stejný: uložte stav grafiky, zavolejte `document.rotate(angle)`, vykreslete tvar a poté obnovte stav. To ukazuje **rotate shape java** a **how to rotate rectangle** v praxi.

## Proč je to důležité – Praktické výhody
- **Výstup nezávislý na zařízení** – Napište jednou a generujte PostScript nebo XPS bez úprav specifických pro platformu.  
- **Detailní kontrola** – Kombinujte překlad, škálování, zkosení a rotaci pro splnění přesných požadavků na rozvržení.  
- **Výkonnostně orientované** – API s nízkou režijní zátěží ideální pro dávkové zpracování rozsáhlých dokumentů.  

## Běžné případy použití
- Generování tisknutelných faktur – například řešení **printable invoice java**, které přesně umisťuje loga a čárové kódy.  
- Vytváření technických diagramů, kde je vyžadováno přesné škálování a umístění.  
- Automatizace tvorby vícestránkových zpráv ve formátu PostScript.  

## Běžné problémy a řešení
- **Transformace se neobnovuje** – Vždy spárujte `document.writeGraphicsSave()` s `document.writeGraphicsRestore()`, aby nedocházelo k nechtěnému přenášení efektů.  
- **Neočekávané barvy** – Ujistěte se, že po každé transformaci nastavíte barvu; stav grafiky po obnovení neuchovává předchozí nastavení barvy.  
- **Velikost souboru je příliš velká** – Použijte `PsSaveOptions` k povolení komprese nebo snížení rozlišení obrázku při vkládání rastrové grafiky.  

## Často kladené otázky

### Mohu použít Aspose.Page pro Java i pro jiné formáty dokumentů?
Aspose.Page se primárně zaměřuje na manipulaci stránek pro formáty PostScript a XPS.

### Kde najdu více příkladů a dokumentaci pro Aspose.Page pro Java?
Navštivte [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) pro komplexní informace.

### Je k dispozici bezplatná zkušební verze Aspose.Page pro Java?
Ano, můžete získat bezplatnou zkušební verzi [zde](https://releases.aspose.com/).

### Jak získat dočasnou licenci pro Aspose.Page pro Java?
Získejte dočasnou licenci [zde](https://purchase.aspose.com/temporary-license/).

### Kde mohu získat komunitní podporu nebo klást otázky ohledně Aspose.Page pro Java?
Navštivte [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) pro komunitní diskuse.

## Často kladené otázky

**Q: Jaký je rozdíl mezi `translate` a `scale`?**  
A: `translate` posouvá počátek souřadnicového systému, zatímco `scale` mění velikost vykreslených objektů podél os X a/nebo Y.

**Q: Mohu kombinovat více transformací v jednom stavu grafiky?**  
A: Ano—voláním `translate`, `scale`, `rotate` nebo `shear` postupně před vykreslením vytvoříte kombinovanou afinní transformaci.

**Q: Jak resetuji transformace po vykreslení tvaru?**  
A: Použijte `document.writeGraphicsRestore()` k návratu k dříve uloženému stavu grafiky.

**Q: Je možné otočit obdélník kolem jeho středu?**  
A: Rozhodně. Přesuňte obdélník do počátku, aplikujte `rotate(angle)`, pak jej vraťte zpět před vykreslením.

**Q: Podporuje Aspose.Page anti‑aliasing pro hladší grafiku?**  
A: Ano—nastavte příslušné možnosti vykreslování v `PsSaveOptions` pro povolení anti‑aliasingu.

---

**Poslední aktualizace:** 2026-02-07  
**Testováno s:** Aspose.Page for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}