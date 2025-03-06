---
title: Fügen Sie mit Aspose.Page für .NET einen horizontalen Farbverlauf zu XPS hinzu
linktitle: Fügen Sie XPS einen horizontalen Farbverlauf hinzu
second_title: Aspose.Page .NET-API
description: Erfahren Sie, wie Sie mit Aspose.Page für .NET atemberaubende horizontale Verläufe zu Ihren XPS-Dokumenten hinzufügen. Steigern Sie mühelos die visuelle Attraktivität.
weight: 13
url: /de/net/gradient-fills/add-horizontal-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fügen Sie mit Aspose.Page für .NET einen horizontalen Farbverlauf zu XPS hinzu

## Einführung

In diesem Tutorial erfahren Sie, wie Sie XPS-Dokumente durch Hinzufügen eines horizontalen Farbverlaufs mithilfe von Aspose.Page für .NET verbessern können. Aspose.Page für .NET ist eine leistungsstarke Bibliothek, die eine nahtlose Verarbeitung von XPS-Dokumenten (XML Paper Specification) in .NET-Anwendungen ermöglicht. Durch das Hinzufügen von Farbverläufen können Sie Ihre Dokumente optisch ansprechender gestalten. Diese Anleitung führt Sie Schritt für Schritt durch den Vorgang.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1.  Aspose.Page for .NET-Bibliothek: Stellen Sie sicher, dass die Aspose.Page for .NET-Bibliothek in Ihrer Entwicklungsumgebung installiert ist. Sie können es hier herunterladen[Aspose.Page für .NET-Dokumentation](https://reference.aspose.com/page/net/).

2. Entwicklungsumgebung: Richten Sie eine geeignete Entwicklungsumgebung ein, einschließlich eines Code-Editors wie Visual Studio.

## Namespaces importieren

Beginnen Sie mit dem Importieren der erforderlichen Namespaces in Ihr Projekt. Diese Namespaces sind für die Arbeit mit Aspose.Page für .NET unerlässlich:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Lassen Sie uns nun das bereitgestellte Beispiel in mehrere Schritte unterteilen.

## Schritt 1: Legen Sie den Dokumentverzeichnispfad fest

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

## Schritt 3: Gradientenstopps initialisieren

```csharp
// ExStart:5
// Liste von XpsGradientStop initialisieren
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## Schritt 4: Erstellen Sie einen neuen Pfad

```csharp
// ExStart:6
//Erstellen Sie einen neuen Pfad, indem Sie die Geometrie in Abkürzungsform definieren
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Schritt 5: Speichern Sie das resultierende XPS-Dokument

```csharp
// ExStart:7
// Speichern Sie das resultierende XPS-Dokument
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

Jetzt haben Sie mit Aspose.Page für .NET erfolgreich einen horizontalen Farbverlauf zu Ihrem XPS-Dokument hinzugefügt.

## Abschluss

Die Verbesserung Ihrer XPS-Dokumente mit Farbverläufen verbessert nicht nur deren visuelle Attraktivität, sondern sorgt auch für ein ansprechenderes Benutzererlebnis. Aspose.Page für .NET vereinfacht diesen Prozess und ermöglicht Ihnen, mühelos professionelle Ergebnisse zu erzielen.

## FAQs

### F1: Wo finde ich die Dokumentation zu Aspose.Page für .NET?

 A1: Sie finden die Dokumentation[Hier](https://reference.aspose.com/page/net/).

### F2: Wie lade ich Aspose.Page für .NET herunter?

 A2: Sie können die Bibliothek von herunterladen[Aspose.Page für .NET-Downloadseite](https://releases.aspose.com/page/net/).

### F3: Wo kann ich Aspose.Page für .NET kaufen?

 A3: Sie können Aspose.Page für .NET bei kaufen[Kaufseite](https://purchase.aspose.com/buy).

### F4: Gibt es eine kostenlose Testversion?

 A4: Ja, Sie können eine kostenlose Testversion von erhalten[Hier](https://releases.aspose.com/).

### F5: Wie erhalte ich eine temporäre Lizenz für Aspose.Page für .NET?

 A5: Sie können eine temporäre Lizenz erhalten von[dieser Link](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
