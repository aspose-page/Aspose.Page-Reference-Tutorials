---
title: Fügen Sie mit Aspose.Page für .NET Rechteck zu PostScript (PS) hinzu
linktitle: Rechteck zu PostScript hinzufügen (PS)
second_title: Aspose.Page .NET-API
description: Verbessern Sie die Dokumenterstellung in .NET mit Aspose.Page. Erfahren Sie Schritt für Schritt, wie Sie Rechtecke zu PostScript-Dateien (PS) hinzufügen.
type: docs
weight: 12
url: /de/net/drawing-shapes/add-rectangle-to-postscript-ps/
---
## Einführung

Wenn Sie Ihre Dokumenterstellungsfunktionen in .NET erweitern möchten, bietet Aspose.Page eine leistungsstarke Lösung für die Verarbeitung von PostScript-Dokumenten. In diesem Tutorial führen wir Sie durch den Prozess des Hinzufügens von Rechtecken zu einem PostScript-Dokument mit Aspose.Page für .NET.

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Aspose.Page für .NET-Bibliothek: Laden Sie die Aspose.Page für .NET-Bibliothek von herunter und installieren Sie sie[Hier](https://releases.aspose.com/page/net/).

- Entwicklungsumgebung: Stellen Sie sicher, dass auf Ihrem Computer eine .NET-Entwicklungsumgebung eingerichtet ist.

## Namespaces importieren

Stellen Sie vor dem Codieren sicher, dass Sie die erforderlichen Namespaces importieren, um auf die erforderlichen Klassen und Methoden zuzugreifen:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Lassen Sie uns das Beispiel nun in mehrere Schritte unterteilen:

## Schritt 1: Richten Sie Ihr Dokumentenverzeichnis ein

```csharp
// ExStart:1
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "Your Document Directory";
```

Ersetzen Sie in diesem Schritt „Ihr Dokumentverzeichnis“ durch den Pfad, in dem Sie Ihr PostScript-Dokument speichern möchten.

## Schritt 2: Ausgabestream für PostScript-Dokument erstellen

```csharp
//Erstellen Sie einen Ausgabestream für ein PostScript-Dokument
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Hier erstellen wir einen Ausgabestream für das PostScript-Dokument und geben den Dateinamen an („AddRectangle_outPS.ps“). Passen Sie den Dateinamen und den Speicherort nach Ihren Wünschen an.

## Schritt 3: Legen Sie die Speicheroptionen fest und erstellen Sie ein PS-Dokument

```csharp
//Erstellen Sie Speicheroptionen im A4-Format
PsSaveOptions options = new PsSaveOptions();

// Erstellen Sie ein neues einseitiges PS-Dokument
PsDocument document = new PsDocument(outPsStream, options, false);
```

Legen Sie die Speicheroptionen fest und geben Sie die gewünschte Seitengröße an (in diesem Fall A4). Erstellen Sie dann ein neues einseitiges PostScript-Dokument.

## Schritt 4: Rechteck und Füllung hinzufügen

```csharp
//Erstellen Sie einen Grafikpfad aus dem ersten Rechteck
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Farbe einstellen
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Füllen Sie das Rechteck
document.Fill(path);
```

Hier erstellen wir einen Grafikpfad, der das erste Rechteck darstellt, legen die Farbe fest (in diesem Fall Orange) und füllen das Rechteck.

## Schritt 5: Fügen Sie ein weiteres Rechteck und einen weiteren Strich hinzu

```csharp
//Erstellen Sie einen Grafikpfad aus dem zweiten Rechteck
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Hub einstellen
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Zeichnen Sie den Umriss des Rechtecks
document.Draw(path);
```

Ähnlich wie im vorherigen Schritt erstellen wir einen Grafikpfad für das zweite Rechteck, legen die Strichfarbe fest (Rot mit einer Stärke von 3) und umreißen das Rechteck.

## Schritt 6: Schließen Sie die Seite und speichern Sie das Dokument

```csharp
//Aktuelle Seite schließen
document.ClosePage();

//Speichern Sie das Dokument
document.Save();
```

Schließen Sie abschließend die aktuelle Seite und speichern Sie das gesamte Dokument.

## Abschluss

Glückwunsch! Sie haben mit Aspose.Page für .NET erfolgreich Rechtecke zu einem PostScript-Dokument hinzugefügt. In diesem Tutorial wurden die wesentlichen Schritte behandelt, von der Einrichtung Ihrer Entwicklungsumgebung bis zum Speichern des endgültigen Dokuments.

## FAQs

### F1: Kann ich die Farben der Rechtecke anpassen?

A1: Ja, Sie können die Farben anpassen, indem Sie die Parameter im anpassen`SolidBrush` Und`Pen` Klassen.

### F2: Ist Aspose.Page mit anderen Dokumentformaten kompatibel?

A2: Ja, Aspose.Page unterstützt verschiedene Dokumentformate, einschließlich XPS und PostScript.

### F3: Wie kann ich dem Dokument Text hinzufügen?

 A3: Sie können das verwenden`TextFragment` Klasse in Aspose.Page, um Text zu Ihrem Dokument hinzuzufügen.

### F4: Wo finde ich zusätzliche Beispiele und Dokumentation?

 A4: Sehen Sie sich die Dokumentation an[Hier](https://reference.aspose.com/page/net/) und besuchen Sie die[Aspose.Page-Forum](https://forum.aspose.com/c/page/39) für die Unterstützung der Gemeinschaft.

### F5: Kann ich Aspose.Page vor dem Kauf testen?

 A5: Ja, Sie können eine kostenlose Testversion erhalten[Hier](https://releases.aspose.com/) , und für längere Verwendung, erwägen Sie a[temporäre Lizenz](https://purchase.aspose.com/temporary-license/).
