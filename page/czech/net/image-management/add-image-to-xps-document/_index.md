---
title: Přidejte obrázek do dokumentu XPS pomocí Aspose.Page pro .NET
linktitle: Přidat obrázek do dokumentu XPS
second_title: Aspose.Page .NET API
description: Prozkoumejte bezproblémovou integraci obrázků do dokumentů XPS s Aspose.Page for .NET. Postupujte podle našeho podrobného průvodce pro hladký vývoj.
type: docs
weight: 11
url: /cs/net/image-management/add-image-to-xps-document/
---
## Úvod

Ve světě vývoje .NET je začlenění obrázků do dokumentů XPS běžným požadavkem. Aspose.Page for .NET tento proces zjednodušuje a nabízí výkonnou sadu nástrojů pro snadnou manipulaci a vylepšení dokumentů XPS. Tento tutoriál vás provede kroky přidání obrázku do dokumentu XPS pomocí Aspose.Page for .NET.

## Předpoklady

Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:

1.  Aspose.Page for .NET Library: Stáhněte a nainstalujte knihovnu z[Aspose.Page .NET dokumentace](https://reference.aspose.com/page/net/).

2. Vývojové prostředí: Nastavte vývojové prostředí .NET, jako je Visual Studio.

3. Ukázkový obrázek: Připravte si vzorový soubor obrázku (např. "QL_logo_color.tif"), který chcete přidat do dokumentu XPS.

## Import jmenných prostorů

Začněte importováním potřebných jmenných prostorů do vašeho projektu .NET. Tyto jmenné prostory jsou životně důležité pro využití funkcí poskytovaných Aspose.Page pro .NET.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Krok 1: Nastavte adresář dokumentů

Začněte zadáním cesty k adresáři dokumentů. Tento krok zajistí, že váš projekt ví, kde má najít a uložit soubory.

```csharp
// Start: 1
string dataDir = "Your Document Directory";
// Rozšíření: 1
```

## Krok 2: Vytvořte dokument XPS

Vytvořte nový dokument XPS pomocí Aspose.Page for .NET.

```csharp
// Start: 1
XpsDocument doc = new XpsDocument();
// Rozšíření: 1
```

## Krok 3: Přidejte obrázek do dokumentu XPS

Nyní přidejte obrázek do dokumentu XPS. V tomto příkladu použijeme vzorový obrázek s názvem "QL_logo_color.tif".

```csharp
// Start: 1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// Rozšíření: 1
```

## Krok 4: Uložte výsledný dokument XPS

Uložte dokument XPS s přidaným obrázkem.

```csharp
// Start: 1
doc.Save(dataDir + "AddImage_outXPS.xps");
// Rozšíření: 1
```

Nyní jste úspěšně přidali obrázek do dokumentu XPS pomocí Aspose.Page for .NET!

## Závěr

V tomto tutoriálu jsme prozkoumali, jak využít Aspose.Page pro .NET k bezproblémovému začlenění obrázků do dokumentů XPS. Tento podrobný průvodce zajišťuje hladký proces integrace a rozšiřuje vaše možnosti vývoje .NET.

## FAQ

### Q1: Je Aspose.Page for .NET kompatibilní s nejnovějšími verzemi rozhraní .NET?

 A1: Aspose.Page for .NET je navržena tak, aby byla kompatibilní s širokou řadou verzí .NET frameworku, včetně nejnovějších verzí. Odkazovat na[dokumentace](https://reference.aspose.com/page/net/) pro konkrétní podrobnosti.

### Q2: Mohu používat Aspose.Page for .NET v prostředí Windows i Linux?

Odpověď 2: Ano, Aspose.Page for .NET je nezávislý na platformě, takže je vhodný pro použití v prostředí Windows i Linux.

### Q3: Existují nějaké možnosti licencování pro Aspose.Page for .NET?

 A3: Ano, můžete prozkoumat možnosti licencování a provést nákup[tady](https://purchase.aspose.com/buy).

### Q4: Je k dispozici bezplatná zkušební verze pro Aspose.Page pro .NET?

 A4: Ano, můžete vyzkoušet Aspose.Page for .NET zdarma přístupem k[zkušební verze zdarma](https://releases.aspose.com/).

### Otázka 5: Kde mohu vyhledat pomoc nebo se zapojit do komunity pro Aspose.Page for .NET?

 A5: Navštivte[Aspose.Page for .NET forum](https://forum.aspose.com/c/page/39) spojit se s komunitou a získat podporu.