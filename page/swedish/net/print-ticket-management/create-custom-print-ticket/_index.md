---
date: 2026-03-19
description: Lär dig hur du lägger till en biljett genom att skapa anpassade utskriftsbiljetter
  med Aspose.Page för .NET. Skräddarsy din utskriftsupplevelse med fin‑granulär kontroll.
linktitle: Create Custom Print Ticket
second_title: Aspose.Page .NET API
title: 'Hur man lägger till biljett: Skapa anpassad utskriftsbiljett med Aspose.Page
  för .NET'
url: /sv/net/print-ticket-management/create-custom-print-ticket/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man lägger till biljett: Skapa anpassad utskriftsbiljett med Aspose.Page för .NET

## Introduction

Om du behöver **how to add ticket**-funktionalitet i en .NET‑applikation, ger Aspose.Page dig möjlighet att generera anpassade utskriftsbiljetter direkt från kod. I den här handledningen går vi igenom hela processen – att konfigurera miljön, skapa ett XPS‑dokument, bifoga en anpassad jobbutskriftsbiljett och spara resultatet. När du är klar kan du lägga till biljettstöd i vilket utskriftsflöde som helst med självförtroende.

## Quick Answers
- **What does “add ticket” mean?** Det avser inbäddning av en anpassad utskriftsbiljett (XPS‑metadata) som styr skrivarinställningarna.  
- **Which library is required?** Aspose.Page for .NET.  
- **Do I need a license?** En tillfällig licens fungerar för utvärdering; en full licens krävs för produktion.  
- **Can I use this with .NET Core?** Ja, Aspose.Page stödjer .NET Framework och .NET Core.  
- **How long does implementation take?** Vanligtvis under 15 minutes för en grundläggande biljett.

## What is a Custom Print Ticket?
En anpassad utskriftsbiljett är en XML‑baserad beskrivning av skrivarpreferenser (såsom sortering, kopior, färghantering osv.) som färdas med ett XPS‑dokument. Den låter utvecklare programatiskt ange hur ett dokument ska skrivas ut, vilket eliminerar manuell konfiguration på klientsidan.

## Why add ticket support with Aspose.Page?
- **Fine‑grained control:** Ställ in sortering, antal kopior, mediatyp med mera från kod.  
- **Cross‑platform consistency:** Samma biljett fungerar på alla skrivare som förstår XPS‑metadata.  
- **Seamless integration:** Fungerar direkt med dina befintliga .NET‑projekt utan extra tjänster.

## Prerequisites

Innan vi dyker ner, se till att du har:

- Grundläggande kunskaper i C# och .NET‑utveckling.  
- Visual Studio (valfri nyare version) installerad.  
- Aspose.Page for .NET‑biblioteket tillagt i ditt projekt.  

Om du ännu inte har lagt till biblioteket kan du ladda ner det från [Aspose.Page för .NET-dokumentationen](https://reference.aspose.com/page/net/). För gemenskapsstöd, besök [Aspose.Page‑forumet](https://forum.aspose.com/c/page/39).

## Import Namespaces

Starta med att importera de namnrymder som exponerar XPS‑ och metadata‑klasserna.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsMetadata;
using Aspose.Page.XPS.XpsModel;
using System;
using System.Drawing;
```

Nu går vi igenom implementeringen steg för steg.

## Step 1: Set up Document Directory

Definiera var den genererade XPS‑filen ska sparas.

```csharp
string dir = "Your Document Directory";
```

## Step 2: Create a New XPS Document

Instansiera ett nytt XPS‑dokument som kommer att innehålla sidorna och biljetten.

```csharp
XpsDocument xDocs = new XpsDocument();
```

## Step 3: Add Custom Job Print Ticket

Bifoga en anpassad jobbutskriftsbiljett till dokumentet. Detta är kärnan i **how to add ticket**‑funktionaliteten – här specificerar du sortering, kopior, rendering‑intent, färghantering och eventuella andra inställningar du behöver.

```csharp
xDocs.JobPrintTicket = new JobPrintTicket(
    new PageDevModeSnaphot("SABlAGwAbABvACEAAAA="),
    new DocumentCollate(Collate.CollateOption.Collated),
    // Add other print settings as needed
);
```

> **Pro tip:** Ersätt platshållar‑snapshot‑strängen med en Base64‑kodad DEVMODE‑struktur som matchar din skrivarens kapabiliteter.

## Step 4: Save the Document

Spara XPS‑dokumentet (med den inbäddade biljetten) till disk.

```csharp
xDocs.Save(dir + "output1.xps");
```

När du öppnar *output1.xps* i en visare som respekterar XPS‑metadata kommer skrivaren automatiskt att tillämpa de inställningar som definierats i biljetten.

## Common Issues and Solutions

| Problem | Orsak | Lösning |
|-------|-------|-----|
| Biljett tillämpas inte | Visaren ignorerar XPS‑metadata | Använd en skrivardrivrutin som stödjer XPS‑utskriftsbiljetter eller en visare som Microsoft XPS Viewer. |
| Ogiltig Base64‑snapshot | Korrupt DEVMODE‑data | Generera om snapshoten från skrivardrivrutinen med `GetPrinter` API. |
| Saknade behörigheter | Skrivbehörighet till `dir` nekad | Se till att applikationen körs med tillräckliga filsystemsrättigheter. |

## Frequently Asked Questions

**Q: Can I use Aspose.Page for .NET with other .NET frameworks?**  
A: Ja, Aspose.Page fungerar med .NET Framework, .NET Core, .NET 5/6 och senare.

**Q: How can I obtain a temporary license for Aspose.Page?**  
A: Besök [denna länk](https://purchase.aspose.com/temporary-license/) för att skaffa en tillfällig licens för Aspose.Page.

**Q: Is there a community forum for Aspose.Page support?**  
A: Absolut, du kan hitta hjälpsamma diskussioner och support på [Aspose.Page‑forumet](https://forum.aspose.com/c/page/39).

**Q: What media types are supported in custom print tickets?**  
A: Aspose.Page stöder ett antal mediatyper, inklusive vanligt papper, glansigt och anpassade medie‑definitioner.

**Q: Are there any sample projects available for Aspose.Page for .NET?**  
A: Utforska [dokumentationen](https://reference.aspose.com/page/net/) för exempelprojekt och kodsnuttar för att kickstarta din utveckling.

## Conclusion

Vi har gått igenom **how to add ticket**‑stöd för ett XPS‑dokument med Aspose.Page för .NET. Genom att följa dessa steg kan du bädda in rika utskriftsinstruktioner direkt i dina filer, vilket ger dig full kontroll över utskriftsflödet från dina .NET‑applikationer. Känn dig fri att experimentera med ytterligare biljettinställningar för att matcha din specifika utskriftsmiljö.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Page for .NET (latest stable version)  
**Author:** Aspose  

---