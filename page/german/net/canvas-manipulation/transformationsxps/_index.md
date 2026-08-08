---
date: 2026-06-25
description: Erfahren Sie, wie Sie XPS-Dokumente mühelos transformieren – der umfassende
  Leitfaden zur Transformation von XPS mit Aspose.Page für .NET, mit code‑freien Schritten
  und praxisnahen Tipps.
keywords:
- how to transform xps
- convert images to xps
- Aspose.Page transformations
linktitle: XPS-Transformationen
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to transform XPS documents effortlessly – the definitive
    guide on how to transform xps using Aspose.Page for .NET, with code‑free steps
    and real‑world tips.
  headline: How to Transform XPS with Aspose.Page for .NET
  type: TechArticle
- description: Learn how to transform XPS documents effortlessly – the definitive
    guide on how to transform xps using Aspose.Page for .NET, with code‑free steps
    and real‑world tips.
  name: How to Transform XPS with Aspose.Page for .NET
  steps:
  - name: Create a New XPS Document
    text: '`XpsDocument` is the Aspose.Page object that represents an XPS file in
      memory. *Explanation*: We start by defining the folder that holds our source
      and output files, then instantiate an empty `XpsDocument`. This object will
      be the canvas for all subsequent transformations.'
  - name: Create a Main Canvas
    text: '`Canvas` is the drawing surface that groups shapes, text, and other graphical
      elements. *Why this matters*: The main canvas acts as a container for all other
      canvases. By applying a small offset we ensure the content isn’t clipped at
      the page edge.'
  - name: Create a Rectangle Path Geometry
    text: '`PathGeometry` defines vector shapes using XPS path syntax (M = move, L
      = line, Z = close). *Tip*: The path string follows the standard XPS path syntax.
      Adjust the coordinates to change rectangle size.'
  - name: Add a Fill for Rectangles
    text: '`SolidColorBrush` creates a solid‑color fill that can be reused across
      multiple shapes. *Pro tip*: Use `CreateColor` with RGB values to match your
      brand palette.'
  - name: Add a New Canvas Without Transformations
    text: '`Canvas` without a transform serves as a baseline element for comparison.
      Here we simply place a rectangle on the page with no extra transformation—useful
      as a baseline element.'
  - name: Add a New Canvas with Translate Transformation
    text: '`TranslateTransform` moves objects along the X and Y axes. *What’s happening?*
      The first matrix moves the rectangle down by 200 units. The subsequent `Translate`
      call shifts it 500 units to the right, demonstrating how multiple translations
      can be chained.'
  - name: Add a New Canvas with Double Scale Transformation
    text: '`ScaleTransform` multiplies the width and height of the canvas by the supplied
      factors. *Why scale?* Scaling by 2 doubles the rectangle’s width and height,
      letting you create larger graphics without redefining the geometry.'
  - name: Add a New Canvas with Rotation Around a Point Transformation
    text: '`RotateAroundTransform` pivots the canvas around a custom point (here (100,
      50)). *Key insight*: `RotateAround` pivots the canvas around a custom point,
      giving you fine control over rotation anchors.'
  - name: Save Resultant XPS Document
    text: '`Save` persists the in‑memory document to disk in XPS format. After all
      transformations are applied, the document is persisted to `output1.xps`. Open
      the file in any XPS viewer to see the stacked rectangles with their respective
      translations, scaling, and rotation.'
  type: HowTo
- questions:
  - answer: Yes, it works seamlessly with Visual Studio, Visual Studio Code, Rider,
      and any IDE that supports .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Is Aspose.Page for .NET compatible with all .NET development environments?
  - answer: Visit the official documentation at [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).
    question: Where can I find additional examples and detailed API docs?
  - answer: 'Absolutely. A free trial is available here: [Aspose.Page Free Trial](https://releases.aspose.com/).'
    question: Can I try Aspose.Page before buying a license?
  - answer: 'Request one via the temporary‑license page: [Temporary License](https://purchase.aspose.com/temporary-license/).'
    question: How do I obtain a temporary license for testing?
  - answer: 'Purchase directly from the Aspose store: [Aspose.Page Buy](https://purchase.aspose.com/buy).'
    question: Where do I purchase a full license?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Wie man XPS mit Aspose.Page für .NET transformiert
url: /de/net/canvas-manipulation/transformationsxps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man XPS mit Aspose.Page für .NET transformiert

## Einführung

In diesem umfassenden Leitfaden lernen Sie **wie man XPS**‑Dokumente mit Aspose.Page für .NET transformiert. Egal, ob Sie verschieben, skalieren, rotieren oder mehrere Grafiken auf einer einzigen Seite kombinieren müssen, bietet die Bibliothek matrixbasierte Kontrolle, ohne in rohes XML eintauchen zu müssen. Wir gehen jeden Schritt durch, erklären, warum jede Transformation wichtig ist, und teilen praktische Tipps, die Sie direkt in Produktionscode übernehmen können.

## Schnelle Antworten
- **Was können Sie erreichen?** Erstellen, verschieben, skalieren und rotieren Sie XPS‑Canvas‑Elemente programmgesteuert.  
- **Welche Bibliothek wird benötigt?** Aspose.Page für .NET (neueste Version).  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Unterstützte Plattformen?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Implementierungszeit?** Ungefähr 10‑15 Minuten für die unten gezeigten Grundtransformationen.

## Was bedeutet „how to transform xps“?
Der Ausdruck *how to transform xps* beschreibt das programmgesteuerte Ändern von Layout, Größe und Ausrichtung von Elementen innerhalb eines XPS (XML Paper Specification)-Dokuments. Mit Aspose.Page wenden Sie matrixbasierte Transformationen auf Canvas‑Objekte an, wodurch Sie pixelgenaue Kontrolle über Positionierung, Skalierung und Rotation erhalten, ohne das XPS‑Markup manuell zu bearbeiten.

## Warum Aspose.Page für XPS-Transformationen verwenden?
Laden Sie Ihre XPS‑Datei, wenden Sie eine Reihe von Transformationen an und speichern Sie – alles in zwei Codezeilen. Aspose.Page unterstützt **50+ input and output formats**, kann **200‑page XPS files in under 2 seconds** verarbeiten und erfordert **no external dependencies**. Das macht es ideal für die Erstellung von Rechnungen, Berichten oder jeder druckbaren Grafik „on the fly“.

## Voraussetzungen

- **Aspose.Page for .NET Library** – laden Sie sie von der offiziellen Dokumentation herunter: [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).  
- **Entwicklungsumgebung** – Visual Studio, Visual Studio Code, Rider oder jede IDE, die .NET unterstützt.  
- **Dokumentverzeichnis** – ein Ordner auf Ihrem Rechner, in dem Sie XPS‑Dateien lesen/schreiben. Ersetzen Sie den Platzhalter im Code durch den tatsächlichen Pfad.

Jetzt, da alles eingerichtet ist, tauchen wir in den Code ein.

## Namespaces importieren

Die folgenden Namespaces stellen die Kern‑Aspose.Page‑Typen bereit, mit denen Sie arbeiten werden:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Wie man XPS mit Aspose.Page transformiert?

Laden Sie Ihr Quell‑XPS (oder beginnen Sie mit einem frischen Dokument) und wenden Sie dann eine Sequenz von Matrix‑Transformationen – translate, scale und rotate – direkt auf Canvas‑Objekte an. Jede Transformation wird in der Reihenfolge angewendet, in der Sie sie aufrufen, sodass Sie komplexe Layouts mit nur wenigen Methodenaufrufen erstellen können.

## Wie man XPS transformiert – Schritt‑für‑Schritt‑Anleitung

In diesem Abschnitt führen wir ein komplettes Beispiel durch, das eine XPS‑Datei erstellt, mehrere Canvas‑Objekte hinzufügt und eine Reihe von Transformationen wie Translation, Skalierung und Rotation anwendet. Jeder Schritt enthält einen knappen Code‑Snippet (durch Platzhalter dargestellt) und erklärt, warum die Operation durchgeführt wird, sodass Sie sie leicht reproduzieren können.

### Schritt 1: Neues XPS‑Dokument erstellen

`XpsDocument` ist das Aspose.Page‑Objekt, das eine XPS‑Datei im Speicher repräsentiert.  
```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

*Erklärung*: Wir beginnen damit, den Ordner zu definieren, der unsere Quell‑ und Ausgabedateien enthält, und instanziieren dann ein leeres `XpsDocument`. Dieses Objekt wird die Canvas für alle nachfolgenden Transformationen sein.

### Schritt 2: Haupt‑Canvas erstellen

`Canvas` ist die Zeichenfläche, die Formen, Text und andere grafische Elemente gruppiert.  
```csharp
// Create main canvas, common for all page elements
XpsCanvas canvas1 = doc.AddCanvas();

// Make left and top offsets in the main canvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

*Warum das wichtig ist*: Das Haupt‑Canvas dient als Container für alle anderen Canvas‑Objekte. Durch Anwenden eines kleinen Offsets stellen wir sicher, dass der Inhalt nicht am Seitenrand abgeschnitten wird.

### Schritt 3: Rechteck‑Pfadgeometrie erstellen

`PathGeometry` definiert Vektorgrafiken mithilfe der XPS‑Pfadsyntax (M = move, L = line, Z = close).  
```csharp
// Create rectangle path geometry
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

*Tipp*: Der Pfad‑String folgt der standardmäßigen XPS‑Pfadsyntax. Passen Sie die Koordinaten an, um die Rechteckgröße zu ändern.

### Schritt 4: Füllung für Rechtecke hinzufügen

`SolidColorBrush` erzeugt eine einfarbige Füllung, die über mehrere Formen wiederverwendet werden kann.  
```csharp
// Create a fill for rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

*Pro‑Tipp*: Verwenden Sie `CreateColor` mit RGB‑Werten, um Ihre Markenpalette zu treffen.

### Schritt 5: Neues Canvas ohne Transformationen hinzufügen

`Canvas` ohne Transformation dient als Basiselement zum Vergleich.  
```csharp
// Add new canvas without any transformations to the main canvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Create rectangle in this canvas and fill it
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Hier platzieren wir einfach ein Rechteck auf der Seite ohne zusätzliche Transformation – nützlich als Basiselement.

### Schritt 6: Neues Canvas mit Translate‑Transformation hinzufügen

`TranslateTransform` verschiebt Objekte entlang der X‑ und Y‑Achsen.  
```csharp
// Add new canvas with translate transformation to the main canvas
XpsCanvas canvas3 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Translate this canvas to the right side of the page
canvas3.RenderTransform.Translate(500, 0);

// Create rectangle in this canvas and fill it
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

*Was passiert?* Die erste Matrix verschiebt das Rechteck um 200 Einheiten nach unten. Der nachfolgende `Translate`‑Aufruf verschiebt es 500 Einheiten nach rechts und demonstriert, wie mehrere Translationen verkettet werden können.

### Schritt 7: Neues Canvas mit doppelter Scale‑Transformation hinzufügen

`ScaleTransform` multipliziert Breite und Höhe des Canvas mit den angegebenen Faktoren.  
```csharp
// Add new canvas with double scale transformation to the main canvas
XpsCanvas canvas4 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Scale this canvas
canvas4.RenderTransform.Scale(2, 2);

// Create rectangle in this canvas and fill it
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

*Warum skalieren?* Eine Skalierung um 2 verdoppelt die Breite und Höhe des Rechtecks, sodass Sie größere Grafiken erstellen können, ohne die Geometrie neu zu definieren.

### Schritt 8: Neues Canvas mit Rotation‑um‑einen‑Punkt‑Transformation hinzufügen

`RotateAroundTransform` dreht das Canvas um einen benutzerdefinierten Punkt (hier (100, 50)).  
```csharp
// Add new canvas with rotation around a point transformation to the main canvas
XpsCanvas canvas5 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Rotate this canvas around a point on 45 degrees
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Create rectangle in this canvas and fill it
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

*Wichtige Erkenntnis*: `RotateAround` dreht das Canvas um einen benutzerdefinierten Punkt und gibt Ihnen feine Kontrolle über die Rotationsanker.

### Schritt 9: Ergebnis‑XPS‑Dokument speichern

`Save` speichert das im Speicher befindliche Dokument auf die Festplatte im XPS‑Format.  
```csharp
// Save resultant XPS document
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

Nachdem alle Transformationen angewendet wurden, wird das Dokument in `output1.xps` persistiert. Öffnen Sie die Datei in einem beliebigen XPS‑Viewer, um die gestapelten Rechtecke mit ihren jeweiligen Translationen, Skalierungen und Rotationen zu sehen.

## Häufige Probleme & Fehlersuche

| Symptom | Wahrscheinliche Ursache | Lösung |
|---------|--------------------------|--------|
| Leere Ausgabedatei | `dataDir` verweist auf einen nicht vorhandenen Ordner | Stellen Sie sicher, dass das Verzeichnis existiert, oder verwenden Sie einen absoluten Pfad |
| Rechtecke nicht wie erwartet positioniert | Falsche Matrixwerte | Überprüfen Sie die Reihenfolge der Aufrufe von `Translate`, `Scale` und `RotateAround` |
| Farben erscheinen falsch | RGB‑Werte außerhalb des Bereichs 0‑255 | Verwenden Sie gültige Byte‑Werte für jeden Kanal |

## Häufig gestellte Fragen

**Q: Ist Aspose.Page für .NET mit allen .NET‑Entwicklungsumgebungen kompatibel?**  
A: Ja, es funktioniert nahtlos mit Visual Studio, Visual Studio Code, Rider und jeder IDE, die .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+ unterstützt.

**Q: Wo finde ich zusätzliche Beispiele und detaillierte API‑Dokumentation?**  
A: Besuchen Sie die offizielle Dokumentation unter [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

**Q: Kann ich Aspose.Page vor dem Kauf einer Lizenz testen?**  
A: Absolut. Eine kostenlose Testversion ist hier verfügbar: [Aspose.Page Free Trial](https://releases.aspose.com/).

**Q: Wie erhalte ich eine temporäre Lizenz zum Testen?**  
A: Fordern Sie eine über die Seite für temporäre Lizenzen an: [Temporary License](https://purchase.aspose.com/temporary-license/).

**Q: Wo kann ich eine Voll‑Lizenz erwerben?**  
A: Kaufen Sie direkt im Aspose‑Store: [Aspose.Page Buy](https://purchase.aspose.com/buy).

---

**Last Updated:** 2026-06-25  
**Tested With:** Aspose.Page 24.11 für .NET  
**Autor:** Aspose

## Verwandte Tutorials

- [XPS-Dokument mit Aspose.Page für .NET erstellen](/page/net/document-creation/create-xps-document/)
- [Wie man XPS mit Aspose.Page für .NET beschneidet](/page/net/canvas-manipulation/clippingxps/)
- [XPS zu PDF mit Aspose.Page für .NET konvertieren](/page/net/document-conversion/convert-xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}