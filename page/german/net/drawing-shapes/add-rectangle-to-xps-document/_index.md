---
title: Fügen Sie mit Aspose.Page für .NET ein Rechteck zum XPS-Dokument hinzu
linktitle: Rechteck zum XPS-Dokument hinzufügen
second_title: Aspose.Page .NET-API
description: Verbessern Sie die Dokumenterstellung mit Aspose.Page für .NET. Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie XPS-Dokumenten Rechtecke hinzufügen.
type: docs
weight: 13
url: /de/net/drawing-shapes/add-rectangle-to-xps-document/
---
## Einführung

Aspose.Page für .NET ist eine leistungsstarke Bibliothek, die eine Vielzahl von Funktionen für die Arbeit mit XPS-Dokumenten (XML Paper Specification) in .NET-Anwendungen bietet. In diesem Tutorial konzentrieren wir uns auf das Hinzufügen eines Rechtecks zu einem XPS-Dokument mithilfe von Aspose.Page für .NET. Befolgen Sie diese Schritt-für-Schritt-Anleitung, um Ihren Dokumentenerstellungsprozess zu verbessern.

## Voraussetzungen

Bevor Sie mit diesem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1.  Aspose.Page for .NET-Bibliothek: Stellen Sie sicher, dass die Aspose.Page for .NET-Bibliothek in Ihrer Entwicklungsumgebung installiert ist. Sie können es herunterladen[Hier](https://releases.aspose.com/page/net/).

2. Dokumentenverzeichnis: Richten Sie ein Verzeichnis ein, in dem Sie Ihre XPS-Dokumente speichern möchten.

## Namespaces importieren

Fügen Sie in Ihre .NET-Anwendung die erforderlichen Namespaces ein, um die Aspose.Page-Funktionen zu nutzen.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Schritt 1: Legen Sie das Dokumentverzeichnis fest

```csharp
// ExStart:3
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Schritt 2: Erstellen Sie ein neues XPS-Dokument

```csharp
// ExStart:4
// Erstellen Sie ein neues XPS-Dokument
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Schritt 3: Fügen Sie ein Rechteck hinzu

```csharp
// ExStart:5
// CMYK (blau) einfarbiges, gestricheltes Rechteck unten links
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

## Schritt 4: Speichern Sie das Dokument

```csharp
// ExStart:6
// Speichern Sie das resultierende XPS-Dokument
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Glückwunsch! Sie haben mit Aspose.Page für .NET erfolgreich ein Rechteck zu einem XPS-Dokument hinzugefügt.

## Abschluss

Aspose.Page für .NET vereinfacht die Bearbeitung von Dokumenten und ermöglicht Entwicklern das mühelose Erstellen und Ändern von XPS-Dokumenten. Diese Schritt-für-Schritt-Anleitung zeigt, wie Sie Ihrem XPS-Dokument ein Rechteck hinzufügen und bietet so eine solide Grundlage für weitere Untersuchungen.

## FAQs

### F1: Ist Aspose.Page mit allen .NET-Anwendungen kompatibel?

A1: Ja, Aspose.Page ist so konzipiert, dass es nahtlos mit allen .NET-Anwendungen zusammenarbeitet.

### F2: Wo finde ich die Dokumentation für Aspose.Page für .NET?

 A2: Die Dokumentation ist verfügbar[Hier](https://reference.aspose.com/page/net/).

### F3: Kann ich Aspose.Page für .NET vor dem Kauf kostenlos testen?

 A3: Ja, Sie können eine kostenlose Testversion erhalten[Hier](https://releases.aspose.com/).

### F4: Wie kann ich eine temporäre Lizenz für Aspose.Page für .NET erhalten?

 A4: Besuchen[dieser Link](https://purchase.aspose.com/temporary-license/) eine befristete Lizenz zu erhalten.

### F5: Wo kann ich Community-Unterstützung suchen oder Fragen zu Aspose.Page für .NET stellen?

 A5: Besuchen Sie die[Aspose.Page-Forum](https://forum.aspose.com/c/page/39) für die Unterstützung der Gemeinschaft.