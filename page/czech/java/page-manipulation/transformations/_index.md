---
date: 2025-12-07
description: Naučte se, jak v Javě pomocí Aspose.Page škálovat obdélník, posunout
  tvar a aplikovat afinní transformaci k vytváření dokumentů PostScript.
language: cs
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Jak škálovat obdélník a aplikovat transformace pomocí Aspose.Page
url: /java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak škálovat obdélník a aplikovat transformace s Aspose.Page

## Úvod
Vítejte v komplexním průvodci využíváním výkonných funkcí **Aspose.Page for Java** k provádění různých transformací stránky. V tomto tutoriálu se naučíte **jak škálovat obdélník**, posouvat tvary, otáčet objekty a **aplikovat afinní transformaci** při vytváření **PostScript dokumentu**. Tyto možnosti vám umožní vytvářet bohaté, graficky náročné Java aplikace bez nutnosti pracovat s nízkoúrovňovým vykreslovacím kódem.

## Rychlé odpovědi
- **Jak mohu v Javě s Aspose.Page škálovat obdélník?** Použijte metodu `document.scale()` před vykreslením tvaru.  
- **Mohu posunout (přeložit) tvar, aniž by to ovlivnilo ostatní grafiku?** Ano — uložte stav grafiky, zavolejte `document.translate(x, y)`, vykreslete a poté obnovte stav.  
- **Která třída vytváří PostScript soubor?** `PsDocument` spolu s `PsSaveOptions`.  
- **Potřebuji licenci pro produkční použití?** Pro komerční nasazení je vyžadována platná licence Aspose.Page.  
- **Jaká verze Javy je podporována?** Aspose.Page funguje s Java 8 a novějšími.

## Požadavky
Než se pustíme do podrobného návodu, ujistěte se, že máte splněny následující požadavky:

- Základní znalosti programování v Javě.  
- Knihovna Aspose.Page for Java nainstalovaná. Můžete si ji stáhnout z [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- Integrované vývojové prostředí (IDE) pro Javu nastavené na vašem počítači.

## Import balíčků
Ve svém Java projektu importujte potřebné balíčky pro využití Aspose.Page for Java:

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Co znamená „jak škálovat obdélník“ v Aspose.Page?
Škálování obdélníka mění jeho velikost podél os X a Y při zachování tvaru. Aspose.Page poskytuje metodu `scale(float sx, float sy)`, která aplikuje **afinní transformaci** na aktuální stav grafiky. Toto je hlavní technika za klíčovým slovem **jak škálovat obdélník**.

## Jak posunout tvar s Aspose.Page
Posunutí (translation) přesune tvar na nové místo, aniž by změnilo jeho rozměry. To je podstata **jak posunout tvar**. Uložením stavu grafiky, aplikací `translate(dx, dy)`, vykreslením a následným obnovením stavu zajistíte, že ostatní objekty zůstanou nedotčeny.

## Příklad 1: Žádné transformace
První příklad vykresluje jednoduchý obdélník bez aplikované transformace. Slouží jako výchozí bod pro srovnání s následujícími příklady.

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

## Příklad 2: Posunutí
Zde demonstrujeme **jak posunout tvar** přesunutím grafického kontextu o 250 jednotek doprava před vykreslením druhého obdélníka.

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
Tento příklad odpovídá na hlavní otázku **jak škálovat obdélník**. Zmenšíme obdélník na 50 % jeho původní šířky a 75 % jeho výšky.

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
Otáčení je další běžná afinní operace. I když jsou úryvky kódu pro otáčení vynechány pro stručnost, vzor je stejný: uložte stav grafiky, zavolejte `document.rotate(angle)`, vykreslete tvar a poté obnovte. Toto ukazuje **rotate shape java** a **jak otáčet obdélník** v praxi.

## Proč použít Aspose.Page pro tyto transformace?
- **Zařízení‑nezávislé**: Napište jednou, generujte PostScript nebo XPS bez platformně specifického kódu.  
- **Detailní kontrola**: Přímý přístup ke stavu grafiky vám umožní kombinovat posunutí, škálování, sklon a otáčení.  
- **Výkon**: Nízká režie API vhodná pro dávkové zpracování velkých dokumentů.  

## Běžné scénáře použití
- Generování tisknutelných faktur s dynamickými čárovými kódy a logy.  
- Vytváření technických diagramů, kde je vyžadováno přesné škálování a umístění.  
- Automatizace tvorby vícestránkových zpráv ve formátu PostScript.

## Závěr
V tomto tutoriálu jsme prozkoumali různé transformace v Java Page Manipulation pomocí Aspose.Page for Java, se zaměřením na **jak škálovat obdélník**, **jak posunout tvar** a další afinní operace. Dodržením těchto příkladů můžete vylepšit své Java aplikace o pokročilé možnosti manipulace se stránkami a **vytvářet PostScript dokumenty**, které splňují profesionální standardy publikování.

## FAQ's
### Mohu použít Aspose.Page for Java i pro jiné formáty dokumentů?
Aspose.Page se primárně zaměřuje na manipulaci stránek pro formáty PostScript a XPS.

### Kde najdu více příkladů a dokumentaci k Aspose.Page for Java?
Navštivte [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) pro komplexní informace.

### Je k dispozici bezplatná zkušební verze Aspose.Page for Java?
Ano, bezplatnou zkušební verzi získáte [zde](https://releases.aspose.com/).

### Jak získat dočasnou licenci pro Aspose.Page for Java?
Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

### Kde mohu získat komunitní podporu nebo klást otázky ohledně Aspose.Page for Java?
Navštivte [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) pro diskuse v komunitě.

## Často kladené otázky

**Q: Jaký je rozdíl mezi `translate` a `scale`?**  
A: `translate` posouvá počátek souřadnicového systému, zatímco `scale` mění velikost vykreslovaných objektů podél os X a/nebo Y.

**Q: Mohu kombinovat více transformací v jednom stavu grafiky?**  
A: Ano — voláním `translate`, `scale`, `rotate` nebo `shear` postupně před vykreslením vytvoříte kombinovanou afinní transformaci.

**Q: Jak resetuji transformace po vykreslení tvaru?**  
A: Použijte `document.writeGraphicsRestore()` k návratu k dříve uloženému stavu grafiky.

**Q: Je možné otáčet obdélník kolem jeho středu?**  
A: Rozhodně. Přesuňte obdélník do počátku, aplikujte `rotate(angle)`, poté jej vraťte zpět před vykreslením.

**Q: Podporuje Aspose.Page anti‑aliasing pro hladší grafiku?**  
A: Ano — nastavte odpovídající možnosti vykreslování v `PsSaveOptions` pro povolení anti‑aliasingu.

---

**Poslední aktualizace:** 2025-12-07  
**Testováno s:** Aspose.Page for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}