---
date: 2026-02-15
description: Naučte se, jak vytvářet PostScript dokumenty v Javě a generovat soubory
  PostScript s posunem a rotací obrázku pomocí Aspose.Page pro Javu.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: Vytvořit PostScript v Javě – Přidat obrázek v Java PostScriptu
url: /cs/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření PostScript Java – Přidání obrázku v Java PostScript

## Úvod
V tomto tutoriálu se naučíte, jak **create postscript java** dokumenty a vložit obrázky pomocí knihovny Aspose.Page for Java. Provedeme vás každým krokem, od inicializace nového souboru PostScript až po aplikaci transformací **translate and rotate image**. Na konci budete schopni programově generovat soubory PostScript a ovládat umístění obrázku s pixelovou přesností – ideální pro automatizované reportování, tiskové workflow nebo jakýkoli scénář, kde potřebujete výstup **generate postscript document** z Javy.

## Rychlé odpovědi
- **What library is required?** Aspose.Page for Java  
- **Can I add multiple images?** Yes – repeat the transform and draw steps  
- **Do I need a license for development?** A free trial works for testing; a license is required for production  
- **Which Java version is supported?** Java 8 and later  
- **Is image rotation supported?** Absolutely – use `AffineTransform.rotate()`

## Co je create postscript java?
Operace **create postscript java** vytváří soubor popisu stránky PostScript, který kóduje text, vektorovou grafiku a rastrové obrázky. S Aspose.Page můžete tyto soubory vytvářet přímo z Java kódu, což vám poskytuje plnou programovou kontrolu nad rozvržením, měřítkem a rotací bez potřeby samostatného interpretu PostScript.

## Proč použít Aspose.Page pro manipulaci s obrázky?
- **High‑level API:** Abstracts low‑level PostScript commands into simple Java methods.  
- **Cross‑platform:** Runs on any OS that supports Java.  
- **Full graphics‑state control:** Save, restore, translate, scale, and rotate graphics at will.  
- **No external dependencies:** Handles image loading, format conversion, and embedding internally.

## Požadavky
- Java Development Kit (JDK) nainstalovaný ve vašem systému.  
- Aspose.Page for Java library. Můžete si ji stáhnout [zde](https://releases.aspose.com/page/java/).  
- Základní znalost programování v Javě.  

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
První krok zahrnuje zápis uložení grafiky do dokumentu. To zajišťuje, že jakékoli transformace nebo úpravy provedené později mohou být v případě potřeby vráceny zpět.

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

## Krok 2: Překlad a transformace (translate and rotate image)
Dále přeložte dokument a vytvořte objekt `BufferedImage` z souboru obrázku. Použijte sérii transformací, jako je škálování a rotace pomocí `AffineTransform`. Zde probíhá operace **translate and rotate image**.

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
Po přidání obrázku zapište obnovení grafiky, aby se změny dokončily.

```java
document.writeGraphicsRestore();
```

## Krok 5: Uzavření aktuální stránky a uložení
Uzavřete aktuální stránku a uložte dokument.

```java
document.closePage();
document.save();
```

Můžete tyto kroky opakovat pro přidání více obrázků nebo přizpůsobit transformace podle svých požadavků.

## Časté problémy a řešení
- **FileNotFoundException:** Ujistěte se, že cesta `dataDir` končí oddělovačem souborů (`/` nebo `\\`) a že název souboru obrázku je přesně shodný.  
- **ImageIO.read returns null:** Ověřte, že formát obrázku je podporován (např. JPEG, PNG).  
- **Incorrect rotation angle:** `AffineTransform.rotate` očekává radiány. Převeďte stupně na radiány (`Math.toRadians(degrees)`) pokud je to potřeba.  

## Často kladené otázky

**Q: Can I use Aspose.Page for Java with other programming languages?**  
A: Aspose.Page primarily supports Java, but there are versions available for other programming languages as well.

**Q: Is there a free trial available for Aspose.Page for Java?**  
A: Yes, you can access the free trial [here](https://releases.aspose.com/).

**Q: How can I obtain a temporary license for Aspose.Page for Java?**  
A: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).

**Q: Where can I find community support and discussions related to Aspose.Page for Java?**  
A: Visit the [Aspose.Page Forum](https://forum.aspose.com/c/page/39) for community support.

**Q: Are there any additional resources for purchasing Aspose.Page for Java?**  
A: You can buy the library [here](https://purchase.aspose.com/buy).

## Závěr
Gratulujeme! Úspěšně jste se naučili, jak **create postscript java** dokumenty a vložit obrázky pomocí Aspose.Page for Java. Prozkoumejte [documentation](https://reference.aspose.com/page/java/) pro pokročilejší funkce a možnosti, jako jsou vektorová grafika, vykreslování textu a vlastní velikosti stránek.

---

**Poslední aktualizace:** 2026-02-15  
**Testováno s:** Aspose.Page for Java 23.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}