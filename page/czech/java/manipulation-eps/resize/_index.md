---
date: 2026-02-07
description: Naučte se, jak změnit velikost EPS souborů v Javě a upravit rozměry EPS
  pomocí Aspose.Page. Tento krok‑za‑krokem průvodce vám ukáže, jak změnit velikost
  EPS pomocí bodů, palců, milimetrů nebo procent.
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: Jak změnit velikost EPS souborů v Javě pomocí Aspose.Page
url: /cs/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak změnit velikost EPS souborů v Javě pomocí Aspose.Page

## Úvod
Pokud hledáte spolehlivý způsob **jak změnit velikost EPS** souborů programově, jste na správném místě. V tomto tutoriálu vás provedeme změnou velikosti EPS obrázků v Javě pomocí knihovny Aspose.Page. Ať už potřebujete velikost zdvojnásobit, zmenšit na konkrétní rozměr nebo pracovat s procenty, níže uvedené kroky vám poskytnou plnou kontrolu nad výstupními rozměry. Porozumění **jak změnit velikost eps** je zásadní, když potřebujete přizpůsobit grafiku různým tiskovým rozvržením nebo rozlišením obrazovky.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.Page pro Java  
- **Mohu měnit velikost pomocí bodů, palců nebo milimetrů?** Ano – API podporuje všechny tři jednotky plus procenta.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze stačí pro testování; licence je vyžadována pro produkci.  
- **Jaká verze Javy je požadována?** Java 8 nebo novější.  
- **Je kód bezpečný pro vlákna?** Každá instance `PsDocument` je izolovaná, takže soubory můžete zpracovávat paralelně.  

## Co je EPS a proč jej měnit velikost?
Encapsulated PostScript (EPS) je populární formát vektorové grafiky používaný v publikování a tisku. Někdy je původní EPS soubor vytvořen v rozměru, který neodpovídá vašemu cílovému výstupu – například logo navržené na 72 pts může potřebovat 144 pts pro větší brožuru. Znalost **jak změnit velikost eps** vám umožní zachovat vektorovou kvalitu a přizpůsobit rozměry jakémukoli workflow.

## Proč použít Aspose.Page pro změnu velikosti EPS?
- **Plná kontrola nad jednotkami** – body, palce, milimetry nebo procenta.  
- **Žádné externí závislosti** – čisté Java API, žádné nativní knihovny.  
- **Vysoký výkon** – vhodné pro dávkové zpracování na serverech.  
- **Zachovává vektorovou věrnost** – výstup zůstává škálovatelný bez rasterizace.

## Požadavky
Než se pustíme do kódu, ujistěte se, že máte následující:

- Java Development Kit (JDK) nainstalovaný na vašem počítači.  
- Knihovnu Aspose.Page pro Java. Můžete si ji stáhnout **[zde](https://releases.aspose.com/page/java/)**.  
- Základní znalosti programování v Javě.  

## Import balíčků
Ve vašem Java projektu zahrňte potřebné importy, abyste mohli pracovat s objekty Aspose.Page a standardními I/O proudy.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## Jak změnit rozměry EPS pomocí různých jednotek
Knihovna vám umožní **změnit rozměry eps** jednoduše výběrem odpovídajícího enumu `Units`. Níže projdeme stejný pětikrokový vzor pro body, palce, milimetry a procenta. Jediné, co se mění, je jednotka, kterou předáte metodě `resizeEps`.

## Jak změnit velikost EPS pomocí bodů
Níže je kompletní, krok‑za‑krokem příklad, který zdvojnásobí velikost EPS souboru pomocí bodů jako měrné jednotky.

### Krok 1: Nastavte vstupní stream
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

### Krok 4: Vytvořte výstupní stream pro změněný soubor
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Krok 5: Změňte velikost a uložte EPS pomocí bodů
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## Jak změnit velikost EPS pomocí palců
Stejný pětikrokový vzor platí; stačí nahradit `Units.Points` za `Units.Inches` a upravit škálovací faktor na požadovanou hodnotu v palcích.

## Jak změnit velikost EPS pomocí milimetrů
Opět postupujte podle stejných kroků, přičemž jednotku vyměníte za `Units.Millimeters`. To je užitečné, když potřebujete metrické rozměry pro tiskové workflow.

## Jak změnit velikost EPS pomocí procent
Pro škálování založené na procentech ponechte jednotku jako `Units.Percent`. Vynásobte původní šířku a výšku požadovaným procentem (např. `0.5` pro 50 % zmenšení).

## Časté úskalí a tipy
- **Vždy zavírejte proudy** – V produkčním kódu obalte proudy do try‑with‑resources, aby nedocházelo k zamykání souborů.  
- **Zachovejte poměr stran** – Násobte šířku i výšku stejným faktorem, pokud nechcete úmyslně deformovat obrázek.  
- **Zkontrolujte DPI** – Změna velikosti nemění DPI; pokud potřebujete jiné DPI, upravte jej samostatně po změně velikosti.  
- **Bezpečnost pro vlákna** – Vytvořte nový `PsDocument` pro každé vlákno; sdílení stejné instance může vést k neočekávaným výsledkům.  

## Často kladené otázky

**Q: Mohu tuto knihovnu použít pro jiné formáty obrázků?**  
A: Ne, Aspose.Page je specializována pouze na soubory PostScript a EPS.

**Q: Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Javu?**  
A: Ano, bezplatnou zkušební verzi můžete prozkoumat **[zde](https://releases.aspose.com/)**.

**Q: Kde mohu najít další pomoc a diskuse?**  
A: Navštivte **[forum Aspose.Page](https://forum.aspose.com/c/page/39)** pro podporu komunity.

**Q: Jak mohu získat dočasnou licenci?**  
A: Dočasnou licenci můžete získat **[zde](https://purchase.aspose.com/temporary-license/)**.

**Q: Existují nějaké ukázkové projekty?**  
A: Ano, podívejte se na dokumentaci **[zde](https://reference.aspose.com/page/java/)**.

---

**Poslední aktualizace:** 2026-02-07  
**Testováno s:** Aspose.Page for Java 24.12 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}