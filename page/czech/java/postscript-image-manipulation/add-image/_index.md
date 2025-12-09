---
date: 2025-12-09
description: Naučte se, jak vytvořit PostScript dokument v Javě a posunout a otočit
  obrázek pomocí Aspose.Page pro bezproblémovou manipulaci s obrázky.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: Vytvoření PostScript dokumentu v Javě – Přidání obrázku v Java PostScript
url: /cs/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření PostScript dokumentu v Javě – Přidání obrázku v Java PostScript

## Úvod
V tomto tutoriálu se naučíte, jak **vytvořit PostScript dokument v Javě** a vložit obrázky pomocí knihovny Aspose.Page pro Java. Provedeme vás každým krokem, od nastavení dokumentu až po aplikaci transformací, jako jsou operace **posunutí a otočení obrázku**. Na konci budete schopni programově generovat bohaté PostScript soubory a přizpůsobit umístění obrázků tak, aby přesně odpovídalo vašemu rozvržení.

## Rychlé odpovědi
- **Jaká knihovna je vyžadována?** Aspose.Page for Java  
- **Mohu přidat více obrázků?** Ano – opakujte kroky transformace a kreslení  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; licence je vyžadována pro produkci  
- **Jaká verze Javy je podporována?** Java 8 a novější  
- **Je podporováno otáčení obrázku?** Rozhodně – použijte `AffineTransform.rotate()`  

## Co je vytváření PostScript dokumentu v Javě?
PostScript dokument je soubor popisující jazyk stránky, který definuje text, grafiku a obrázky. Pomocí Aspose.Page můžete tyto soubory programově generovat v Javě, což vám dává plnou kontrolu nad rozvržením, stavem grafiky a manipulací s obrázky bez potřeby PostScript interpretátoru.

## Proč použít Aspose.Page pro manipulaci s obrázky?
- **High‑level API:** Zjednodušuje složité PostScript příkazy.  
- **Cross‑platform:** Funguje na jakémkoli OS, který podporuje Javu.  
- **Full graphics state control:** Snadno ukládá, obnovuje, posouvá, škáluje a otáčí grafiku.  
- **No external dependencies:** Interně zpracovává načítání a konverzi obrázků.  

## Požadavky
Než se pustíme do kódu, ujistěte se, že máte:

- Nainstalovaný Java Development Kit (JDK) na vašem systému.  
- Knihovnu Aspose.Page for Java. Můžete si ji stáhnout [zde](https://releases.aspose.com/page/java/).  
- Základní znalosti programování v Javě.  

## Import balíčků
Pro zahájení importujte potřebné balíčky ve vašem Java projektu. Použijte následující úryvek kódu jako referenci:

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Krok 1: Zapsání uložení grafiky
Prvním krokem je zapsání uložení grafiky do dokumentu. Tím zajistíte, že jakékoli transformace nebo úpravy provedené později lze v případě potřeby vrátit zpět.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

## Krok 2: Posunutí a transformace (posunutí a otočení obrázku)
Dále posuňte dokument a vytvořte objekt `BufferedImage` z obrázkového souboru. Aplikujte sérii transformací, jako je škálování a otáčení pomocí `AffineTransform`. Zde se provádí operace **posunutí a otočení obrázku**.

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

## Krok 3: Přidání obrázku do dokumentu
Nyní přidejte transformovaný obrázek do dokumentu.

```java
document.drawImage(image, transform, null);
```

## Krok 4: Zapsání obnovení grafiky
Po přidání obrázku zapište obnovení grafiky, čímž dokončíte provedené změny.

```java
document.writeGraphicsRestore();
```

## Krok 5: Uzavření aktuální stránky a uložení
Uzavřete aktuální stránku a uložte dokument.

```java
document.closePage();
document.save();
```

Tyto kroky můžete opakovat pro přidání více obrázků nebo přizpůsobit transformace podle vašich požadavků.

## Časté problémy a řešení
- **FileNotFoundException:** Ujistěte se, že cesta `dataDir` končí oddělovačem souborů (`/` nebo `\\`) a že název obrázkového souboru přesně odpovídá.  
- **ImageIO.read returns null:** Ověřte, že formát obrázku je podporován (např. JPEG, PNG).  
- **Incorrect rotation angle:** `AffineTransform.rotate` očekává radiány. Případně převádějte stupně na radiány (`Math.toRadians(degrees)`).  

## Často kladené otázky

**Q: Mohu použít Aspose.Page pro Java s jinými programovacími jazyky?**  
A: Aspose.Page primárně podporuje Javu, ale jsou k dispozici verze i pro jiné programovací jazyky.

**Q: Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Java?**  
A: Ano, bezplatnou zkušební verzi získáte [zde](https://releases.aspose.com/).

**Q: Jak mohu získat dočasnou licenci pro Aspose.Page pro Java?**  
A: Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

**Q: Kde najdu komunitní podporu a diskuse týkající se Aspose.Page pro Java?**  
A: Navštivte [Aspose.Page Forum](https://forum.aspose.com/c/page/39) pro komunitní podporu.

**Q: Existují další zdroje pro zakoupení Aspose.Page pro Java?**  
A: Knihovnu můžete zakoupit [zde](https://purchase.aspose.com/buy).

## Závěr
Gratulujeme! Úspěšně jste se naučili, jak **vytvořit PostScript dokument v Javě** a vložit obrázky pomocí Aspose.Page pro Java. Prozkoumejte [dokumentaci](https://reference.aspose.com/page/java/) pro pokročilejší funkce a možnosti, jako jsou vektorová grafika, vykreslování textu a vlastní velikosti stránek.

---

**Poslední aktualizace:** 2025-12-09  
**Testováno s:** Aspose.Page for Java 23.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}