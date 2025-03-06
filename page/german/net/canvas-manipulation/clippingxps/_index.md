---
title: Beschneiden von XPS mit Aspose.Page für .NET
linktitle: XPS beschneiden
second_title: Aspose.Page .NET-API
description: Entdecken Sie die Leistungsfähigkeit von Aspose.Page für .NET in dieser Schritt-für-Schritt-Anleitung zum Ausschneiden von XPS-Dokumenten. Erstellen, bearbeiten und speichern Sie mühelos XPS-Dateien.
weight: 11
url: /de/net/canvas-manipulation/clippingxps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Beschneiden von XPS mit Aspose.Page für .NET

## Einführung

Willkommen zu diesem umfassenden Tutorial zum Ausschneiden von XPS mit Aspose.Page für .NET! In diesem Leitfaden führen wir Sie durch den Prozess der Erstellung, Bearbeitung und Speicherung von XPS-Dokumenten mit Aspose.Page für .NET. XPS oder XML Paper Specification ist ein standardisiertes und offenes Dokumentformat, und Aspose.Page für .NET bietet leistungsstarke Tools für die Arbeit mit XPS-Dokumenten in Ihren .NET-Anwendungen.

## Voraussetzungen

Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Visual Studio ist auf Ihrem Computer installiert.
-  Aspose.Page für .NET-Bibliothek zu Ihrem Projekt hinzugefügt. Sie können es herunterladen[Hier](https://releases.aspose.com/page/net/).
- Grundkenntnisse der Programmiersprache C#.

## Namespaces importieren

Um Aspose.Page für .NET-Funktionen nutzen zu können, müssen Sie die erforderlichen Namespaces in Ihr Projekt importieren. Folge diesen Schritten:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Lassen Sie uns nun den von Ihnen bereitgestellten Beispielcode in mehrere Schritte aufteilen.

## Schritt 1: Legen Sie den Dokumentverzeichnispfad fest.

```csharp
string dataDir = "Your Document Directory";
```

Stellen Sie sicher, dass Sie „Ihr Dokumentverzeichnis“ durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis ersetzen.

## Schritt 2: Erstellen Sie ein neues XPS-Dokument.

```csharp
XpsDocument doc = new XpsDocument();
```

Dadurch wird ein neues XPS-Dokument erstellt, mit dem Sie arbeiten werden.

## Schritt 3: Erstellen Sie die Hauptleinwand.

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

In diesem Schritt wird die Hauptleinwand erstellt, die allen Seitenelementen gemeinsam ist.

## Schritt 4: Legen Sie den linken und oberen Versatz im Hauptbereich fest.

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

Passen Sie den linken und oberen Versatz entsprechend Ihren Anforderungen an.

## Schritt 5: Erstellen Sie eine rechteckige Pfadgeometrie.

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

Dadurch wird eine Pfadgeometrie für ein Rechteck erstellt.

## Schritt 6: Erstellen Sie eine Füllung für Rechtecke.

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

Definieren Sie die Füllfarbe für die Rechtecke.

## Schritt 7: Fügen Sie eine weitere Leinwand mit Clip zur Hauptleinwand hinzu.

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

Dieser Schritt fügt der Hauptleinwand eine weitere Leinwand hinzu.

## Schritt 8: Erstellen Sie eine Kreisgeometrie für den Clip.

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

Dadurch wird eine kreisförmige Clip-Geometrie erstellt und auf die zweite Leinwand angewendet.

## Schritt 9: Erstellen Sie ein Rechteck auf der zweiten Leinwand und füllen Sie es.

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Dieser Schritt erstellt ein Rechteck in der zweiten Leinwand und füllt es.

## Schritt 10: Fügen Sie die zweite Leinwand mit einem gestrichelten Rechteck zur Hauptleinwand hinzu.

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

Dadurch wird der Hauptleinwand eine weitere Leinwand hinzugefügt.

## Schritt 11: Erstellen Sie ein Rechteck auf der dritten Leinwand und streichen Sie darüber.

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

Dadurch wird ein Rechteck auf der dritten Leinwand erstellt und ein Strich darauf angewendet.

## Schritt 12: Speichern Sie das resultierende XPS-Dokument.

```csharp
doc.Save(dataDir + "output2.xps");
```

Dadurch wird das XPS-Dokument im angegebenen Verzeichnis gespeichert.

## Abschluss

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie XPS mit Aspose.Page für .NET beschneiden. Dieser Leitfaden bietet eine detaillierte Anleitung zu den einzelnen Prozessschritten.

## FAQs

### F1: Kann ich Aspose.Page für .NET mit anderen Dokumentformaten verwenden?

A1: Aspose.Page für .NET konzentriert sich hauptsächlich auf XPS-Dokumente, Aspose bietet jedoch auch andere Bibliotheken für verschiedene Dokumentformate.

### F2: Ist Aspose.Page für .NET für Anfänger geeignet?

A2: Ja, Aspose.Page für .NET ist benutzerfreundlich gestaltet und Anfänger können seine Funktionalitäten mit der richtigen Dokumentation schnell verstehen.

### F3: Wo finde ich weitere Beispiele und Ressourcen?

 A3: Besuchen Sie die[Dokumentation](https://reference.aspose.com/page/net/) Und[Aspose.Page-Forum](https://forum.aspose.com/c/page/39) für umfangreiche Ressourcen und Beispiele.

### F4: Wie kann ich eine temporäre Lizenz für Aspose.Page für .NET erhalten?

 A4: Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).

### F5: Gibt es eine kostenlose Testversion für Aspose.Page für .NET?

 A5: Ja, Sie können die kostenlose Testversion erkunden[Hier](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
