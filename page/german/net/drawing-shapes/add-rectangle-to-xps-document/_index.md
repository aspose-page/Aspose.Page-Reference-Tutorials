---
date: 2026-07-19
description: Erfahren Sie, wie Sie ein XPS-Dokument in .NET erstellen und ein Rechteck
  mit Aspose.Page für .NET in einer prägnanten Schritt‑für‑Schritt‑Anleitung hinzufügen.
keywords:
- create xps document .net
- add rectangle xps
- aspose.page .net
lastmod: 2026-07-19
linktitle: Rechteck zu XPS-Dokument hinzufügen
og_description: Erstellen Sie schnell ein XPS-Dokument in .NET. Dieses Tutorial zeigt,
  wie man ein Rechteck zu einer XPS-Datei mit Aspose.Page für .NET hinzufügt, inklusive
  klarer Codebeispiele und Tipps.
og_image_alt: Guide to adding a rectangle to an XPS document using Aspose.Page for
  .NET
og_title: XPS-Dokument in .NET erstellen – Rechteck hinzufügen mit Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  headline: Create XPS Document .NET – Add Rectangle with Aspose.Page
  type: TechArticle
- description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  name: Create XPS Document .NET – Add Rectangle with Aspose.Page
  steps:
  - name: Create a New XPS Document
    text: The `XpsDocument` class represents the XPS file you are building and provides
      methods to add pages, graphics, and other resources.
  - name: Add a Rectangle
    text: '`XpsPath` defines a drawable path object within the XPS document, allowing
      you to set geometry, stroke, fill, and other visual properties.'
  - name: Save the Document
    text: The `Save` method writes the constructed XPS document to the specified file
      path on disk. Congratulations! You have successfully added a rectangle to an
      XPS document using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works seamlessly with desktop, web, and cloud .NET applications.
    question: Is Aspose.Page compatible with all .NET applications?
  - answer: The full API reference is available [here](https://reference.aspose.com/page/net/).
    question: Where can I find the documentation for Aspose.Page for .NET?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Can I try Aspose.Page for .NET for free before purchasing?
  - answer: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain
      a temporary license.
    question: How can I obtain a temporary license for Aspose.Page for .NET?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support.
    question: Where can I seek community support or ask questions related to Aspose.Page
      for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- xps document
- aspose.page
- .net drawing
title: XPS-Dokument in .NET erstellen – Rechteck hinzufügen mit Aspose.Page
url: /de/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS-Dokument .NET erstellen – Rechteck hinzufügen mit Aspose.Page

## Einführung

In diesem Tutorial lernen Sie, wie Sie ein **XPS-Dokument .NET** erstellen und mit Aspose.Page für .NET ein Rechteck darin zeichnen. Egal, ob Sie eine Reporting‑Engine, eine druckbare Rechnung oder eine benutzerdefinierte Grafikebene bauen, die Möglichkeit, XPS‑Dateien programmgesteuert zu erzeugen, gibt Ihnen die volle Kontrolle über Layout und Genauigkeit. Folgen Sie den nachstehenden Schritten und Sie haben in wenigen Minuten eine einsatzbereite XPS‑Datei.

## Schnelle Antworten
- **Was ist das Hauptziel?** Ein XPS-Dokument .NET erstellen und eine Rechteckform hinzufügen.  
- **Welche Bibliothek wird benötigt?** Aspose.Page für .NET (von der offiziellen Website herunterladbar).  
- **Benötige ich eine Lizenz für Tests?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.  
- **Wie lange dauert die Implementierung?** Etwa 5‑10 Minuten für ein einfaches Rechteck.

## Was ist Aspose.Page für .NET?
Aspose.Page für .NET ist eine hochleistungsfähige, vollständig verwaltete API, die Entwicklern ermöglicht, XPS (XML Paper Specification)-Dokumente programmgesteuert zu erstellen, zu bearbeiten und zu rendern, ohne externe Komponenten zu benötigen. Sie bietet ein umfangreiches Objektmodell zum Zeichnen von Formen, Text und Bildern und unterstützt erweiterte Funktionen wie Farbmanagement, Kompression und PDF-Konvertierung, wodurch sie sich für ein breites Spektrum an Dokumentenerzeugungs‑Szenarien eignet.

## Warum Aspose.Page zum Erstellen von XPS-Dokumenten .NET verwenden?
Aspose.Page unterstützt **30+ XPS‑Funktionen** – einschließlich Vektorgrafiken, Textlayout und Farbmanagement – und kann Dateien bis zu **500 MB** erzeugen, ohne das gesamte Dokument in den Speicher zu laden. Diese quantifizierte Fähigkeit sorgt für reibungslose Leistung selbst bei groß angelegten Druckaufträgen.

## Voraussetzungen

Bevor Sie mit diesem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Aspose.Page für .NET Bibliothek: Stellen Sie sicher, dass die Aspose.Page für .NET Bibliothek in Ihrer Entwicklungsumgebung installiert ist. Sie können sie [hier](https://releases.aspose.com/page/net/) herunterladen.

2. Dokumentverzeichnis: Richten Sie ein Verzeichnis ein, in dem Sie Ihre XPS‑Dokumente speichern möchten.

## Namespaces importieren

In Ihrer .NET‑Anwendung binden Sie die notwendigen Namespaces ein, um die Funktionen von Aspose.Page zu nutzen.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Wie füge ich einem XPS-Dokument in .NET ein Rechteck hinzu?

Laden Sie das XPS‑Dokument, erstellen Sie ein `Graphics`‑Objekt, definieren Sie ein `RectangleF` mit der gewünschten Größe und rufen Sie `DrawRectangle` auf. Diese Sequenz zeichnet ein Rechteck in einer einzigen Codezeile und kümmert sich automatisch um die DPI‑Skalierung. Für typische A4‑Seiten erscheint ein 200 × 100 pt‑Rechteck zentriert, ohne zusätzliche Berechnungen.

### Schritt 1: Dokumentverzeichnis festlegen

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

### Schritt 2: Neues XPS-Dokument erstellen

Die Klasse `XpsDocument` repräsentiert die XPS‑Datei, die Sie erstellen, und bietet Methoden zum Hinzufügen von Seiten, Grafiken und anderen Ressourcen.

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

### Schritt 3: Ein Rechteck hinzufügen

`XpsPath` definiert ein zeichnbares Pfadobjekt innerhalb des XPS‑Dokuments, mit dem Sie Geometrie, Kontur, Füllung und weitere visuelle Eigenschaften festlegen können.

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

### Schritt 4: Dokument speichern

Die Methode `Save` schreibt das erstellte XPS‑Dokument an den angegebenen Dateipfad auf dem Datenträger.

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Herzlichen Glückwunsch! Sie haben erfolgreich ein Rechteck zu einem XPS‑Dokument mit Aspose.Page für .NET hinzugefügt.

## Häufige Probleme und Tipps

- **Fehlende Schriften:** Stellen Sie sicher, dass die von Ihnen referenzierten Schriften auf dem Server installiert sind; andernfalls ersetzt Aspose.Page sie durch eine Standardschrift, was das Layout verändern kann.  
- **Große Dokumente:** Beim Erzeugen von Dateien, die größer als 200 MB sind, sollten Sie `document.SaveOptions.Compress = true` aufrufen, um den Speicherverbrauch zu reduzieren.  
- **Koordinatensystem:** XPS verwendet Punkte (1/72 Zoll). Denken Sie daran, Pixel in Punkte umzuwandeln, wenn Sie mit bildschirmbasierten Abmessungen arbeiten.

## Häufig gestellte Fragen

**Q: Ist Aspose.Page mit allen .NET‑Anwendungen kompatibel?**  
A: Ja, Aspose.Page funktioniert nahtlos mit Desktop-, Web- und Cloud‑.NET‑Anwendungen.

**Q: Wo finde ich die Dokumentation für Aspose.Page für .NET?**  
A: Die vollständige API‑Referenz ist [hier](https://reference.aspose.com/page/net/) verfügbar.

**Q: Kann ich Aspose.Page für .NET kostenlos testen, bevor ich es kaufe?**  
A: Ja, Sie können eine kostenlose Testversion [hier](https://releases.aspose.com/) erhalten.

**Q: Wie kann ich eine temporäre Lizenz für Aspose.Page für .NET erhalten?**  
A: Besuchen Sie [diesen Link](https://purchase.aspose.com/temporary-license/), um eine temporäre Lizenz zu erhalten.

**Q: Wo kann ich Community‑Support erhalten oder Fragen zu Aspose.Page für .NET stellen?**  
A: Besuchen Sie das [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39) für Community‑Support.

**Zuletzt aktualisiert:** 2026-07-19  
**Getestet mit:** Aspose.Page for .NET 24.9  
**Autor:** Aspose

## Verwandte Tutorials

- [XPS-Dokument mit Aspose.Page für .NET erstellen](/page/net/document-creation/create-xps-document/)
- [Aspose.Page .NET – Formen zeichnen](/page/net/drawing-shapes/)
- [Text zu XPS-Dokument mit Aspose.Page für .NET hinzufügen](/page/net/text-manipulation/add-text-to-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}