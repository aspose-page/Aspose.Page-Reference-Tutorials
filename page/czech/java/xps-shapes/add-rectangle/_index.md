---
date: 2025-12-30
description: Naučte se, jak v Javě vytvořit XPS dokument přidáním obdélníků pomocí
  Aspose.Page. Postupujte podle tohoto krok‑za‑krokem průvodce pro bezproblémovou
  manipulaci s XPS dokumenty.
linktitle: Create XPS Document Java – Add Rectangle
second_title: Aspose.Page Java API
title: Vytvoření XPS dokumentu v Javě – Přidání obdélníku pomocí Aspose.Page
url: /cs/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření XPS dokumentu v Javě – Přidání obdélníku

## Úvod
V tomto komplexním tutoriálu **vytvoříte XPS dokument v Javě** a naučíte se přidávat obdélníky pomocí knihovny Aspose.Page. Ať už vytváříte zprávy, faktury nebo vlastní grafiku, ovládnutí tvorby obdélníků vám poskytne přesnou kontrolu nad rozvržením XPS. Provedeme vás každým krokem, vysvětlíme, proč je každá řádka kódu napsána, a ukážeme, jak přizpůsobit barvy a tahy pro profesionální výsledek.

## Rychlé odpovědi
- **Jaká knihovna je doporučena?** Aspose.Page for Java  
- **Jak dlouho trvá implementace?** Přibližně 10 minut pro základní obdélník  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence  
- **Která verze Javy je podporována?** Java 8 a novější  
- **Mohu přidat více tvarů?** Ano – opakujte kroky pro každý tvar

## Předpoklady
- Základní znalost programovacího jazyka Java.  
- Knihovna Aspose.Page nainstalována. Pokud ne, můžete ji stáhnout z [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).  
- Fungující vývojové prostředí Java (IDE, JDK a Maven/Gradle, pokud preferujete).

## Import balíčků
Abyste mohli začít, importujte potřebné balíčky do svého Java projektu. Ujistěte se, že je knihovna Aspose.Page správně přidána do classpath. Zde je základní příklad:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Nyní rozebráme uvedený příklad na několik kroků pro přidání obdélníku v Java XPS.

## Krok 1: Nastavení adresáře dokumentu
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

Nahraďte `"Your Document Directory"` cestou ke složce, kam chcete ukládat soubory XPS.

## Krok 2: Vytvoření nového XPS dokumentu
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Tento řádek **vytváří** nový XPS dokument, který můžete později naplnit tvary, textem nebo obrázky.

## Krok 3: Přidání obdélníku s CMYK plnou barvou a obrysem
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```

Tento krok přidá obdélník s obrysem a CMYK plnou barvou. Můžete změnit řetězec geometrie (`"M 20,10 L 220,10 220,100 20,100 Z"`), abyste upravili velikost nebo pozici, a upravit hodnoty barev v `createColor` podle svého návrhu.

## Krok 4: Uložení výsledného XPS dokumentu
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```

Nakonec uložte upravený XPS dokument s přidaným obdélníkem do adresáře, který jste zadali dříve.

## Běžné případy použití
- **Záhlaví zpráv** – Použijte obdélníky jako pozadí pro nadpisy.  
- **Tabulky faktur** – Zvýrazněte buňky nebo sekce barevnými okraji.  
- **Vlastní grafika** – Kombinujte více obdélníků pro vytvoření složitých tvarů.

## Tipy pro řešení problémů
- **Chyba souboru nenalezen:** Ověřte, že `dataDir` ukazuje na existující složku a že ICC profil (`uswebuncoated.icc`) je přítomen.  
- **Nesprávné barvy:** Ujistěte se, že ICC profil odpovídá barevnému prostoru, který chcete použít (CMYK vs. RGB).  
- **Neočekávané rozměry:** Upravte řetězec geometrie tak, aby odrážel správné souřadnice.

## Závěr
Gratulujeme! Úspěšně jste se naučili, jak **vytvořit XPS dokument v Javě** a přidat obdélníky pomocí Aspose.Page. Tento základ vám umožní vytvářet bohatší XPS dokumenty, přizpůsobovat grafiku a integrovat tvary do rozsáhlejších pracovních postupů.

## Často kladené otázky
### Můžu přidat více obdélníků v jednom XPS dokumentu?
Ano, můžete přidat libovolný počet obdélníků opakováním kroků popsaných v tutoriálu.

### Jak mohu změnit barvu obdélníku?
Upravte hodnoty barev v metodě `createColor`, abyste dosáhli požadované barvy.

### Je Aspose.Page vhodný pro manipulaci s komplexními XPS dokumenty?
Rozhodně! Aspose.Page poskytuje robustní sadu funkcí pro různé úkoly spojené s XPS dokumenty.

### Kde najdu další příklady a podporu?
Prozkoumejte [Aspose.Page forum](https://forum.aspose.com/c/page/39) pro více příkladů a požádejte o pomoc komunitu.

### Můžu vyzkoušet Aspose.Page před zakoupením?
Ano, můžete si vyzkoušet [bezplatnou zkušební verzi](https://releases.aspose.com/) a poznat možnosti Aspose.Page.

## Často kladené otázky

**Q: Funguje tento přístup s Java 11 nebo novější?**  
A: Ano, knihovna Aspose.Page je kompatibilní s Java 8 a novějšími, včetně Java 11, 17 a vyšších.

**Q: Mohu vložit obrázky do oblasti obdélníku?**  
A: Můžete přidat prvek `XpsImage` a umístit jej nad nebo dovnitř obdélníku pomocí stejných souřadnic geometrie.

**Q: Jak nastavit výplňovou barvu místo jen obrysu?**  
A: Zavolejte `path.setFill(...)` s pevnou barvou vytvořenou pomocí `doc.createSolidColorBrush(...)`.

**Q: Je možné obdélník otočit?**  
A: Použijte transformační matici na cestu pomocí `path.setTransform(...)` pro otočení nebo škálování.

**Q: Jaká licence je vyžadována pro produkční použití?**  
A: Pro nasazení je potřeba komerční licence Aspose.Page; bezplatná zkušební verze je omezena na hodnocení a vývoj.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2025-12-30  
**Testováno s:** Aspose.Page for Java 24.12 (latest)  
**Autor:** Aspose  

---