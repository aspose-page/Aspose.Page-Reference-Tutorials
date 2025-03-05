---
title: Fügen Sie mit Aspose.Page für .NET einen vertikalen Farbverlauf zu XPS hinzu
linktitle: Fügen Sie XPS einen vertikalen Farbverlauf hinzu
second_title: Aspose.Page .NET-API
description: Erfahren Sie, wie Sie XPS-Dokumente mit vertikalen Verläufen mit Aspose.Page für .NET verbessern. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für eine nahtlose Integration.
type: docs
weight: 15
url: /de/net/gradient-fills/add-vertical-gradient-to-xps/
---
## Einführung

Willkommen bei dieser Schritt-für-Schritt-Anleitung zum Hinzufügen eines vertikalen Farbverlaufs zu einem XPS-Dokument mit Aspose.Page für .NET. Aspose.Page ist eine leistungsstarke API, die Ihnen die Arbeit mit XPS-Dateien (XML Paper Specification) in Ihren .NET-Anwendungen ermöglicht. In diesem Tutorial führen wir Sie durch den Prozess der Erstellung eines neuen XPS-Dokuments, des Hinzufügens eines vertikalen Farbverlaufs zu einem Pfad und des Speicherns des Ergebnisses.

## Voraussetzungen

Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

-  Aspose.Page for .NET-Bibliothek: Stellen Sie sicher, dass die Aspose.Page for .NET-Bibliothek in Ihrer Entwicklungsumgebung installiert ist. Sie können es herunterladen[Hier](https://releases.aspose.com/page/net/).

- Entwicklungsumgebung: Richten Sie eine .NET-Entwicklungsumgebung mit Ihrer bevorzugten IDE ein, beispielsweise Visual Studio.

Beginnen wir nun mit dem Hinzufügen eines vertikalen Farbverlaufs zu einem XPS-Dokument mithilfe von Aspose.Page für .NET.

## Namespaces importieren

Fügen Sie in Ihre .NET-Anwendung die erforderlichen Namespaces ein, um auf Aspose.Page-Klassen und -Methoden zuzugreifen.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Schritt 1: Richten Sie Ihr Dokumentenverzeichnis ein

Bevor Sie beginnen, legen Sie den Pfad zu Ihrem Dokumentverzeichnis fest, in dem Sie das resultierende XPS-Dokument speichern möchten.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Schritt 2: Erstellen Sie ein neues XPS-Dokument

Initialisieren Sie ein neues XPS-Dokument mit dem folgenden Code:

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Schritt 3: Gradientenstopps definieren

Erstellen Sie eine Liste mit Verlaufsstopps und geben Sie die Farbe und Position für jeden Stopp an. In diesem Beispiel definieren wir einen vertikalen Farbverlauf mit fünf Stopps.

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExEnd:5
```

## Schritt 4: Erstellen Sie einen Pfad mit Farbverlauf

Definieren Sie einen Pfad, indem Sie seine Geometrie angeben und einen linearen Verlaufspinsel darauf anwenden.

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Schritt 5: Speichern Sie das resultierende XPS-Dokument

Speichern Sie das geänderte XPS-Dokument in Ihrem angegebenen Verzeichnis.

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

Glückwunsch! Sie haben mit Aspose.Page für .NET erfolgreich einen vertikalen Farbverlauf zu einem XPS-Dokument hinzugefügt.

## Abschluss

In diesem Tutorial haben wir untersucht, wie Sie Aspose.Page für .NET nutzen können, um XPS-Dokumente mit vertikalen Farbverläufen zu verbessern. Aspose.Page vereinfacht komplexe Aufgaben und bietet Entwicklern eine nahtlose Möglichkeit, XPS-Dateien in ihren .NET-Anwendungen zu bearbeiten.

## FAQs

### F1: Ist Aspose.Page mit Visual Studio 2019 kompatibel?

A1: Ja, Aspose.Page ist mit Visual Studio 2019 kompatibel. Stellen Sie sicher, dass Sie die richtige Version der Bibliothek installiert haben.

### F2: Kann ich Aspose.Page für kommerzielle Projekte verwenden?

 A2: Ja, Aspose.Page kann für kommerzielle Projekte verwendet werden. Besuchen[Hier](https://purchase.aspose.com/buy) um Lizenzoptionen zu erkunden.

### F3: Gibt es eine kostenlose Testversion?

 A3: Ja, Sie können Aspose.Page kostenlos testen[Hier](https://releases.aspose.com/).

### F4: Wo finde ich die Aspose.Page-Dokumentation?

 A4: Die Dokumentation ist verfügbar[Hier](https://reference.aspose.com/page/net/).

### F5: Wie kann ich Unterstützung erhalten oder Fragen stellen?

 A5: Besuchen Sie die[Aspose.Page-Forum](https://forum.aspose.com/c/page/39) für die Unterstützung der Gemeinschaft.