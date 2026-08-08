---
date: 2026-04-24
description: Naučte se, jak vytvořit XPS dokument v Javě s elipsou s radiálním gradientem.
  Tento krok‑za‑krokem průvodce ukazuje, jak nastavit tloušťku tahu a definovat geometrii
  cesty pomocí Aspose.Page.
keywords:
- create xps document java
- set stroke thickness
- define path geometry
linktitle: Přidat elipsu v Java XPS
second_title: Aspose.Page Java API
title: Vytvořit XPS dokument v Javě – Přidat elipsu s radiálním gradientem
url: /cs/java/xps-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání elipsy s radiálním gradientem pomocí Aspose.Page

## Úvod
V tomto tutoriálu se naučíte, jak **create XPS document Java** s krásnou elipsou ohraničenou radiálním gradientem pomocí Aspose.Page pro Java. Aspose.Page je robustní knihovna, která abstrahuje nízkoúrovňové detaily XPS, takže se můžete soustředit na design místo na složitosti formátu souboru. Na konci tohoto průvodce budete mít připravený XPS soubor, který můžete vložit do zpráv, faktur nebo jakéhokoli workflow generování dokumentů.

## Rychlé odpovědi
- **Co tento kód vytváří?** Jednostránkový XPS soubor obsahující elipsu ohraničenou vícebarevným radiálním gradientem.  
- **Které primární API se používá?** `Aspose.Page` pro Java (`XpsDocument`, `XpsCanvas`, `XpsPath`, atd.).  
- **Potřebuji licenci pro spuštění vzorku?** Dočasná licence funguje pro hodnocení; plná licence je vyžadována pro produkci.  
- **Jaké klíčové vlastnosti nastavujeme?** Štětec tahu (radiální gradient), metoda rozšíření, zastávky gradientu a tloušťka tahu.  
- **Mohu změnit velikost elipsy?** Ano – upravte řetězec geometrie cesty nebo souřadnice štětce gradientu.

## Co znamená “create XPS document Java”?
Vytvoření XPS dokumentu v Javě znamená programově generovat soubor XML Paper Specification (XPS) – formát pevného rozvržení podobný PDF – přímo z Java kódu. Aspose.Page poskytuje vysoceúrovňový objektový model (`XpsDocument`, `XpsCanvas`, atd.), který abstrahuje XML značkování, což proces zjednodušuje na práci se standardními Java objekty.

## Proč použít elipsu s radiálním gradientem?
Radiální gradient poskytuje trojrozměrný dojem, ideální pro vizuální zvýraznění, loga nebo dekorativní prvky ve zprávách. Ve srovnání s jednobarevným okrajem přidává gradient hloubku, aniž by výrazně zvětšil velikost souboru, a formát XPS zachovává vektorovou kvalitu při jakémkoli škálování.

## Požadavky
Než začneme, ujistěte se, že máte následující předpoklady:
- Java Development Kit (JDK) nainstalovaný na vašem počítači.
- Knihovna Aspose.Page pro Java stažená. Můžete ji získat [zde](https://releases.aspose.com/page/java/).
- Editor kódu dle vašeho výběru (Eclipse, IntelliJ, atd.) pro psaní a spouštění Java kódu.

## Import balíčků
Ujistěte se, že máte ve svém Java projektu importovány potřebné balíčky pro použití Aspose.Page. Přidejte následující importy na začátek vašeho Java souboru:

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```

## Krok 1: Nastavení adresáře dokumentu
Definujte cestu k adresáři, kde bude XPS dokument uložen:

```java
String dataDir = "Your Document Directory";
```

## Krok 2: Vytvoření XPS dokumentu
Inicializujte nový XPS dokument pomocí následujícího kódu:

```java
XpsDocument doc = new XpsDocument();
```

## Krok 3: Definice zastávek radiálního gradientu
Vytvořte seznam zastávek gradientu pro elipsu ohraničenou radiálním gradientem:

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```

## Krok 4: Vytvoření geometrie cesty
Definujte elipsu ohraničenou radiálním gradientem pomocí geometrie cesty:

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```

## Krok 5: Přidání plátna a cesty
Přidejte nové plátno do dokumentu a připojte cestu s definovanou geometrií:

```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```

## Krok 6: Nastavení tahu a gradientu
Nakonfigurujte tah cesty pomocí štětce radiálního gradientu:

```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```

## Krok 7: Nastavení tloušťky tahu
Určete **set stroke thickness** cesty:

```java
path.setStrokeThickness(12f);
```

## Krok 8: Uložení dokumentu
Uložte výsledný XPS dokument:

```java
doc.save(dataDir + "AddEllipse_out.xps");
```

Gratulujeme! Úspěšně jste přidali elipsu ohraničenou radiálním gradientem při **create XPS document Java** s Aspose.Page.

## Časté problémy a řešení
| Problém | Proč se to děje | Řešení |
|-------|----------------|-----|
| **Elipsa vypadá plochá** | Použití `XpsSpreadMethod.Pad` místo `Reflect` | Změňte metodu rozšíření na `XpsSpreadMethod.Reflect` podle kroku 6. |
| **Žádný výstupní soubor** | `dataDir` ukazuje na neexistující složku | Ujistěte se, že adresář existuje, nebo použijte absolutní cestu. |
| **Barvy gradientu jsou špatné** | Nesprávné pořadí zastávek gradientu | Ověřte, že hodnoty `offset` (0 → 1) rostou monotónně. |
| **Chyby kompilace** | Chybějící JAR soubory Aspose.Page v classpath | Přidejte `aspose-page-xx.jar` do závislostí projektu. |

## Často kladené otázky

**Q: Mohu použít Aspose.Page pro Java s jinými knihovnami Java?**  
A: Ano, Aspose.Page pro Java lze snadno integrovat s dalšími Java knihovnami.

**Q: Je Aspose.Page vhodný pro zpracování dokumentů ve velkém měřítku?**  
A: Rozhodně! Aspose.Page je navržen tak, aby efektivně zvládal zpracování dokumentů ve velkém měřítku.

**Q: Kde najdu další tutoriály a příklady pro Aspose.Page pro Java?**  
A: Navštivte [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) pro komplexní tutoriály a příklady.

**Q: Jak získat dočasnou licenci pro Aspose.Page pro Java?**  
A: Dočasnou licenci můžete získat [zde](https://purchase.aspose.com/temporary-license/).

**Q: Existují komunitní fóra pro diskuze o Aspose.Page?**  
A: Ano, připojte se k [Aspose.Page community forum](https://forum.aspose.com/c/page/39), kde můžete komunikovat s dalšími vývojáři a získat pomoc.

---

**Poslední aktualizace:** 2026-04-24  
**Testováno s:** Aspose.Page for Java 24.11 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}