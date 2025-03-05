---
title: Transformace XPS s Aspose.Page pro .NET
linktitle: Transformace XPS
second_title: Aspose.Page .NET API
description: Transformujte dokumenty XPS bez námahy pomocí Aspose.Page for .NET. Postupujte podle našeho podrobného průvodce pro bezproblémové transformace.
type: docs
weight: 13
url: /cs/net/canvas-manipulation/transformationsxps/
---
## Úvod

Vítejte ve světě Aspose.Page for .NET, výkonné knihovny, která vám umožňuje bez námahy provádět různé transformace dokumentů XPS. V tomto tutoriálu se ponoříme do procesu transformace dokumentů XPS pomocí Aspose.Page for .NET. Ať už jste zkušený vývojář nebo teprve začínáte, tento průvodce vás provede každým krokem a zajistí vám snadné pochopení pojmů.

## Předpoklady

Než začneme, ujistěte se, že máte na svém místě následující:

-  Aspose.Page for .NET Library: Stáhněte a nainstalujte knihovnu z[Aspose.Page pro dokumentaci .NET](https://reference.aspose.com/page/net/).

- Vývojové prostředí: Nastavte kompatibilní vývojové prostředí, jako je Visual Studio nebo jakýkoli jiný vývojový nástroj .NET.

- Váš adresář dokumentů: Nahraďte zástupný symbol v kódu skutečnou cestou k adresáři dokumentů.

Nyní se vrhněme na tutoriál!

## Import jmenných prostorů

Nejprve se ujistěte, že importujete potřebné jmenné prostory, aby byly funkce Aspose.Page for .NET dostupné ve vašem kódu. Na začátek skriptu přidejte následující jmenné prostory:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Krok 1: Vytvořte nový dokument XPS

```csharp
// Start: 1
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";

// Vytvořte nový dokument XPS
XpsDocument doc = new XpsDocument();
```

## Krok 2: Vytvořte hlavní plátno

```csharp
// Vytvořte hlavní plátno, společné pro všechny prvky stránky
XpsCanvas canvas1 = doc.AddCanvas();

// Proveďte levé a horní odsazení na hlavním plátně
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Krok 3: Vytvořte obdélníkovou geometrii cesty

```csharp
// Vytvořte obdélníkovou geometrii cesty
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

## Krok 4: Přidejte výplň pro obdélníky

```csharp
// Vytvořte výplň pro obdélníky
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Krok 5: Přidejte nové plátno bez transformací

```csharp
// Přidejte nové plátno bez jakýchkoli transformací na hlavní plátno
XpsCanvas canvas2 = canvas1.AddCanvas();

// Na tomto plátně vytvořte obdélník a vyplňte jej
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Krok 6: Přidejte nové plátno pomocí Transformace překladu

```csharp
// Přidejte nové plátno s transformací překladu na hlavní plátno
XpsCanvas canvas3 = canvas1.AddCanvas();

// Přeložte toto plátno a umístěte nový obdélník pod předchozí obdélník
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Přeložte toto plátno na pravou stranu stránky
canvas3.RenderTransform.Translate(500, 0);

// Na tomto plátně vytvořte obdélník a vyplňte jej
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

## Krok 7: Přidejte nové plátno s transformací Double Scale

```csharp
//Přidejte nové plátno s transformací dvojitého měřítka na hlavní plátno
XpsCanvas canvas4 = canvas1.AddCanvas();

// Přeložte toto plátno a umístěte nový obdélník pod předchozí obdélník
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Měřítko tohoto plátna
canvas4.RenderTransform.Scale(2, 2);

// Na tomto plátně vytvořte obdélník a vyplňte jej
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

## Krok 8: Přidejte nové plátno s rotací kolem bodové transformace

```csharp
// Přidejte nové plátno s rotací kolem transformace bodu na hlavní plátno
XpsCanvas canvas5 = canvas1.AddCanvas();

// Přeložte toto plátno a umístěte nový obdélník pod předchozí obdélník
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Otočte toto plátno kolem bodu o 45 stupňů
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Na tomto plátně vytvořte obdélník a vyplňte jej
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

## Krok 9: Uložte výsledný dokument XPS

```csharp
// Uložte výsledný dokument XPS
doc.Save(dataDir + "output1.xps");
// Rozšíření: 1
```

## Závěr

Gratulujeme! Úspěšně jste transformovali dokument XPS pomocí Aspose.Page for .NET. Tato příručka pokrývala základní kroky, od nastavení předpokladů až po provádění různých transformací. Experimentujte s těmito technikami a odemkněte ve svých projektech plný potenciál Aspose.Page for .NET.

## FAQ

### Q1: Je Aspose.Page for .NET kompatibilní se všemi vývojovými prostředími .NET?

Odpověď 1: Ano, Aspose.Page for .NET je navržena tak, aby bezproblémově spolupracovala s různými vývojovými prostředími .NET, včetně sady Visual Studio.

### Q2: Kde najdu další příklady a dokumentaci pro Aspose.Page for .NET?

 A2: Navštivte[Aspose.Page pro dokumentaci .NET](https://reference.aspose.com/page/net/) pro komplexní dokumentaci a příklady.

### Q3: Mohu vyzkoušet Aspose.Page for .NET před nákupem?

 A3: Ano, bezplatnou zkušební verzi můžete prozkoumat návštěvou[Bezplatná zkušební verze Aspose.Page](https://releases.aspose.com/).

### Q4: Jak mohu získat dočasnou licenci pro Aspose.Page for .NET?

 A4: Získejte dočasnou licenci návštěvou[Dočasná licence](https://purchase.aspose.com/temporary-license/).

### Q5: Kde mohu zakoupit Aspose.Page pro .NET?

 A5: Nákup Aspose.Page pro .NET na[Aspose.Page Koupit](https://purchase.aspose.com/buy).