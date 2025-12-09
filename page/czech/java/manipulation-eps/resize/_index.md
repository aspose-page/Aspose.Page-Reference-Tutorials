---
date: 2025-12-02
description: Naučte se snadno měnit velikost EPS souborů v Javě pomocí Aspose.Page.
  Tento krok za krokem průvodce vám ukáže, jak měnit velikost EPS pomocí bodů, palců,
  milimetrů nebo procent.
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: Jak změnit velikost EPS souborů v Javě pomocí Aspose.Page
url: /cs/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak změnit velikost souborů EPS vivý způsob **jak změnit velikost EPS** souborů programově, jste na správném místě. V tomto tutoriálu vás provedeme změnou velikosti EPS obrázků v Javě pomocí knihovny Aspose.Page. Ať už potřebujete velikost zdvojnásobit, zmenšit na konkrétní rozměr, nebo pracovat s procenty, níže uvedené kroky vám poskytnou plnou kontrolu nad výstupními rozměry.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.Page for Java  
- **Mohu měnit velikost pomocí bodů, palců nebo milimetrů?** Ano – API podporuje všechny tři jednotky plus procenta.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; licence je vyžadována pro produkci.  
- **Jaká verze Javy je vyžadována?** Java 8 nebo novější.  
- **Je kód thread‑safe?** Každá instance `PsDocument` je izolovaná, takže můžete zpracovávat soubory paralelně.

## Požadavky
Než se pustíme do kódu, ujistěte se, že máte následující:

- Java Development Kit (JDK) nainstalovaný na vašem počítači.  
- Aspose.Page for Java library. Můžete si ji stáhnout **[zde](https://releases.aspose.com/page/java/)**.  
- Základní znalost programování v Javě.  

## Import balíčků
Ve vašem Java projektu zahrňte požadované importy, abyste mohli pracovat s objekty Aspose.Page a standardními I/O proudy.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## Jak změnit velikost EPS pomocí bodů
Níže je kompletní, krok za krokem příklad, který zdvojnásobí velikost EPS souboru pomocí bodů jako jednotky měření.

### Krok 1: Nastavte vstupní proud
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Krok 2: Inicializujte objekt `PsDocument`
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Krok 3: Získejte aktuální velikost EPS obrázku
```java
Dimension oldSize = doc.extractEpsSize();
```

### Krok 4: Vytvořte výstupní proud pro změněný soubor
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Krok 5: Změňte velikost a uložte EPS pomocí bodů
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## Jak změnit velikost EPS pomocí palců
Stejný pětikrokový vzor platí; stačí nahradit `Units.Points` za `Units.Inches` a podle potřeby upravit škálovací faktor.

## Jak změnit velikost EPS pomocí milimetrů
Opět postupujte podle stejných kroků, vyměňte jednotku za `Units.Millimeters`. To je užitečné, když potřebujete metrické rozměry pro tiskové workflow.

## Jak změnit velikost EPS pomocí procent
Pro škálování založené na procentech ponechte jednotku jako `Units.Percent`. Vynásobte původní šířku a výšku požadovaným procentem (např. `0.5` pro 50 % zmenšení).

## Časté úskalí a tipy
- **Vždy zavírejte proudy** – V produkčním kódu obalte proudy do try‑with‑resources, aby nedocházelo k zamykání souborů.  
- **Zachovejte poměr stran** – Vynásobte jak šířku, tak výšku stejným faktorem, pokud nechcete úmyslně deformaci.  
- **Zkontrolujte DPI** – Změna velikosti nemění DPI; pokud potřebujete jiné DPI, upravte jej samostatně po změně velikosti.

## Závěr
Nyní víte **jak změnit velikost EPS** souborů v Javě pomocí Aspose.Page, ať už preferujete body, palce, milimetry nebo procenta. Tato flexibilita vám umožní integrovat manipulaci s EPS do automatizovaných pipeline, desktopových utilit nebo serverových služeb.

## Často kladené otázky

**Q: Mohu tuto knihovnu použít pro jiné formáty obrázků?**  
A: Ne, Aspose.Page je specializována pouze na soubory PostScript a EPS.

**Q: Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Java?**  
A: Ano, můžete si prozkoumat bezplatnou zkušební verzi **[zde](https://releases.aspose.com/)**.

**Q: Kde mohu najít další pomoc a diskuze?**  
A: Navštivte **[forum Aspose.Page](https://forum.aspose.com/c/page/39)** pro podporu komunity.

**Q: Jak mohu získat dočasnou licenci?**  
A: Dočasnou licenci můžete získat **[zde](https://purchase.aspose.com/temporary-license/)**.

**Q: Existují nějaké ukázkové projekty?**  
A: Ano, podívejte se na dokumentaci **[zde](https://reference.aspose.com/page/java/)**.

---

**Poslední aktualizace:** 2025-12-02  
**Testováno s:** Aspose.Page for Java 24.12 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}