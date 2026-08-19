---
date: 2026-02-25
description: Verbessern Sie PostScript‑Dokumente mit einem linearen Farbverlauf‑Rechteck
  mithilfe von Aspose.Page für .NET. Folgen Sie unserer Schritt‑für‑Schritt‑Anleitung,
  um das Füllen von Text mit Farbverlauf und den Farbverlauf von Textumrissen zu erlernen.
linktitle: Add Horizontal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Ein Rechteck mit linearem Farbverlauf zu PostScript (PS) mit Aspose.Page hinzufügen
url: /de/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ein lineares Farbverlaufsrechteck zu PostScript (PS) mit Aspose.Page hinzufügen

## Einführung

Willkommen zu diesem umfassenden Tutorial, in dem gezeigt wird, wie man ein **lineares Farbverlaufsrechteck** zu PostScript (PS)-Dokumenten mit Aspose.Page für .NET hinzufügt. Aspose.Page ist eine leistungsstarke Bibliothek, die es Ihnen ermöglicht, Dokumente in verschiedenen Formaten zu erstellen, zu ändern und zu rendern, und heute konzentrieren wir uns darauf, wie Sie auffällige Verläufe in Ihre PS‑Dateien einbringen.

### Schnelle Antworten
- **Was macht das lineare Farbverlaufsrechteck?** Es füllt einen rechteckigen Bereich mit einem sanften Farbwechsel von einer Seite zur anderen.  
- **Welche API verarbeitet den Farbverlauf‑Fülltext?** `LinearGradientBrush` kombiniert mit `SetPaint` und `FillAndStrokeText`.  
- **Kann ich Text mit einem Farbverlauf umranden?** Ja — verwenden Sie `SetStroke` mit einem Farbverlaufs‑Brush und rufen Sie `OutlineText` auf.  
- **Benötige ich eine Lizenz für die Produktion?** Für den nicht‑evaluativen Einsatz ist eine kommerzielle Aspose.Page‑Lizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Voraussetzungen

Bevor wir starten, stellen Sie sicher, dass Sie Folgendes haben:

- Aspose.Page for .NET Library: Stellen Sie sicher, dass die Bibliothek in Ihrem Projekt referenziert ist. Sie können sie aus der [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/) herunterladen.  
- Document Directory: Erstellen Sie einen Ordner auf dem Datenträger, in dem die erzeugte PS‑Datei gespeichert wird, und ersetzen Sie **„Your Document Directory“** im Code durch diesen Pfad.

## Namespaces importieren

Um zu beginnen, importieren Sie die Namespaces, die Ihnen Zugriff auf die Zeichen‑ und PS‑spezifischen Klassen geben:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Was ist ein lineares Farbverlaufsrechteck?

Ein **lineares Farbverlaufsrechteck** ist einfach eine rechteckige Form, deren Innenfläche mit einem linearen Farbverlauf gefüllt ist — die Farben gehen dabei sanft entlang einer geraden Linie über, typischerweise von links nach rechts (horizontal) oder von oben nach unten (vertikal). In Aspose.Page erreichen Sie dies, indem Sie einen `GraphicsPath`, der das Rechteck definiert, mit einem `LinearGradientBrush` kombinieren, der den Farbwechsel beschreibt.

## Warum Farbverlauf‑Fülltext und Kontur‑Farbverlauf verwenden?

- **Visuelle Attraktivität:** Mit Farbverlauf‑gefülltem Text erhalten Berichte, Rechnungen oder Werbematerialien Tiefe und ein modernes Design.  
- **Markenkonsistenz:** Passen Sie Unternehmensfarben mit genauen ARGB‑Werten an.  
- **Vielseitigkeit:** Derselbe Brush kann für Formfüllungen, Textfüllungen und Kontur‑Verläufe wiederverwendet werden, wodurch Code‑Duplikate reduziert werden.

## Schritt 1: Dokument einrichten

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## Schritt 2: Farbverlaufsrechteck und Farben definieren

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // Create graphics path from the first rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    // Create linear gradient brush with rectangle as bounds, start, and end colors
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## Schritt 3: Transformation für den Pinsel festlegen

```csharp
    // Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    // Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Set transform
    brush.Transform = brushTransform;
```

## Schritt 4: Paint setzen und das Rechteck füllen

```csharp
    // Set paint
    document.SetPaint(brush);

    // Fill the rectangle
    document.Fill(path);
```

## Wie man Farbverlauf‑Fülltext anwendet

```csharp
    // Fill text with gradient
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## Verwendung von Kontur‑Farbverlauf für Text

```csharp
    // Set current stroke
    document.SetStroke(new Pen(brush, 5));
    // Outline text with gradient
    document.OutlineText("ABC", font, 200, 400);
```

## Schritt 7: Aktuelle Seite schließen und Dokument speichern

```csharp
    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Herzlichen Glückwunsch! Sie haben erfolgreich ein **lineares Farbverlaufsrechteck** zu einem PostScript‑Dokument hinzugefügt und denselben Brush für **Farbverlauf‑Fülltext** sowie einen **Kontur‑Farbverlauf für Text** verwendet.

## Häufige Anwendungsfälle & Tipps

- **Berichts‑Überschriften:** Füllen Sie große Textblöcke mit Verläufen, um Abschnittstitel hervorzuheben.  
- **Marken‑Logos:** Reproduzieren Sie Logo‑Formen mit Farbverlauf‑gefüllten Formen für ein konsistentes Branding.  
- **Pro‑Tipp:** Verwenden Sie dieselbe `LinearGradientBrush`‑Instanz für mehrere Zeichenaufrufe, um die Farben über Formen und Text hinweg perfekt abzustimmen.

## Häufig gestellte Fragen

### F1: Kann ich Verläufe auf andere Formen als Rechtecke anwenden?
**A:** Ja, Sie können Verläufe auf jede Form anwenden, die durch einen `GraphicsPath` definiert ist. Fügen Sie einfach Kreise, Polygone oder benutzerdefinierte Pfade hinzu, bevor Sie `document.Fill(path)` aufrufen.

### F2: Wie kann ich die Farben des Farbverlaufs ändern?
**A:** Ändern Sie die `Color.FromArgb`‑Werte beim Erzeugen des `LinearGradientBrush`. Die erste Farbe ist der Start, die zweite die Endfarbe des Verlaufs.

### F3: Ist Aspose.Page mit verschiedenen Dokumentformaten kompatibel?
**A:** Absolut. Aspose.Page unterstützt XPS, PS, PDF und mehrere weitere Vektorformate. Die offizielle Dokumentation enthält die vollständige Liste.

### F4: Kann ich Aspose.Page für kommerzielle Projekte nutzen?
**A:** Ja, eine kommerzielle Lizenz ist verfügbar. Einzelheiten finden Sie auf der Kaufseite: [here](https://purchase.aspose.com/buy).

### F5: Wo finde ich Community‑Support?
**A:** Treten Sie dem Aspose.Page‑Community‑Forum bei: [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

---

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.Page 24.10 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}