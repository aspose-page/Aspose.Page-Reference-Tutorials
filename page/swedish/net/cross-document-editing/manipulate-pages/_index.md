---
date: 2026-07-24
description: Lär dig hur du slår ihop XPS-dokument med Aspose.Page för .NET. Denna
  steg‑för‑steg‑guide visar tekniker för sidhantering för effektiva resultat.
keywords:
- merge xps documents
- how to merge xps
- asp page .net tutorial
lastmod: 2026-07-24
linktitle: Hantera sidor
og_description: Slå ihop XPS-dokument effektivt med Aspose.Page för .NET. Denna guide
  går igenom sammanslagning, infogning och borttagning av sidor med tydliga kodexempel.
og_image_alt: Guide showing how to merge XPS documents using Aspose.Page in a .NET
  application
og_title: Slå ihop XPS-dokument med Aspose.Page för .NET – Snabb sidhantering
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
title: Slå ihop XPS-dokument med Aspose.Page för .NET
url: /sv/net/cross-document-editing/manipulate-pages/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sammanfoga XPS-dokument med Aspose.Page för .NET

## Introduktion

I den här handledningen kommer du att upptäcka hur du **sammanfogar XPS-dokument** och manipulerar deras sidor med hjälp av Aspose.Page‑biblioteket i en .NET‑miljö. Oavsett om du behöver kombinera flera rapporter till en enda XPS‑fil, ändra sidordning för ett polerat resultat, eller ta bort oönskade avsnitt, guidar den här guiden dig genom hela arbetsflödet med tydliga, konversativa förklaringar och färdiga kodexempel.

## Snabba svar
- **Vad kan jag göra med Aspose.Page?** Sammanfoga XPS-dokument, infoga, lägga till eller ta bort sidor, och spara resultatet.  
- **Behöver jag en licens för testning?** En tillfällig licens finns tillgänglig för utvärdering.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Krävs Visual Studio?** Nej, alla IDE:er som stödjer C# fungerar, men Visual Studio rekommenderas.  
- **Hur lång tid tar sammanslagningen?** Vanligtvis några sekunder för XPS‑filer av standardstorlek.

## Vad är sammanslagning av XPS-dokument?

Att sammanfoga XPS-dokument innebär att ta sidor från två eller fler befintliga XPS‑filer och kombinera dem till ett enda XPS‑dokument. Detta tillvägagångssätt låter dig skapa konsoliderade rapporter, sammanställa flerkapitelshandböcker eller förbereda utskriftsklara paket utan att konvertera till ett annat format, vilket sparar både tid och lagringsutrymme.

## Varför använda Aspose.Page för .NET?

Aspose.Page erbjuder ett **rent .NET‑API** som arbetar direkt med XPS‑filer—ingen extern verktyg eller tredjepartskomponent behövs. Det ger dig fin‑granulär kontroll över sidordning, infogningspunkter och bevarande av innehåll, vilket gör sammanslagningsprocessen pålitlig och snabb. Biblioteket stödjer **30+ XPS‑manipuleringsmetoder** och kan hantera dokument upp till **500 sidor** utan att ladda hela filen i minnet, vilket levererar prestanda på företagsnivå.

## Förutsättningar

- **Aspose.Page for .NET** – ladda ner från [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/).  
- **Utvecklingsmiljö** – Visual Studio, Rider eller någon IDE som stödjer C#.  
- **Inmatnings‑XPS‑filer** – tre exempel‑filer (`input1.xps`, `input2.xps`, `input3.xps`) placerade i en känd mapp.

## Importera namnrymder

Dessa namnrymder ger dig åtkomst till de grundläggande XPS‑dokumentklasserna, sidmodellerna och grundläggande ritverktyg.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Steg 1: Ange dokumentkatalogen

Byt ut **Your Document Directory** mot den fullständiga sökvägen där dina XPS‑filer lagras, t.ex. `C:\\Docs\\XpsFiles\\`.

```csharp
string dataDir = "Your Document Directory";
```

## Steg 2: Skapa XPS‑dokumentinstanser

`XpsDocument`‑klassen representerar en enskild XPS‑fil och tillhandahåller metoder för att läsa, redigera och spara dess sidor.  

```csharp
XpsDocument doc1 = new XpsDocument(dataDir + "input1.xps");
XpsDocument doc2 = new XpsDocument(dataDir + "input2.xps");
XpsDocument doc3 = new XpsDocument(dataDir + "input3.xps");
XpsDocument doc4 = new XpsDocument();
```

- `doc1`, `doc2` och `doc3` representerar källdokumenten du vill sammanfoga.  
- `doc4` är ett tomt XPS‑dokument som kommer att innehålla det sammanslagna resultatet.

## Steg 3: Infoga, lägga till och ta bort sidor

`InsertPage`‑metoden infogar en källsida på en angiven position i mål‑XPS‑dokumentet.  
`AddPage`‑metoden lägger till en källsida i slutet av mål‑dokumentet.  
`RemovePageAt`‑metoden tar bort en sida på det angivna noll‑baserade indexet.  
`SelectActivePage`‑metoden hämtar en specifik sida från ett källdokument för vidare operationer.  

```csharp
doc4.InsertPage(1, doc2.Page, false);
doc4.AddPage(doc3.Page, false);
doc4.RemovePageAt(2);
doc4.InsertPage(2, doc1.SelectActivePage(3), false);
```

Här är vad varje rad gör:

1. **InsertPage(1, doc2.Page, false)** – placerar den första sidan av `doc2` på position 1 i `doc4`.  
2. **AddPage(doc3.Page, false)** – lägger till den första sidan av `doc3` i slutet av `doc4`.  
3. **RemovePageAt(2)** – tar bort sidan som nu är på index 2 (användbart för att eliminera oönskade sidor).  
4. **InsertPage(2, doc1.SelectActivePage(3), false)** – infogar den tredje sidan av `doc1` på position 2, vilket slutför sammanslagningen.

Dessa operationer visar hur du kan **sammanfoga XPS-dokument** samtidigt som du omordnar eller tar bort sidor efter behov.

## Steg 4: Spara det sammanslagna dokumentet

`Save`‑metoden skriver den minnes‑XPS‑strukturen till en fysisk fil.  

```csharp
doc4.Save(dataDir + "out.xps");
```

Den slutliga sammanslagna XPS‑filen (`out.xps`) skrivs till samma katalog. Du kan nu öppna den i någon XPS‑visare eller vidarebearbeta den med Aspose.Page.

## Vanliga problem och lösningar
- **File not found** – dubbelkolla `dataDir`‑sökvägen och säkerställ att indatafilerna finns.  
- **Invalid page index** – sidindex är 1‑baserade; försök att infoga en icke‑existerande sida kastar ett undantag.  
- **License errors** – använd en tillfällig eller full licens innan du distribuerar till produktion.

## Vanliga frågor

**Q: Kan jag sammanfoga mer än tre XPS‑filer?**  
A: Absolut. Skapa ytterligare `XpsDocument`‑instanser och använd `InsertPage` eller `AddPage` upprepade gånger för att bygga ett större sammanslaget dokument.

**Q: Bevarar sammanslagningen originalformatering och grafik?**  
A: Ja. Aspose.Page kopierar sidans innehåll byte‑för‑byte, så text, bilder och vektorgrafik förblir oförändrade.

**Q: Hur infogar jag en sida i slutet utan att ange ett index?**  
A: Använd `AddPage(sourcePage, false)` som lägger till sidan i dokumentets slut.

**Q: Är det möjligt att sammanfoga XPS‑dokument på en server utan UI?**  
A: API:et är helt huvudlöst; du kan köra samma kod i ASP.NET, Azure Functions eller någon server‑sidig .NET‑miljö.

**Q: Vad händer om mina XPS‑filer är lösenordsskyddade?**  
A: Aspose.Page stödjer för närvarande inte krypterade XPS‑filer; du måste dekryptera dem innan sammanslagning.

**Senast uppdaterad:** 2026-07-24  
**Testat med:** Aspose.Page for .NET 24.10  
**Författare:** Aspose

## Relaterade handledningar

- [Skapa XPS-dokument – Aspose.Page för .NET](/page/net/document-creation/create-xps-document/)
- [Lägg till sida i XPS-dokument med Aspose.Page för .NET](/page/net/page-manipulation/add-page-to-xps-document/)
- [Sammanfoga XPS-dokument till PDF med Aspose.Page för .NET](/page/net/document-merging/merge-xps-documents-into-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}