---
date: 2026-05-05
description: Naučte se, jak pomocí Aspose.Page pro Java přidávat pojmenované hodnoty
  XMP do souborů EPS – krok za krokem průvodce s příklady kódu.
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
linktitle: Přidat pojmenovanou hodnotu do XMP pomocí Javy
second_title: Aspose.Page Java API
title: Jak přidat pojmenovanou hodnotu XMP do souborů EPS pomocí Javy
url: /cs/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání pojmenované hodnoty do XMP metadat pomocí Javy

## Úvod
V moderním vývoji v Javě je naučit se **jak přidat XMP** metadata do souborů EPS nezbytné pro zachování původu dokumentu a zlepšení vyhledatelnosti. S **asp** (Aspose.Page for Java) můžete snadno vložit vlastní pojmenované hodnoty do XMP paketu. Tento tutoriál vás provede přesné kroky — včetně úryvků kódu — takže můžete ještě dnes začít přidávat XMP metadata do svých EPS dokumentů.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.Page for Java (asp)  
- **Jaký typ souboru je cílový?** EPS soubory obsahující XMP metadata  
- **Hlavní případ použití?** Přidat vlastní pojmenované hodnoty (např. limity velikosti stránky) do XMP  
- **Předpoklady?** JDK 8+ a knihovna Aspose.Page for Java  
- **Typický čas implementace?** 5–10 minut po nastavení knihovny  

## Co je asp?
*asp* je zkratka pro **Aspose**, rodinu .NET a Java API, které usnadňují zpracování dokumentů. Komponenta Aspose.Page for Java vám umožňuje vytvářet, upravovat a konvertovat soubory PostScript a EPS a poskytuje plný programový přístup k jejich metadatům, včetně XMP.

## Proč přidávat pojmenované hodnoty do XMP metadat?
- **Přátelskost k vyhledávačům:** Vlastní značky zlepšují objevitelnost.  
- **Automatizace pracovních toků:** Následující nástroje mohou číst vaše vlastní hodnoty a na jejich základě rozhodovat.  
- **Soulad s předpisy:** Vložit regulační informace přímo do balíčku dokumentu.  

## Proč je to důležité
Přidání pojmenovaných hodnot do XMP vám umožňuje ukládat libovolné páry klíč‑hodnota, které lze číst bez nutnosti parsovat celý soubor EPS. Tato schopnost je zvláště cenná v automatizovaných publikovacích pipelinech, systémech pro správu digitálních aktiv a pracovních tocích řízených souladností, kde metadata řídí následné akce.

## Předpoklady
Před tím, než se ponoříme, ujistěte se, že máte následující:

- **Java Development Kit (JDK):** Nedávný JDK (8 nebo vyšší) nainstalovaný na vašem počítači.  
- **Aspose.Page for Java Library:** Stáhněte ji z oficiálního [download link](https://releases.aspose.com/page/java/). Přidejte JAR do classpath vašeho projektu.  
- **Soubor EPS** který již obsahuje XMP metadata nebo bude mít XMP vygenerováno automaticky.

## Import balíčků
Začněte importováním potřebných Java balíčků. Tyto importy vám poskytují přístup k souborovým tokům, modelu EPS dokumentu a třídám pro práci s XMP.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Jak přidat pojmenovanou hodnotu XMP do souborů EPS pomocí Javy
Níže je stručný, číslovaný průvodce, který přesně ukazuje **jak přidat XMP** pojmenované hodnoty do EPS dokumentu.

### Krok 1: Inicializace vstupního EPS souborového proudu
Načtěte zdrojový EPS soubor do `FileInputStream`. Tento proud předává dokument do API Aspose.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **Tip:** Uchovejte proměnnou `dataDir` konfigurovatelnou, aby stejný kód fungoval v různých prostředích.

### Krok 2: Získání XMP metadat
Získejte existující XMP paket. Pokud EPS soubor neobsahuje žádný, Aspose vytvoří nový XMP objekt naplněný z PS komentářů.

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### Krok 3: Přidání pojmenované hodnoty
Vložte vlastní pojmenovanou hodnotu do XMP struktury. V tomto příkladu přidáváme nový klíč pod jmenný prostor `xmpTPg:MaxPageSize`.

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **Proč je to důležité:** Pojmenované hodnoty vám umožňují ukládat libovolné páry klíč‑hodnota, které následné aplikace mohou číst bez parsování celého dokumentu.

### Krok 4: Inicializace výstupního EPS souborového proudu
Připravte `FileOutputStream`, kam bude upravený EPS uložen.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### Krok 5: Uložení dokumentu
Uložte změny. Volání `save` zapíše aktualizovaný XMP paket zpět do EPS souboru.

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### Krok 6: Uzavření vstupního EPS proudu
Uvolněte původní souborový handle, aby nedocházelo k únikům prostředků.

```java
psStream.close();
```

Po provedení těchto šesti kroků jste úspěšně **přidali pojmenovanou hodnotu do XMP metadat** pomocí **asp** (Aspose.Page for Java).

## Časté problémy a řešení
| Problém | Příčina | Řešení |
|---------|---------|--------|
| `NullPointerException` na `xmp` | Soubor EPS neobsahuje XMP a Aspose ho nedokázal vygenerovat | Ujistěte se, že EPS obsahuje alespoň jeden PS komentář nebo ručně vytvořte novou instanci `XmpMetadata`. |
| Výstupní soubor je prázdný | Výstupní stream není vyprázdněn/uzavřen | Ověřte, že `outPsStream.close()` je voláno v bloku `finally` (jak je ukázáno). |
| Chyba duplicitního klíče | Stejná pojmenovaná hodnota přidána dvakrát | Zkontrolujte, zda klíč již existuje pomocí `xmp.containsNamedValue(...)` před přidáním. |

## Často kladené otázky

**Q: Mohu použít Aspose.Page for Java s jinými Java knihovnami?**  
A: Ano, Aspose.Page for Java je navržena tak, aby spolupracovala bez problémů s jinými Java knihovnami, což poskytuje flexibilitu ve vašem vývojovém prostředí.

**Q: Je k dispozici bezplatná zkušební verze pro Aspose.Page for Java?**  
A: Ano, můžete získat bezplatnou zkušební verzi Aspose.Page for Java [zde](https://releases.aspose.com/).

**Q: Jak mohu získat dočasnou licenci pro Aspose.Page for Java?**  
A: Navštivte [tento odkaz](https://purchase.aspose.com/temporary-license/) a získejte dočasnou licenci pro Aspose.Page for Java.

**Q: Kde najdu více tutoriálů a příkladů pro Aspose.Page for Java?**  
A: Prozkoumejte [dokumentaci](https://reference.aspose.com/page/java/) pro komplexní tutoriály a příklady.

**Q: Je Aspose.Page for Java vhodná pro rozsáhlé projekty?**  
A: Rozhodně, Aspose.Page for Java je navržena tak, aby efektivně zvládala rozsáhlé projekty a poskytovala robustní možnosti manipulace s dokumenty.

## Závěr
V tomto průvodci jsme ukázali, jak **asp** (Aspose.Page for Java) usnadňuje **přidání pojmenovaných hodnot do XMP metadat** v EPS souborech. S výše uvedenými kroky můžete obohatit své dokumenty o vlastní metadata, zlepšit vyhledatelnost a umožnit inteligentnější následné zpracování.

---

**Poslední aktualizace:** 2026-05-05  
**Testováno s:** Aspose.Page for Java 24.12 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}