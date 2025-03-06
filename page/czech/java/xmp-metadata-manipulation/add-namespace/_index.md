---
title: Přidejte jmenný prostor v XMP pomocí Javy
linktitle: Přidejte jmenný prostor v XMP pomocí Javy
second_title: Aspose.Page Java API
description: Odemkněte sílu manipulace s dokumenty pomocí Aspose.Page for Java. Naučte se snadno přidávat jmenné prostory XMP v tomto komplexním průvodci.
weight: 13
url: /cs/java/xmp-metadata-manipulation/add-namespace/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidejte jmenný prostor v XMP pomocí Javy


## Úvod

V oblasti manipulace s dokumenty vyniká Aspose.Page for Java jako robustní nástroj, který nabízí širokou škálu funkcí. Jednou z výkonných funkcí je možnost přidávat jmenné prostory do XMP (Extensible Metadata Platform) pomocí Javy. Tento tutoriál vás provede celým procesem a rozdělí jej do snadno pochopitelných kroků.

## Předpoklady

Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:

-  Aspose.Page for Java: Ujistěte se, že máte nainstalovanou knihovnu. Můžete si jej stáhnout[tady](https://releases.aspose.com/page/java/).

- Vývojové prostředí Java: Nastavte ve svém systému prostředí Java.

- Soubor dokumentu: Mějte soubor EPS s metadaty XMP. Pokud neobsahuje metadata XMP, knihovna je vytvoří na základě komentářů k metadatům PS.

## Importujte balíčky

Chcete-li začít, importujte potřebné balíčky do svého projektu Java:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;

import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Krok 1: Získejte metadata XMP

```java

// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";

// Inicializujte vstupní proud souboru EPS
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");

PsDocument document = new PsDocument(psStream);
// Získejte metadata XMP. Pokud soubor EPS neobsahuje metadata XMP, vytvořte nový soubor naplněný hodnotami z komentářů metadat PS (%%Creator, %%CreateDate, %%Title atd.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Krok 2: Zaregistrujte nový jmenný prostor

```java
// Přidejte nový jmenný prostor XML „http://www.some.org/schema/tmp#“ s předponou „tmp“
xmp.registerNamespaceURI("tmp", "http://www.some.org/schema/tmp#");
```

## Krok 3: Přidejte novou vlastnost

```java
// Přidejte novou vlastnost "tmp:newKey" do nového jmenného prostoru XML
xmp.put("tmp:newKey", new XmpValue("NewValue"));
```

## Krok 4: Uložte dokument

```java
// Inicializujte výstupní proud souboru EPS
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");

//Uložte dokument se změněnými metadaty XMP
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Krok 5: Zavřete streamy

```java
// Zavřete vstupní EPS stream
psStream.close();
```

Nyní jste úspěšně přidali jmenný prostor v XMP pomocí Aspose.Page for Java. Neváhejte a prozkoumejte další funkce a využijte plný potenciál této knihovny.

## Závěr

Aspose.Page for Java zjednodušuje složitý úkol manipulace s metadaty XMP v souborech EPS. Sledováním tohoto podrobného průvodce jste získali cenné dovednosti, jak zlepšit své možnosti zpracování dokumentů.

## Nejčastější dotazy

### Mohu používat Aspose.Page for Java s jinými programovacími jazyky?
Aspose.Page primárně podporuje Javu, ale jsou k dispozici verze pro jiné jazyky, jako je .NET.

### Je k dispozici bezplatná zkušební verze?
 Ano, můžete vyzkoušet bezplatnou zkušební verzi[tady](https://releases.aspose.com/).

### Kde najdu komplexní dokumentaci?
 Viz dokumentace[tady](https://reference.aspose.com/page/java/).

### Jak mohu získat dočasnou licenci?
 Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).

### Existují pro Aspose.Page komunitní fóra?
 Ano, můžete se zapojit do komunity na[Fórum Aspose.Page](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
