---
date: 2026-04-03
description: Erfahren Sie, wie Sie in .NET mit Aspose.Page ein transparentes Rechteck
  hinzufügen und einen Grid‑Visual‑Brush anwenden, um beeindruckende XPS‑Dokumente
  zu erstellen.
keywords:
- add transparent rectangle
- grid visual brush
- Aspose.Page .NET
linktitle: Raster-VisualBrush anwenden
second_title: Aspose.Page .NET API
title: Transparentes Rechteck mit Grid‑Visual‑Brush hinzufügen (.NET)
url: /de/net/visual-brushes/apply-grid-visual-brush/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Transparentes Rechteck mit Grid Visual Brush (.NET) hinzufügen

## Einleitung

Wenn Sie ein **transparentes Rechteck** zu einem XPS‑Dokument hinzufügen und gleichzeitig einen stilvollen Grid Visual Brush anwenden möchten, sind Sie hier genau richtig. In diesem Tutorial führen wir Sie Schritt für Schritt mit Aspose.Page für .NET durch die notwendigen Vorgänge, sodass Sie visuell ansprechende Dokumente erstellen können, die herausstechen. Am Ende haben Sie ein vollständiges, ausführbares Beispiel, das beide Techniken in einem leicht nachvollziehbaren Workflow demonstriert.

## Schnelle Antworten
- **Was bewirkt ein transparentes Rechteck?** Es fügt eine halbtransparente Überlagerung hinzu, die den Hintergrundinhalt durchscheinen lässt.  
- **Welche API erstellt den Pinsel?** `XpsDocument.CreateVisualBrush` erstellt den Grid Visual Brush.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für Tests; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Welche .NET-Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Wie lange dauert die Implementierung?** Etwa 10‑15 Minuten für ein einfaches Beispiel.

## Was ist ein transparentes Rechteck in XPS?
Ein transparentes Rechteck ist einfach eine Form, deren Füllfarbe einen Alpha‑Wert kleiner als 1,0 enthält, sodass die darunter liegenden Grafiken teilweise sichtbar bleiben. Das ist ideal, um Abschnitte hervorzuheben, ohne den Hintergrund vollständig zu verdecken.

## Warum einen Grid Visual Brush verwenden?
Ein Grid Visual Brush ermöglicht es, eine kleine Vektorgrafik über eine größere Fläche zu kacheln und Muster wie Gitter, Schraffuren oder benutzerdefinierte Texturen zu erzeugen. In Kombination mit einem transparenten Rechteck erhalten Sie geschichtete visuelle Effekte, die sowohl leichtgewichtig als auch auflösungsunabhängig sind.

## Voraussetzungen

Bevor Sie in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

- **Aspose.Page für .NET** – Sie können es [hier](https://releases.aspose.com/page/net/) herunterladen.  
- Eine .NET‑Entwicklungsumgebung (Visual Studio, VS Code oder jede andere bevorzugte IDE).  
- Einen Ordner, in dem die generierten XPS‑Dateien gespeichert werden.

## Namespaces importieren

In Ihrer C#‑Datei importieren Sie die erforderlichen Namespaces:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Jetzt teilen wir die Lösung in klare, nummerierte Schritte auf.

## Schritt 1: XpsDocument initialisieren

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

Wir beginnen mit der Erstellung einer `XpsDocument`‑Instanz, die alle nachfolgenden Zeichenoperationen enthält.

## Schritt 2: Magenta‑Gittergeometrie erstellen

```csharp
// ExStart:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExEnd:4
```

Diese Geometrie definiert die Kontur des Gitters, das der Visual Brush füllen wird.

## Schritt 3: Magenta‑Gitter‑VisualBrush entwerfen

```csharp
// ExStart:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExEnd:5
```

Hier zeichnen wir eine kleine magentafarbene Kachel, die über das Gitter wiederholt wird.

## Schritt 4: VisualBrush auf das Gitter anwenden

```csharp
// ExStart:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExEnd:6
```

Der Aufruf `CreateVisualBrush` verknüpft die magentafarbene Kachel mit der Gittergeometrie und aktiviert das Kacheln.

## Schritt 5: Gitter zur Leinwand hinzufügen

```csharp
// ExStart:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExEnd:7
```

Wir platzieren das gekachelte Gitter auf einer Leinwand und wenden eine Translations‑Transformation an, damit es an der gewünschten Position erscheint.

## Schritt 6: Transparentes Rechteck hinzufügen

```csharp
// ExStart:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f; // This opacity makes the rectangle transparent
// ExEnd:8
```

In diesem Schritt **fügen wir ein transparentes Rechteck hinzu** (die rote Form mit `Opacity = 0.7f`). Passen Sie den Opazitätswert an, um zu steuern, wie durchscheinend das Rechteck ist.

## Schritt 7: Dokument speichern

```csharp
// ExStart:9
doc.Save(dataDir + "AddGrid_out.xps");
// ExEnd:9
```

Die XPS‑Datei wird in den zuvor angegebenen Ordner geschrieben.

## Häufige Anwendungsfälle

- **Berichtshervorhebung:** Legen Sie ein halbtransparentes Rechteck über ein Diagramm oder eine Tabelle, um es zu betonen.  
- **Wasserzeichen‑Effekte:** Kombinieren Sie ein gekacheltes Gitter mit einer transparenten Überlagerung für ein dezentes Branding.  
- **Interaktive PDFs/XPS:** Verwenden Sie das Muster als Hintergrund für Formularfelder, während die Benutzeroberfläche lesbar bleibt.

## Fehlerbehebungstipps

- **Opacity nicht sichtbar?** Stellen Sie sicher, dass Ihr Viewer XPS‑Transparenz unterstützt; einige ältere Viewer ignorieren die `Opacity`‑Eigenschaft.  
- **Falsche Kachelgröße?** Überprüfen Sie, ob das Quellrechteck (`new RectangleF(0f, 0f, 10f, 10f)`) den Abmessungen der Vektorkachel entspricht.  
- **Datei nicht gespeichert?** Überprüfen Sie, ob `dataDir` auf ein existierendes, beschreibbares Verzeichnis zeigt.

## Häufig gestellte Fragen

**F: Kann ich Aspose.Page für .NET sowohl in Web‑ als auch in Desktop‑Anwendungen verwenden?**  
A: Ja, die Bibliothek funktioniert in allen .NET‑Anwendungstypen.

**F: Gibt es eine Testversion vor dem Kauf?**  
A: Absolut, Sie können die kostenlose Testversion [hier](https://releases.aspose.com/) nutzen.

**F: Wo finde ich zusätzlichen Support oder Community‑Diskussionen?**  
A: Besuchen Sie das [Aspose.Page Forum](https://forum.aspose.com/c/page/39) für Hilfe von der Community und den Aspose‑Entwicklern.

**F: Wie kann ich eine temporäre Lizenz für die Evaluierung erhalten?**  
A: Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erwerben.

**F: Welche weitere Dokumentation gibt es für Aspose.Page für .NET?**  
A: Erkunden Sie die umfassende Dokumentation [hier](https://reference.aspose.com/page/net/).

---

**Zuletzt aktualisiert:** 2026-04-03  
**Getestet mit:** Aspose.Page 24.12 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}