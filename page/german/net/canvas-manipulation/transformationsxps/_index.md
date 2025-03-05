---
title: Transformationen XPS mit Aspose.Page für .NET
linktitle: Transformationen XPS
second_title: Aspose.Page .NET-API
description: Transformieren Sie XPS-Dokumente mühelos mit Aspose.Page für .NET. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für nahtlose Transformationen.
type: docs
weight: 13
url: /de/net/canvas-manipulation/transformationsxps/
---
## Einführung

Willkommen in der Welt von Aspose.Page für .NET, einer leistungsstarken Bibliothek, mit der Sie mühelos verschiedene Transformationen an XPS-Dokumenten durchführen können. In diesem Tutorial befassen wir uns mit dem Prozess der Transformation von XPS-Dokumenten mit Aspose.Page für .NET. Unabhängig davon, ob Sie ein erfahrener Entwickler sind oder gerade erst anfangen, führt Sie dieser Leitfaden durch jeden Schritt und stellt sicher, dass Sie die Konzepte leicht verstehen.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Folgendes vorhanden ist:

-  Aspose.Page für .NET-Bibliothek: Laden Sie die Bibliothek herunter und installieren Sie sie von[Aspose.Page für .NET-Dokumentation](https://reference.aspose.com/page/net/).

- Entwicklungsumgebung: Richten Sie eine kompatible Entwicklungsumgebung ein, z. B. Visual Studio oder ein anderes .NET-Entwicklungstool.

- Ihr Dokumentenverzeichnis: Ersetzen Sie den Platzhalter im Code durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis.

Kommen wir nun zum Tutorial!

## Namespaces importieren

Stellen Sie zunächst sicher, dass Sie die erforderlichen Namespaces importieren, um die Funktionalitäten von Aspose.Page für .NET in Ihrem Code verfügbar zu machen. Fügen Sie am Anfang Ihres Skripts die folgenden Namespaces hinzu:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Schritt 1: Erstellen Sie ein neues XPS-Dokument

```csharp
// ExStart:1
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "Your Document Directory";

// Erstellen Sie ein neues XPS-Dokument
XpsDocument doc = new XpsDocument();
```

## Schritt 2: Erstellen Sie eine Hauptleinwand

```csharp
// Erstellen Sie eine Hauptleinwand, die allen Seitenelementen gemeinsam ist
XpsCanvas canvas1 = doc.AddCanvas();

// Nehmen Sie in der Hauptleinwand Versätze nach links und oben vor
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Schritt 3: Erstellen Sie eine rechteckige Pfadgeometrie

```csharp
// Erstellen Sie eine rechteckige Pfadgeometrie
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

## Schritt 4: Fügen Sie eine Füllung für Rechtecke hinzu

```csharp
// Erstellen Sie eine Füllung für Rechtecke
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Schritt 5: Fügen Sie eine neue Leinwand ohne Transformationen hinzu

```csharp
// Fügen Sie eine neue Leinwand hinzu, ohne dass Änderungen zur Hauptleinwand erforderlich sind
XpsCanvas canvas2 = canvas1.AddCanvas();

// Erstellen Sie ein Rechteck auf dieser Leinwand und füllen Sie es
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Schritt 6: Fügen Sie eine neue Leinwand mit Translate Transformation hinzu

```csharp
// Fügen Sie eine neue Leinwand mit Übersetzungstransformation zur Hauptleinwand hinzu
XpsCanvas canvas3 = canvas1.AddCanvas();

// Verschieben Sie diese Leinwand, um ein neues Rechteck unter dem vorherigen Rechteck zu positionieren
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Übersetzen Sie diese Leinwand auf die rechte Seite der Seite
canvas3.RenderTransform.Translate(500, 0);

// Erstellen Sie ein Rechteck auf dieser Leinwand und füllen Sie es
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

## Schritt 7: Fügen Sie eine neue Leinwand mit doppelter Skalierungstransformation hinzu

```csharp
//Fügen Sie der Hauptleinwand eine neue Leinwand mit doppelter Skalierungstransformation hinzu
XpsCanvas canvas4 = canvas1.AddCanvas();

// Verschieben Sie diese Leinwand, um ein neues Rechteck unter dem vorherigen Rechteck zu positionieren
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Skalieren Sie diese Leinwand
canvas4.RenderTransform.Scale(2, 2);

// Erstellen Sie ein Rechteck auf dieser Leinwand und füllen Sie es
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

## Schritt 8: Fügen Sie eine neue Leinwand mit Drehung um eine Punkttransformation hinzu

```csharp
// Fügen Sie der Hauptleinwand eine neue Leinwand mit Drehung um eine Punkttransformation hinzu
XpsCanvas canvas5 = canvas1.AddCanvas();

// Verschieben Sie diese Leinwand, um ein neues Rechteck unter dem vorherigen Rechteck zu positionieren
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Drehen Sie diese Leinwand um einen Punkt um 45 Grad
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Erstellen Sie ein Rechteck auf dieser Leinwand und füllen Sie es
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

## Schritt 9: Speichern Sie das resultierende XPS-Dokument

```csharp
// Speichern Sie das resultierende XPS-Dokument
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

## Abschluss

Glückwunsch! Sie haben ein XPS-Dokument erfolgreich mit Aspose.Page für .NET transformiert. In diesem Leitfaden wurden wesentliche Schritte behandelt, vom Einrichten der Voraussetzungen bis zur Durchführung verschiedener Transformationen. Experimentieren Sie mit diesen Techniken und nutzen Sie das volle Potenzial von Aspose.Page für .NET in Ihren Projekten.

## FAQs

### F1: Ist Aspose.Page für .NET mit allen .NET-Entwicklungsumgebungen kompatibel?

A1: Ja, Aspose.Page für .NET ist so konzipiert, dass es nahtlos mit verschiedenen .NET-Entwicklungsumgebungen, einschließlich Visual Studio, zusammenarbeitet.

### F2: Wo finde ich zusätzliche Beispiele und Dokumentation für Aspose.Page für .NET?

 A2: Besuchen Sie die[Aspose.Page für .NET-Dokumentation](https://reference.aspose.com/page/net/) für umfassende Dokumentation und Beispiele.

### F3: Kann ich Aspose.Page für .NET vor dem Kauf testen?

 A3: Ja, Sie können eine kostenlose Testversion ausprobieren, indem Sie hier klicken[Kostenlose Testversion von Aspose.Page](https://releases.aspose.com/).

### F4: Wie kann ich eine temporäre Lizenz für Aspose.Page für .NET erhalten?

 A4: Holen Sie sich eine temporäre Lizenz, indem Sie vorbeischauen[Temporäre Lizenz](https://purchase.aspose.com/temporary-license/).

### F5: Wo kann ich Aspose.Page für .NET kaufen?

 A5: Kaufen Sie Aspose.Page für .NET unter[Aspose.Seite kaufen](https://purchase.aspose.com/buy).