---
title: Fügen Sie mit Aspose.Page für .NET eine Kreisellipse zum XPS-Dokument hinzu
linktitle: Fügen Sie dem XPS-Dokument eine Kreisellipse hinzu
second_title: Aspose.Page .NET-API
description: Verbessern Sie XPS-Dokumente mit lebendigen radialen Verläufen mit Aspose.Page für .NET. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für atemberaubende visuelle Effekte.
weight: 11
url: /de/net/drawing-shapes/add-circle-ellipse-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fügen Sie mit Aspose.Page für .NET eine Kreisellipse zum XPS-Dokument hinzu

## Einführung

Die Erstellung optisch ansprechender XPS-Dokumente ist eine häufige Anforderung in verschiedenen Anwendungen. Aspose.Page für .NET bietet leistungsstarke Funktionen zur effizienten Bearbeitung von XPS-Dokumenten. In diesem Tutorial konzentrieren wir uns auf das Hinzufügen einer Kreisellipse zu einem XPS-Dokument mithilfe von Aspose.Page für .NET. Führen Sie die folgenden Schritte aus, um Ihre XPS-Dokumente mit lebendigen radialen Farbverläufen zu verbessern.

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Installierte Aspose.Page für .NET-Bibliothek. Sie können es herunterladen unter[Hier](https://releases.aspose.com/page/net/).
- Eine Entwicklungsumgebung, vorzugsweise Visual Studio oder ein anderes .NET-Entwicklungstool.
- Grundkenntnisse der C#-Programmierung.

## Namespaces importieren

Fügen Sie zunächst die erforderlichen Namespaces in Ihren C#-Code ein:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Lassen Sie uns das Beispiel nun in mehrere Schritte unterteilen:

## Schritt 1: Richten Sie das Dokument ein

```csharp
// ExStart:1
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "Your Document Directory";
// Erstellen Sie ein neues XPS-Dokument
XpsDocument doc = new XpsDocument();
```

Hier initialisieren wir ein neues XPS-Dokument mit Aspose.Page für .NET.

## Schritt 2: Definieren Sie die radiale Gradientenellipse

```csharp
// Mit radialem Farbverlauf gestrichelte Ellipse unten links
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 0, 255), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), .25f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 255, 0), .5f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 255, 0), .75f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), 1f));

XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250"));
```

In diesem Schritt wird eine radiale Verlaufsellipse mit verschiedenen Farbstopps definiert.

## Schritt 3: Radialen Verlaufspinsel festlegen

```csharp
path.Stroke = doc.CreateRadialGradientBrush(new PointF(575f, 125f), new PointF(575f, 100f), 75f, 50f);
((XpsGradientBrush)path.Stroke).SpreadMethod = XpsSpreadMethod.Reflect;
((XpsGradientBrush)path.Stroke).GradientStops.AddRange(stops);
stops.Clear();
```

Hier stellen wir den Strich der Ellipse auf einen radialen Verlaufspinsel ein und versehen ihn mit den erforderlichen Parametern.

## Schritt 4: Passen Sie die Strichstärke an

```csharp
path.StrokeThickness = 12f;
```

Bei diesem Schritt wird die Stärke des Strichs angepasst, um eine bessere Visualisierung zu ermöglichen.

## Schritt 5: Speichern Sie das resultierende XPS-Dokument

```csharp
// Speichern Sie das resultierende XPS-Dokument
doc.Save(dataDir + "AddEllipse_outXPS.xps");
// ExEnd:1
```

Speichern Sie abschließend das geänderte XPS-Dokument am gewünschten Ort.

## Abschluss

Glückwunsch! Sie haben mit Aspose.Page für .NET erfolgreich eine Kreisellipse mit radialen Farbverläufen zu Ihrem XPS-Dokument hinzugefügt. Experimentieren Sie mit verschiedenen Parametern und Farben, um die gewünschten visuellen Effekte in Ihren Dokumenten zu erzielen.

## FAQs

### F1: Kann ich Aspose.Page für .NET mit anderen Dokumentformaten verwenden?

A1: Aspose.Page für .NET befasst sich speziell mit der Manipulation von XPS-Dokumenten. Erwägen Sie für andere Formate die Verwendung verwandter Aspose-Bibliotheken.

### F2: Ist zu Testzwecken eine temporäre Lizenz verfügbar?

 A2: Ja, Sie können eine temporäre Lizenz zum Testen erhalten, indem Sie hier vorbeischauen[dieser Link](https://purchase.aspose.com/temporary-license/).

### F3: Wo finde ich zusätzliche Hilfe und Diskussionen?

 A3: Besuchen Sie die[Aspose.Page-Forum](https://forum.aspose.com/c/page/39) für Community-Unterstützung und Diskussionen.

### F4: Gibt es Musterdokumente als Referenz?

 A4: Entdecken Sie die[Dokumentation](https://reference.aspose.com/page/net/) Ausführliche Beispiele und Richtlinien finden Sie hier.

### F5: Kann ich Aspose.Page für .NET kaufen?

 A5: Ja, Sie können die Bibliothek kaufen[Hier](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
