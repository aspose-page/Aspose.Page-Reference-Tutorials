---
date: 2026-01-12
description: Naučte se, jak uložit soubor PostScript a vytvořit dokument PostScript
  pomocí Aspose.Page pro .NET a aplikovat více transformací pro dynamickou grafiku.
linktitle: Transformations PS
second_title: Aspose.Page .NET API
title: Uložení souboru PostScript pomocí Aspose.Page Transformations (.NET)
url: /cs/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Uložení souboru PostScript pomocí Aspose.Page Transformations (.NET)

## Úvod

V tomto tutoriálu se dozvíte, jak **uložit soubor PostScript** při práci s Aspose.Page pro .NET. Provedeme vás vytvořením dokumentu PostScript, aplikací několika transformací, jako je posunutí, škálování, otáčení a zkosení, a nakonec uložením výsledku. Na konci budete pohodlně vytvářet dynamickou grafiku programově a přesně vědět, kde umístit každou transformaci ve stavovém grafickém kontextu.

## Rychlé odpovědi
- **Co mohu vytvořit?** Plnohodnotný dokument PostScript s transformovanou grafikou.  
- **Která knihovna je vyžadována?** Aspose.Page pro .NET (ke stažení na oficiálních stránkách).  
- **Jak soubor uložit?** Použijte `PsDocument.Save()` po nastavení stavů grafiky.  
- **Mohu použít více transformací?** Ano – kombinujte je pomocí `Transform` nebo sekvenčních volání.  
- **Je potřeba licence?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.

## Co je operace „uložit postscript soubor“?

Uložení souboru PostScript znamená zapsání kreslicích příkazů, které jste vytvořili v paměti, do souboru `.ps` na disku. Soubor pak může být vykreslen libovolným interpretem PostScript, tiskárnou nebo prohlížečem.

## Proč použít Aspose.Page pro .NET k vytvoření postscript dokumentu?

Aspose.Page poskytuje vysoceúrovňové, zařízení‑nezávislé API, které abstrahuje nízkoúrovňovou syntaxi PostScript. Získáte:

- Silně typované objekty C# pro cesty, štětce a transformace.  
- Automatické řízení zásobníku stavů grafiky (save/restore).  
- Plnou podporu pro složité transformační matice bez ručních výpočtů.  

## Požadavky

Než začnete, ujistěte se, že máte:

- **Aspose.Page pro .NET** knihovnu integrovanou ve vašem projektu. Stáhněte ji z [download link](https://releases.aspose.com/page/net/).  
- Zapisovatelnou složku, kde bude uložen generovaný soubor `.ps`. Nahraďte zástupnou cestu v kódu skutečným adresářem.

## Import jmenných prostorů

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Nyní se podívejme na každou transformaci krok za krokem.

## Žádné transformace

### Krok 1: Vytvoření výstupního proudu

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Create save options with default values
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Create graphics path from the rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Set paint in graphics state on upper level
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Fill the first rectangle that is on the upper-level graphics state and without any transformations
    document.Fill(path);

    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Tento úryvek vytvoří **dokument PostScript** s jedním oranžovým obdélníkem a **uloží soubor PostScript** bez aplikace jakýchkoli transformací.

## Posunutí (Translation)

### Krok 1: Uložení stavu grafiky

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

Uložení stavu grafiky vám umožní vrátit se zpět po přesunu objektů.

### Krok 2: Posunutí stavu grafiky

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

Posunutí posune vše, co bude nakresleno po tomto volání, o 250 jednotek doprava.

### Krok 3: Vyplnění obdélníku s transformací posunutí

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

Nyní se modrý obdélník objeví 250 bodů vpravo od oranžového.

### Krok 4: Obnovení stavu grafiky

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

Obnovení vrátí souřadnicový systém do původní pozice, takže následné kreslení nebude ovlivněno posunutím.

## Škálování

> *Můžete následovat stejný vzor — uložit stav, aplikovat `Scale`, kreslit, pak obnovit.*  
> **Tip:** Použijte neuniformní škálování (`Scale(sx, sy)`) pro natažení objektů jen v jednom směru.

## Otáčení

> *Otáčejte kolem počátku nebo vlastního pivotního bodu pomocí `Rotate(angle)`.*
> **Tip:** Kombinujte `Translate` před otáčením, abyste otáčeli kolem konkrétního bodu.

## Zkosení (Shearing)

> *Zkosení (`Shear(shx, shy)`) nakloní tvary, užitečné pro kurzívu.*  

## Složené transformace

> *Pro pokročilé scénáře vytvořte vlastní `Matrix` a předávejte ji metodě `Transform(matrix)`.*
> Zde **aplikujete více transformací** v jediném kroku.

## Závěr

Naučili jste se, jak **uložit soubor PostScript**, **vytvořit dokument PostScript** a **aplikovat více transformací** pomocí Aspose.Page pro .NET. Experimentujte s různými pořadími transformací, kombinujte je a sledujte, jak se grafika vyvíjí.

## Často kladené otázky

**Q: Jak mohu aplikovat více transformací na jeden objekt?**  
A: Použijte metodu `Transform` s vlastním `Matrix`, který kombinuje posunutí, škálování, otáčení nebo zkosení v požadovaném pořadí.

**Q: Můžu si před uložením dokumentu prohlédnout transformace?**  
A: Ano — vyrenderujte `PsDocument` do obrázku nebo použijte PostScript prohlížeč k inspekci výstupu před voláním `Save()`.

**Q: Je možné aplikovat transformace na konkrétní prvky v dokumentu?**  
A: Rozhodně. Uložte stav grafiky před kreslením prvku, aplikujte požadovanou transformaci, nakreslete a poté obnovte stav.

**Q: Existují nějaké výkonnostní úvahy při práci se složitými transformacemi?**  
A: Složité matice zvyšují zátěž CPU. Udržujte transformace co nejjednodušší a opakovaně používejte uložené stavy při kreslení mnoha podobných objektů.

**Q: Jak mohu získat podporu nebo pomoc s dotazy týkajícími se Aspose.Page?**  
A: Navštivte [Aspose.Page forum](https://forum.aspose.com/c/page/39) pro komunitní pomoc, nebo kontaktujte přímo podporu Aspose.

---

**Poslední aktualizace:** 2026-01-12  
**Testováno s:** Aspose.Page 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}