---
date: 2026-01-20
description: Voeg moeiteloos paginanummers toe aan PDF's terwijl u XPS‑documenten
  samenvoegt tot PDF's van hoge kwaliteit met Aspose.Page voor .NET. Volg onze stapsgewijze
  handleiding om XPS naar PDF te converteren.
linktitle: Merge XPS Documents into PDF
second_title: Aspose.Page .NET API
title: Paginanummers toevoegen aan PDF – XPS naar PDF samenvoegen met Aspose.Page
url: /nl/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pagina‑nummers toevoegen PDF – XPS samenvoegen tot PDF met Aspose.Page

## Introductie

Als je **add page numbers PDF** moet toevoegen tijdens het samenvoegen van XPS‑bestanden, maakt Aspose.Page for .NET het proces moeiteloos. In deze tutorial lopen we een volledig, productie‑klaar voorbeeld door dat een XPS‑document converteert naar een PDF van hoge kwaliteit, je controle geeft over beeldcompressie, en automatisch paginanummers in de uiteindelijke PDF invoegt. Aan het einde heb je een herbruikbare code‑snippet die je in elk C#‑project kunt gebruiken.

## Snelle antwoorden
- **Kan ik paginanummers toevoegen bij het samenvoegen van XPS naar PDF?** Ja – de `PdfSaveOptions.PageNumbers`‑eigenschap doet precies dat.  
- **Welke bibliotheek verzorgt de conversie?** Aspose.Page for .NET.  
- **Heb ik een licentie nodig voor productiegebruik?** Een geldige Aspose.Page‑licentie is vereist; een tijdelijke licentie is beschikbaar voor testdoeleinden.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, en .NET 5/6+.  
- **Is output met hoge beeldkwaliteit mogelijk?** Absoluut – stel `JpegQualityLevel` in op 100 en kies `PdfImageCompression.Jpeg`.

## Voorvereisten

Voordat je aan de tutorial begint, zorg dat je de volgende zaken gereed hebt:

- Aspose.Page for .NET: Zorg ervoor dat je de Aspose.Page‑bibliotheek geïnstalleerd hebt. Je kunt deze downloaden vanaf [here](https://releases.aspose.com/page/net/).

- Documentbestanden: Zorg dat het XPS‑document (`input.xps`) klaarstaat in de opgegeven map.

## Namespaces importeren

In je .NET‑project voeg je de benodigde namespaces toe voor het werken met Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

Deze stap zorgt ervoor dat je toegang hebt tot de klassen en methoden die nodig zijn voor de documentconversie.

## Hoe pagina‑nummers toevoegen PDF bij het samenvoegen van XPS‑documenten

De `PdfSaveOptions.PageNumbers`‑collectie laat je precies specificeren welke pagina’s (of paginabereiken) in de uitvoer‑PDF moeten verschijnen. Door deze te vullen met de gewenste paginanummers, voegt Aspose.Page automatisch de juiste nummering toe.

### Stap 1: Streams initialiseren

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

Deze stap omvat het instellen van de invoer‑ en uitvoer‑streams voor de XPS‑ en PDF‑bestanden. Zorg dat de juiste paden en bestandsnamen worden gebruikt.

### Stap 2: XPS‑document laden

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

Hier laden we het XPS‑document in het `XpsDocument`‑object, zodat het klaar is voor verdere verwerking.

### Stap 3: Opslaan‑opties initialiseren (XPS samenvoegen tot PDF)

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }   // <-- adds page numbers PDF
};
// ExEnd:5
```

Pas het `PdfSaveOptions`‑object aan op basis van jouw voorkeuren, waarbij je parameters zoals beeldcompressie, tekstcompressie en de **page numbers** die je in de uiteindelijke PDF wilt zien, opgeeft. Het instellen van `JpegQualityLevel` op 100 zorgt voor **high quality PDF images**.

### Stap 4: Rendering‑apparaat maken

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

De `PdfDevice` is het hulpmiddel dat verantwoordelijk is voor het renderen van het XPS‑document naar PDF‑formaat.

### Stap 5: Document opslaan (C# XPS naar PDF)

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

Tot slot sla je het document op met behulp van het render‑apparaat en de opgegeven opties. De resulterende PDF bevat de geselecteerde pagina’s met automatisch toegevoegde paginanummers.

## Waarom Aspose.Page gebruiken voor deze conversie?

- **Betrouwbaarheid** – Verwerkt complexe XPS‑functies zonder verlies van kwaliteit.  
- **Prestaties** – Stream‑gebaseerde verwerking voorkomt het laden van volledige bestanden in het geheugen.  
- **Flexibiliteit** – Fijnmazige controle over beeldkwaliteit, compressie en paginanummering.  
- **Cross‑platform** – Werkt op Windows, Linux en macOS met .NET Core.

## Veelvoorkomende problemen en oplossingen

| Issue | Solution |
|-------|----------|
| **Output PDF is blank** | Controleer of het pad naar het XPS‑bestand correct is en of het bestand niet beschadigd is. |
| **Page numbers not appearing** | Zorg ervoor dat `PageNumbers` is ingesteld op de juiste nul‑gebaseerde paginabereiken (bijv. `new int[] {1,2,6}`). |
| **Low‑quality images** | Verhoog `JpegQualityLevel` en kies `PdfImageCompression.Jpeg`. |
| **Large XPS files cause memory pressure** | Verwerk de XPS in kleinere delen of vergroot de geheugengrens van de applicatie. |

## Veelgestelde vragen

### Q1: Kan ik meerdere XPS‑bestanden samenvoegen tot één PDF?

A1: Ja, dat kan. Pas simpelweg de `PageNumbers`‑parameter in de `PdfSaveOptions` aan om de gewenste pagina’s uit verschillende XPS‑bestanden op te nemen, of laad elk XPS‑bestand opeenvolgend en roep `document.Save` aan op dezelfde `PdfDevice`.

### Q2: Is er een tijdelijke licentie beschikbaar voor Aspose.Page for .NET?

A2: Ja, je kunt een tijdelijke licentie verkrijgen [here](https://purchase.aspose.com/temporary-license/) voor testdoeleinden.

### Q3: Zijn er beperkingen qua bestandsgrootte bij het gebruik van Aspose.Page voor documentconversie?

A3: Aspose.Page for .NET legt geen strikte limieten op de bestandsgrootte, maar optimale prestaties worden bereikt met redelijk grote bestanden. Voor zeer grote XPS‑documenten kun je overwegen ze in streams te verwerken om het geheugenverbruik te verminderen.

### Q4: Kan ik de output‑PDF verder aanpassen, bijvoorbeeld door watermerken of annotaties toe te voegen?

A4: Ja, Aspose.Page for .NET biedt uitgebreide mogelijkheden voor PDF‑manipulatie. Na de conversie kun je de Aspose.PDF‑bibliotheek gebruiken om watermerken, annotaties of andere verbeteringen toe te voegen.

### Q5: Ondersteunt Aspose.Page for .NET cross‑platform ontwikkeling?

A5: Ja, Aspose.Page for .NET is ontworpen om naadloos te werken op verschillende platforms, waaronder Windows, Linux en macOS, wanneer het wordt gebruikt met .NET Core of .NET 5/6.

**Last Updated:** 2026-01-20  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}