---
date: 2026-04-24
description: Naučte se, jak nastavit barvu obdélníku a přidat obdélník v Java XPS
  pomocí Aspose.Page. Tento průvodce pokrývá přidání obdélníku v Javě a změnu tahu
  obdélníku.
keywords:
- set rectangle color
- add rectangle java
- change rectangle stroke
linktitle: Přidat obdélník v Java XPS
second_title: Aspose.Page Java API
title: Nastavte barvu obdélníku a přidejte obdélník v Java XPS
url: /cs/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nastavit barvu obdélníku a přidat obdélník v Java XPS

## Úvod
V tomto průvodci se naučíte, jak **nastavit barvu obdélníku** a **přidat obdélník** v Java XPS pomocí knihovny Aspose.Page. Ať už potřebujete kreslit jednoduché tvary pro zprávu nebo vytvářet složité vektorové grafiky, ovládnutí stylování obdélníků vám poskytne přesnou kontrolu nad vašimi XPS dokumenty.  

## Rychlé odpovědi
- **Jaká knihovna je vyžadována?** Aspose.Page for Java  
- **Mohu změnit tah obdélníku?** Ano, pomocí `setStroke` a `setStrokeThickness`  
- **Je podporován CMYK barevný profil?** Rozhodně – můžete načíst ICC profily, jak je ukázáno  
- **Potřebuji licenci pro produkci?** Ano, pro ne‑evaluační použití je vyžadována komerční licence  
- **Jak dlouho trvá implementace?** Obvykle méně než 10 minut pro základní obdélník

## Co je **set rectangle color**?
Nastavení barvy obdélníku znamená definovat barvu výplně nebo tahu, kterou bude tvar vykreslen ve finálním XPS dokumentu. S Aspose.Page můžete použít RGB, CMYK nebo dokonce vlastní ICC barevné profily pro dosažení přesného barevného odpovídání.

## Proč použít Aspose.Page k **add rectangle java** a **change rectangle stroke**?
- **Plnohodnotné API** – podporuje jak plné barvy, tak gradienty.  
- **Cross‑platform** – funguje na jakémkoli Java runtime bez nativních závislostí.  
- **Bohatá podpora geometrie** – vytvářejte složité cesty, aplikujte transformace a snadno spravujte tloušťku tahu.  

## Předpoklady
Než se ponoříme do kódu, ujistěte se, že máte:

- Základní znalosti programování v Javě.  
- Knihovna Aspose.Page nainstalována. Pokud ne, stáhněte ji z [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).  
- Funkční vývojové prostředí Java (IDE, JDK, atd.).  

## Import balíčků
Pro začátek importujte potřebné balíčky do svého Java projektu. Ujistěte se, že knihovna Aspose.Page je správně přidána do classpath. Zde je základní příklad:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Nyní rozdělíme poskytnutý příklad do několika kroků, abychom **přidali obdélník** a **nastavili jeho barvu** v Java XPS.

## Krok 1: Nastavit adresář dokumentu
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
Nahraďte `"Your Document Directory"` absolutní cestou, kde chcete číst/zapisovat XPS soubory.

## Krok 2: Vytvořit nový XPS dokument
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```
Tento řádek inicializuje nový XPS dokument, který bude obsahovat naše tvary.

## Krok 3: Přidat CMYK obdélník s pevnou barvou a tahem
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
Tento krok přidá **obdélník s tahem** s pevnou CMYK barvou. Metoda `setStroke` definuje barvu obrysu obdélníku, zatímco `setStrokeThickness` řídí šířku čáry – ideální pro **změnu tahu obdélníku**.

### Tip:
Pokud dáváte přednost RGB barvě, nahraďte volání `createColor` za `doc.createColor(0, 0, 255)` pro pevné modré vyplnění.

## Krok 4: Uložit výsledný XPS dokument
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```
Nakonec uložte XPS dokument na disk. Soubor `AddRectangle_out.xps` nyní obsahuje obdélník, jehož barvu a tah jste definovali.

## Časté problémy a řešení
| Problém | Příčina | Řešení |
|-------|-------|----------|
| **Obdélník není viditelný** | Nesprávná geometrie cesty nebo tloušťka tahu nastavena na 0 | Ověřte řetězec cesty (`"M 20,10 L 220,10 220,100 20,100 Z"`) a ujistěte se, že `setStrokeThickness` je větší než 0. |
| **Špatná barva** | Použití ICC profilu, který neodpovídá zamýšlenému barevnému prostoru | Použijte `doc.createColor(r, g, b)` pro RGB nebo dvojitě zkontrolujte cestu k ICC souboru. |
| **Soubor nebyl uložen** | `dataDir` ukazuje na neexistující složku nebo nemá oprávnění k zápisu | Vytvořte složku předem nebo zvolte zapisovatelnou lokaci. |

## Často kladené otázky

**Q:** *Mohu přidat více obdélníků v jednom XPS dokumentu?*  
A: Ano. Jednoduše opakujte kroky tvorby geometrie a stylování pro každý potřebný obdélník.

**Q:** *Jak mohu změnit výplňovou barvu obdélníku místo tahu?*  
A: Použijte `path.setFill(...)` s pevnou barevnou štětcí, podobně jako se používá `setStroke`.

**Q:** *Je Aspose.Page vhodný pro složité manipulace s XPS dokumenty?*  
A: Rozhodně. Knihovna podporuje pokročilé funkce jako gradienty, transformace a vložená písma.

**Q:** *Kde najdu další příklady a podporu komunity?*  
A: Prozkoumejte [Aspose.Page forum](https://forum.aspose.com/c/page/39) pro více ukázek kódu a pomoc od komunity.

**Q:** *Mohu vyzkoušet Aspose.Page před zakoupením?*  
A: Ano, můžete si vyzkoušet [free trial](https://releases.aspose.com/) pro ohodnocení možností API.

---

**Poslední aktualizace:** 2026-04-24  
**Testováno s:** Aspose.Page for Java 24.12  
**Autor:** Aspose

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}