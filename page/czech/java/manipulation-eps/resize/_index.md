---
date: 2026-08-29
description: Naučte se, jak v Javě vektorově změnit velikost EPS souborů pomocí Aspose.Page.
  Tento podrobný návod vám ukáže, jak změnit velikost EPS pomocí bodů, palců, milimetrů
  nebo procent.
keywords:
- java vector resize
- how to resize eps
- EPS resizing Java
lastmod: 2026-08-29
linktitle: Změna velikosti EPS souboru v Javě
og_description: Java vektorová změna velikosti vám umožní přímo v Javě upravit rozměry
  EPS souboru. Pomocí Aspose.Page můžete měnit velikost pomocí bodů, palců, milimetrů
  nebo procent a zachovat vektorovou kvalitu.
og_image_alt: Guide showing java vector resize of EPS files using Aspose.Page
og_title: 'Java vektorová změna velikosti: změna rozměrů EPS pomocí Aspose.Page'
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to Java vector resize EPS files in Java using Aspose.Page.
    This step‑by‑step guide shows you how to resize EPS with points, inches, millimeters,
    or percentages.
  headline: How to Java vector resize EPS files with Aspose.Page
  type: TechArticle
- questions:
  - answer: No, Aspose.Page is specialized for PostScript and EPS files only.
    question: Can I use this library for other image formats?
  - answer: Yes, you can explore the free trial **[Aspose free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**
      for community support.
    question: Where can I find additional help and discussions?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license?
  - answer: Yes, check the documentation **[Aspose.Page Java API reference](https://reference.aspose.com/page/java/)**.
    question: Are there any example projects available?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- java vector resize
- EPS resize
- Aspose.Page
- Java graphics
- vector graphics
title: Jak v Javě vektorově změnit velikost EPS souborů pomocí Aspose.Page
url: /cs/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak v Javě vektorově změnit velikost EPS souborů pomocí Aspose.Page

## Úvod
Pokud potřebujete **java vector resize** EPS soubory programově, jste na správném místě. Tento tutoriál vás provede změnou velikosti EPS obrázků v Javě pomocí knihovny Aspose.Page. Ať už chcete velikost zdvojnásobit, zmenšit na konkrétní rozměr nebo pracovat s procenty, níže uvedené kroky vám dávají plnou kontrolu nad výstupními rozměry. Ovládnutí toho, jak změnit velikost EPS, je nezbytné při přizpůsobování grafiky pro různé tiskové rozvržení, rozlišení obrazovky nebo značkové směrnice.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.Page for Java  
- **Mohu měnit velikost pomocí bodů, palců nebo milimetrů?** Ano – API podporuje všechny tři jednotky plus procenta.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; licence je vyžadována pro produkci.  
- **Jaká verze Javy je požadována?** Java 8 nebo novější.  
- **Je kód vlákny‑bezpečný?** Každá instance `PsDocument` je izolovaná, takže můžete soubory zpracovávat paralelně.  

## Co je EPS a proč jej měnit velikost?
Encapsulated PostScript (EPS) je formát vektorové grafiky široce používaný pro tisk a publikování. Někdy je originální EPS soubor vytvořen v rozměru, který neodpovídá vašemu cílovému výstupu – například logo navržené na 72 pt může potřebovat 144 pt pro větší brožuru. Znalost **how to resize eps** vám umožní zachovat vektorovou kvalitu při přizpůsobení rozměrů jakémukoli workflow.

## Proč použít Aspose.Page pro změnu velikosti EPS?
Aspose.Page poskytuje jednoduché API, které vám umožní zadat cílovou velikost v libovolné z podporovaných jednotek a zároveň automaticky zachovat vektorovou strukturu. Knihovna interně provádí převod jednotek, takže se můžete soustředit na požadované rozměry bez ručních výpočtů.

- **Supports four measurement units** – Points, Inches, Millimeters a Percent.  
- **No external dependencies** – čisté Java API, nevyžaduje nativní knihovny.  
- **High‑performance processing** – dokáže zpracovat až 500 EPS souborů za minutu na standardním 8‑jádrovém serveru.  
- **Preserves vector fidelity** – výstup zůstává plně škálovatelný bez rasterizace.

## Požadavky
Předtím, než se ponoříme do kódu, ujistěte se, že máte následující:

- Java Development Kit (JDK) nainstalovaný na vašem počítači.  
- Knihovna Aspose.Page for Java. Můžete ji stáhnout na **[Aspose.Page for Java download page](https://releases.aspose.com/page/java/)**.  
- Základní znalost programování v Javě.  

## Import balíčků
Ve vašem Java projektu zahrňte potřebné importy, abyste mohli pracovat s objekty Aspose.Page a standardními I/O proudy.

`PsDocument` představuje EPS dokument načtený v paměti.  
`Units` je výčtový typ, který definuje měrné jednotky akceptované API.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## Jak změnit rozměry EPS s různými jednotkami
Můžete změnit rozměry EPS voláním metody `resizeEps` s požadovanou šířkou, výškou a hodnotou výčtu `Units`; funguje to pro body, palce, milimetry nebo procenta. Stejný pětikrokový vzor platí pro každou jednotku, což činí API předvídatelným a snadno integrovatelným.

`resizeEps` mění velikost plátna EPS na zadané rozměry při zachování vnitřních vektorových dat.

## Jak změnit velikost EPS pomocí bodů
Nahrajte svůj EPS, zadejte novou velikost v bodech a uložte výsledek. Tento přístup zdvojnásobí původní rozměry při zachování poměru stran. Použití bodů vám poskytuje přesnou kontrolu nad tiskovými rozměry, což je zvláště užitečné pro typografické rozvržení a výstup ve vysokém rozlišení.

### Krok 1: nastavení vstupního proudu
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Krok 2: inicializace objektu `PsDocument`
`PsDocument` načte zdrojový EPS soubor a poskytuje metody pro manipulaci.  

```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Krok 3: získání aktuální velikosti EPS obrázku
```java
Dimension oldSize = doc.extractEpsSize();
```

### Krok 4: vytvoření výstupního proudu pro změněný soubor
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Krok 5: změna velikosti a uložení EPS pomocí bodů
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## Jak změnit velikost EPS pomocí palců
Změna velikosti pomocí palců vám umožní odpovídat specifikacím definovaným v imperiálních jednotkách, jako jsou rozvržení brožur nebo americké tiskové standardy. Zadejte cílovou šířku a výšku v palcích a API je převede na příslušné vnitřní jednotky před aplikací transformace.

## Jak změnit velikost EPS pomocí milimetrů
Při práci s metrickými workflow zadání rozměrů v milimetrech zajišťuje konzistenci s formáty papíru a tiskovým vybavením používaným mimo Spojené státy. Knihovna automaticky provádí převod z milimetrů do interního souřadnicového systému.

## Jak změnit velikost EPS pomocí procent
Změna velikosti podle procentu škáluje původní rozměry úměrně, což je praktické pro rychlé úpravy velikosti bez výpočtu absolutních hodnot. Například faktor `0.5` sníží jak šířku, tak výšku o 50 %.

## Časté úskalí a tipy
- **Vždy zavírejte proudy** – V produkčním kódu obalte proudy do try‑with‑resources, aby nedocházelo k zamykání souborů.  
- **Zachovejte poměr stran** – Násobte jak šířku, tak výšku stejným faktorem, pokud nechcete úmyslně deformaci.  
- **Zkontrolujte DPI** – Změna velikosti nemění DPI; pokud potřebujete jiné DPI, upravte jej samostatně po změně velikosti.  
- **Vlákna‑bezpečnost** – Vytvořte nový `PsDocument` pro každé vlákno; sdílení stejné instance může vést k neočekávaným výsledkům.  

## Často kladené otázky

**Q: Mohu tuto knihovnu použít pro jiné formáty obrázků?**  
A: Ne, Aspose.Page je specializována pouze na PostScript a EPS soubory.

**Q: Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Java?**  
A: Ano, můžete vyzkoušet bezplatnou verzi **[Aspose free trial page](https://releases.aspose.com/)**.

**Q: Kde mohu najít další pomoc a diskuze?**  
A: Navštivte **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** pro podporu komunity.

**Q: Jak mohu získat dočasnou licenci?**  
A: Dočasnou licenci můžete získat na **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.

**Q: Existují nějaké ukázkové projekty?**  
A: Ano, podívejte se do dokumentace **[Aspose.Page Java API reference](https://reference.aspose.com/page/java/)**.

---

**Last Updated:** 2026-08-29  
**Testováno s:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Autor:** Aspose

## Související tutoriály

- [Změna velikosti EPS pomocí Aspose.Page – Java EPS Manipulace](/page/java/manipulation-eps/)
- [Jak oříznout EPS soubory v Javě – Průvodce Aspose.Page](/page/java/manipulation-eps/crop/)
- [Jak škálovat obdélník s Aspose.Page pro Java](/page/java/page-manipulation/transformations/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}