---
date: 2026-09-19
description: Naučte se, jak přidat pojmenované hodnoty XMP do souborů EPS pomocí Aspose.Page
  for Java – krok za krokem průvodce s ukázkami kódu.
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
- EPS XMP manipulation
- Java metadata API
lastmod: 2026-09-19
linktitle: Přidat pojmenovanou hodnotu v XMP pomocí Javy
og_description: Jak přidat pojmenované hodnoty XMP do souborů EPS pomocí Aspose.Page
  for Java. Postupujte podle tohoto stručného průvodce a během několika minut vložte
  vlastní metadata.
og_image_alt: Screenshot of Java code adding XMP named value to an EPS file with Aspose.Page
og_title: Jak přidat pojmenovanou hodnotu XMP do souborů EPS pomocí Javy
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  headline: How to add XMP named value in EPS files using Java
  type: TechArticle
- description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  name: How to add XMP named value in EPS files using Java
  steps:
  - name: Initialize input EPS file stream
    text: '**FileInputStream** is a Java I/O class that reads raw bytes from a file.
      Load the source EPS file into a `FileInputStream`. This stream feeds the document
      into Aspose’s API. > **Pro tip:** Keep the `dataDir` variable configurable so
      the same code works across environments.'
  - name: Obtain XMP metadata
    text: '**XmpMetadata** represents the XMP packet associated with an EPS document.
      Retrieve the existing XMP packet; if the EPS file lacks one, Aspose creates
      a fresh XMP object populated from the PS comments.'
  - name: Add named value
    text: '**NamedValue** is a key‑value pair stored within the XMP metadata namespace.
      Insert a custom named value into the XMP structure. In this example we add a
      new key under the `xmpTPg:MaxPageSize` namespace. > **Why this matters:** Named
      values let you store arbitrary key‑value pairs that downstream app'
  - name: Initialize output EPS file stream
    text: '**FileOutputStream** is a Java I/O class that writes raw bytes to a file.
      Prepare a `FileOutputStream` where the modified EPS will be saved.'
  - name: Save document
    text: The `save` method persists the changes. It writes the updated XMP packet
      back into the EPS file, guaranteeing that the new named value becomes part of
      the document’s metadata.
  - name: Close input EPS stream
    text: Closing the original file handle prevents resource leaks and ensures that
      the file is not locked for subsequent operations. By following these six steps,
      you have successfully **added a named value in XMP metadata** using **Aspose.Page
      for Java**.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly with other Java
      libraries, providing flexibility in your development environment.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can access a free trial of Aspose.Page for Java on the [Aspose
      releases page](https://releases.aspose.com/).
    question: Is a free trial available for Aspose.Page for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to obtain a temporary license for Aspose.Page for Java.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Explore the [documentation](https://reference.aspose.com/page/java/) for
      comprehensive tutorials and examples.
    question: Where can I find more tutorials and examples for Aspose.Page for Java?
  - answer: Absolutely, Aspose.Page for Java is designed to handle large‑scale projects
      efficiently, providing robust document manipulation capabilities.
    question: Is Aspose.Page for Java suitable for large‑scale projects?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- XMP metadata
- Aspose.Page
- Java EPS
- document automation
title: Jak přidat pojmenovanou hodnotu XMP do souborů EPS pomocí Javy
url: /cs/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání pojmenované hodnoty do XMP metadat pomocí Javy

## Úvod
V moderním vývoji v Javě je naučit se **jak přidat XMP** metadata do souborů EPS nezbytné pro zachování původu dokumentu a zlepšení vyhledatelnosti. S **Aspose.Page for Java** můžete snadno vložit vlastní pojmenované hodnoty do XMP paketu. Tento tutoriál vás provede přesné kroky — včetně ukázek kódu — takže můžete ještě dnes začít přidávat XMP metadata do svých EPS dokumentů.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.Page for Java (Aspose)  
- **Jaký typ souboru je cílový?** EPS files containing XMP metadata  
- **Primární případ použití?** Add custom named values (e.g., page size limits) to XMP  
- **Předpoklady?** JDK 8+ and the Aspose.Page for Java library  
- **Typický čas implementace?** 5–10 minutes once the library is set up  

## Co je Aspose?
Aspose je zkratka pro Aspose, sadu API, které vývojářům umožňují vytvářet, upravovat, konvertovat a renderovat širokou škálu formátů dokumentů bez nutnosti externího softwaru. Komponenta Aspose.Page for Java se konkrétně zaměřuje na zpracování PostScriptu a EPS, poskytuje programový přístup k obsahu stránky, grafice a metadatům, jako je XMP.

## Proč přidávat pojmenované hodnoty do XMP metadat?
Pojmenované hodnoty vám umožňují uložit libovolné páry klíč‑hodnota přímo uvnitř XMP paketu, což je okamžitě čitelné downstream nástroji. To zlepšuje přívětivost pro vyhledávače, umožňuje automatizaci pracovních toků a splňuje požadavky na shodu tím, že vkládá regulační informace bez změny vizuálního obsahu.

## Proč je to důležité
Přidání pojmenovaných hodnot do XMP vám umožní uložit libovolné páry klíč‑hodnota, které lze číst bez parsování celého souboru EPS. Tato schopnost je zvláště cenná v automatizovaných publikovacích pipelinech, systémech pro správu digitálních aktiv a pracovních tocích řízených shodou, kde metadata řídí downstream akce.

## Předpoklady
Než se pustíme dál, ujistěte se, že máte následující:

- **Java Development Kit (JDK):** Nedávno nainstalovaný JDK (8 nebo vyšší) na vašem počítači.  
- **Aspose.Page for Java Library:** Stáhněte ji z oficiálního [Aspose.Page for Java download](https://releases.aspose.com/page/java/). Přidejte JAR do classpath vašeho projektu.  
- **EPS soubor**, který již obsahuje XMP metadata nebo bude automaticky vygenerován.

## Import balíčků
Začněte importováním potřebných Java balíčků. Tyto importy vám poskytují přístup k souborovým proudům, modelu EPS dokumentu a třídám pro práci s XMP.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Jak přidat pojmenovanou hodnotu XMP do souborů EPS pomocí Javy
Pro přidání pojmenované hodnoty načtěte EPS soubor pomocí `FileInputStream`, získejte nebo vytvořte jeho objekt `XmpMetadata`, vložte požadovaný `NamedValue` do příslušného jmenného prostoru a poté upravený dokument zapište zpět pomocí `FileOutputStream`. Aspose.Page automaticky vytvoří XMP paket, pokud chybí, a zajistí správné vložení nových metadat.

### Krok 1: Inicializace vstupního proudu souboru EPS
**FileInputStream** je třída Java I/O, která čte surové bajty ze souboru. Načtěte zdrojový EPS soubor do `FileInputStream`. Tento proud předává dokument API Aspose.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **Tip:** Udržujte proměnnou `dataDir` konfigurovatelnou, aby stejný kód fungoval v různých prostředích.

### Krok 2: Získání XMP metadat
**XmpMetadata** představuje XMP paket spojený s EPS dokumentem. Získejte existující XMP paket; pokud EPS soubor žádný nemá, Aspose vytvoří nový XMP objekt naplněný z PS komentářů.

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### Krok 3: Přidání pojmenované hodnoty
**NamedValue** je pár klíč‑hodnota uložený v jmenném prostoru XMP metadat. Vložte vlastní pojmenovanou hodnotu do XMP struktury. V tomto příkladu přidáváme nový klíč pod jmenný prostor `xmpTPg:MaxPageSize`.

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **Proč je to důležité:** Pojmenované hodnoty vám umožňují uložit libovolné páry klíč‑hodnota, které downstream aplikace mohou číst bez parsování celého dokumentu.

### Krok 4: Inicializace výstupního proudu souboru EPS
**FileOutputStream** je třída Java I/O, která zapisuje surové bajty do souboru. Připravte `FileOutputStream`, kam bude upravený EPS uložen.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### Krok 5: Uložení dokumentu
Metoda `save` uloží změny. Zapíše aktualizovaný XMP paket zpět do EPS souboru, čímž zajistí, že nová pojmenovaná hodnota se stane součástí metadat dokumentu.

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### Krok 6: Uzavření vstupního proudu EPS
Uzavření původního souborového handle zabraňuje únikům zdrojů a zajišťuje, že soubor nebude zamčen pro následné operace.

```java
psStream.close();
```

Postupováním těmito šesti kroky jste úspěšně **přidali pojmenovanou hodnotu do XMP metadat** pomocí **Aspose.Page for Java**.

## Časté problémy a řešení
| Problém | Příčina | Řešení |
|-------|-------|-----|
| `NullPointerException` on `xmp` | EPS soubor nemá XMP a Aspose se mu nepodařilo vytvořit | Ujistěte se, že EPS obsahuje alespoň jeden PS komentář nebo ručně vytvořte novou instanci `XmpMetadata`. |
| Output file is empty | Výstupní proud není vyprázdněn/uzavřen | Ověřte, že `outPsStream.close()` je voláno v `finally` bloku (jak je ukázáno). |
| Duplicate key error | Stejná pojmenovaná hodnota byla přidána dvakrát | Zkontrolujte, zda klíč již existuje pomocí `xmp.containsNamedValue(...)` před přidáním. |

## Často kladené otázky

**Q: Mohu používat Aspose.Page pro Javu s jinými Java knihovnami?**  
A: Ano, Aspose.Page pro Javu je navržena tak, aby hladce spolupracovala s dalšími Java knihovnami, což poskytuje flexibilitu ve vašem vývojovém prostředí.

**Q: Je k dispozici bezplatná zkušební verze pro Aspose.Page pro Javu?**  
A: Ano, můžete získat bezplatnou zkušební verzi Aspose.Page pro Javu na [Aspose releases page](https://releases.aspose.com/).

**Q: Jak mohu získat dočasnou licenci pro Aspose.Page pro Javu?**  
A: Navštivte [temporary license page](https://purchase.aspose.com/temporary-license/) a získejte dočasnou licenci pro Aspose.Page pro Javu.

**Q: Kde najdu více tutoriálů a příkladů pro Aspose.Page pro Javu?**  
A: Prozkoumejte [documentation](https://reference.aspose.com/page/java/) pro komplexní tutoriály a příklady.

**Q: Je Aspose.Page pro Javu vhodná pro rozsáhlé projekty?**  
A: Rozhodně, Aspose.Page pro Javu je navržena tak, aby efektivně zvládala rozsáhlé projekty a poskytovala robustní schopnosti manipulace s dokumenty.

## Závěr
V tomto průvodci jsme ukázali, jak **Aspose.Page pro Javu** usnadňuje **přidání pojmenovaných hodnot do XMP metadat** v EPS souborech. S výše uvedenými kroky můžete obohatit své dokumenty o vlastní metadata, zlepšit vyhledatelnost a umožnit inteligentnější downstream zpracování.

---

**Poslední aktualizace:** 2026-09-19  
**Testováno s:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Autor:** Aspose

## Související tutoriály

- [Jak přidat XMP jmenný prostor do souborů EPS pomocí Aspose.Page – Java tutoriál](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Přidat XMP metadata do souborů EPS pomocí Javy](/page/java/xmp-metadata-manipulation/add-simple-properties/)
- [Číst XMP pomocí Aspose.Page – Java průvodce](/page/java/xmp-metadata-manipulation/get-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}