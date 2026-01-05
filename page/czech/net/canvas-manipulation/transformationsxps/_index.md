---
date: 2026-01-05
description: Naučte se snadno transformovat XPS dokumenty pomocí Aspose.Page pro .NET.
  Postupujte podle našeho krok‑za‑krokem průvodce pro bezproblémové transformace.
linktitle: Transformations XPS
second_title: Aspose.Page .NET API
title: Jak transformovat XPS pomocí Aspose.Page pro .NET
url: /cs/net/canvas-manipulation/transformationsxps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak transformovat XPS pomocí Aspose.Page pro .NET

## Úvod

Vítejte ve světě Aspose.Page pro .NET, výkonné knihovny, která vám umožní snadno provádět různé transformace XPS dokumentů. **V tomto tutoriálu se dozvíte, jak transformovat XPS dokumenty pomocí Aspose.Page pro .NET**, ať už jste zkušený vývojář nebo teprve začínáte. Provedeme vás každým krokem, vysvětlíme důvody za každou transformací a poskytneme praktické tipy, které můžete použít v reálných projektech.

## Rychlé odpovědi
- **Co můžete dosáhnout?** Vytvářet, posouvat, měnit měřítko a otáčet prvky XPS plátna programově.  
- **Která knihovna je vyžadována?** Aspose.Page pro .NET (nejnovější verze).  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Podporované platformy?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní transformace zde ukázané.

## Co znamená „jak transformovat xps“?
Fráze *how to transform xps* odkazuje na programové upravování rozvržení, velikosti a orientace prvků uvnitř XPS (XML Paper Specification) dokumentu. Pomocí Aspose.Page můžete na plátna aplikovat transformace založené na maticích, což vám poskytuje detailní kontrolu nad umístěním, měřítkem a rotací bez ruční úpravy XPS XML.

## Proč používat Aspose.Page pro XPS transformace?
- **Plná integrace s .NET** – funguje bez problémů s Visual Studio, Rider a dalšími IDE.  
- **Žádné externí závislosti** – API se postará o všechny nízkoúrovňové detaily XPS za vás.  
- **Bohatá podpora transformací** – posun, měřítko, rotace a kombinace více transformací v jednom volání.  
- **Optimalizovaný výkon** – vhodné pro generování reportů, faktur nebo jakýchkoli tisknutelných grafiky za běhu.

## Předpoklady

Předtím, než začneme, ujistěte se, že máte:

- **Knihovna Aspose.Page pro .NET** – stáhněte a nainstalujte ji z oficiální dokumentace: [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).  
- **Vývojové prostředí** – Visual Studio, Visual Studio Code nebo jakékoli jiné IDE kompatibilní s .NET.  
- **Adresář dokumentů** – složka ve vašem počítači, kde budete číst/zapisovat XPS soubory. Nahraďte zástupný znak v kódu skutečnou cestou.

Nyní, když máme vše připravené, ponořme se do kódu.

## Importovat jmenné prostory

Nejprve importujte jmenné prostory, které poskytují třídy Aspose.Page, jež budete potřebovat:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Jak transformovat XPS – Průvodce krok za krokem

### Krok 1: Vytvořit nový XPS dokument

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

*Vysvětlení*: Začínáme definováním složky, která obsahuje naše vstupní a výstupní soubory, a poté vytvoříme prázdný `XpsDocument`. Tento objekt bude plátnem pro všechny následné transformace.

### Krok 2: Vytvořit hlavní plátno

```csharp
// Create main canvas, common for all page elements
XpsCanvas canvas1 = doc.AddCanvas();

// Make left and top offsets in the main canvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

*Proč je to důležité*: Hlavní plátno funguje jako kontejner pro všechna ostatní plátna. Použitím malého posunu zajistíme, že obsah nebude oříznut na okraji stránky.

### Krok 3: Vytvořit geometrii cesty obdélníku

```csharp
// Create rectangle path geometry
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

*Tip*: Řetězec cesty následuje standardní syntaxi XPS cesty (`M` pro přesun, `L` pro čáru, `Z` pro uzavření). Upravením souřadnic změníte velikost obdélníku.

### Krok 4: Přidat výplň pro obdélníky

```csharp
// Create a fill for rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

*Profesionální tip*: Použijte `CreateColor` s RGB hodnotami, aby odpovídaly vaší firemní paletě.

### Krok 5: Přidat nové plátno bez transformací

```csharp
// Add new canvas without any transformations to the main canvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Create rectangle in this canvas and fill it
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Zde jednoduše umístíme obdélník na stránku bez další transformace – užitečné jako základní prvek.

### Krok 6: Přidat nové plátno s transformací posunu

```csharp
// Add new canvas with translate transformation to the main canvas
XpsCanvas canvas3 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Translate this canvas to the right side of the page
canvas3.RenderTransform.Translate(500, 0);

// Create rectangle in this canvas and fill it
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

*Co se děje?* První matice posune obdélník o 200 jednotek dolů. Následující volání `Translate` ho posune o 500 jednotek doprava, což ukazuje, jak lze řetězit více posunů.

### Krok 7: Přidat nové plátno s dvojitou transformací měřítka

```csharp
// Add new canvas with double scale transformation to the main canvas
XpsCanvas canvas4 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Scale this canvas
canvas4.RenderTransform.Scale(2, 2);

// Create rectangle in this canvas and fill it
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

*Proč měřítko?* Měřítko 2‑násobně zdvojnásobí šířku a výšku obdélníku, což vám umožní vytvořit větší grafiku bez redefinování geometrie.

### Krok 8: Přidat nové plátno s rotací kolem bodu

```csharp
// Add new canvas with rotation around a point transformation to the main canvas
XpsCanvas canvas5 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Rotate this canvas around a point on 45 degrees
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Create rectangle in this canvas and fill it
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

*Klíčový poznatek*: `RotateAround` otáčí plátno kolem vlastního bodu (zde (100, 50)), což vám poskytuje detailní kontrolu nad kotevními body rotace.

### Krok 9: Uložit výsledný XPS dokument

```csharp
// Save resultant XPS document
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

Po aplikaci všech transformací je dokument uložen do `output1.xps`. Otevřete soubor v libovolném XPS prohlížeči a uvidíte naskládané obdélníky s jejich příslušnými posuny, měřítkem a rotací.

## Časté problémy a řešení

| Příznak | Pravděpodobná příčina | Oprava |
|---------|-----------------------|--------|
| Prázdný výstupní soubor | `dataDir` ukazuje na neexistující složku | Zajistěte, aby složka existovala, nebo použijte absolutní cestu |
| Obdélníky nejsou umístěny podle očekávání | Nesprávné hodnoty matice | Zkontrolujte pořadí volání `Translate`, `Scale` a `RotateAround` |
| Barvy jsou špatné | RGB hodnoty mimo rozsah 0‑255 | Použijte platné byte hodnoty pro každý kanál |

## Často kladené otázky

**Q: Je Aspose.Page pro .NET kompatibilní se všemi .NET vývojovými prostředími?**  
A: Ano, funguje bez problémů s Visual Studio, Visual Studio Code, Rider a jakýmkoli IDE, které podporuje .NET.

**Q: Kde mohu najít další příklady a podrobné API dokumentace?**  
A: Navštivte oficiální dokumentaci na [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

**Q: Můžu vyzkoušet Aspose.Page před zakoupením licence?**  
A: Rozhodně. Bezplatná zkušební verze je k dispozici zde: [Aspose.Page Free Trial](https://releases.aspose.com/).

**Q: Jak získat dočasnou licenci pro testování?**  
A: Můžete si ji vyžádat na stránce dočasné licence: [Temporary License](https://purchase.aspose.com/temporary-license/).

**Q: Kde mohu zakoupit plnou licenci?**  
A: Zakupte přímo v obchodě Aspose: [Aspose.Page Buy](https://purchase.aspose.com/buy).

---

**Poslední aktualizace:** 2026-01-05  
**Testováno s:** Aspose.Page 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}