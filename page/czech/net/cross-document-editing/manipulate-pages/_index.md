---
date: 2026-01-10
description: Naučte se, jak sloučit XPS dokumenty pomocí Aspose.Page pro .NET. Tento
  krok‑za‑krokem průvodce ukazuje techniky manipulace se stránkami pro efektivní výsledky.
linktitle: Manipulate Pages
second_title: Aspose.Page .NET API
title: Sloučit XPS dokumenty pomocí Aspose.Page pro .NET
url: /cs/net/cross-document-editing/manipulate-pages/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sloučení XPS dokumentů pomocí Aspose.Page pro .NET

## Úvod

V tomto tutoriálu se dozvíte, jak **sloučit XPS dokumenty** a manipulovat s jejich stránkami pomocí knihovny Aspose.Page v prostředí .NET. Ať už potřebujete spojit několik zpráv do jediného XPS souboru nebo přeuspořádat stránky pro profesionální výstup, tento průvodce vás provede procesem krok za krokem, s jasnými vysvětleními a připraveným kódem.

## Rychlé odpovědi
- **Co mohu dělat s Aspose.Page?** Sloučit XPS dokumenty, vkládat, přidávat nebo odstraňovat stránky a uložit výsledek.  
- **Potřebuji licenci pro testování?** Dočasná licence je k dispozici pro vyhodnocení.  
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Je vyžadován Visual Studio?** Ne, funguje jakékoli IDE, které podporuje C#, ale Visual Studio se doporučuje.  
- **Jak dlouho trvá sloučení?** Obvykle několik sekund pro standardně velké XPS soubory.

## Co je sloučení XPS dokumentů?

Sloučení XPS dokumentů znamená vzít stránky ze dvou nebo více existujících XPS souborů a spojit je do jediného XPS dokumentu. To je užitečné pro vytváření konsolidovaných zpráv, sestavování vícestránkových příruček nebo přípravu tiskových balíčků bez převodu do jiného formátu.

## Proč používat Aspose.Page pro .NET?

Aspose.Page nabízí **čisté .NET API**, které pracuje přímo se soubory XPS – není potřeba externí nástroje nebo komponenty třetích stran. Poskytuje detailní kontrolu nad pořadím stránek, místy vkládání a zachováním obsahu, což činí proces sloučení spolehlivým a rychlým.

## Požadavky

- **Aspose.Page for .NET** – stáhněte z [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/).  
- **Vývojové prostředí** – Visual Studio, Rider nebo jakékoli IDE, které podporuje C#.  
- **Vstupní XPS soubory** – tři ukázkové soubory (`input1.xps`, `input2.xps`, `input3.xps`) umístěné ve známé složce.

## Import jmenných prostorů

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Tyto jmenné prostory vám poskytují přístup k základním třídám XPS dokumentu, modelům stránek a základním kreslicím utilitám.

## Krok 1: Nastavte adresář dokumentů

```csharp
string dataDir = "Your Document Directory";
```

Nahraďte **Your Document Directory** úplnou cestou, kde jsou vaše XPS soubory uloženy, např. `C:\\Docs\\XpsFiles\\`.

## Krok 2: Vytvořte instance XPS dokumentu

```csharp
XpsDocument doc1 = new XpsDocument(dataDir + "input1.xps");
XpsDocument doc2 = new XpsDocument(dataDir + "input2.xps");
XpsDocument doc3 = new XpsDocument(dataDir + "input3.xps");
XpsDocument doc4 = new XpsDocument();
```

- `doc1`, `doc2` a `doc3` představují zdrojové dokumenty, které chcete sloučit.  
- `doc4` je prázdný XPS dokument, který bude obsahovat výsledek sloučení.

## Krok 3: Vkládejte, přidávejte a odstraňujte stránky

```csharp
doc4.InsertPage(1, doc2.Page, false);
doc4.AddPage(doc3.Page, false);
doc4.RemovePageAt(2);
doc4.InsertPage(2, doc1.SelectActivePage(3), false);
```

Zde je, co každá řádka dělá:

1. **InsertPage(1, doc2.Page, false)** – umístí první stránku `doc2` na pozici 1 v `doc4`.  
2. **AddPage(doc3.Page, false)** – přidá první stránku `doc3` na konec `doc4`.  
3. **RemovePageAt(2)** – odstraní stránku, která je nyní na indexu 2 (užitečné pro odstranění nechtěných stránek).  
4. **InsertPage(2, doc1.SelectActivePage(3), false)** – vloží třetí stránku `doc1` na pozici 2, čímž dokončí sloučení.

Tyto operace ukazují, jak můžete **sloučit XPS dokumenty** při přeuspořádání nebo odstraňování stránek podle potřeby.

## Krok 4: Uložte sloučený dokument

```csharp
doc4.Save(dataDir + "out.xps");
```

Finální sloučený XPS soubor (`out.xps`) je zapsán do stejného adresáře. Nyní jej můžete otevřít v libovolném XPS prohlížeči nebo dále zpracovat pomocí Aspose.Page.

## Časté problémy a řešení
- **File not found** – zkontrolujte cestu `dataDir` a ujistěte se, že vstupní soubory existují.  
- **Invalid page index** – indexy stránek jsou založeny na 1; pokus o vložení neexistující stránky vyvolá výjimku.  
- **License errors** – použijte dočasnou nebo plnou licenci před nasazením do produkce.

## Často kladené otázky

### Q1: Mohu manipulovat se stránkami z různých XPS dokumentů?

A1: Ano, jak je ukázáno v tutoriálu, můžete vkládat stránky z více XPS dokumentů do nového dokumentu.

### Q2: Jak mohu odstranit konkrétní stránku z dokumentu?

A2: Použijte metodu `RemovePageAt` a zadejte index stránky, kterou chcete odstranit.

### Q3: Je Aspose.Page kompatibilní s Visual Studio?

A3: Ano, Aspose.Page je plně kompatibilní s Visual Studio, což usnadňuje integraci do vašich .NET projektů.

### Q4: Existují nějaké licenční možnosti?

A4: Ano, můžete prozkoumat licenční možnosti a získat dočasnou licenci [zde](https://purchase.aspose.com/temporary-license/).

### Q5: Kde mohu získat podporu nebo položit otázky?

A5: Navštivte [Aspose.Page fórum](https://forum.aspose.com/c/page/39), kde získáte podporu a můžete se zapojit do komunity.

## Často kladené otázky

**Q: Mohu sloučit více než tři XPS soubory?**  
A: Rozhodně. Vytvořte další instance `XpsDocument` a opakovaně používejte `InsertPage` nebo `AddPage` k vytvoření většího sloučeného dokumentu.

**Q: Zachovává sloučení původní formátování a grafiku?**  
A: Ano. Aspose.Page kopíruje obsah stránky bajt po bajtu, takže text, obrázky a vektorová grafika zůstávají nezměněny.

**Q: Jak vložím stránku na konec bez specifikace indexu?**  
A: Použijte `AddPage(sourcePage, false)`, který přidá stránku na konec dokumentu.

**Q: Je možné sloučit XPS dokumenty na serveru bez UI?**  
A: API je zcela bezhlavé; můžete spustit stejný kód v ASP.NET, Azure Functions nebo jakémkoli serverovém .NET prostředí.

**Q: Co když jsou mé XPS soubory chráněny heslem?**  
A: Aspose.Page v současnosti nepodporuje šifrované XPS soubory; musíte je před sloučením dešifrovat.

---

**Poslední aktualizace:** 2026-01-10  
**Testováno s:** Aspose.Page for .NET 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}