---
title: Fügen Sie mit Aspose.Page für .NET ein gekacheltes Bild zu einem XPS-Dokument hinzu
linktitle: Gekacheltes Bild zum XPS-Dokument hinzufügen
second_title: Aspose.Page .NET-API
description: Entdecken Sie, wie Sie mit Aspose.Page für .NET mühelos gekachelte Bilder zu XPS-Dokumenten hinzufügen können. Verbessern Sie die visuelle Attraktivität und erstellen Sie beeindruckende Dokumente.
weight: 12
url: /de/net/image-management/add-tiled-image-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fügen Sie mit Aspose.Page für .NET ein gekacheltes Bild zu einem XPS-Dokument hinzu

## Einführung

Möchten Sie Ihre XPS-Dokumente durch das Hinzufügen optisch ansprechender gekachelter Bilder aufwerten? Mit Aspose.Page für .NET können Entwickler dies nahtlos erreichen. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch den Prozess des Hinzufügens eines gekachelten Bildes zu einem XPS-Dokument mit Aspose.Page für .NET.

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Aspose.Page für .NET: Stellen Sie sicher, dass Sie die Aspose.Page-Bibliothek installiert haben. Hier finden Sie eine ausführliche Dokumentation und können die Bibliothek herunterladen[Hier](https://reference.aspose.com/page/net/).
- Entwicklungsumgebung: Richten Sie Ihre bevorzugte .NET-Entwicklungsumgebung ein, z. B. Visual Studio.

## Namespaces importieren

Importieren Sie zunächst die erforderlichen Namespaces in Ihr Projekt. Dadurch wird sichergestellt, dass Sie Zugriff auf die Klassen und Methoden haben, die für die Arbeit mit Aspose.Page erforderlich sind. Fügen Sie am Anfang Ihres Codes die folgenden Namespaces hinzu:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Lassen Sie uns das Beispiel nun in mehrere Schritte unterteilen.

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "Your Document Directory";
```

Stellen Sie sicher, dass Sie „Ihr Dokumentverzeichnis“ durch den tatsächlichen Pfad ersetzen, in dem Sie Ihr XPS-Dokument speichern möchten.

## Schritt 2: Erstellen Sie ein neues XPS-Dokument

```csharp
// Erstellen Sie ein neues XPS-Dokument
XpsDocument doc = new XpsDocument();
```

 Instanziieren Sie ein neues XPS-Dokument mit`XpsDocument` Klasse.

## Schritt 3: Fügen Sie ein gekacheltes Bild hinzu

```csharp
// Kachelbild
// Mit ImageBrush gefülltes Rechteck rechts oben unten
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

Dieser Schritt fügt dem XPS-Dokument ein gekacheltes Bild hinzu. Passen Sie die Koordinaten und den Bilddateipfad entsprechend Ihren Anforderungen an.

## Schritt 4: Speichern Sie das resultierende XPS-Dokument

```csharp
// Speichern Sie das resultierende XPS-Dokument
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

Speichern Sie das geänderte XPS-Dokument im angegebenen Verzeichnis.

## Abschluss

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Page für .NET ein gekacheltes Bild zu einem XPS-Dokument hinzufügen. Mit dieser einfachen, aber leistungsstarken Funktion können Sie die visuelle Attraktivität Ihrer Dokumente mühelos verbessern.

## FAQs

### F1: Ist Aspose.Page mit allen .NET-Entwicklungsumgebungen kompatibel?

A1: Ja, Aspose.Page ist so konzipiert, dass es nahtlos mit verschiedenen .NET-Entwicklungsumgebungen, einschließlich Visual Studio, zusammenarbeitet.

### F2: Kann ich die Deckkraft des gekachelten Bildes anpassen?

A2: Natürlich können Sie, wie im Beispiel gezeigt, die Deckkraft des gefüllten Rechtecks mithilfe von festlegen`Opacity` Eigentum.

### F3: Sind in Aspose.Page für .NET andere Kachelmodi verfügbar?

 A3: Ja, Aspose.Page bietet verschiedene Kachelmodi. In diesem Tutorial haben wir verwendet`XpsTileMode.Tile`, aber Sie können andere Optionen in der Dokumentation erkunden.

### F4: Wie gehe ich mit temporären Lizenzen für Aspose.Page um?

 A4: Siehe[temporäre Lizenz](https://purchase.aspose.com/temporary-license/) Auf der Aspose-Website finden Sie Anleitungen zum Erhalten und Implementieren temporärer Lizenzen.

### F5: Wo kann ich Hilfe suchen oder mich mit der Aspose.Page-Community verbinden?

 A5: Besuchen Sie die[Aspose.Page-Forum](https://forum.aspose.com/c/page/39) um mit der Community in Kontakt zu treten, Fragen zu stellen und Lösungen zu finden.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
