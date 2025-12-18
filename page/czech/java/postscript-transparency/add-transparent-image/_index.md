---
date: 2025-12-18
description: Naučte se, jak vytvořit PostScript dokument v Javě a přidat průhledný
  obrázek pomocí Aspose.Page pro Javu. Tento průvodce ukazuje, jak snadno přidat obrázek
  do PostScriptu.
linktitle: Create PostScript Document Java – Add Transparent Image
second_title: Aspose.Page Java API
title: Vytvořit PostScript dokument v Javě – Přidat průhledný obrázek
url: /cs/java/postscript-transparency/add-transparent-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání průhledného obrázku v Java PostScript

## Úvod
Ve světě Java PostScript se často pro zvýšení vizuální přitažlivosti dokumentů používají průhledné obrázky. Tento tutoriál vás provede procesem **create postscript document java** při začlenění průhledné grafiky pomocí výkonné knihovny Aspose.Page for Java. Ukážeme si, jak přidat obrázek do postscriptu, přesně jej umístit a řídit jeho neprůhlednost pro profesionální výsledek.

## Rychlé odpovědi
- **Co tento tutoriál pokrývá?** Přidání průhledného PNG do PostScript dokumentu pomocí Aspose.Page for Java.  
- **Která knihovna je vyžadována?** Aspose.Page for Java (stáhněte z oficiální webové stránky).  
- **Potřebuji licenci?** Pro produkční použití je vyžadována dočasná nebo plná licence; je k dispozici bezplatná zkušební verze.  
- **Mohu použít jiné formáty obrázků?** Ano, ale PNG s alfa kanálem funguje nejlépe pro průhlednost.  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní příklad.

## Co je PostScript dokument v Javě?
PostScript dokument je soubor jazyka pro popis stránky, který popisuje text, grafiku a obrázky. Pomocí Javy můžete tyto soubory programově generovat, což vám poskytuje plnou kontrolu nad rozvržením a vykreslováním. Hlavní klíčové slovo **create postscript document java** odráží tuto schopnost.

## Proč přidávat průhledné obrázky?
Průhledné obrázky vám umožňují překrývat grafiku, aniž by zakrývaly podkladový obsah, což je ideální pro vodoznaky, loga nebo dekorativní prvky. Kombinace průhlednosti s přesným umístěním vytváří vyladěné dokumenty v souladu se značkou.

## Požadavky
Před ponořením se do tutoriálu se ujistěte, že máte následující požadavky připravené:
1. Java Development Kit (JDK): Ujistěte se, že máte na svém počítači nainstalovaný nejnovější JDK.  
2. Aspose.Page for Java: Stáhněte a nainstalujte knihovnu Aspose.Page for Java z [webové stránky](https://releases.aspose.com/page/java/).  
3. Dokumentový adresář: Vytvořte na svém systému adresář, kde budete ukládat své Java PostScript dokumenty.  
4. Soubor průhledného obrázku: Připravte soubor průhledného obrázku (např. „mask1.png“), který použijete v tutoriálu.

## Import balíčků
Ve svém Java projektu importujte potřebné balíčky, abyste využili funkce poskytované knihovnou Aspose.Page for Java. Níže je přesný blok importů, který budete potřebovat:

```java
import java.awt.Color;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Jak vytvořit postscript dokument v Javě s průhledným obrázkem?
Níže je krok za krokem průvodce. Každý krok obsahuje krátké vysvětlení následované původním blokem kódu (beze změny).

### Krok 1: Nastavení barvy pozadí
Začínáme vytvořením PostScript dokumentu, otevřením výstupního proudu a nakreslením červeného obdélníku jako vizuální reference pro průhledný obrázek.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTransparentImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Add a red rectangle under images for visual contrast
document.setPaint(new Color(211, 8, 48));
document.fill(new Rectangle2D.Float(0, 0, (int) options.getPageSize().getWidth(), 300));
```

### Krok 2: Posunutí souřadnic
Před kreslením posuneme počátek do vhodné polohy na stránce, aby se obrázek objevil tam, kde jej chceme.

```java
// Translate to a specific position on the page
document.writeGraphicsSave();
document.translate(20, 100);
```

### Krok 3: Vytvoření objektu obrázku
Načtěte soubor PNG, který obsahuje alfa kanál. Tento obrázek bude použit jak pro neprůhledné, tak pro průhledné vykreslení.

```java
// Create an image from the translucent image file
BufferedImage image = ImageIO.read(new File(dataDir + "mask1.png"));
```

### Krok 4: Přidání neprůhledného obrázku
Nejprve nakreslíme obrázek jako běžnou RGB bitmapu. Tím demonstrujeme rozdíl, když později použijeme průhlednost.

```java
// Add the image to the document as an opaque RGB image
document.drawImage(image, new AffineTransform(1, 0, 0, 1, 100, 0), null);
```

### Krok 5: Přidání průhledného obrázku
Nyní nakreslíme stejný obrázek s plnou neprůhledností (255) nebo libovolnou hodnotou mezi 0‑255 pro řízení průhlednosti. Zde používáme 255 pro plnou neprůhlednost, ale můžete hodnotu snížit pro efekt průhlednosti.

```java
// Add the image to the document as a transparent image
document.drawTransparentImage(image, new AffineTransform(1, 0, 0, 1, 350, 0), 255);
```

### Krok 6: Uložení a uzavření
Nakonec obnovíme stav grafiky, zavřeme stránku a uložíme dokument na disk.

```java
// Save and close the document
document.writeGraphicsRestore();
document.closePage();
document.save();
```

## Časté problémy a řešení
- **FileNotFoundException** – Ověřte, že `dataDir` ukazuje na správnou složku a že `mask1.png` existuje.  
- **ImageIO.read returns null** – Ujistěte se, že PNG má platný formát a není poškozený.  
- **Transparent image appears opaque** – Upravte třetí parametr funkce `drawTransparentImage` (0 = zcela průhledné, 255 = zcela neprůhledné).  

## Často kladené otázky
### Mohu použít Aspose.Page for Java s jinými Java knihovnami?
Ano, Aspose.Page for Java lze bez problémů integrovat s jinými Java knihovnami pro rozšíření schopností zpracování dokumentů.

### Je k dispozici bezplatná zkušební verze Aspose.Page for Java?
Ano, můžete získat bezplatnou zkušební verzi Aspose.Page for Java [zde](https://releases.aspose.com/).

### Jak mohu získat dočasnou licenci pro Aspose.Page for Java?
Dočasnou licenci můžete získat na [tomto odkazu](https://purchase.aspose.com/temporary-license/).

### Existují fóra pro podporu Aspose.Page for Java?
Ano, navštivte [forum Aspose.Page for Java](https://forum.aspose.com/c/page/39) pro komunitní podporu a diskuse.

### Kde najdu dokumentaci k Aspose.Page for Java?
Podívejte se na komplexní [dokumentaci](https://reference.aspose.com/page/java/) pro podrobné informace o Aspose.Page for Java.

## Závěr
Gratulujeme! Úspěšně jste se naučili, jak **create postscript document java** a přidávat průhledné obrázky pomocí Aspose.Page for Java. Experimentujte s různými obrázky, úrovněmi neprůhlednosti a pozicemi, abyste vytvořili vizuálně úchvatné dokumenty, které splňují požadavky vaší značky.

---

**Poslední aktualizace:** 2025-12-18  
**Testováno s:** Aspose.Page for Java 24.11 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}