---
date: 2026-03-05
description: Naučte se, jak nastavit barvu pozadí v Javě a přidávat průhledné obrázky
  do PostScriptu pomocí Aspose.Page pro Javu. Jednoduše převádějte PNG do PostScriptu.
linktitle: Add Transparent Image in Java PostScript
second_title: Aspose.Page Java API
title: 'Nastavit barvu pozadí v Javě: Přidat průhledný obrázek do PS'
url: /cs/java/postscript-transparency/add-transparent-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nastavit barvu pozadí v Java: Přidat průhledný obrázek do PS

## Úvod
Pokud potřebujete **set background color java** při práci s Java PostScript, přidání průhledných obrázků může vašim dokumentům dodat vyleštěný, profesionální vzhled. V tomto tutoriálu vás provedeme kompletním procesem nastavení barevného pozadí, konverzí PNG do PostScriptu a vykreslením jak neprůhledných, tak průhledných obrázků pomocí knihovny Aspose.Page for Java. Na konci budete schopni **add image to postscript** soubory s plnou kontrolou nad průhledností.

## Rychlé odpovědi
- **Jaká knihovna zpracovává průhlednost v Java PostScript?** Aspose.Page for Java.  
- **Mohu nastavit barvu pozadí před vykreslením obrázků?** Ano – použijte `document.setPaint()` a `fill()`.  
- **Jak převést PNG do PostScriptu?** Načtěte PNG pomocí `ImageIO.read()` a vykreslete jej pomocí `drawImage` nebo `drawTransparentImage`.  
- **Je podpora průhlednosti pro obrázky?** Použijte `drawTransparentImage` k zadání hodnoty průhlednosti (0‑255).  
- **Potřebuji licenci pro produkční použití?** Je vyžadována platná licence Aspose.Page for Java; je k dispozici bezplatná zkušební verze.

## Požadavky
Než začnete, ujistěte se, že máte:

1. **Java Development Kit (JDK)** – nainstalovanou nejnovější verzi.  
2. **Aspose.Page for Java** – stáhněte z [webu](https://releases.aspose.com/page/java/).  
3. **Document Directory** – složka, do které budete zapisovat soubory PostScript.  
4. **Translucent Image File** – např. `mask1.png`, který použijeme k demonstraci průhlednosti.

## Import balíčků
Ve vašem Java projektu importujte potřebné třídy. Tento blok zůstává nezměněn:

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

## Krok 1: Nastavit barvu pozadí v Java
Zde vytvoříme dokument, zvolíme velikost A4 a vyplníme červený obdélník, aby ilustroval kontrast pozadí.

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

## Krok 2: Přeložit souřadnice
Přesuňte kreslicí kurzor na vhodné místo na stránce před umístěním obrázků.

```java
// Translate to a specific position on the page
document.writeGraphicsSave();
document.translate(20, 100);
```

## Krok 3: Vytvořit objekt obrázku
Načtěte soubor PNG (náš krok **convert png to postscript**).

```java
// Create an image from the translucent image file
BufferedImage image = ImageIO.read(new File(dataDir + "mask1.png"));
```

## Krok 4: Přidat neprůhledný obrázek
Vykreslete obrázek normálně—tím se demonstruje **add image to postscript** bez průhlednosti.

```java
// Add the image to the document as an opaque RGB image
document.drawImage(image, new AffineTransform(1, 0, 0, 1, 100, 0), null);
```

## Krok 5: Přidat průhledný obrázek (vykreslit obrázek s průhledností)
Nyní použijeme `drawTransparentImage` k vykreslení stejného PNG s plnou neprůhledností (255). Upravením hodnoty můžete řídit průhlednost.

```java
// Add the image to the document as a transparent image
document.drawTransparentImage(image, new AffineTransform(1, 0, 0, 1, 350, 0), 255);
```

## Krok 6: Uložit a zavřít
Dokončete dokument a uvolněte prostředky.

```java
// Save and close the document
document.writeGraphicsRestore();
document.closePage();
document.save();
```

## Proč je to důležité
Nastavení barvy pozadí v Java vám poskytne plátno, které může zvýraznit překryté grafiky. Kombinací s **draw image with opacity** můžete přímo v PostScriptu vytvářet vodoznaky, loga nebo UI mock‑upy bez potřeby externích editačních nástrojů.

## Časté problémy a tipy
- **Obrázek se nezobrazuje průhledně:** Ověřte, že PNG skutečně obsahuje alfa kanál.  
- **Nesprávné barvy:** Pamatujte, že obdélník pozadí je vykreslen před obrázkem; změňte hodnoty `Color`, aby odpovídaly vašemu návrhu.  
- **Výkon:** Pro velké dokumenty znovu použijte jedinou instanci `AffineTransform`, aby se snížila zátěž tvorby objektů.

## Často kladené otázky

**Q: Mohu použít Aspose.Page for Java s jinými Java knihovnami?**  
A: Ano, Aspose.Page for Java lze bez problémů integrovat s jinými Java knihovnami pro rozšíření možností zpracování dokumentů.

**Q: Je k dispozici bezplatná zkušební verze Aspose.Page for Java?**  
A: Ano, bezplatnou zkušební verzi Aspose.Page for Java můžete získat [zde](https://releases.aspose.com/).

**Q: Jak mohu získat dočasnou licenci pro Aspose.Page for Java?**  
A: Dočasnou licenci můžete získat na [této stránce](https://purchase.aspose.com/temporary-license/).

**Q: Existují fóra pro podporu Aspose.Page for Java?**  
A: Ano, navštivte [forum Aspose.Page for Java](https://forum.aspose.com/c/page/39) pro komunitní podporu a diskuse.

**Q: Kde najdu dokumentaci k Aspose.Page for Java?**  
A: Podívejte se na komplexní [dokumentaci](https://reference.aspose.com/page/java/) pro podrobné informace o Aspose.Page for Java.

---

**Poslední aktualizace:** 2026-03-05  
**Testováno s:** Aspose.Page for Java 24.11 (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}