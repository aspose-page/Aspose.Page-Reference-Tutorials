---
date: 2026-01-12
description: Erfahren Sie, wie Sie eine PostScript‑Datei speichern und ein PostScript‑Dokument
  mit Aspose.Page für .NET erstellen und mehrere Transformationen für dynamische Grafiken
  anwenden.
linktitle: Transformations PS
second_title: Aspose.Page .NET API
title: PostScript-Datei mit Aspose.Page-Transformationen (.NET) speichern
url: /de/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Save PostScript file with Aspose.Page Transformations (.NET)

## Einführung

In diesem Tutorial erfahren Sie, wie Sie **PostScript-Datei speichern** können, während Sie mit Aspose.Page für .NET arbeiten. Wir führen Sie durch das Erstellen eines PostScript-Dokuments, das Anwenden mehrerer Transformationen wie Translation, Skalierung, Rotation und Scherung und schließlich das Speichern des Ergebnisses. Am Ende können Sie dynamische Grafiken programmgesteuert erstellen und wissen genau, wo jede Transformation im Grafikzustand platziert werden muss.

## Schnelle Antworten
- **Was kann ich erstellen?** Ein voll funktionsfähiges PostScript-Dokument mit transformierten Grafiken.  
- **Welche Bibliothek wird benötigt?** Aspose.Page für .NET (herunterladbar von der offiziellen Website).  
- **Wie speichere ich die Datei?** Verwenden Sie `PsDocument.Save()` nach der Konfiguration der Grafikzustände.  
- **Kann ich mehrere Transformationen anwenden?** Ja – kombinieren Sie sie mit `Transform` oder sequenziellen Aufrufen.  
- **Wird eine Lizenz benötigt?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.

## Was ist eine „PostScript-Datei speichern“-Operation?

Das Speichern einer PostScript-Datei bedeutet, die Zeichenbefehle, die Sie im Speicher erstellt haben, in einer `.ps`-Datei auf der Festplatte zu persistieren. Die Datei kann dann von jedem PostScript-Interpreter, Drucker oder Betrachter gerendert werden.

## Warum Aspose.Page für .NET verwenden, um ein PostScript-Dokument zu erstellen?

Aspose.Page bietet eine hochrangige, geräteunabhängige API, die die Low-Level-PostScript-Syntax abstrahiert. Sie erhalten:
- Stark typisierte C#-Objekte für Pfade, Pinsel und Transformationen.  
- Automatische Handhabung des Grafikzustands-Stacks (save/restore).  
- Vollständige Unterstützung für komplexe Transformationsmatrizen ohne manuelle Berechnungen.  

## Voraussetzungen

Stellen Sie vor dem Start sicher, dass Sie Folgendes haben:
- **Aspose.Page für .NET** Bibliothek in Ihr Projekt integriert. Holen Sie sie vom [Download-Link](https://releases.aspose.com/page/net/).  
- Einen beschreibbaren Ordner, in dem die erzeugte `.ps`-Datei gespeichert wird. Ersetzen Sie den Platzhalterpfad im Code durch Ihr tatsächliches Verzeichnis.

## Namespaces importieren

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Jetzt lassen Sie uns jede Transformationsschritt für Schritt erkunden.

## Keine Transformationen

### Schritt 1: Ausgabestream erstellen

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Create save options with default values
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Create graphics path from the rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Set paint in graphics state on upper level
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Fill the first rectangle that is on the upper-level graphics state and without any transformations
    document.Fill(path);

    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Dieses Snippet erstellt ein **PostScript-Dokument** mit einem einzelnen orangefarbenen Rechteck und **speichert die PostScript-Datei**, ohne irgendwelche Transformationen anzuwenden.

## Verschiebung

### Schritt 1: Grafikzustand speichern

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

Das Speichern des Grafikzustands ermöglicht es Ihnen, nach dem Verschieben von Objekten zurückzukehren.

### Schritt 2: Grafikzustand verschieben

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

Die Verschiebung bewegt alles, was nach diesem Aufruf gezeichnet wird, um 250 Einheiten nach rechts.

### Schritt 3: Rechteck mit Verschiebungstransformation füllen

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

Jetzt erscheint ein blaues Rechteck 250 Punkte rechts vom orangefarbenen.

### Schritt 4: Grafikzustand wiederherstellen

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

Das Wiederherstellen setzt das Koordinatensystem in seine ursprüngliche Position zurück, sodass nachfolgende Zeichnungen nicht von der Verschiebung beeinflusst werden.

## Skalierung

> *Sie können dasselbe Muster folgen – Zustand speichern, `Scale` anwenden, zeichnen und dann wiederherstellen.*  
> **Pro Tipp:** Verwenden Sie nicht‑uniforme Skalierung (`Scale(sx, sy)`), um Objekte nur in eine Richtung zu strecken.

## Rotation

> *Rotieren Sie um den Ursprung oder einen benutzerdefinierten Drehpunkt mit `Rotate(angle)`. *  
> **Pro Tipp:** Kombinieren Sie `Translate` vor der Rotation, um um einen bestimmten Punkt zu rotieren.

## Scherung

> *Schertransformationen (`Shear(shx, shy)`) neigen Formen, nützlich für kursive Effekte.*  

## Komplexe Transformationen

> *Für fortgeschrittene Szenarien erstellen Sie eine benutzerdefinierte `Matrix` und übergeben sie an `Transform(matrix)`. *  
Hier **wenden Sie mehrere Transformationen** in einem einzigen Schritt an.

## Fazit

Sie haben gelernt, wie man **PostScript-Datei speichert**, **PostScript-Dokument erstellt** und **mehrere Transformationen** mit Aspose.Page für .NET **anwendet**. Experimentieren Sie mit verschiedenen Transformationsreihenfolgen, kombinieren Sie sie und beobachten Sie, wie sich die Grafiken entwickeln.

## Häufig gestellte Fragen

**F: Wie kann ich mehrere Transformationen auf ein einzelnes Objekt anwenden?**  
A: Verwenden Sie die `Transform`‑Methode mit einer benutzerdefinierten `Matrix`, die Translation, Skalierung, Rotation oder Scherung in der gewünschten Reihenfolge kombiniert.

**F: Kann ich die Transformationen vor dem Speichern des Dokuments ansehen?**  
A: Ja – rendern Sie das `PsDocument` zu einem Bild oder verwenden Sie einen PostScript‑Betrachter, um die Ausgabe zu prüfen, bevor Sie `Save()` aufrufen.

**F: Ist es möglich, Transformationen auf bestimmte Elemente in einem Dokument anzuwenden?**  
A: Absolut. Speichern Sie den Grafikzustand vor dem Zeichnen des Elements, wenden Sie die gewünschte Transformation an, zeichnen Sie und stellen Sie dann den Zustand wieder her.

**F: Gibt es Leistungsaspekte bei komplexen Transformationen?**  
A: Komplexe Matrizen erhöhen die CPU‑Belastung. Halten Sie Transformationen so einfach wie möglich und verwenden Sie gespeicherte Zustände wieder, wenn Sie viele ähnliche Objekte zeichnen.

**F: Wie kann ich Unterstützung oder Hilfe für Aspose.Page‑bezogene Fragen erhalten?**  
A: Besuchen Sie das [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39) für Community‑Hilfe oder kontaktieren Sie den Aspose‑Support direkt.

---

**Last Updated:** 2026-01-12  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}