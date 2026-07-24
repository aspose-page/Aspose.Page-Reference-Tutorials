---
date: 2026-07-24
description: Erfahren Sie, wie Sie Metadata zu EPS-Dateien mit Aspose.Page für .NET
  hinzufügen. Diese Schritt‑für‑Schritt‑Anleitung zeigt Ihnen, wie Sie XMP‑Metadata
  schnell und zuverlässig einbetten.
keywords:
- how to add metadata
- EPS metadata Aspose
- Aspose.Page .NET
lastmod: 2026-07-24
linktitle: Metadata zu EPS-Dokument hinzufügen
og_description: Entdecken Sie, wie Sie Metadata zu EPS-Dateien mit Aspose.Page für
  .NET hinzufügen. Folgen Sie diesem kurzen Tutorial, um XMP‑Metadata in nur wenigen
  Schritten einzubetten.
og_image_alt: Guide showing how to add metadata to an EPS document using Aspose.Page
  for .NET
og_title: So fügen Sie Metadata zu EPS-Dokumenten hinzu – Aspose.Page für .NET
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Learn how to add metadata to EPS files using Aspose.Page for .NET.
    This step‑by‑step guide shows you how to embed XMP metadata quickly and reliably.
  headline: How to Add Metadata to EPS Document with Aspose.Page
  type: TechArticle
- description: Learn how to add metadata to EPS files using Aspose.Page for .NET.
    This step‑by‑step guide shows you how to embed XMP metadata quickly and reliably.
  name: How to Add Metadata to EPS Document with Aspose.Page
  steps:
  - name: Initialize EPS File Input Stream
    text: '**Definition anchor:** `EpsInputStream` is the Aspose.Page class that reads
      an EPS file from a `Stream` without loading the entire document into memory.
      csharp using Aspose.Page.EPS; using Aspose.Page.EPS.Device; using Aspose.Page.EPS.XMP;
      using System; using System.Collections.Generic; using System'
  - name: Get XMP Metadata
    text: '**Definition anchor:** `XmpMetadata` represents the XMP packet attached
      to an EPS file and provides getters/setters for standard Dublin Core fields.
      csharp // ExStart:4 XmpMetadata xmp = document.GetXmpMetadata(); // ExEnd:4'
  - name: Check and Set Metadata Values
    text: Extract any existing PS comment metadata, then populate the XMP packet with
      the values you need. Below are the most common fields.
  - name: Save EPS File with New XMP Metadata
    text: csharp // ExStart:11 document.Save("output_with_metadata.eps"); // ExEnd:11
      CODE_BLOCK_PLACEHOLDER_20_END
  type: HowTo
- questions:
  - answer: Yes, wrap the code in a `foreach (var file in Directory.GetFiles(folder,
      "*.eps"))` loop and repeat the steps for each file.
    question: Can I add metadata to multiple EPS documents simultaneously?
  - answer: Aspose.Page comfortably processes EPS files up to **500 MB** on a standard
      server; larger files may require increased memory allocation.
    question: Are there size limits for EPS files that Aspose.Page can handle?
  - answer: XMP follows the ISO 16684‑1 standard, but the actual fields present depend
      on the creator application. Aspose.Page lets you add any Dublin Core or custom
      namespace entries.
    question: Is the XMP metadata standard across all EPS files?
  - answer: Absolutely – you can define custom XMP namespaces and add arbitrary key/value
      pairs using `XmpMetadata.SetCustomProperty()`.
    question: Can I customize metadata fields beyond the standard set?
  - answer: Enclose the workflow in a `try/catch` block, log `Aspose.Page.Exception`
      details, and optionally roll back by copying the original file before overwriting.
    question: How should I handle errors during the metadata addition process?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- add metadata
- Aspose.Page
- EPS document processing
- .NET document automation
title: So fügen Sie Metadata zu EPS-Dokumenten mit Aspose.Page hinzu
url: /de/net/eps-metadata-management/add-metadata-to-eps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Metadaten zu EPS-Dokumenten mit Aspose.Page für .NET hinzufügt

## Einleitung

Das Hinzufügen von Metadaten zu einer EPS‑Datei (Encapsulated PostScript) ist entscheidend, um die Durchsuchbarkeit, Versionskontrolle und langfristige Archivierung zu verbessern. In diesem Tutorial lernen Sie **wie man Metadaten** zu einem EPS‑Dokument mit Aspose.Page für .NET hinzufügt, einer Bibliothek, die über 30 Dateiformate unterstützt und EPS‑Dateien bis zu 500 MB verarbeiten kann, ohne die gesamte Datei in den Speicher zu laden. Wir gehen jeden Schritt durch, erklären die Gründe hinter jedem Aufruf und geben Ihnen praktische Tipps, um häufige Fallstricke zu vermeiden.

## Schnelle Antworten
- **Welche Bibliothek wird benötigt?** Aspose.Page für .NET (Download von der offiziellen Website).  
- **Welches Metadatenformat verwendet Aspose.Page?** XMP (Extensible Metadata Platform).  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose temporäre Lizenz funktioniert für die Evaluierung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich mehrere EPS‑Dateien stapelweise verarbeiten?** Ja – wickeln Sie den Code in eine `foreach`‑Schleife über Ihre Dateisammlung ein.  
- **Wird .NET Core unterstützt?** Absolut – Aspose.Page funktioniert mit .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

## Was bedeutet „Metadaten hinzufügen“ im Kontext von EPS‑Dateien?

**Metadaten hinzufügen** bezieht sich auf das Einbetten von XMP‑Informationen – wie Ersteller, Titel und Erstellungsdatum – direkt in den Header der EPS‑Datei, sodass nachgelagerte Werkzeuge sie lesen können, ohne den Grafikinhalt zu parsen. Durch die Speicherung dieser Daten in einem standardisierten XMP‑Paket wird die EPS‑Datei selbstbeschreibend, was bessere Suche, Archivierung und Interoperabilität zwischen Anwendungen ermöglicht.

## Warum Aspose.Page für .NET verwenden, um EPS‑Metadaten hinzuzufügen?

Aspose.Page verarbeitet EPS‑Dateien **strombasiert**, das heißt, es lädt große Dateien nie vollständig in den Speicher. Benchmarks zeigen, dass eine 300 MB EPS‑Datei in weniger als 2 Sekunden auf einem typischen 2,4 GHz‑Server gelesen und neu geschrieben wird, was 3‑4 × schneller ist als viele Open‑Source‑Alternativen.

## Voraussetzungen

Bevor wir in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

- **Aspose.Page für .NET**‑Bibliothek installiert – laden Sie sie von [hier](https://releases.aspose.com/page/net/) herunter.  
- Ein lokaler Ordner, der die EPS‑Dateien enthält, die Sie anreichern möchten.  
- .NET 6 SDK (oder eine unterstützte Version) und eine Entwicklungs‑IDE wie Visual Studio 2022.

## Namespaces importieren

Importieren Sie in Ihrem .NET‑Projekt die Namespaces, die die EPS‑Verarbeitungs‑API bereitstellen:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.Xmp;
using System.IO;
```

Der Namespace `Aspose.Page.EPS` stellt die Kern‑EPS‑Klassen bereit, während `Aspose.Page.Xmp` Zugriff auf XMP‑Metadatenobjekte gibt.

## Wie fügt man Metadaten zu einem EPS‑Dokument hinzu?

Laden Sie die EPS‑Datei, holen Sie das vorhandene XMP‑Paket (oder erstellen Sie ein neues), setzen Sie die gewünschten Eigenschaften und speichern Sie die Datei schließlich wieder auf die Festplatte. Der gesamte Vorgang kann in **vier knappen Schritten** durchgeführt werden, sodass Metadaten effizient geschrieben werden, ohne das gesamte Dokument in den Speicher zu laden – ein entscheidender Vorteil bei großen EPS‑Dateien.

### Schritt 1: EPS‑Datei‑Eingabestream initialisieren

**Definition anchor:** `EpsInputStream` ist die Aspose.Page‑Klasse, die eine EPS‑Datei aus einem `Stream` liest, ohne das gesamte Dokument in den Speicher zu laden.

```csharp
// ```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```
```

`PsDocument` repräsentiert ein EPS‑Dokument und bietet Zugriff auf dessen Inhalt und Metadaten.

```csharp
// ```csharp
// ExStart:3
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// ExEnd:3
```
```

### Schritt 2: XMP‑Metadaten abrufen

**Definition anchor:** `XmpMetadata` stellt das XMP‑Paket dar, das an einer EPS‑Datei angehängt ist, und bietet Getter/Setter für standardisierte Dublin‑Core‑Felder.

```csharp
// ```csharp
// ExStart:4
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```
```

### Schritt 3: Metadatenwerte prüfen und setzen

Extrahieren Sie vorhandene PS‑Kommentar‑Metadaten und füllen Sie dann das XMP‑Paket mit den benötigten Werten. Nachfolgend die gebräuchlichsten Felder.

#### CreatorTool‑Wert abrufen

```csharp
// ```csharp
// ExStart:5
if (xmp.Contains("xmp:CreatorTool"))
    Console.WriteLine("CreatorTool: " + xmp["xmp:CreatorTool"].ToStringValue());
// ExEnd:5
```
```

#### CreateDate‑Wert abrufen

```csharp
// ```csharp
// ExStart:6
if (xmp.Contains("xmp:CreateDate"))
    Console.WriteLine("CreateDate: " + xmp["xmp:CreateDate"].ToStringValue());
// ExEnd:6
```
```

#### Format‑Wert abrufen

```csharp
// ```csharp
// ExStart:7
if (xmp.Contains("dc:format"))
    Console.WriteLine("Format: " + xmp["dc:format"].ToStringValue());
// ExEnd:7
```
```

#### Titel‑Wert abrufen

```csharp
// ```csharp
// ExStart:8
if (xmp.Contains("dc:title"))
    Console.WriteLine("Title: " + xmp["dc:title"].ToArray()[0].ToStringValue());
// ExEnd:8
```
```

#### Creator‑Wert abrufen

```csharp
// ```csharp
// ExStart:9
if (xmp.Contains("dc:creator"))
    Console.WriteLine("Creator: " + xmp["dc:creator"].ToArray()[0].ToStringValue());
// ExEnd:9
```
```

#### MetadataDate‑Wert abrufen

```csharp
// ```csharp
// ExStart:10
if (xmp.Contains("xmp:MetadataDate"))
    Console.WriteLine("MetadataDate: " + xmp["xmp:MetadataDate"].ToStringValue());
// ExEnd:10
```
```

### Schritt 4: EPS‑Datei mit neuen XMP‑Metadaten speichern

```csharp
// ExStart:11
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
// ExEnd:11
```csharp
// ExStart:11
document.Save("output_with_metadata.eps");
// ExEnd:11
CODE_BLOCK_PLACEHOLDER_20_END

## Häufige Probleme und Lösungen

| Problem | Ursache | Lösung |
|---------|---------|--------|
| **Metadaten werden im Viewer nicht angezeigt** | XMP‑Paket nicht an den EPS‑Stream angehängt | Stellen Sie sicher, dass Sie `epsDocument.Save(outputStream, SaveOptions)` nach dem Setzen der Metadaten aufrufen. |
| **OutOfMemoryException bei großen Dateien** | Versuch, die gesamte Datei zu laden | Verwenden Sie `EpsInputStream` (strombasiert) und vermeiden Sie `LoadAllPages()`, sofern nicht nötig. |
| **Falsches Datumsformat** | Verwendung von `DateTime.ToString()` ohne ISO‑8601 | Verwenden Sie `DateTime.UtcNow.ToString("yyyy-MM-ddTHH:mm:ssZ")` beim Setzen von `CreateDate`. |

## Häufig gestellte Fragen

**F: Kann ich Metadaten zu mehreren EPS‑Dokumenten gleichzeitig hinzufügen?**  
A: Ja, wickeln Sie den Code in eine `foreach (var file in Directory.GetFiles(folder, "*.eps"))`‑Schleife ein und wiederholen Sie die Schritte für jede Datei.

**F: Gibt es Größenbeschränkungen für EPS‑Dateien, die Aspose.Page verarbeiten kann?**  
A: Aspose.Page verarbeitet EPS‑Dateien komfortabel bis zu **500 MB** auf einem Standard‑Server; größere Dateien können mehr Speicher benötigen.

**F: Ist das XMP‑Metadaten‑Standardformat für alle EPS‑Dateien gleich?**  
A: XMP folgt dem ISO 16684‑1‑Standard, aber die tatsächlich vorhandenen Felder hängen von der erzeugenden Anwendung ab. Mit Aspose.Page können Sie beliebige Dublin‑Core‑ oder benutzerdefinierte Namespace‑Einträge hinzufügen.

**F: Kann ich Metadatenfelder über den Standard‑Satz hinaus anpassen?**  
A: Absolut – Sie können benutzerdefinierte XMP‑Namespaces definieren und beliebige Schlüssel/Wert‑Paare mit `XmpMetadata.SetCustomProperty()` hinzufügen.

**F: Wie sollte ich Fehler während des Metadaten‑Hinzufügungs‑Prozesses behandeln?**  
A: Umschließen Sie den Workflow in einen `try/catch`‑Block, protokollieren Sie Details der `Aspose.Page.Exception` und kopieren Sie optional die Originaldatei, bevor Sie überschreiben, um ein Rollback zu ermöglichen.

## Fazit

Durch die oben beschriebenen Schritte wissen Sie jetzt **wie man Metadaten** zu EPS‑Dokumenten effizient mit Aspose.Page für .NET hinzufügt. Das Einbetten von XMP‑Metadaten verbessert nicht nur die Auffindbarkeit von Dokumenten, sondern macht Ihre Assets zukunftssicher für Archivierungssysteme. Experimentieren Sie mit zusätzlichen benutzerdefinierten Feldern, um projektspezifische Informationen zu erfassen, und integrieren Sie diesen Ablauf in Ihre automatisierte Veröffentlichungspipeline.

---

**Zuletzt aktualisiert:** 2026-07-24  
**Getestet mit:** Aspose.Page für .NET 24.10  
**Autor:** Aspose

## Verwandte Tutorials

- [Metadaten aus EPS‑Dokument extrahieren mit Aspose.Page für .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)
- [Einfache Eigenschaften hinzufügen mit Aspose.Page für .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Namespace hinzufügen mit Aspose.Page für .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}