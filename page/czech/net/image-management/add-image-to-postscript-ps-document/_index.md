---
title: Přidejte obrázek do dokumentu PostScript (PS) pomocí Aspose.Page
linktitle: Přidat obrázek do dokumentu PostScript (PS).
second_title: Aspose.Page .NET API
description: Naučte se, jak vylepšit své PostScriptové dokumenty přidáním obrázků pomocí Aspose.Page for .NET. Postupujte podle našeho podrobného průvodce pro bezproblémový zážitek.
type: docs
weight: 10
url: /cs/net/image-management/add-image-to-postscript-ps-document/
---
## Úvod

V tomto tutoriálu prozkoumáme proces přidávání obrázků do dokumentu PostScript (PS) pomocí výkonné knihovny Aspose.Page for .NET. Aspose.Page zjednodušuje manipulaci s dokumenty PS a nabízí efektivní a přímočarý způsob, jak vylepšit dokument pomocí obrázků. Tento průvodce vás krok za krokem provede celým procesem a zajistí, že důkladně pochopíte každý koncept.

## Předpoklady

Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:

-  Knihovna Aspose.Page for .NET: Stáhněte si a nainstalujte knihovnu Aspose.Page for .NET z[tady](https://releases.aspose.com/page/net/).
- Adresář dokumentů: Vytvořte v systému adresář pro ukládání souborů dokumentů a obrázků.

## Import jmenných prostorů

Začněte importováním potřebných jmenných prostorů do vašeho projektu. Tyto jmenné prostory vám umožňují využívat funkce Aspose.Page ve vaší aplikaci .NET:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Krok 1: Nastavte adresář dokumentů

 Ujistěte se, že máte vyhrazený adresář pro vaše dokumenty. Nahradit`"Your Document Directory"` ve fragmentu kódu níže s cestou k adresáři vašeho dokumentu.

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: Vytvořte výstupní stream pro dokument PS

Nastavte výstupní proud pro dokument PostScript. Tento stream bude použit k uložení upraveného dokumentu.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddImage_outPS.ps", FileMode.Create))
```

## Krok 3: Vytvořte možnosti uložení

Vytvořte možnosti uložení pro dokument PS a zadejte požadovaná nastavení, jako je velikost stránky.

```csharp
PsSaveOptions options = new PsSaveOptions();
```

## Krok 4: Vytvořte dokument PS

Inicializujte nový 1stránkový dokument PS a připravte se na grafické operace.

```csharp
PsDocument document = new PsDocument(outPsStream, options, false);
document.WriteGraphicsSave();
document.Translate(100, 100);
```

## Krok 5: Přidejte obrázek do dokumentu

Načtěte objekt Bitmap ze souboru obrázku a použijte transformace. Přidejte obrázek do dokumentu PS.

```csharp
using (Bitmap image = new Bitmap(dataDir + "TestImage Format24bppRgb.jpg"))
{
    System.Drawing.Drawing2D.Matrix transform = new System.Drawing.Drawing2D.Matrix();
    transform.Translate(35, 300);
    transform.Scale(3, 3);
    transform.Rotate(-45);
    
    document.DrawImage(image, transform, Color.Empty);
}
```

## Krok 6: Dokončete grafické operace

Dokončete grafické operace a zavřete aktuální stránku.

```csharp
document.WriteGraphicsRestore();
document.ClosePage();
```

## Krok 7: Uložte dokument

Uložte upravený dokument PS.

```csharp
document.Save();
```

## Závěr

Gratulujeme! Úspěšně jste přidali obrázek do dokumentu PostScript pomocí Aspose.Page for .NET. Tento výukový program poskytuje jasného a stručného průvodce pro začlenění obrázků do dokumentů PS, díky nimž budou vaše dokumenty vizuálně přitažlivé a poutavé.

## FAQ

### Q1: Mohu přidat více obrázků do jednoho dokumentu PS pomocí Aspose.Page?

A1: Ano, můžete. Jednoduše opakujte kroky přidání obrázku v dokumentu.

### Q2: Jaké formáty obrázků podporuje Aspose.Page for .NET?

Odpověď 2: Aspose.Page for .NET podporuje různé formáty obrázků, včetně JPEG, PNG, BMP a GIF.

### Q3: Existuje omezení velikosti pro obrázky, které lze přidat?

A3: Limit velikosti závisí na specifikacích dokumentu PS a systémových prostředcích. Aspose.Page zvládá širokou škálu velikostí obrázků.

### Q4: Mohu na obrázky použít další efekty, jako jsou filtry nebo překryvy?

A4: Ano, Aspose.Page umožňuje aplikovat různé transformace a efekty na obrázky před jejich přidáním do dokumentu.

### Q5: Jak mohu extrahovat obrázky z dokumentu PS?

A5: Aspose.Page for .NET poskytuje metody pro extrahování obrázků z dokumentů PS. Podrobné informace naleznete v dokumentaci.