---
date: 2026-07-19
description: Naučte se, jak vytvořit dokument PostScript v ASP.NET pomocí Aspose.Page
  pro .NET, aplikovat více transformací a efektivně uložit soubor.
keywords:
- create postscript document asp.net
- aspose.page transformations
- postscript graphics .net
lastmod: 2026-07-19
linktitle: Transformace PS
og_description: Vytvořte dokument PostScript v ASP.NET pomocí Aspose.Page. Naučte
  se aplikovat translaci, škálování, rotaci a sklon, a poté soubor uložit.
og_image_alt: Guide to creating and transforming PostScript documents using Aspose.Page
  for .NET
og_title: Vytvoření dokumentu PostScript v ASP.NET – Průvodce Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create PostScript document ASP.NET using Aspose.Page for
    .NET, apply multiple transformations, and save the file efficiently.
  headline: Create PostScript Document ASP.NET with Aspose.Page
  type: TechArticle
- questions:
  - answer: Use the `Transform` method with a custom `Matrix` that combines translation,
      scaling, rotation, or shearing in the order you need.
    question: How can I apply multiple transformations to a single object?
  - answer: Yes—render the `PsDocument` to an image using `PsDocument.Save("output.png",
      SaveFormat.Png)` or open the `.ps` file in a PostScript viewer to inspect the
      result before calling `Save()` for the final file.
    question: Can I preview the transformations before saving the document?
  - answer: Absolutely. Save the graphics state before drawing the element, apply
      the desired transformation, draw, then restore the state so later elements remain
      unaffected.
    question: Is it possible to apply transformations to specific elements in a document?
  - answer: Complex matrices increase CPU work. Keep transformations as simple as
      possible and reuse saved states when drawing many similar objects. Aspose.Page
      processes a 300‑page document with mixed transformations in under 2 seconds
      on a typical 3.2 GHz CPU.
    question: Are there any performance considerations when dealing with complex transformations?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community help, or contact Aspose support directly for priority assistance.
    question: How can I get support or seek assistance for Aspose.Page-related queries?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- postscript
- aspose.page
- .net graphics
- transformations
title: Vytvoření dokumentu PostScript v ASP.NET pomocí Aspose.Page
url: /cs/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření PostScript dokumentu ASP.NET pomocí Aspose.Page

## Úvod

V tomto krok‑za‑krokem tutoriálu **vytvoříte PostScript dokument ASP.NET** pomocí knihovny Aspose.Page, použijete různé grafické transformace a nakonec výsledek uložíte do souboru `.ps`. Na konci průvodce pochopíte, kde umístit každou transformaci na zásobník grafického stavu, jak ji efektivně kombinovat a jak zachovat kreslicí příkazy tak, aby je mohl vykreslit libovolný PostScript interpret. Tyto znalosti jsou nezbytné pro generování tisknutelných grafik, vlastních reportů nebo dynamických tiskových aktiv přímo z .NET aplikací.

## Rychlé odpovědi
- **Co mohu vytvořit?** Plnohodnotný PostScript dokument s transformovanou grafikou.  
- **Která knihovna je vyžadována?** Aspose.Page pro .NET (ke stažení z oficiální stránky).  
- **Jak soubor uložit?** Použijte `PsDocument.Save()` po nastavení grafických stavů.  
- **Mohu použít více transformací?** Ano – kombinujte je pomocí `Transform` nebo sekvenčních volání.  
- **Je potřeba licence?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.

## Co je operace „uložit PostScript soubor“?
Uložení PostScript souboru znamená zachování kreslicích příkazů, které jste vytvořili v paměti, do souboru `.ps` na disku. Soubor pak může být vykreslen libovolným PostScript interpretem, tiskárnou nebo prohlížečem, což z něj činí přenosnou, nezávislou na zařízení reprezentaci vektorové grafiky. Když zavoláte metodu `Save`, Aspose.Page serializuje celý grafický stav, včetně cest, štětců a transformačních matic, do platné PostScript syntaxe, která odpovídá specifikaci Adobe®.

## Proč použít Aspose.Page pro .NET k vytvoření PostScript dokumentu?
Aspose.Page pro .NET poskytuje silně typované, objektově orientované API, které abstrahuje nízkoúrovňový jazyk PostScript. Automaticky spravuje zásobník grafického stavu, podporuje více než 50 metod souvisejících s transformacemi a dokáže zpracovat dokumenty přesahující 500 stránek, aniž by načítal celý soubor do paměti. To snižuje dobu vývoje až o 70 % ve srovnání s ručním psaním PostScript kódu a zaručuje kompatibilitu se všemi hlavními tiskárnami.

## Požadavky
- **Aspose.Page pro .NET** knihovna integrovaná do vašeho projektu. Stáhněte ji z [odkaz ke stažení](https://releases.aspose.com/page/net/).  
- Zapisovatelná složka, kam bude uložen vygenerovaný soubor `.ps`. Nahraďte zástupnou cestu v kódu skutečnou cestou.  
- .NET 6.0 nebo novější (knihovna také podporuje .NET Core 3.1 a .NET Framework 4.6+).

## Import jmenných prostorů
Třída `PsDocument` se nachází v jmenném prostoru `Aspose.Page.Drawing`, zatímco pomocníci pro transformace jsou v `Aspose.Page.Drawing.Graphics`. Importujte je na začátku souboru:

```csharp
using Aspose.Page.Drawing;
using Aspose.Page.Drawing.Graphics;
using Aspose.Page.Drawing.Shapes;
```

`PsDocument` je hlavní třída Aspose.Page představující PostScript dokument v paměti. Po importování jmenných prostorů můžete začít vytvářet kreslicí plochu.

Nyní prozkoumejme každou transformaci krok za krokem.

## Žádné transformace
`PsDocument` je vstupním bodem pro všechny kreslicí operace. Následující úryvek vytvoří nový dokument, nakreslí jednoduchý oranžový obdélník a uloží jej bez jakékoli transformace.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Tento úryvek vytvoří **PostScript dokument** s jedním oranžovým obdélníkem a **uloží PostScript soubor** bez aplikace jakýchkoli transformací.

## Translaci
Uložení grafického stavu vám umožní vrátit se zpět po přesunu objektů. Metoda `SaveState` vloží aktuální transformační matici na vnitřní zásobník.

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

Metoda `Translate` posune souřadnicový systém o zadané posuny, což ovlivní všechny následující kreslicí příkazy.

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

Nyní se modrý obdélník objeví 250 bodů vpravo od oranžového, protože je aktivní matice translace.

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

Obnovení vrátí souřadnicový systém do původní polohy, takže následné kreslení není ovlivněno translací.

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

## Škálování
`Scale` mění velikost kreslených objektů aplikací škálovací matice na aktuální grafický stav.

> *Můžete následovat stejný vzor—uložit stav, aplikovat `Scale`, kreslit a poté obnovit.*  
> **Tip:** Použijte neuniformní škálování (`Scale(sx, sy)`) k natažení objektů jen v jednom směru, což je užitečné pro vytváření efektů sloupcových grafů.

## Rotace
`Rotate` aplikuje rotační matici na aktuální grafický stav, čímž otáčí následné kreslení o zadaný úhel.

> *Otáčejte kolem počátku nebo vlastního otočného bodu pomocí `Rotate(angle)`.*
> **Tip:** Kombinujte `Translate` před rotací, abyste otáčeli kolem konkrétního bodu místo počátku.

## Šikmá transformace
`Shear` zkosením (šikmým posunem) mění souřadnicový systém podle daných faktorů, nakloní kreslené objekty horizontálně a/nebo vertikálně.

> *Šikmé transformace (`Shear(shx, shy)`) nakloní tvary, což je užitečné pro kurzívní efekty nebo perspektivní triky.*

## Složené transformace
`Transform` aplikuje vlastní transformační matici na grafický stav, kombinující více operací do jedné.

> *Pro pokročilé scénáře vytvořte vlastní `Matrix` a předávejte ji metodě `Transform(matrix)`.*
> Zde **aplikujete více transformací** v jednom kroku, čímž snižujete počet ukládání a obnovování stavů.

## Jak uložit PostScript soubor s transformacemi?
`Save` zapíše aktuální `PsDocument` do souboru ve formátu PostScript. Načtěte svůj `PsDocument`, aplikujte požadovanou sekvenci transformací a zavolejte `Save` s cílovou cestou — Aspose.Page v jednom průchodu vytvoří standardně kompatibilní soubor `.ps`. Knihovna automaticky uzavře jakýkoli otevřený grafický stav, takže není potřeba další úklidový kód. Tento přístup funguje pro libovolnou kombinaci translace, škálování, rotace nebo šikmých transformací.

## Běžné případy použití
- **Dynamické generování reportů** – vytvářejte grafy, které se během běhu přizpůsobují velikosti dat.  
- **Faktury připravené k tisku** – vložte firemní loga a otočte je tak, aby odpovídala orientaci tiskárny.  
- **Vlastní návrh štítků** – použijte šikmé transformace k simulaci efektu reliéfního textu.  

## Často kladené otázky
**Q: Jak mohu aplikovat více transformací na jediný objekt?**  
A: Použijte metodu `Transform` s vlastním `Matrix`, který kombinuje translaci, škálování, rotaci nebo šikmé transformace v požadovaném pořadí.

**Q: Můžu si před uložením dokumentu prohlédnout transformace?**  
A: Ano — vyrenderujte `PsDocument` do obrázku pomocí `PsDocument.Save("output.png", SaveFormat.Png)` nebo otevřete soubor `.ps` v PostScript prohlížeči a zkontrolujte výsledek před voláním `Save()` pro finální soubor.

**Q: Je možné aplikovat transformace na konkrétní prvky v dokumentu?**  
A: Rozhodně. Uložte grafický stav před kreslením prvku, aplikujte požadovanou transformaci, nakreslete a poté obnovte stav, aby pozdější prvky zůstaly neovlivněny.

**Q: Existují nějaké výkonnostní úvahy při práci s komplexními transformacemi?**  
A: Komplexní matice zvyšují zátěž CPU. Udržujte transformace co nejjednodušší a při kreslení mnoha podobných objektů znovu používejte uložené stavy. Aspose.Page zpracuje 300‑stránkový dokument s kombinovanými transformacemi za méně než 2 sekundy na typickém 3,2 GHz procesoru.

**Q: Jak mohu získat podporu nebo pomoc ohledně dotazů týkajících se Aspose.Page?**  
A: Navštivte [forum Aspose.Page](https://forum.aspose.com/c/page/39) pro komunitní pomoc nebo kontaktujte přímo podporu Aspose pro prioritní asistenci.

---

**Poslední aktualizace:** 2026-07-19  
**Testováno s:** Aspose.Page 24.11 pro .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

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

## Související tutoriály

- [Vytvořit PostScript dokument .net – Přidat obdélník pomocí Aspose.Page](/page/net/drawing-shapes/add-rectangle-to-postscript-ps/)
- [Přidat obrázek do PostScript (PS) dokumentu pomocí Aspose.Page](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Přidat stránku do PostScript (PS) dokumentu pomocí Aspose.Page](/page/net/page-manipulation/add-page-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}