---
title: Přidejte dlaždicový obrázek v Java XPS
linktitle: Přidejte dlaždicový obrázek v Java XPS
second_title: Aspose.Page Java API
description: Prozkoumejte bezproblémovou manipulaci s dokumenty Java XPS pomocí Aspose.Page. Naučte se snadno přidávat dlaždicové obrázky pomocí tohoto podrobného průvodce.
weight: 11
url: /cs/java/xps-image-manipulation/add-tiled-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidejte dlaždicový obrázek v Java XPS

## Úvod
dynamickém světě vývoje Java neustále roste potřeba efektivní manipulace s dokumenty a jejich vytváření. Aspose.Page for Java se ukazuje jako výkonný nástroj, který vývojářům poskytuje možnost bezproblémově pracovat s dokumenty XPS. Tento tutoriál se zaměřuje na konkrétní úkol – přidání dlaždicového obrázku do dokumentu Java XPS.
## Předpoklady
Než se ponoříte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
1. Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovaný JDK.
2.  Aspose.Page for Java: Stáhněte a nainstalujte Aspose.Page for Java z[webová stránka](https://releases.aspose.com/page/java/).
3. Adresář dokumentů: Vyberte nebo vytvořte adresář, kam chcete uložit dokument XPS.
## Importujte balíčky
Do svého projektu Java importujte potřebné balíčky, abyste mohli využívat funkce Aspose.Page:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
Nyní si rozeberme proces přidávání dlaždicového obrázku do dokumentu Java XPS do jasných a zvládnutelných kroků.
## Krok 1: Nastavte svůj projekt
Začněte nastavením svého projektu Java a ujistěte se, že je Aspose.Page for Java správně integrována.
## Krok 2: Vytvořte dokument XPS
Inicializujte nový dokument XPS pomocí následujícího kódu:
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte nový dokument XPS
XpsDocument doc = new XpsDocument();
```
## Krok 3: Definujte cestu k dlaždicovému obrázku
Zadejte cestu k dlaždicovému obrazu, který chcete přidat do dokumentu XPS.
## Krok 4: Přidejte dlaždicový obrázek
Pomocí níže uvedeného úryvku kódu přidejte dlaždicový obrázek do dokumentu XPS:
```java
// Obrázek dlaždice
// Obdélník vyplněný ImageBrushem vpravo nahoře dole
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```
## Krok 5: Uložte dokument
Nakonec uložte výsledný dokument XPS pomocí kódu níže:
```java
// Uložte výsledný dokument XPS
doc.save(dataDir + "AddTiledImage_out.xps"); 
```
Opakujte tyto kroky, abyste bez námahy začlenili dlaždicový obrázek do dokumentu Java XPS pomocí Aspose.Page.
## Závěr
Aspose.Page for Java zjednodušuje proces práce s dokumenty XPS a nabízí vývojářům efektivní řešení pro manipulaci s dokumenty. Podle tohoto podrobného průvodce můžete bez námahy přidat dlaždicový obrázek do dokumentu Java XPS.

## Nejčastější dotazy
### Je Aspose.Page kompatibilní se všemi verzemi Java?
 Aspose.Page je navržena pro práci s různými verzemi Java. Zajistěte kompatibilitu kontrolou dokumentace[tady](https://reference.aspose.com/page/java/).
### Mohu použít Aspose.Page pro komerční projekty?
Ano, Aspose.Page nabízí komerční licence. Kupte si je[tady](https://purchase.aspose.com/buy).
### Je k dispozici bezplatná zkušební verze?
 Ano, prozkoumejte funkce Aspose.Page pomocí bezplatné zkušební verze[tady](https://releases.aspose.com/).
### Kde najdu podporu komunity a diskuse?
 Zapojte se do komunity Aspose.Page na[Fórum](https://forum.aspose.com/c/page/39).
### Jak mohu získat dočasnou licenci pro Aspose.Page?
 Získejte dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
