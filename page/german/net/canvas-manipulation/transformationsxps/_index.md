---
date: 2026-01-05
description: Erfahren Sie, wie Sie XPS‑Dokumente mühelos mit Aspose.Page für .NET
  transformieren. Folgen Sie unserer Schritt‑für‑Schritt‑Anleitung für nahtlose Transformationen.
linktitle: Transformations XPS
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

Willkommen in der Welt von Aspose.Page für .NET, einer leistungsstarken Bibliothek, die es Ihnen ermöglicht, mühelos verschiedene Transformationen an XPS‑Dokumenten durchzuführen. **In diesem Tutorial erfahren Sie, wie Sie XPS‑Dokumente mit Aspose.Page für .NET transformieren**, egal ob Sie ein erfahrener Entwickler sind oder gerade erst anfangen. Wir gehen Schritt für Schritt durch, erklären die Gründe hinter jeder Transformation und geben Ihnen praktische Tipps, die Sie in realen Projekten anwenden können.

## Schnelle Antworten
- **Was können Sie erreichen?** Create, translate, scale, and rotate XPS canvas elements programmatically.  
- **Welche Bibliothek wird benötigt?** Aspose.Page for .NET (latest version).  
- **Benötige ich eine Lizenz?** A free trial works for development; a commercial license is required for production.  
- **Unterstützte Plattformen?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Wie lange dauert die Implementierung?** About 10‑15 minutes for the basic transformations shown here.

## Was bedeutet „how to transform xps“?
Der Ausdruck *how to transform xps* bezieht sich darauf, programmgesteuert das Layout, die Größe und die Ausrichtung von Elementen innerhalb eines XPS‑Dokuments (XML Paper Specification) zu ändern. Mit Aspose.Page können Sie matrixbasierte Transformationen auf Canvas‑Objekte anwenden und erhalten so eine feinkörnige Kontrolle über Positionierung, Skalierung und Drehung, ohne das XPS‑XML manuell bearbeiten zu müssen.

## Warum Aspose.Page für XPS‑Transformationen verwenden?
- **Vollständige .NET-Integration** – funktioniert nahtlos mit Visual Studio, Rider und anderen IDEs.  
- **Keine externen Abhängigkeiten** – die API übernimmt alle Low‑Level‑XPS‑Details für Sie.  
- **Umfangreiche Transformationsunterstützung** – verschieben, skalieren, rotieren und mehrere Transformationen in einem Aufruf kombinieren.  
- **Leistungsoptimiert** – geeignet für die Erstellung von Berichten, Rechnungen oder beliebigen druckbaren Grafiken in Echtzeit.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- **Aspose.Page for .NET Library** – laden Sie sie von der offiziellen Dokumentation herunter und installieren Sie sie: [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).  
- **Entwicklungsumgebung** – Visual Studio, Visual Studio Code oder jede andere .NET‑kompatible IDE.  
- **Dokumentenverzeichnis** – ein Ordner auf Ihrem Rechner, in dem Sie XPS‑Dateien lesen/schreiben. Ersetzen Sie den Platzhalter im Code durch den tatsächlichen Pfad.

Jetzt, da alles eingerichtet ist, tauchen wir in den Code ein.

## Namespaces importieren

Zuerst importieren Sie die Namespaces, die die Aspose.Page‑Klassen bereitstellen, die Sie benötigen:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Wie man XPS transformiert – Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Ein neues XPS‑Dokument erstellen

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

*Erklärung*: Wir beginnen damit, den Ordner zu definieren, der unsere Quell‑ und Ausgabedateien enthält, und dann ein leeres `XpsDocument` zu instanziieren. Dieses Objekt wird die Canvas für alle nachfolgenden Transformationen sein.

### Schritt 2: Ein Haupt‑Canvas erstellen

```csharp
// Create main canvas, common for all page elements
XpsCanvas canvas1 = doc.AddCanvas();

// Make left and top offsets in the main canvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

*Warum das wichtig ist*: Das Haupt‑Canvas dient als Container für alle anderen Canvas‑Objekte. Durch das Anwenden eines kleinen Versatzes stellen wir sicher, dass der Inhalt nicht am Seitenrand abgeschnitten wird.

### Schritt 3: Eine Rechteck‑Pfadgeometrie erstellen

```csharp
// Create rectangle path geometry
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

*Tipp*: Der Pfad‑String folgt der standardmäßigen XPS‑Pfadsyntax (`M` für move, `L` für line, `Z` zum Schließen). Passen Sie die Koordinaten an, um die Rechteckgröße zu ändern.

### Schritt 4: Eine Füllung für Rechtecke hinzufügen

```csharp
// Create a fill for rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

*Pro‑Tipp*: Verwenden Sie `CreateColor` mit RGB‑Werten, um Ihre Markenpalette zu treffen.

### Schritt 5: Ein neues Canvas ohne Transformationen hinzufügen

```csharp
// Add new canvas without any transformations to the main canvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Create rectangle in this canvas and fill it
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Hier platzieren wir einfach ein Rechteck auf der Seite ohne zusätzliche Transformation – nützlich als Basiselement.

### Schritt 6: Ein neues Canvas mit Translate‑Transformation hinzufügen

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

*Was passiert?*: Die erste Matrix verschiebt das Rechteck um 200 Einheiten nach unten. Der nachfolgende `Translate`‑Aufruf verschiebt es 500 Einheiten nach rechts und demonstriert, wie mehrere Verschiebungen verkettet werden können.

### Schritt 7: Ein neues Canvas mit doppelter Skalierungs‑Transformation hinzufügen

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

*Warum skalieren?*: Durch Skalieren um 2 verdoppelt sich die Breite und Höhe des Rechtecks, sodass Sie größere Grafiken erstellen können, ohne die Geometrie neu zu definieren.

### Schritt 8: Ein neues Canvas mit Rotation‑um‑einen‑Punkt‑Transformation hinzufügen

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

*Wichtige Erkenntnis*: `RotateAround` dreht das Canvas um einen benutzerdefinierten Punkt (hier (100, 50)), wodurch Sie die Drehungsanker präzise steuern können.

### Schritt 9: Ergebnis‑XPS‑Dokument speichern

```csharp
// Save resultant XPS document
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

Nachdem alle Transformationen angewendet wurden, wird das Dokument in `output1.xps` gespeichert. Öffnen Sie die Datei in einem beliebigen XPS‑Viewer, um die gestapelten Rechtecke mit ihren jeweiligen Verschiebungen, Skalierungen und Rotationen zu sehen.

## Häufige Probleme & Fehlersuche

| Symptom | Wahrscheinliche Ursache | Lösung |
|---------|--------------------------|--------|
| Leere Ausgabedatei | `dataDir` verweist auf einen nicht vorhandenen Ordner | Stellen Sie sicher, dass das Verzeichnis existiert oder verwenden Sie einen absoluten Pfad |
| Rechtecke nicht wie erwartet positioniert | Falsche Matrixwerte | Überprüfen Sie die Reihenfolge der Aufrufe `Translate`, `Scale` und `RotateAround` |
| Farben erscheinen falsch | RGB‑Werte außerhalb des Bereichs 0‑255 | Verwenden Sie gültige Byte‑Werte für jeden Kanal |

## Häufig gestellte Fragen

**F: Ist Aspose.Page für .NET mit allen .NET‑Entwicklungsumgebungen kompatibel?**  
A: Ja, es funktioniert nahtlos mit Visual Studio, Visual Studio Code, Rider und jeder IDE, die .NET unterstützt.

**F: Wo finde ich zusätzliche Beispiele und detaillierte API‑Dokumentation?**  
A: Besuchen Sie die offizielle Dokumentation unter [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

**F: Kann ich Aspose.Page vor dem Kauf einer Lizenz testen?**  
A: Absolut. Eine kostenlose Testversion ist hier verfügbar: [Aspose.Page Free Trial](https://releases.aspose.com/).

**F: Wie erhalte ich eine temporäre Lizenz zum Testen?**  
A: Sie können eine über die Seite für temporäre Lizenzen anfordern: [Temporary License](https://purchase.aspose.com/temporary-license/).

**F: Wo kann ich eine Voll‑Lizenz erwerben?**  
A: Kaufen Sie direkt im Aspose‑Shop: [Aspose.Page Buy](https://purchase.aspose.com/buy).

**Zuletzt aktualisiert:** 2026-01-05  
**Getestet mit:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}