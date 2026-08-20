---
date: 2026-03-13
description: Naučte se, jak převést XPS na JPEG v Javě pomocí Aspose.Page Java. Tento
  krok‑za‑krokem průvodce vám ukáže, jak efektivně převést XPS na JPEG pomocí knihovny
  Aspose.Page Java.
linktitle: Convert XPS to JPEG in Java
second_title: Aspose.Page Java API
title: Jak převést XPS na JPEG v Javě pomocí Aspose.Page Java
url: /cs/java/xps-conversion/to-jpeg/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak převést XPS na JPEG v Javě pomocí Aspose.Page Java

## Úvod do Aspose.Page Java
V tomto tutoriálu **se naučíte, jak převést XPS na JPEG** pomocí knihovny **Aspose.Page Java**. Převod souborů XPS na obrázky JPEG je častý požadavek, když potřebujete zobrazit stránky dokumentu jako rastrovou grafiku v webových portálech, desktopových prohlížečích nebo e‑mailových přílohách. Projdeme každý řádek kódu, vysvětlíme, proč je každé nastavení důležité, a podělíme se o praktické tipy, abyste mohli tuto konverzní pipeline s jistotou začlenit do svých Java aplikací.

## Rychlé odpovědi
- **Jaká knihovna provádí konverzi?** Aspose.Page Java  
- **Mohu vybrat konkrétní stránky?** Ano – použijte `setPageNumbers` v `JpegSaveOptions`  
- **Jakou kvalitu obrazu mohu ovládat?** Režim vyhlazování, rozlišení a nastavení kvality JPEG  
- **Potřebuji licenci pro produkční nasazení?** Ano, je vyžadována komerční licence (k dispozici je bezplatná zkušební verze)  
- **Je kód kompatibilní s Java 8?** Naprosto – API funguje s Java 8 a novějšími  

## Co je XPS a proč převádět XPS na JPEG?
XPS (XML Paper Specification) je formát dokumentu s pevnou rozvržením, podobný PDF. Převod XPS na JPEG je užitečný, když potřebujete rastrové obrázky pro náhledy, e‑mailové přílohy nebo při integraci se systémy, které akceptují jen soubory s obrázky. JPEG poskytuje dobrý poměr mezi vizuální kvalitou a velikostí souboru, což ho činí ideálním pro webové náhledy.

## Požadavky
Než se ponoříme do kódu, ujistěte se, že máte následující:

- **Vývojové prostředí Java** – nainstalovaný a nakonfigurovaný JDK 8 nebo novější.  
- **Aspose.Page pro Java** – stáhněte si nejnovější knihovnu z oficiální stránky [here](https://releases.aspose.com/page/java/).  
- **Ukázkový XPS dokument** – soubor XPS, který chcete převést na obrázky JPEG.  

## Import balíčků
Začněte importováním potřebných tříd do svého Java zdrojového souboru:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Krok 1: Inicializace cest a načtení XPS dokumentu
Nastavte adresář, který obsahuje váš zdrojový XPS soubor, a vytvořte instanci `XpsDocument`:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize XPS input stream
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

> **Tip:** Použijte `Paths.get()` z `java.nio.file` pro platformově nezávislé zpracování cest.

## Krok 2: Nastavení možností uložení JPEG
Definujte, jak mají být JPEG obrázky vykresleny – rozlišení, vyhlazování a které stránky exportovat:

```java
// Initialize options object with necessary parameters.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

- `setResolution(300)` vytváří výstup s vysokým rozlišením vhodný pro tisk.  
- `setPageNumbers` vám umožní vybrat jen požadované stránky, čímž šetří čas i paměť.

## Krok 3: Vytvoření vykreslovacího zařízení
`ImageDevice` zachycuje vykreslené stránky jako pole bajtů:

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

## Krok 4: Vykreslení XPS dokumentu do JPEG
Zavolejte metodu `save` a předávejte zařízení i dříve nakonfigurované možnosti:

```java
document.save(device, options);
```

V tomto okamžiku `device` obsahuje dvourozměrné pole, kde každý prvek představuje stránku zakódovanou jako JPEG.

## Krok 5: Procházení výsledku a zápis souborů
Projděte vykreslené stránky a každé pole bajtů zapište do samostatného JPEG souboru:

```java
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //close the stream
        imageStream.close();
    }
}
```

Každý soubor bude pojmenován `XPStoJPEG_<documentIndex>_<pageIndex>.jpeg`, což usnadní identifikaci zdrojového dokumentu a čísla stránky.

## Běžné případy použití
- **Generování náhledů** pro systémy správy dokumentů.  
- **Vkládání náhledových stránek** do webových aplikací, kde jsou podporovány jen formáty obrázků.  
- **Dávkové zpracování velkých archivů XPS** do JPEG pro archivaci nebo reportování.  

## Běžné problémy a řešení
| Symptom | Předpokládaná příčina | Řešení |
|---------|-----------------------|--------|
| **Prázdné soubory JPEG** | Výstupní stream není správně vyprázdněn nebo uzavřen | Ujistěte se, že `imageStream.close()` je voláno uvnitř vnitřní smyčky (jak je ukázáno). |
| **Chyby nedostatku paměti** při velkých XPS souborech | Vykreslování všech stránek najednou spotřebuje příliš mnoho RAM | Zpracovávejte stránky v menších dávkách nebo zvyšte haldu JVM (`-Xmx`). |
| **Chybějící stránky** | `setPageNumbers` neobsahuje požadovanou stránku | Ověřte, že pole čísel stránek odpovídá skutečným indexům stránek XPS (číslování od 1). |

## Často kladené otázky

### Q: Je Aspose.Page vhodný pro komerční projekty?
A: Ano, Aspose.Page je komerční produkt s dostupnými licenčními možnostmi. Podrobnosti najdete [here](https://purchase.aspose.com/buy).

### Q: Mohu si Aspose.Page vyzkoušet před zakoupením?
A: Ano, můžete získat bezplatnou zkušební verzi [here](https://releases.aspose.com/).

### Q: Kde najdu dokumentaci k Aspose.Page?
A: Dokumentace je k dispozici [here](https://reference.aspose.com/page/java/).

### Q: Jak mohu získat podporu pro Aspose.Page?
A: Navštivte [Aspose.Page Forum](https://forum.aspose.com/c/page/39) pro komunitně založenou podporu.

### Q: Potřebuji dočasnou licenci pro testování?
A: Ano, dočasnou licenci můžete získat [here](https://purchase.aspose.com/temporary-license/).

## Závěr
Nyní ovládáte **jak převést XPS na JPEG** pomocí **Aspose.Page Java**. Dodržením tohoto krok‑za‑krokem návodu můžete tuto konverzní pipeline integrovat do jakékoli Java aplikace – ať už jde o desktopový nástroj, webovou službu nebo dávkové zpracování. Nebojte se experimentovat s různými rozlišeními, výběrem stránek a formáty obrázků, aby vyhovovaly potřebám vašeho projektu.

---

**Last Updated:** 2026-03-13  
**Tested With:** Aspose.Page 24.11 for Java (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}