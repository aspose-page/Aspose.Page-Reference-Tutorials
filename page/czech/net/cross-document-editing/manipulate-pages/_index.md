---
date: 2026-07-24
description: Naučte se, jak sloučit XPS dokumenty pomocí Aspose.Page pro .NET. Tento
  krok‑za‑krokem průvodce ukazuje techniky manipulace s stránkami pro efektivní výsledky.
keywords:
- merge xps documents
- how to merge xps
- asp page .net tutorial
lastmod: 2026-07-24
linktitle: Manipulace se stránkami
og_description: Efektivně sloučte XPS dokumenty pomocí Aspose.Page pro .NET. Tento
  průvodce vás provede sloučením, vkládáním a odstraňováním stránek s přehlednými
  ukázkami kódu.
og_image_alt: Guide showing how to merge XPS documents using Aspose.Page in a .NET
  application
og_title: Sloučit XPS dokumenty s Aspose.Page pro .NET – Rychlá manipulace se stránkami
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Learn how to merge XPS documents with Aspose.Page for .NET. This step‑by‑step
    guide shows page manipulation techniques for efficient results.
  headline: Merge XPS Documents with Aspose.Page for .NET
  type: TechArticle
- description: Learn how to merge XPS documents with Aspose.Page for .NET. This step‑by‑step
    guide shows page manipulation techniques for efficient results.
  name: Merge XPS Documents with Aspose.Page for .NET
  steps:
  - name: '**InsertPage(1, doc2.Page, false)** – places the first page of `doc2` at
      position 1 in `doc4`.'
    text: '**InsertPage(1, doc2.Page, false)** – places the first page of `doc2` at
      position 1 in `doc4`.'
  - name: '**AddPage(doc3.Page, false)** – appends the first page of `doc3` to the
      end of `doc4`.'
    text: '**AddPage(doc3.Page, false)** – appends the first page of `doc3` to the
      end of `doc4`.'
  - name: '**RemovePageAt(2)** – removes the page now at index 2 (useful for eliminating
      unwanted pages).'
    text: '**RemovePageAt(2)** – removes the page now at index 2 (useful for eliminating
      unwanted pages).'
  - name: '**InsertPage(2, doc1.SelectActivePage(3), false)** – inserts the third
      page of `doc1` into position 2, completing the merge.'
    text: '**InsertPage(2, doc1.SelectActivePage(3), false)** – inserts the third
      page of `doc1` into position 2, completing the merge.'
  type: HowTo
- questions:
  - answer: Absolutely. Create additional `XpsDocument` instances and use `InsertPage`
      or `AddPage` repeatedly to build a larger merged document.
    question: Can I merge more than three XPS files?
  - answer: Yes. Aspose.Page copies the page content byte‑for‑byte, so text, images,
      and vector graphics remain unchanged.
    question: Does the merge preserve original formatting and graphics?
  - answer: Use `AddPage(sourcePage, false)` which appends the page to the document’s
      end.
    question: How do I insert a page at the end without specifying an index?
  - answer: The API is fully headless; you can run the same code in ASP.NET, Azure
      Functions, or any server‑side .NET environment.
    question: Is it possible to merge XPS documents on a server without a UI?
  - answer: Aspose.Page currently does not support encrypted XPS files; you must decrypt
      them before merging.
    question: What if my XPS files are password‑protected?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- merge xps
- Aspose.Page
- .NET XPS manipulation
- document merging
- C# XPS processing
title: Sloučit XPS dokumenty s Aspose.Page pro .NET
url: /cs/net/cross-document-editing/manipulate-pages/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sloučení XPS dokumentů pomocí Aspose.Page pro .NET

## Úvod

V tomto tutoriálu se dozvíte, jak **sloučit XPS dokumenty** a manipulovat s jejich stránkami pomocí knihovny Aspose.Page v prostředí .NET. Ať už potřebujete spojit několik zpráv do jednoho XPS souboru, přeuspořádat stránky pro profesionální výstup nebo odstranit nechtěné části, tento průvodce vás provede celým pracovním postupem s jasnými, konverzačními vysvětleními a připravenými ukázkovými kódy.

## Rychlé odpovědi
- **Co mohu dělat s Aspose.Page?** Sloučit XPS dokumenty, vkládat, přidávat nebo odstraňovat stránky a uložit výsledek.  
- **Potřebuji licenci pro testování?** Dočasná licence je k dispozici pro hodnocení.  
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Je vyžadován Visual Studio?** Ne, funguje jakékoli IDE podporující C#, ale Visual Studio se doporučuje.  
- **Jak dlouho trvá sloučení?** Obvykle několik sekund pro standardně velké XPS soubory.

## Co je sloučení XPS dokumentů?
Sloučení XPS dokumentů znamená převzít stránky ze dvou nebo více existujících XPS souborů a spojit je do jednoho XPS dokumentu. Tento přístup vám umožní vytvořit konsolidované zprávy, sestavit vícekapitolové příručky nebo připravit tiskové balíčky bez konverze do jiného formátu, čímž ušetříte čas i úložný prostor.

## Proč použít Aspose.Page pro .NET?
Aspose.Page nabízí **čisté .NET API**, které pracuje přímo se soubory XPS – není potřeba externích nástrojů ani komponent třetích stran. Poskytuje jemnou kontrolu nad pořadím stránek, místy vkládání a zachováním obsahu, což činí proces sloučení spolehlivým a rychlým. Knihovna podporuje **více než 30 metod pro manipulaci s XPS** a dokáže zpracovat dokumenty až do **500 stránek** bez načítání celého souboru do paměti, což poskytuje výkonnost na úrovni podnikového nasazení.

## Požadavky

- **Aspose.Page pro .NET** – stáhněte z [dokumentace Aspose.Page pro .NET](https://reference.aspose.com/page/net/).  
- **Vývojové prostředí** – Visual Studio, Rider nebo jakékoli IDE podporující C#.  
- **Vstupní XPS soubory** – tři ukázkové soubory (`input1.xps`, `input2.xps`, `input3.xps`) umístěné ve známé složce.

## Import jmenných prostorů

Tyto jmenné prostory vám poskytují přístup k základním třídám XPS dokumentu, modelům stránek a základním kreslicím utilitám.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Krok 1: Nastavení adresáře dokumentů

Nahraďte **Your Document Directory** úplnou cestou, kde jsou uloženy vaše XPS soubory, např. `C:\\Docs\\XpsFiles\\`.

```csharp
string dataDir = "Your Document Directory";
```

## Krok 2: Vytvoření instancí XPS dokumentu

Třída `XpsDocument` představuje jeden XPS soubor a poskytuje metody pro čtení, úpravu a ukládání jeho stránek.  

```csharp
XpsDocument doc1 = new XpsDocument(dataDir + "input1.xps");
XpsDocument doc2 = new XpsDocument(dataDir + "input2.xps");
XpsDocument doc3 = new XpsDocument(dataDir + "input3.xps");
XpsDocument doc4 = new XpsDocument();
```

- `doc1`, `doc2` a `doc3` představují zdrojové dokumenty, které chcete sloučit.  
- `doc4` je prázdný XPS dokument, který bude obsahovat sloučený výsledek.

## Krok 3: Vkládání, přidávání a odstraňování stránek

Metoda `InsertPage` vkládá zdrojovou stránku na určenou pozici v cílovém XPS dokumentu.  
Metoda `AddPage` přidává zdrojovou stránku na konec cílového dokumentu.  
Metoda `RemovePageAt` odstraňuje stránku na zadaném nulově založeném indexu.  
Metoda `SelectActivePage` získává konkrétní stránku ze zdrojového dokumentu pro další operace.  

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

## Krok 4: Uložení sloučeného dokumentu

Metoda `Save` zapíše strukturu XPS v paměti do fyzického souboru.  

```csharp
doc4.Save(dataDir + "out.xps");
```

Finální sloučený XPS soubor (`out.xps`) je uložen do stejného adresáře. Nyní jej můžete otevřít v libovolném XPS prohlížeči nebo dále zpracovat pomocí Aspose.Page.

## Časté problémy a řešení
- **Soubor nenalezen** – zkontrolujte cestu `dataDir` a ujistěte se, že vstupní soubory existují.  
- **Neplatný index stránky** – indexy stránek jsou založeny na 1; pokus o vložení neexistující stránky vyvolá výjimku.  
- **Chyby licence** – použijte dočasnou nebo plnou licenci před nasazením do produkce.

## Často kladené otázky

**Q: Můžu sloučit více než tři XPS soubory?**  
A: Rozhodně. Vytvořte další instance `XpsDocument` a opakovaně používejte `InsertPage` nebo `AddPage` k vytvoření většího sloučeného dokumentu.

**Q: Zachovává sloučení původní formátování a grafiku?**  
A: Ano. Aspose.Page kopíruje obsah stránky bajt po bajtu, takže text, obrázky a vektorová grafika zůstávají nezměněny.

**Q: Jak vložím stránku na konec bez specifikace indexu?**  
A: Použijte `AddPage(sourcePage, false)`, který přidá stránku na konec dokumentu.

**Q: Je možné sloučit XPS dokumenty na serveru bez uživatelského rozhraní?**  
A: API je zcela bezhlavé; můžete spustit stejný kód v ASP.NET, Azure Functions nebo jakémkoli serverovém .NET prostředí.

**Q: Co když jsou mé XPS soubory chráněny heslem?**  
A: Aspose.Page v současnosti nepodporuje šifrované XPS soubory; před sloučením je musíte dešifrovat.

---

**Poslední aktualizace:** 2026-07-24  
**Testováno s:** Aspose.Page for .NET 24.10  
**Autor:** Aspose

## Související tutoriály

- [Vytvořit XPS dokument – Aspose.Page pro .NET](/page/net/document-creation/create-xps-document/)
- [Přidat stránku do XPS dokumentu pomocí Aspose.Page pro .NET](/page/net/page-manipulation/add-page-to-xps-document/)
- [Sloučit XPS dokumenty do PDF pomocí Aspose.Page pro .NET](/page/net/document-merging/merge-xps-documents-into-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}