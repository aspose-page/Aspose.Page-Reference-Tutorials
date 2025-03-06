---
title: Fügen Sie mit Aspose.Page für .NET ein Bild zum XPS-Dokument hinzu
linktitle: Bild zum XPS-Dokument hinzufügen
second_title: Aspose.Page .NET-API
description: Entdecken Sie die nahtlose Integration von Bildern in XPS-Dokumente mit Aspose.Page für .NET. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für eine reibungslose Entwicklung.
weight: 11
url: /de/net/image-management/add-image-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fügen Sie mit Aspose.Page für .NET ein Bild zum XPS-Dokument hinzu

## Einführung

In der Welt der .NET-Entwicklung ist die Einbindung von Bildern in XPS-Dokumente eine häufige Anforderung. Aspose.Page für .NET vereinfacht diesen Prozess und bietet ein leistungsstarkes Toolkit zur mühelosen Bearbeitung und Verbesserung von XPS-Dokumenten. Dieses Tutorial führt Sie durch die Schritte zum Hinzufügen eines Bildes zu einem XPS-Dokument mit Aspose.Page für .NET.

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1.  Aspose.Page für .NET-Bibliothek: Laden Sie die Bibliothek herunter und installieren Sie sie von[Aspose.Page .NET-Dokumentation](https://reference.aspose.com/page/net/).

2. Entwicklungsumgebung: Richten Sie eine .NET-Entwicklungsumgebung ein, z. B. Visual Studio.

3. Beispielbild: Halten Sie eine Beispielbilddatei bereit (z. B. „QL_logo_color.tif“), die Sie dem XPS-Dokument hinzufügen möchten.

## Namespaces importieren

Beginnen Sie mit dem Importieren der erforderlichen Namespaces in Ihr .NET-Projekt. Diese Namespaces sind für die Nutzung der von Aspose.Page für .NET bereitgestellten Funktionen von entscheidender Bedeutung.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Schritt 1: Dokumentverzeichnis festlegen

Geben Sie zunächst den Pfad zu Ihrem Dokumentverzeichnis an. Dieser Schritt stellt sicher, dass Ihr Projekt weiß, wo Dateien gesucht und gespeichert werden müssen.

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
// ExEnd:1
```

## Schritt 2: XPS-Dokument erstellen

Erstellen Sie ein neues XPS-Dokument mit Aspose.Page für .NET.

```csharp
// ExStart:1
XpsDocument doc = new XpsDocument();
// ExEnd:1
```

## Schritt 3: Bild zum XPS-Dokument hinzufügen

Fügen wir nun das Bild zum XPS-Dokument hinzu. In diesem Beispiel verwenden wir ein Beispielbild mit dem Namen „QL_logo_color.tif“.

```csharp
// ExStart:1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// ExEnd:1
```

## Schritt 4: Speichern Sie das resultierende XPS-Dokument

Speichern Sie das XPS-Dokument mit dem hinzugefügten Bild.

```csharp
// ExStart:1
doc.Save(dataDir + "AddImage_outXPS.xps");
// ExEnd:1
```

Jetzt haben Sie mit Aspose.Page für .NET erfolgreich ein Bild zu einem XPS-Dokument hinzugefügt!

## Abschluss

In diesem Tutorial haben wir untersucht, wie Sie Aspose.Page für .NET nutzen können, um Bilder nahtlos in XPS-Dokumente zu integrieren. Diese Schritt-für-Schritt-Anleitung sorgt für einen reibungslosen Integrationsprozess und verbessert Ihre .NET-Entwicklungsmöglichkeiten.

## FAQs

### F1: Ist Aspose.Page für .NET mit den neuesten .NET Framework-Versionen kompatibel?

 A1: Aspose.Page für .NET ist so konzipiert, dass es mit einer Vielzahl von .NET Framework-Versionen kompatibel ist, einschließlich der neuesten Versionen. Siehe die[Dokumentation](https://reference.aspose.com/page/net/) für spezifische Details.

### F2: Kann ich Aspose.Page für .NET sowohl in Windows- als auch in Linux-Umgebungen verwenden?

A2: Ja, Aspose.Page für .NET ist plattformunabhängig und eignet sich daher sowohl für den Einsatz in Windows- als auch Linux-Umgebungen.

### F3: Gibt es Lizenzoptionen für Aspose.Page für .NET?

 A3: Ja, Sie können Lizenzoptionen erkunden und einen Kauf tätigen[Hier](https://purchase.aspose.com/buy).

### F4: Gibt es eine kostenlose Testversion für Aspose.Page für .NET?

 A4: Ja, Sie können Aspose.Page für .NET kostenlos testen, indem Sie auf zugreifen[Kostenlose Testphase](https://releases.aspose.com/).

### F5: Wo kann ich Hilfe suchen oder mit der Community für Aspose.Page für .NET in Kontakt treten?

 A5: Besuchen Sie die[Aspose.Page für .NET-Forum](https://forum.aspose.com/c/page/39) um mit der Community in Kontakt zu treten und Unterstützung zu erhalten.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
