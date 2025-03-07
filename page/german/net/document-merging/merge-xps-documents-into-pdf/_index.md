---
title: Führen Sie XPS-Dokumente mit Aspose.Page für .NET in PDF zusammen
linktitle: XPS-Dokumente in PDF zusammenführen
second_title: Aspose.Page .NET-API
description: Führen Sie XPS-Dokumente mit Aspose.Page für .NET mühelos in hochwertige PDFs zusammen. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für eine reibungslose Dokumentenkonvertierung.
weight: 11
url: /de/net/document-merging/merge-xps-documents-into-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Führen Sie XPS-Dokumente mit Aspose.Page für .NET in PDF zusammen

## Einführung

In der sich ständig weiterentwickelnden Landschaft der Dokumentenverarbeitung erweist sich Aspose.Page für .NET als leistungsstarkes Tool zum nahtlosen Zusammenführen von XPS-Dokumenten in das PDF-Format. Dieses Tutorial führt Sie durch den Prozess und schlüsselt jeden Schritt auf, um eine reibungslose und effektive Ausführung zu gewährleisten.

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Aspose.Page für .NET: Stellen Sie sicher, dass die Aspose.Page-Bibliothek installiert ist. Sie können es herunterladen unter[Hier](https://releases.aspose.com/page/net/).

- Dokumentdateien: Halten Sie das XPS-Dokument bereit (`input.xps`) in Ihrem angegebenen Verzeichnis bereit.

## Namespaces importieren

Fügen Sie in Ihr .NET-Projekt die erforderlichen Namespaces für die Arbeit mit Aspose.Page ein:

```csharp
using Aspose.Page.XPS;
```

Dieser Schritt stellt sicher, dass Sie Zugriff auf die für die Dokumentkonvertierung erforderlichen Klassen und Methoden haben.

## Schritt 1: Streams initialisieren

```csharp
// ExStart:3
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "Your Document Directory";
// PDF-Ausgabestream initialisieren
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialisieren Sie den XPS-Eingabestream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

Dieser Schritt umfasst das Einrichten der Eingabe- und Ausgabestreams für die XPS- und PDF-Dateien. Stellen Sie sicher, dass die richtigen Pfade und Dateinamen verwendet werden.

## Schritt 2: XPS-Dokument laden

```csharp
// ExStart:4
// Laden Sie das XPS-Dokument aus dem Stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// oder laden Sie das XPS-Dokument direkt aus der Datei. Dann ist kein xpsStream erforderlich.
//XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

 Hier laden wir das XPS-Dokument in das`XpsDocument` Objekt und bereitet es für die weitere Bearbeitung vor.

## Schritt 3: Speicheroptionen initialisieren

```csharp
// ExStart:5
// Initialisieren Sie das Optionsobjekt mit den erforderlichen Parametern.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
// ExEnd:5
```

 Passen Sie die an`PdfSaveOptions` Objekt basierend auf Ihren Präferenzen, indem Sie Parameter wie Bildkomprimierung, Textkomprimierung und Seitenzahlen angeben.

## Schritt 4: Erstellen Sie ein Rendering-Gerät

```csharp
// ExStart:6
// Erstellen Sie ein Rendering-Gerät für das PDF-Format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

 Der`PdfDevice` ist das Tool, das für die Umwandlung des XPS-Dokuments in das PDF-Format verantwortlich ist.

## Schritt 5: Speichern Sie das Dokument

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

Speichern Sie abschließend das Dokument mit dem Rendering-Gerät und den angegebenen Optionen.

## Abschluss

Glückwunsch! Sie haben XPS-Dokumente mit Aspose.Page für .NET erfolgreich in PDF zusammengeführt. Dieser nahtlose Prozess stellt die Beibehaltung der Dokumentqualität und -formatierung sicher.

## FAQs

### F1: Kann ich mehrere XPS-Dateien in einer einzigen PDF-Datei zusammenführen?

 A1: Ja, das können Sie. Passen Sie einfach die an`PageNumbers` Parameter in der`PdfSaveOptions` um die gewünschten Seiten aus verschiedenen XPS-Dateien einzubinden.

### F2: Ist eine temporäre Lizenz für Aspose.Page für .NET verfügbar?

 A2: Ja, Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/) zu Testzwecken.

### F3: Gibt es Einschränkungen hinsichtlich der Dateigröße, wenn Aspose.Page für die Dokumentkonvertierung verwendet wird?

A3: Aspose.Page für .NET legt keine strengen Beschränkungen der Dateigröße fest, aber eine optimale Leistung wird mit angemessenen Dateigrößen erreicht.

### F4: Kann ich das Ausgabe-PDF weiter anpassen, z. B. durch Hinzufügen von Wasserzeichen oder Anmerkungen?

A4: Ja, Aspose.Page für .NET bietet umfangreiche Funktionen zur PDF-Bearbeitung. Weitere Informationen zu erweiterten Anpassungsoptionen finden Sie in der Dokumentation.

### F5: Unterstützt Aspose.Page für .NET die plattformübergreifende Entwicklung?

A5: Ja, Aspose.Page für .NET ist so konzipiert, dass es nahtlos auf verschiedenen Plattformen funktioniert.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
