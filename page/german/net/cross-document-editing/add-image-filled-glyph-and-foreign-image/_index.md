---
title: Fügen Sie mit Aspose.Page .NET bildgefüllte Glyphen und Fremdbilder hinzu
linktitle: Bildgefüllte Glyphe und Fremdbild hinzufügen
second_title: Aspose.Page .NET-API
description: Nutzen Sie mit Aspose.Page die Leistungsfähigkeit der Dokumentverarbeitung in .NET. Fügen Sie mühelos bildgefüllte Glyphen hinzu. Verbessern Sie die visuelle Darstellung und optimieren Sie Ihren Arbeitsablauf.
type: docs
weight: 11
url: /de/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
---
## Einführung

In der Welt der .NET-Entwicklung sticht Aspose.Page als leistungsstarkes Toolkit für die Bearbeitung von Dokumentverarbeitungsaufgaben hervor. Dieses Tutorial führt Sie durch den Prozess des Hinzufügens bildgefüllter Glyphen und der Einbindung fremder Bilder mit Aspose.Page für .NET. Am Ende dieses Leitfadens werden Sie ein solides Verständnis dafür haben, wie Sie Ihre Fähigkeiten zur Dokumentenverarbeitung verbessern können.

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Aspose.Page für .NET: Stellen Sie sicher, dass Sie die Aspose.Page-Bibliothek installiert haben. Sie können es herunterladen unter[Hier](https://releases.aspose.com/page/net/).

- Entwicklungsumgebung: Richten Sie eine funktionierende .NET-Entwicklungsumgebung mit Visual Studio oder einer anderen bevorzugten IDE ein.

- Dokumentenverzeichnis: Erstellen Sie ein Verzeichnis, in dem Sie Ihre Dokumente speichern. In den Codebeispielen wird dies als „Ihr Dokumentverzeichnis“ bezeichnet.

## Namespaces importieren

Beginnen Sie in Ihrer .NET-Anwendung mit dem Importieren der erforderlichen Namespaces, um auf die von Aspose.Page bereitgestellten Klassen und Methoden zuzugreifen:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Schritt 1: Erstellen Sie das erste XPS-Dokument

Beginnen Sie mit der Erstellung des ersten XPS-Dokuments mit Aspose.Page. Dieses Dokument dient als Grundlage für das Hinzufügen bildgefüllter Glyphen.

```csharp
// ExStart:1
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "Your Document Directory";

// Erstellen Sie das erste XPS-Dokument
XpsDocument doc1 = new XpsDocument();
```

## Schritt 2: Glyphen zum ersten Dokument hinzufügen

Fügen Sie dem ersten Dokument Glyphen hinzu und geben Sie dabei Schriftart, Größe, Stil und Position an.

```csharp
// Fügen Sie dem ersten Dokument Glyphen hinzu
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## Schritt 3: Füllen Sie Glyphen mit einem Bildpinsel

Füllen Sie die Glyphen mit einem Bildpinsel und verwenden Sie dabei ein Bild aus Ihrem Datenverzeichnis.

```csharp
// Füllen Sie die Glyphen mit einem Bildpinsel
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## Schritt 4: Erstellen Sie das zweite XPS-Dokument

Erstellen Sie nun das zweite XPS-Dokument, das Glyphen aus dem ersten Dokument enthält.

```csharp
// Erstellen Sie das zweite XPS-Dokument
XpsDocument doc2 = new XpsDocument();
```

## Schritt 5: Fügen Sie Glyphen mit der Schriftart aus dem ersten Dokument hinzu

Fügen Sie dem zweiten Dokument Glyphen hinzu und verwenden Sie dabei die Schriftart aus dem ersten Dokument.

```csharp
// Fügen Sie Glyphen mit der Schriftart aus dem ersten Dokument zum zweiten Dokument hinzu
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## Schritt 6: Erstellen Sie einen Bildpinsel aus der Füllung des ersten Dokuments

Erstellen Sie einen Bildpinsel aus der Füllung des ersten Dokuments und füllen Sie damit die Glyphen im zweiten Dokument.

```csharp
// Erstellen Sie einen Bildpinsel aus der Füllung des ersten Dokuments und füllen Sie Glyphen im zweiten Dokument
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## Schritt 7: Speichern Sie die Dokumente

Speichern Sie sowohl das erste als auch das zweite XPS-Dokument.

```csharp
// Speichern Sie das erste XPS-Dokument
doc1.Save(dataDir + "out1.xps");

// Speichern Sie das zweite XPS-Dokument
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Abschluss

Glückwunsch! Sie haben mit Aspose.Page für .NET erfolgreich bildgefüllte Glyphen hinzugefügt und Fremdbilder eingebunden. Dieses Tutorial bietet eine Grundlage für die Verbesserung Ihrer Dokumentverarbeitungsfähigkeiten und eröffnet neue Möglichkeiten für kreative und optisch ansprechende Dokumente.

## FAQs

### F1: Kann ich zum Füllen von Glyphen verschiedene Bildformate verwenden?

A1: Ja, Aspose.Page unterstützt verschiedene Bildformate. Stellen Sie die Kompatibilität mit dem gewählten Bildformat sicher.

### F2: Wie kann ich das Erscheinungsbild von Glyphen weiter anpassen?

A2: Entdecken Sie die Aspose.Page-Dokumentation für zusätzliche Eigenschaften und Methoden zur Feinabstimmung des Glyphen-Erscheinungsbilds.

### F3: Ist Aspose.Page für die Verarbeitung großer Dokumentensätze geeignet?

A3: Aspose.Page ist darauf ausgelegt, sowohl kleine als auch große Dokumentensätze effizient zu verarbeiten.

### F4: Kann ich unterschiedliche Stile auf einzelne Glyphen anwenden?

A4: Ja, Sie können Stile für jede Glyphe unabhängig anpassen, was ein hohes Maß an Flexibilität bietet.

### F5: Welche Vorteile bietet die Verwendung von Aspose.Page gegenüber anderen Dokumentenverarbeitungstools?

A5: Aspose.Page bietet umfassende Funktionen, hervorragende Leistung und umfangreiche Dokumentation, was es für viele Entwickler zur bevorzugten Wahl macht.