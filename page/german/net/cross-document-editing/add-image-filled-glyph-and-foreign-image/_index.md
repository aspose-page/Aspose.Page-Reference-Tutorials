---
date: 2026-01-07
description: Erfahren Sie, wie Sie ein XPS‑Dokument in .NET mit Aspose.Page erstellen.
  Dieser Leitfaden zeigt, wie man bildgefüllte Glyphen und fremde Bilder hinzufügt,
  um die Dokumentvisualisierung zu verbessern.
linktitle: Add Image Filled Glyph & Foreign Image
second_title: Aspose.Page .NET API
title: XPS-Dokument mit .NET und Aspose.Page erstellen – Bildgefülltes Glyph & Fremdbild
url: /de/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS-Dokument .NET mit Aspose.Page erstellen – Bildgefüllte Glyphen & Fremdbild

## Einführung

Wenn Sie **XPS-Dokumente .NET** erstellen möchten, die poliert und professionell aussehen, bietet Ihnen Aspose.Page die Werkzeuge, um Bilder direkt in Glyphen einzubetten und Grafikressourcen über Dokumente hinweg wiederzuverwenden. In diesem Tutorial führen wir Sie durch das Erstellen von zwei XPS‑Dateien, das Befüllen von Glyphen mit einem Image‑Brush und das anschließende Wiederverwenden dieses Brushes in einem zweiten Dokument. Am Ende verstehen Sie, warum dieser Ansatz Speicher spart, das Styling vereinfacht und kreative Möglichkeiten für Berichte, Rechnungen oder jeglichen druckbaren Inhalt eröffnet.

## Schnellantworten
- **Worum geht es in diesem Tutorial?** Hinzufügen von bildgefüllten Glyphen und deren Wiederverwendung in XPS‑Dokumenten mit Aspose.Page für .NET.  
- **Welches primäre Schlüsselwort wird angesteuert?** `create xps document .net`.  
- **Voraussetzungen?** .NET‑Entwicklungsumgebung, Aspose.Page für .NET und ein Ordner für Ihre XPS‑Dateien.  
- **Wie lange dauert die Implementierung?** Etwa 10‑15 Minuten für einen funktionierenden Prototyp.  
- **Kann ich andere Bildformate verwenden?** Ja – jedes von .NETs `System.Drawing.Image` unterstützte Format.

## Voraussetzungen

Bevor Sie in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes bereit haben:

- **Aspose.Page for .NET** – laden Sie die neueste Bibliothek von [hier](https://releases.aspose.com/page/net/) herunter.  
- **Entwicklungsumgebung** – Visual Studio 2022 (oder jede IDE, die .NET 6+ unterstützt).  
- **Dokumentenverzeichnis** – erstellen Sie einen Ordner auf Ihrem Rechner, der die Eingabebilder und die erzeugten XPS‑Dateien enthält; wir werden im Code darauf als **Your Document Directory** verweisen.

## Namespaces importieren

Beginnen Sie damit, die Namespaces zu importieren, die für die Arbeit mit XPS‑Objekten und Zeichen‑Hilfsprogrammen erforderlich sind.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Das erste XPS‑Dokument erstellen

Wir beginnen mit der Instanziierung eines leeren XPS‑Dokuments, das das bildgefüllte Glyphen aufnehmen wird.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

### Schritt 2: Glyphen zum ersten Dokument hinzufügen

Als nächstes fügen wir ein Glyph (ein Textzeichen) hinzu, das wir später mit einem Image‑Brush füllen.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Schritt 3: Glyphen mit einem Image‑Brush füllen

Hier erstellen wir einen `ImageBrush` aus einer TIFF‑Datei, die sich in unserem Datenverzeichnis befindet, und wenden ihn auf das Glyph an. Der Brush ist auf Tile‑Modus eingestellt, sodass das Bild wiederholt wird, falls der Glyph‑Bereich größer als das Bild ist.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

### Schritt 4: Das zweite XPS‑Dokument erstellen

Jetzt erzeugen wir ein zweites XPS‑Dokument, das den Glyph‑Stil und den Image‑Brush des ersten Dokuments wiederverwendet.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

### Schritt 5: Glyphen mit der Schriftart aus dem ersten Dokument hinzufügen

Wir fügen dem zweiten Dokument ein Glyph hinzu und verwenden dabei exakt das Font‑Objekt aus dem ersten Dokument. Das sorgt für visuelle Konsistenz in beiden Dateien.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

### Schritt 6: Einen Image‑Brush aus der Füllung des ersten Dokuments erstellen

Anstatt das Bild erneut zu laden, klonen wir den Brush von `glyphs1` und weisen ihn `glyphs2` zu. Das demonstriert, wie Sie **create XPS document .NET** Workflows erstellen können, die Ressourcen effizient teilen.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

### Schritt 7: Die Dokumente speichern

Abschließend speichern wir beide XPS‑Dateien auf der Festplatte. Sie können sie nun mit jedem XPS‑Viewer öffnen, um den bildgefüllten Glyph‑Effekt zu sehen.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Warum Bild‑gefüllte Glyphen verwenden, wenn Sie XPS‑Dokument .NET erstellen?

- **Visueller Eindruck** – Verwandeln Sie einfachen Text in grafisch reiche Elemente, ohne die gesamte Seite zu rasterisieren.  
- **Ressourcen‑Wiederverwendung** – Teilen Sie Brushes und Fonts über mehrere Dokumente hinweg, wodurch der Speicherverbrauch reduziert wird.  
- **Flexibilität** – Kacheln, strecken oder drehen Sie den Image‑Brush, um benutzerdefinierte Muster oder Markenauftritte zu erzielen.

## Häufige Probleme & Tipps

- **Dateipfad‑Fehler** – Stellen Sie sicher, dass `dataDir` mit einem Pfadtrennzeichen (`\` oder `/`) endet, das für Ihr Betriebssystem geeignet ist.  
- **Nicht unterstützte Bildformate** – Aspose.Page arbeitet am besten mit TIFF, PNG und JPEG. Konvertieren Sie andere Formate vor der Verwendung.  
- **TileMode nicht angewendet** – Vergewissern Sie sich, dass Sie zu `XpsImageBrush` casten, bevor Sie `TileMode` setzen; andernfalls wird die Eigenschaft ignoriert.

## Häufig gestellte Fragen

### Q1: Kann ich verschiedene Bildformate zum Befüllen von Glyphen verwenden?

**A:** Ja, Aspose.Page unterstützt TIFF, PNG, JPEG, BMP und GIF. Geben Sie einfach die korrekte Dateierweiterung im Aufruf von `CreateImageBrush` an.

### Q2: Wie kann ich das Aussehen von Glyphen weiter anpassen?

**A:** Untersuchen Sie zusätzliche Eigenschaften von `XpsGlyphs` wie `Opacity`, `RenderTransform` und `Stroke`, um das Rendering fein abzustimmen.

### Q3: Ist Aspose.Page für die Verarbeitung großer Dokumentenmengen geeignet?

**A:** Absolut. Die Bibliothek ist für Hochleistungs‑Szenarien optimiert und kann Tausende von XPS‑Dateien in Batch‑Jobs verarbeiten.

### Q4: Kann ich unterschiedliche Stile auf einzelne Glyphen anwenden?

**A:** Ja. Jede `XpsGlyphs`‑Instanz kann ihre eigene Füllung, Kontur und Transformation besitzen, was Ihnen eine feinkörnige Kontrolle ermöglicht.

### Q5: Welche Vorteile bietet Aspose.Page gegenüber anderen Dokumenten‑Verarbeitungstools?

**A:** Aspose.Page bietet eine vollständige, lizenzfreie API für die Erstellung, Manipulation und Konvertierung von XPS, mit umfangreicher Dokumentation und 24/7‑Support.

---

**Zuletzt aktualisiert:** 2026-01-07  
**Getestet mit:** Aspose.Page 24.12 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}