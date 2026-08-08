---
date: 2026-08-08
description: Erfahren Sie, wie Sie Array-Elemente zu EPS-Metadaten mit Aspose.Page
  EPS metadata hinzufügen. Dieser Schritt‑für‑Schritt .NET‑Leitfaden zeigt, wie man
  Array-Elemente hinzufügt und EPS‑Dateien effizient liest.
keywords:
- aspse page eps metadata
- how to add array item
- read eps file .net
lastmod: 2026-08-08
linktitle: Array-Elemente hinzufügen
og_description: Entdecken Sie, wie Sie Array-Elemente zu EPS-Metadaten mit Aspose.Page
  EPS metadata hinzufügen. Folgen Sie diesem prägnanten .NET‑Tutorial, um EPS‑Dateien
  zu lesen und Metadaten effizient zu verwalten.
og_image_alt: Guide showing how to add array items to EPS metadata with Aspose.Page
  in a .NET project
og_title: Array-Elemente mit Aspose.Page EPS metadata in .NET hinzufügen
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  headline: Add array items with Aspose.Page EPS metadata in .NET
  type: TechArticle
- description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  name: Add array items with Aspose.Page EPS metadata in .NET
  steps:
  - name: initialize eps file input stream
    text: '`PsDocument` represents an EPS document and provides methods to access
      its content. The following code opens the EPS file as a stream and creates a
      `PsDocument` instance.'
  - name: get xmp metadata
    text: '`GetXmpMetadata()` retrieves the XMP packet embedded in the EPS file. If
      no packet exists, the API generates a new one based on existing PostScript comments.'
  - name: change xmp metadata values
    text: '`AddArrayItem()` appends a new value to an existing XMP array without overwriting
      other entries. Use it to add titles, creators, or custom tags to the metadata.'
  - name: save eps file with changed xmp metadata
    text: '`Save()` writes the modified XMP packet back into the EPS file while preserving
      the original PostScript content. Provide the output path to create a new file
      or overwrite the source.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works across .NET Framework 4.5+, .NET Core 3.1+, and
      .NET 5/6/7, providing consistent API behavior on Windows, Linux and macOS.
    question: Is Aspose.Page compatible with all .NET environments?
  - answer: You can evaluate the library with a free trial download from the [Aspose
      purchase page](https://purchase.aspose.com/buy). A commercial license is required
      for production deployments.
    question: Can I use Aspose.Page for free?
  - answer: Temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      for short‑term projects or evaluation periods.
    question: Are temporary licenses available for Aspose.Page?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      to ask questions and share solutions with other developers.
    question: Where can I find community support for Aspose.Page?
  - answer: Refer to the official [documentation](https://reference.aspose.com/page/net/)
      for the most recent release notes and download links.
    question: What is the latest version of Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: Array-Elemente mit Aspose.Page EPS metadata in .NET hinzufügen
url: /de/net/eps-metadata-management/modify-eps-metadata-add-array-items/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Array-Elemente mit Aspose.Page EPS-Metadaten in .NET hinzufügen

## Einführung

In diesem Tutorial lernen Sie, wie Sie Array-Elemente zu EPS-Metadaten mithilfe von **Aspose.Page EPS metadata** hinzufügen. Egal, ob Sie eine EPS-Datei mit zusätzlichen Titeln, Erstellern oder benutzerdefinierten Tags anreichern müssen, Aspose.Page macht die Aufgabe für jeden .NET‑Entwickler unkompliziert. Wir gehen jeden Schritt durch, vom Öffnen des EPS‑Streams bis zum Persistieren des aktualisierten XMP‑Pakets, sodass Sie die Metadatenverarbeitung mit Vertrauen in Ihre eigenen Anwendungen integrieren können.

## Schnelle Antworten
- **Was ermöglicht Aspose.Page EPS metadata?** Es ermöglicht das Lesen und Schreiben von XMP‑Metadaten‑Arrays in EPS‑Dateien aus .NET.  
- **Welche Klasse repräsentiert ein EPS‑Dokument?** `PsDocument` ist die Kernklasse zum Laden und Speichern von EPS‑Inhalten.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion funktioniert für Tests; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich Metadaten ändern, ohne die EPS‑Grafiken zu verändern?** Ja, es wird nur das XMP‑Paket geändert, während der Seiteninhalt unverändert bleibt.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Was ist Aspose.Page EPS metadata?
Aspose.Page EPS metadata ist ein XMP‑basiertes Informationsblock, das in einer EPS‑Datei eingebettet ist. Es speichert beschreibende Eigenschaften wie Titel, Ersteller, Schlüsselwörter und benutzerdefinierte Tags gemäß dem ISO 16684‑1‑Standard. Die Metadaten können programmgesteuert über die Aspose.Page‑API abgerufen und geändert werden, was eine automatisierte Dokumentenverwaltung und Suchoptimierung ermöglicht.

## Warum EPS-Metadaten ändern?
Aspose.Page kann **über 30 Metadatenfelder** verarbeiten und EPS‑Dateien bis zu **200 MB** handhaben, ohne das gesamte Dokument in den Speicher zu laden, was den CPU‑Verbrauch im Vergleich zur vollständigen Dateianalyse um bis zu 40 % reduziert. Das Aktualisieren von Metadaten verbessert die Durchsuchbarkeit, die Konformität und die nachgelagerte Workflow‑Automatisierung.

## Voraussetzungen

- Grundlegende .NET‑Programmierkenntnisse.  
- Aspose.Page für .NET installiert – laden Sie es von [Aspose.Page für .NET herunterladen](https://releases.aspose.com/page/net/).  
- Visual Studio (oder jede .NET‑kompatible IDE), um den Beispielcode auszuführen.  

## Wie fügt man Array-Elemente zu EPS-Metadaten hinzu?
Um Array-Elemente hinzuzufügen, laden Sie zunächst die EPS‑Datei in ein `PsDocument` und rufen dann das XMP‑Paket mit `GetXmpMetadata()` ab. Verwenden Sie die Methode `AddArrayItem()` auf dem gewünschten XMP‑Array, z. B. `dc:title` oder `dc:creator`, um neue Werte anzuhängen. Abschließend rufen Sie `Save()` auf, um die aktualisierten Metadaten zurück in die Datei zu schreiben, wobei der Grafikinhalt unverändert bleibt.

### Schritt 1: EPS-Dateieingabestream initialisieren
`PsDocument` repräsentiert ein EPS‑Dokument und bietet Methoden zum Zugriff auf dessen Inhalt. Der folgende Code öffnet die EPS‑Datei als Stream und erstellt eine `PsDocument`‑Instanz.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Schritt 2: XMP-Metadaten abrufen
`GetXmpMetadata()` ruft das in der EPS‑Datei eingebettete XMP‑Paket ab. Wenn kein Paket vorhanden ist, erzeugt die API ein neues basierend auf vorhandenen PostScript‑Kommentaren.

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

### Schritt 3: XMP-Metadatenwerte ändern
`AddArrayItem()` fügt einem bestehenden XMP‑Array einen neuen Wert hinzu, ohne andere Einträge zu überschreiben. Verwenden Sie es, um Titel, Ersteller oder benutzerdefinierte Tags zu den Metadaten hinzuzufügen.

```csharp
// ExStart:4
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

### Schritt 4: EPS-Datei mit geänderten XMP-Metadaten speichern
`Save()` schreibt das modifizierte XMP‑Paket zurück in die EPS‑Datei und bewahrt dabei den ursprünglichen PostScript‑Inhalt. Geben Sie den Ausgabepfad an, um eine neue Datei zu erstellen oder die Quelle zu überschreiben.

```csharp
// ExStart:5
// Change XMP metadata values

// Add one more title. It will be added at the end of the array by default.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Add one more creator. It will be added in the array by an index (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

## Häufige Fallstricke und Fehlersuche

- **Null XMP‑Paket** – Wenn `GetXmpMetadata()` `null` zurückgibt, stellen Sie sicher, dass die EPS‑Datei mindestens einen Kommentarblock enthält; andernfalls erstellen Sie manuell eine neue `XmpMetadata`‑Instanz.  
- **Kodierungsprobleme** – Verwenden Sie UTF‑8 beim Hinzufügen von Zeichenkettenwerten, um Zeichenkorruption in Nicht‑ASCII‑Sprachen zu vermeiden.  
- **Große Dateien** – Bei EPS‑Dateien größer als 150 MB sollten Sie den Input über `FileStream` mit einem Puffer streamen, um den Speicherverbrauch gering zu halten.

## Häufig gestellte Fragen

**Q: Ist Aspose.Page mit allen .NET‑Umgebungen kompatibel?**  
A: Ja, Aspose.Page funktioniert über .NET Framework 4.5+, .NET Core 3.1+ und .NET 5/6/7 hinweg und bietet konsistentes API‑Verhalten unter Windows, Linux und macOS.

**Q: Kann ich Aspose.Page kostenlos nutzen?**  
A: Sie können die Bibliothek mit einem kostenlosen Testdownload von der [Aspose Kaufseite](https://purchase.aspose.com/buy) evaluieren. Für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.

**Q: Sind temporäre Lizenzen für Aspose.Page verfügbar?**  
A: Temporäre Lizenzen können von der [temporäre Lizenzseite](https://purchase.aspose.com/temporary-license/) für kurzfristige Projekte oder Evaluationsphasen bezogen werden.

**Q: Wo finde ich Community‑Support für Aspose.Page?**  
A: Nehmen Sie an der Diskussion im [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39) teil, um Fragen zu stellen und Lösungen mit anderen Entwicklern zu teilen.

**Q: Was ist die neueste Version von Aspose.Page für .NET?**  
A: Siehe die offizielle [Dokumentation](https://reference.aspose.com/page/net/) für die neuesten Versionshinweise und Download‑Links.

---

**Zuletzt aktualisiert:** 2026-08-08  
**Getestet mit:** Aspose.Page 24.11 für .NET  
**Autor:** Aspose

```csharp
// ExStart:6
// Save EPS file with changed XMP metadata

// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
// ExEnd:6
```

## Verwandte Tutorials

- [Array-Elemente ändern mit Aspose.Page für .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-array-items/)
- [Einfache Eigenschaften hinzufügen mit Aspose.Page für .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Namespace hinzufügen mit Aspose.Page für .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}