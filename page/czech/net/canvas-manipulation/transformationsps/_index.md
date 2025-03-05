---
title: Transformace PS s Aspose.Page pro .NET
linktitle: Transformace PS
second_title: Aspose.Page .NET API
description: Odemkněte potenciál Aspose.Page for .NET s tímto komplexním průvodcem postscriptovými transformacemi. Vytvářejte dynamickou grafiku bez námahy.
type: docs
weight: 12
url: /cs/net/canvas-manipulation/transformationsps/
---
## Úvod

Vítejte ve světě Aspose.Page for .NET, kde můžete využít sílu transformací v PostScriptových dokumentech. Tento výukový program vás provede různými transformacemi, jako je posun, změna měřítka, rotace, stříhání a složité transformace, což vám umožní vytvářet vizuálně ohromující a dynamickou grafiku.

## Předpoklady

Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:

-  Knihovna Aspose.Page for .NET: Ujistěte se, že máte knihovnu Aspose.Page for .NET integrovanou do vašeho projektu. Můžete si jej stáhnout z[odkaz ke stažení](https://releases.aspose.com/page/net/).

- Adresář dokumentů: Nastavte adresář pro své dokumenty a nahraďte zástupný symbol v kódu skutečnou cestou.

## Import jmenných prostorů

Do svého projektu .NET importujte potřebné jmenné prostory pro práci s Aspose.Page:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Nyní si každý příklad rozdělíme do několika kroků ve formátu průvodce krok za krokem.


## Žádné proměny

### Krok 1: Vytvořte výstupní proud

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";

// Vytvořte výstupní proud pro dokument PostScript
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Vytvořte možnosti uložení s výchozími hodnotami
    PsSaveOptions options = new PsSaveOptions();

    // Vytvořte nový 1stránkový dokument PS
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Vytvořte cestu grafiky z obdélníku
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Nastavte barvu v grafickém stavu na horní úrovni
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Vyplňte první obdélník, který je ve stavu grafiky vyšší úrovně a bez jakýchkoli transformací
    document.Fill(path);

    // Zavřít aktuální stránku
    document.ClosePage();

    // Uložte dokument
    document.Save();
}
```

Tento kód vytvoří PostScriptový dokument bez transformací a vyplní obdélník oranžovou barvou.

## Překlad

### Krok 1: Uložte stav grafiky

```csharp
// Uložte stav grafiky pro návrat do tohoto stavu po transformaci
document.WriteGraphicsSave();
```

Tento krok uloží aktuální stav grafiky, což nám umožní vrátit se k němu po transformaci.

### Krok 2: Přeložte stav grafiky

```csharp
// Posuňte aktuální grafický stav o 250 doprava
document.Translate(250, 0);
```

Převeďte aktuální grafický stav přidáním komponenty překladu a poté nastavte barvu v aktuálním grafickém stavu na modrou barvu.

### Krok 3: Vyplňte obdélník transformací překladu

```csharp
// Nastavit malování v aktuálním stavu grafiky
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Vyplňte druhý obdélník v aktuálním grafickém stavu (má transformaci překladu)
document.Fill(path);
```

Tento krok vyplní druhý obdélník v aktuálním grafickém stavu, který nyní zahrnuje transformaci překladu.

### Krok 4: Obnovte stav grafiky

```csharp
// Obnovte stav grafiky na předchozí (vyšší) úroveň
document.WriteGraphicsRestore();
```

Po vyplnění obdélníku obnovte grafický stav na předchozí úroveň.

Pokračujte v tomto podrobném průvodci pro každý typ transformace, včetně změny měřítka, rotace, zkosení a komplexních transformací.

## Závěr

Gratulujeme! Úspěšně jste prošli transformačními schopnostmi Aspose.Page for .NET. Nyní experimentujte s různými kombinacemi a popusťte uzdu své kreativitě při transformacích PostScriptových dokumentů.

## FAQ

### Q1: Jak mohu použít více transformací na jeden objekt?

A1: Chcete-li použít více transformací, použijte`Transform` metoda s vlastní transformační maticí.

### Q2: Mohu zobrazit náhled transformací před uložením dokumentu?

Odpověď 2: Ano, transformace můžete vizualizovat vykreslením dokumentu a jeho náhledem ve vhodném prohlížeči.

### Q3: Je možné aplikovat transformace na konkrétní prvky v dokumentu?

Odpověď 3: Ano, můžete izolovat transformace na konkrétní grafické prvky v dokumentu.

### Otázka 4: Existují nějaká hlediska týkající se výkonu při řešení složitých transformací?

A4: Složité transformace mohou ovlivnit výkon, proto optimalizujte svůj kód pro efektivitu.

### Q5: Jak mohu získat podporu nebo vyhledat pomoc pro dotazy související s Aspose.Page?

 A5: Navštivte[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) za podporu komunity a diskuze.