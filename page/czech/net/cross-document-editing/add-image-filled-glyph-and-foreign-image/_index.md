---
title: Přidejte obrázek plný glyfů a cizí obrázek pomocí Aspose.Page .NET
linktitle: Přidat obrázek vyplněný glyfem a cizí obrázek
second_title: Aspose.Page .NET API
description: Odemkněte sílu zpracování dokumentů v .NET s Aspose.Page. Bez námahy přidejte glyfy plné obrázků. Vylepšete vizuály a zefektivněte svůj pracovní postup.
weight: 11
url: /cs/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidejte obrázek plný glyfů a cizí obrázek pomocí Aspose.Page .NET

## Úvod

Ve světě vývoje .NET vyniká Aspose.Page jako výkonná sada nástrojů pro zpracování úloh zpracování dokumentů. Tento tutoriál vás provede procesem přidávání glyfů s obrázky a začleňování cizích obrázků pomocí Aspose.Page for .NET. Na konci této příručky budete dobře rozumět tomu, jak zlepšit možnosti zpracování dokumentů.

## Předpoklady

Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:

-  Aspose.Page for .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Page. Můžete si jej stáhnout z[tady](https://releases.aspose.com/page/net/).

- Vývojové prostředí: Nastavte funkční vývojové prostředí .NET pomocí sady Visual Studio nebo jiného preferovaného IDE.

- Adresář dokumentů: Vytvořte adresář, do kterého budete ukládat své dokumenty. Toto bude v příkladech kódu označováno jako „Adresář vašich dokumentů“.

## Import jmenných prostorů

Ve své aplikaci .NET začněte importováním potřebných jmenných prostorů pro přístup ke třídám a metodám poskytovaným Aspose.Page:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Krok 1: Vytvořte první dokument XPS

Začněte vytvořením prvního dokumentu XPS pomocí Aspose.Page. Tento dokument bude sloužit jako základ pro přidávání glyfů s obrázky.

```csharp
// Start: 1
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";

// Vytvořte první dokument XPS
XpsDocument doc1 = new XpsDocument();
```

## Krok 2: Přidejte do prvního dokumentu glyfy

Přidejte glyfy do prvního dokumentu, určete písmo, velikost, styl a polohu.

```csharp
// Přidejte glyfy do prvního dokumentu
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## Krok 3: Vyplňte glyfy pomocí obrázkového štětce

Vyplňte glyfy štětcem s obrázkem s využitím obrázku z vašeho datového adresáře.

```csharp
// Vyplňte glyfy pomocí obrázkového štětce
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## Krok 4: Vytvořte druhý dokument XPS

Nyní vytvořte druhý dokument XPS, který bude obsahovat glyfy z prvního dokumentu.

```csharp
// Vytvořte druhý dokument XPS
XpsDocument doc2 = new XpsDocument();
```

## Krok 5: Přidejte glyfy s písmem z prvního dokumentu

Přidejte glyfy do druhého dokumentu pomocí písma z prvního dokumentu.

```csharp
// Přidejte glyfy s písmem z prvního dokumentu do druhého dokumentu
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## Krok 6: Vytvořte obrazový štětec z výplně prvního dokumentu

Vytvořte obrazový štětec z výplně prvního dokumentu a použijte jej k vyplnění glyfů ve druhém dokumentu.

```csharp
// Vytvořte obrazový štětec z výplně prvního dokumentu a vyplňte glyfy ve druhém dokumentu
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## Krok 7: Uložte dokumenty

Uložte první i druhý dokument XPS.

```csharp
// Uložte první dokument XPS
doc1.Save(dataDir + "out1.xps");

// Uložte druhý dokument XPS
doc2.Save(dataDir + "out2.xps");
// Rozšíření: 1
```

## Závěr

Gratulujeme! Úspěšně jste přidali glyfy plné obrázků a začlenili cizí obrázky pomocí Aspose.Page for .NET. Tento výukový program poskytuje základ pro vylepšení vašich schopností zpracování dokumentů a otevírá nové možnosti pro kreativní a vizuálně přitažlivé dokumenty.

## FAQ

### Q1: Mohu použít různé formáty obrázků pro vyplňování glyfů?

A1: Ano, Aspose.Page podporuje různé formáty obrázků. Zajistěte kompatibilitu se zvoleným formátem obrázku.

### Q2: Jak mohu dále přizpůsobit vzhled glyfů?

A2: Prozkoumejte dokumentaci Aspose.Page pro další vlastnosti a metody pro doladění vzhledu glyfu.

### Q3: Je Aspose.Page vhodný pro zpracování velkých sad dokumentů?

A3: Aspose.Page je navržen tak, aby efektivně zpracovával malé i velké sady dokumentů.

### Q4: Mohu na jednotlivé glyfy použít různé styly?

A4: Ano, můžete přizpůsobit styly pro každý glyf nezávisle, což poskytuje vysokou úroveň flexibility.

### Q5: Jaké jsou výhody používání Aspose.Page oproti jiným nástrojům pro zpracování dokumentů?

A5: Aspose.Page nabízí komplexní sadu funkcí, vynikající výkon a rozsáhlou dokumentaci, takže je preferovanou volbou pro mnoho vývojářů.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
