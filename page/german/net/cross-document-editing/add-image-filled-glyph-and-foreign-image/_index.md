---
date: 2026-06-30
description: Erfahren Sie, wie Sie ein XPS-Dokument .NET erstellen und image‑filled
  glyphs oder foreign images mit Aspose.Page für .NET in wenigen einfachen Schritten
  hinzufügen.
keywords:
- create xps document .net
- image filled glyph
- foreign image
linktitle: Hinzufügen Image Filled Glyph & Foreign Image
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create XPS document .NET and add image‑filled glyphs or
    foreign images using Aspose.Page for .NET in a few easy steps.
  headline: Create XPS Document .NET – Add Image Filled Glyph & Foreign Image with
    Aspose.Page
  type: TechArticle
- questions:
  - answer: Over 25 image formats and the ability to process XPS files up to 500 MB
      without full memory loading.
    question: What does Aspose.Page support?
  - answer: 'Just two lines: create an `ImageBrush` and assign it to a `Glyph`.'
    question: How many lines of code to add an image‑filled glyph?
  - answer: Yes, a commercial license removes evaluation watermarks.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are compatible?
  - answer: Absolutely – you can import the font collection from the first document
      into the second.
    question: Can I reuse fonts from another XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: XPS-Dokument .NET – Add Image Filled Glyph & Foreign Image mit Aspose.Page
url: /de/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen Sie XPS-Dokument .NET – Bildgefülltes Glyph & Fremdbild mit Aspose.Page

## Einführung

In der .NET‑Entwicklung sind **create XPS document .NET**‑Aufgaben üblich, wenn Sie hochwertige, auflösungsunabhängige Grafiken benötigen. Aspose.Page für .NET macht dies unkompliziert und ermöglicht es Ihnen, XPS‑Dateien mit bildgefüllten Glyphs zu bereichern oder Bilder aus einem anderen XPS‑Dokument zu übernehmen. Am Ende dieses Tutorials wissen Sie, wie Sie zwei XPS‑Dokumente erstellen, Glyphs mit Bildern füllen und diese Bilder über Dokumente hinweg wiederverwenden – ideal für die Erstellung von Rechnungen, Zertifikaten oder anderen visuell reichen Ausgaben.

## Schnelle Antworten
- **Was unterstützt Aspose.Page?** Über 25 Bildformate und die Möglichkeit, XPS‑Dateien bis zu 500 MB zu verarbeiten, ohne den gesamten Speicher zu laden.  
- **Wie viele Codezeilen benötigt man, um ein bildgefülltes Glyph hinzuzufügen?** Nur zwei Zeilen: Erstellen Sie einen `ImageBrush` und weisen Sie ihn einem `Glyph` zu.  
- **Benötige ich eine Lizenz für die Produktion?** Ja, eine kommerzielle Lizenz entfernt Evaluationswasserzeichen.  
- **Welche .NET‑Versionen sind kompatibel?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Kann ich Schriftarten aus einem anderen XPS wiederverwenden?** Absolut – Sie können die Schriftartsammlung aus dem ersten Dokument in das zweite importieren.

## Wie erstellt man ein XPS-Dokument mit Aspose.Page .NET?

Laden Sie die Aspose.Page‑Bibliothek, instanziieren Sie ein `XpsDocument`, fügen Sie eine Seite hinzu und rufen Sie `Save` auf – das ist der komplette Workflow in drei knappen Anweisungen. Die API übernimmt automatisch Seitengröße, DPI und Ressourcenverwaltung, sodass Sie sich nicht um niedrige XPS‑Strukturen kümmern müssen. Dieser Ansatz skaliert von einem einseitigen Flyer bis hin zu mehrhundertseitigen Katalogen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- **Aspose.Page für .NET** – laden Sie es von [hier](https://releases.aspose.com/page/net/) herunter.  
- **Eine .NET‑IDE** – Visual Studio, Rider oder VS Code mit der C#‑Erweiterung.  
- **Ein Ordner für Ihre Dokumente** – wir werden ihn im Code als **Your Document Directory** bezeichnen.

## Namespaces importieren

Der `Aspose.Page.XPS`‑Namespace stellt die Kernklassen für XPS‑Dokumente bereit, während `Aspose.Page.XPS.XpsModel` Model‑Elemente wie Glyphs und Brushes enthält. Importieren Sie sie am Anfang Ihrer Datei:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Was ist ein bildgefülltes Glyph?

Ein Glyph ist eine Vektorform, die mit einer Vollfarbe, einem Farbverlauf oder einem ImageBrush gerendert werden kann. Wenn Sie einen `ImageBrush` anwenden, wird das Innere des Glyphs mit dem angegebenen Bild gefüllt, wodurch komplexe visuelle Effekte ohne Rasterisierung der gesamten Seite ermöglicht werden.

## Schritt 1: Erstellen Sie das erste XPS-Dokument

`XpsDocument` repräsentiert ein XPS‑Paket und ist der Einstiegspunkt zum Erstellen und Speichern von XPS‑Dateien. Beginnen Sie damit, das erste XPS‑Dokument zu erstellen, das die bildgefüllten Glyphs hosten wird.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

## Schritt 2: Glyphs zum ersten Dokument hinzufügen

`XpsGlyphs` definiert eine Sammlung von Glyphs (Textzeichen), die auf einer Seite platziert werden können. Fügen Sie dem ersten Dokument Glyphs hinzu und geben Sie Schriftart, Größe, Stil und Position an.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## Schritt 3: Glyphs mit einem ImageBrush füllen

`ImageBrush` malt einen Bereich mit einem Bild und ermöglicht es, Muster oder Bilder in Formen zu füllen. Füllen Sie die Glyphs mit einem ImageBrush, indem Sie ein Bild aus Ihrem Datenverzeichnis verwenden.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## Schritt 4: Erstellen Sie das zweite XPS-Dokument

`XpsDocument` wird verwendet, um eine neue XPS‑Datei zu erstellen, die Seiten, Ressourcen und Inhalte enthalten kann. Erstellen Sie nun das zweite XPS‑Dokument, das Glyphs aus dem ersten Dokument einbinden wird.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

## Schritt 5: Glyphs mit der Schriftart aus dem ersten Dokument hinzufügen

`Font` repräsentiert eine Schriftart, die zum Rendern von Text in einem XPS‑Dokument verwendet wird. Fügen Sie dem zweiten Dokument Glyphs hinzu und nutzen Sie die aus dem ersten Dokument extrahierte Schriftart. Durch das Teilen der Schriftartsammlung halten Sie die Dateigröße gering und gewährleisten visuelle Konsistenz.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## Schritt 6: Einen ImageBrush aus der Füllung des ersten Dokuments erstellen

`ImageBrush` kann aus einer bestehenden Füllung erstellt werden, um dasselbe Bild über Dokumente hinweg wiederzuverwenden. Erstellen Sie einen ImageBrush aus der Füllung des ersten Dokuments und verwenden Sie ihn, um die Glyphs im zweiten Dokument zu füllen. Diese „Fremdbild“-Technik ermöglicht die Wiederverwendung von Grafiken, ohne die Quelldatei zu duplizieren.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## Schritt 7: Dokumente speichern

`Save` schreibt das XPS‑Paket in eine Datei und bettet alle Ressourcen ein. Speichern Sie sowohl das erste als auch das zweite XPS‑Dokument im Ausgabeverzeichnis. Die `Save`‑Methode schreibt das XPS‑Paket, bettet alle Ressourcen ein und bewahrt die bildgefüllten Glyphs.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Häufige Probleme und Lösungen

| Problem | Warum es passiert | Lösung |
|---------|-------------------|--------|
| **Bild erscheint nicht im Glyph** | Der `ImageBrush` wurde mit einer falschen URI erstellt oder die Bildgröße überschreitet die Glyph‑Grenzen. | Überprüfen Sie den Bildpfad und setzen Sie optional `ImageBrush.Stretch = Stretch.Uniform`. |
| **Schriftarten fehlen im zweiten Dokument** | Schriftartressourcen wurden nicht aus dem ersten XPS exportiert. | Verwenden Sie `firstDoc.Fonts.SaveTo(secondDoc.Fonts)` bevor Sie Glyphs hinzufügen. |
| **Leistungsverlust bei großen Dateien** | Laden großer Bilder in den Speicher für jedes Glyph. | Verwenden Sie eine einzelne `ImageBrush`‑Instanz für alle Glyphs oder reduzieren Sie die Bildgröße vor der Verwendung. |

## Häufig gestellte Fragen

### Q1: Kann ich verschiedene Bildformate zum Füllen von Glyphs verwenden?

A1: Ja, Aspose.Page unterstützt PNG, JPEG, BMP, GIF, TIFF und mehr – insgesamt über 25 Formate.

### Q2: Wie kann ich das Aussehen von Glyphs weiter anpassen?

A2: Untersuchen Sie Eigenschaften wie `Glyph.Stroke`, `Glyph.FillOpacity` und `Glyph.Transform`, um Konturen, Transparenz und Drehung anzupassen.

### Q3: Eignet sich Aspose.Page für die Verarbeitung großer Dokumentensätze?

A3: Absolut. Die Bibliothek verarbeitet XPS‑Dateien mit mehreren hundert Seiten mittels Streaming und hält den Speicherverbrauch unter 100 MB, selbst bei 500‑seitigen Dokumenten.

### Q4: Kann ich einzelnen Glyphs unterschiedliche Stile zuweisen?

A4: Ja, jede `Glyph`‑Instanz hat eigene Eigenschaften `Fill`, `Stroke` und `Transform`, die eine individuelle Gestaltung pro Glyph ermöglichen.

### Q5: Welche Vorteile bietet die Verwendung von Aspose.Page gegenüber anderen XPS‑Tools?

A5: Aspose.Page unterstützt mehr als 25 Bildformate, verarbeitet Dateien bis zu 500 MB ohne vollständiges Laden in den Speicher und bietet eine 100 % .NET‑native API – wodurch COM‑Interop oder externe Werkzeuge entfallen.

**Zuletzt aktualisiert:** 2026-06-30  
**Getestet mit:** Aspose.Page 24.11 für .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [XPS-Dokument erstellen – Aspose.Page für .NET](/page/net/document-creation/)
- [Bild zu XPS-Dokument hinzufügen mit Aspose.Page für .NET](/page/net/image-management/add-image-to-xps-document/)
- [Glyph-Klon hinzufügen und Farbe ändern mit Aspose.Page für .NET](/page/net/cross-document-editing/add-glyph-clone-and-change-color/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}