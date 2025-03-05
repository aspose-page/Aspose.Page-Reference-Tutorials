---
title: Konvertieren Sie XPS in PDF mit Aspose.Page für .NET
linktitle: Konvertieren Sie XPS in PDF
second_title: Aspose.Page .NET-API
description: Konvertieren Sie mit Aspose.Page mühelos XPS in PDF in .NET. Laden Sie die Bibliothek herunter, erkunden Sie die Dokumentation und erhalten Sie eine kostenlose Testversion.
type: docs
weight: 11
url: /de/net/document-conversion/convert-xps-to-pdf/
---
## Einführung

In diesem Tutorial befassen wir uns mit dem Prozess der Konvertierung von XPS-Dokumenten (XML Paper Specification) in PDF (Portable Document Format) mithilfe der leistungsstarken Bibliothek Aspose.Page für .NET. Aspose.Page für .NET bietet eine Reihe robuster Funktionen für die Arbeit mit XPS-Dateien, sodass Entwickler diese mit verschiedenen Anpassungsoptionen nahtlos in das PDF-Format konvertieren können.

## Voraussetzungen

Bevor wir uns auf den Weg zur Umstellung machen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Aspose.Page for .NET-Bibliothek: Stellen Sie sicher, dass die Aspose.Page for .NET-Bibliothek in Ihrer Entwicklungsumgebung installiert ist. Sie können es hier herunterladen[Aspose.Page-Dokumentation](https://reference.aspose.com/page/net/).

- Entwicklungsumgebung: Richten Sie eine .NET-Entwicklungsumgebung mit Visual Studio oder einer anderen kompatiblen IDE ein.

- XPS-Dokument: Bereiten Sie das XPS-Dokument vor, das Sie in PDF konvertieren möchten. Dies könnte Ihre Beispiel-XPS-Datei sein, die in einem bestimmten Verzeichnis gespeichert ist.

## Namespaces importieren

Bevor wir uns mit dem Code befassen, importieren wir die erforderlichen Namespaces, um die Funktionalitäten von Aspose.Page für .NET in unserem Code zugänglich zu machen:

```csharp
using Aspose.Page.XPS;
```

## Schritt 1: Dokumentverzeichnis initialisieren

```csharp
string dataDir = "Your Document Directory";
```

Ersetzen Sie „Ihr Dokumentverzeichnis“ durch den Pfad zu dem Verzeichnis, das Ihr XPS-Dokument enthält.

## Schritt 2: Initialisieren Sie PDF- und XPS-Streams

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

Öffnen Sie Streams sowohl für die Ausgabe-PDF-Datei als auch für die Eingabe-XPS-Datei. Stellen Sie sicher, dass Sie die entsprechenden Dateipfade festgelegt haben.

## Schritt 3: XPS-Dokument laden

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

Laden Sie das XPS-Dokument mit der Aspose.Page for .NET-Bibliothek.

## Schritt 4: PDF-Speicheroptionen initialisieren

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

Richten Sie die PDF-Speicheroptionen ein, einschließlich Parameter wie JPEG-Qualitätsstufe, Bildkomprimierung, Textkomprimierung und bestimmte einzuschließende Seitenzahlen.

## Schritt 5: Erstellen Sie ein PDF-Rendering-Gerät

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

Erstellen Sie mithilfe der Aspose.Page for .NET-Bibliothek ein Rendering-Gerät für das PDF-Format.

## Schritt 6: Dokument als PDF speichern

```csharp
document.Save(device, options);
```

Speichern Sie das XPS-Dokument mit dem angegebenen Rendering-Gerät und den angegebenen Optionen als PDF.

## Abschluss

Glückwunsch! Sie haben ein XPS-Dokument mit Aspose.Page für .NET erfolgreich in PDF konvertiert. Diese vielseitige Bibliothek bietet Entwicklern ein leistungsstarkes Toolset für den mühelosen Umgang mit verschiedenen Dokumentformaten.

## FAQs

### F1: Kann ich mit Aspose.Page für .NET mehrere XPS-Dateien in ein einziges PDF konvertieren?

A1: Ja, Sie können mehrere XPS-Dateien durchlaufen und dieselben Schritte ausführen, um sie in einer einzigen PDF-Datei zusammenzuführen.

### F2: Werden andere Ausgabeformate von Aspose.Page für .NET unterstützt?

A2: Ja, Aspose.Page für .NET unterstützt verschiedene Ausgabeformate, darunter TIFF, JPEG, PNG und mehr.

### F3: Wie kann ich das Erscheinungsbild des konvertierten PDF-Dokuments anpassen?

A3: Sie können die Objektparameter der Optionen wie Bildkomprimierung und Textkomprimierung anpassen, um das gewünschte Erscheinungsbild zu erzielen.

### F4: Gibt es eine Testversion für Aspose.Page für .NET?

 A4: Ja, Sie können die Funktionen von Aspose.Page für .NET erkunden, indem Sie eine kostenlose Testversion von erhalten[Hier](https://releases.aspose.com/).

### F5: Wo erhalte ich Community-Unterstützung für Aspose.Page für .NET?

 A5: Besuchen Sie die[Aspose.Page-Forum](https://forum.aspose.com/c/page/39) für Community-Diskussionen und Unterstützung.