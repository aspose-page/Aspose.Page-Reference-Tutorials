---
date: 2026-01-10
description: Lär dig hur du slår ihop XPS‑dokument med Aspose.Page för .NET. Denna
  steg‑för‑steg‑guide visar tekniker för sidmanipulation för effektiva resultat.
linktitle: Manipulate Pages
second_title: Aspose.Page .NET API
title: Sammanfoga XPS-dokument med Aspose.Page för .NET
url: /sv/net/cross-document-editing/manipulate-pages/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Slå ihop XPS-dokument med Aspose.Page för .NET

## Introduktion

I den här handledningen kommer du att upptäcka hur du **slår ihop XPS-dokument** och manipulerar deras sidor med hjälp av Aspose.Page‑biblioteket i en .NET‑miljö. Oavsett om du behöver kombinera flera rapporter till en enda XPS‑fil eller omarrangera sidor för ett polerat resultat, guidar den här guiden dig genom processen steg för steg, med tydliga förklaringar och färdig‑körbar kod.

## Snabba svar
- **Vad kan jag göra med Aspose.Page?** Slå ihop XPS-dokument, infoga, lägga till eller ta bort sidor, och spara resultatet.  
- **Behöver jag en licens för testning?** En tillfällig licens finns tillgänglig för utvärdering.  
- **Vilka .NET-versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Krävs Visual Studio?** Nej, alla IDE:er som stödjer C# fungerar, men Visual Studio rekommenderas.  
- **Hur lång tid tar sammanslagningen?** Vanligtvis några sekunder för XPS‑filer av standardstorlek.

## Vad är sammanslagning av XPS-dokument?
Att slå ihop XPS-dokument innebär att ta sidor från två eller fler befintliga XPS-filer och kombinera dem till ett enda XPS-dokument. Detta är användbart för att skapa konsoliderade rapporter, sammanställa flersidiga manualer eller förbereda utskriftsklara paket utan att konvertera till ett annat format.

## Varför använda Aspose.Page för .NET?
Aspose.Page erbjuder ett **rent .NET API** som arbetar direkt med XPS-filer—ingen extern verktyg eller tredjepartskomponent behövs. Det ger dig fin‑granulerad kontroll över sidordning, infogningspunkter och bevarande av innehåll, vilket gör sammanslagningsprocessen pålitlig och snabb.

## Förutsättningar

- **Aspose.Page for .NET** – ladda ner från [Aspose.Page for .NET-dokumentationen](https://reference.aspose.com/page/net/).  
- **Utvecklingsmiljö** – Visual Studio, Rider eller någon IDE som stödjer C#.  
- **Inmatnings‑XPS‑filer** – tre exempel‑filer (`input1.xps`, `input2.xps`, `input3.xps`) placerade i en känd mapp.

## Importera namnrymder

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Dessa namnrymder ger dig åtkomst till de grundläggande XPS‑dokumentklasserna, sidmodellerna och grundläggande ritverktyg.

## Steg 1: Ange dokumentkatalogen

```csharp
string dataDir = "Your Document Directory";
```

Byt ut **Your Document Directory** mot den fullständiga sökvägen där dina XPS‑filer lagras, t.ex. `C:\\Docs\\XpsFiles\\`.

## Steg 2: Skapa XPS‑dokumentinstanser

```csharp
XpsDocument doc1 = new XpsDocument(dataDir + "input1.xps");
XpsDocument doc2 = new XpsDocument(dataDir + "input2.xps");
XpsDocument doc3 = new XpsDocument(dataDir + "input3.xps");
XpsDocument doc4 = new XpsDocument();
```

- `doc1`, `doc2` och `doc3` representerar källdokumenten du vill slå ihop.  
- `doc4` är ett tomt XPS‑dokument som kommer att hålla det sammanslagna resultatet.

## Steg 3: Infoga, lägga till och ta bort sidor

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

Dessa operationer illustrerar hur du kan **slå ihop XPS-dokument** samtidigt som du omordnar eller kastar bort sidor efter behov.

## Steg 4: Spara det sammanslagna dokumentet

```csharp
doc4.Save(dataDir + "out.xps");
```

Den slutgiltiga sammanslagna XPS-filen (`out.xps`) skrivs till samma katalog. Du kan nu öppna den i någon XPS‑visare eller vidarebearbeta den med Aspose.Page.

## Vanliga problem och lösningar
- **Fil ej hittad** – dubbelkolla `dataDir`‑sökvägen och säkerställ att indatafilerna finns.  
- **Ogiltigt sidindex** – sidindex är 1‑baserade; försök att infoga en icke‑existerande sida kastar ett undantag.  
- **Licensfel** – använd en tillfällig eller fullständig licens innan du distribuerar till produktion.

## Vanliga frågor

### Q1: Kan jag manipulera sidor från olika XPS-dokument?

A1: Ja, som demonstrerat i handledningen kan du infoga sidor från flera XPS-dokument i ett nytt dokument.

### Q2: Hur kan jag ta bort en specifik sida från ett dokument?

A2: Använd metoden `RemovePageAt` och ange indexet för den sida du vill ta bort.

### Q3: Är Aspose.Page kompatibel med Visual Studio?

A3: Ja, Aspose.Page är fullt kompatibel med Visual Studio, vilket gör det enkelt att integrera i dina .NET‑projekt.

### Q4: Finns det några licensalternativ tillgängliga?

A4: Ja, du kan utforska licensalternativ och skaffa en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

### Q5: Var kan jag få support eller ställa frågor?

A5: Besök [Aspose.Page‑forumet](https://forum.aspose.com/c/page/39) för att få support och engagera dig med communityn.

## Vanligt förekommande frågor

**Q: Kan jag slå ihop mer än tre XPS‑filer?**  
A: Absolut. Skapa ytterligare `XpsDocument`‑instanser och använd `InsertPage` eller `AddPage` upprepade gånger för att bygga ett större sammanslaget dokument.

**Q: Bevarar sammanslagningen originalformatering och grafik?**  
A: Ja. Aspose.Page kopierar sidinnehållet byte‑för‑byte, så text, bilder och vektorgrafik förblir oförändrade.

**Q: Hur infogar jag en sida i slutet utan att ange ett index?**  
A: Använd `AddPage(sourcePage, false)` som lägger till sidan i dokumentets slut.

**Q: Är det möjligt att slå ihop XPS‑dokument på en server utan UI?**  
A: API:et är helt huvudlöst; du kan köra samma kod i ASP.NET, Azure Functions eller någon annan server‑sidig .NET‑miljö.

**Q: Vad händer om mina XPS‑filer är lösenordsskyddade?**  
A: Aspose.Page stödjer för närvarande inte krypterade XPS‑filer; du måste dekryptera dem innan sammanslagning.

**Senast uppdaterad:** 2026-01-10  
**Testat med:** Aspose.Page for .NET 24.10  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}