---
title: Wenden Sie mit Aspose.Page ein Texturkachelmuster auf PostScript (PS) an
linktitle: Anwenden von Texturkachelmuster auf PostScript (PS)
second_title: Aspose.Page .NET-API
description: Erweitern Sie Ihre PostScript-Dokumente (PS) mit Texturkachelmustern mithilfe von Aspose.Page für .NET. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für eine kreative Note.
type: docs
weight: 10
url: /de/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
---
## Einführung

Willkommen zu dieser Schritt-für-Schritt-Anleitung zum Anwenden eines Texturkachelmusters auf ein PostScript-Dokument (PS) mit Aspose.Page für .NET. Aspose.Page ist eine leistungsstarke Bibliothek, die Ihnen die Arbeit mit verschiedenen Dokumentformaten ermöglicht. In diesem Tutorial erfahren Sie, wie Sie Ihre PS-Dokumente durch das Hinzufügen von Texturkachelmustern verbessern können.

## Voraussetzungen

Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- [Visual Studio](https://visualstudio.microsoft.com/) auf Ihrem Computer installiert.
- Grundkenntnisse der C#-Programmierung.
-  Laden Sie das herunter und installieren Sie es[Aspose.Page für .NET-Bibliothek](https://releases.aspose.com/page/net/).
- Eine Bilddatei für das Texturmuster (z. B. „TestTexture.bmp“).

## Namespaces importieren

Stellen Sie in Ihrem C#-Code sicher, dass Sie die erforderlichen Namespaces importieren:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Lassen Sie uns das bereitgestellte Beispiel in mehrere Schritte unterteilen, um Sie durch den Prozess zu führen.

## Schritt 1: Dokumentenverzeichnis einrichten

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "Your Document Directory";
```

Stellen Sie sicher, dass Sie „Ihr Dokumentverzeichnis“ durch den Pfad ersetzen, in dem Sie Ihr PS-Dokument speichern möchten.

## Schritt 2: Ausgabestream für PS-Dokument erstellen

```csharp
// Erstellen Sie einen Ausgabestream für ein PostScript-Dokument
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Erstellen Sie Speicheroptionen im A4-Format
    PsSaveOptions options = new PsSaveOptions();

    // Erstellen Sie ein neues einseitiges PS-Dokument
    PsDocument document = new PsDocument(outPsStream, options, false);
```

In diesem Schritt wird der Ausgabestream für das PS-Dokument eingerichtet, einschließlich der Definition der Dokumentgröße.

## Schritt 3: Texturkachelmuster anwenden

```csharp
// Erstellen Sie ein Bitmap-Objekt aus der Bilddatei
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Erstellen Sie einen Texturpinsel aus dem Bild
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    //Fügen Sie dem Muster eine Skalierung in X-Richtung hinzu
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Legen Sie diesen Texturpinsel als aktuelle Farbe fest
    document.SetPaint(brush);
}
```

In diesem Schritt erstellen Sie einen Texturpinsel aus einem Bild und legen ihn als aktuelle Farbe für das Dokument fest.

## Schritt 4: Erstellen Sie einen rechteckigen Pfad und füllen Sie ihn

```csharp
// Erstellen Sie einen rechteckigen Pfad
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Rechteck füllen
document.Fill(path);
```

Hier definieren wir einen rechteckigen Pfad und füllen ihn mit dem zuvor festgelegten Texturpinsel.

## Schritt 5: Legen Sie Strich und Zeichnung fest

```csharp
// Besorgen Sie sich aktuelle Lackierung
Brush paint = document.GetPaint();

// Roten Strich setzen
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Streichen Sie über das Rechteck
document.Draw(path);
```

Dieser Schritt umfasst das Festlegen der Stricheigenschaften und das Zeichnen des umrissenen Rechtecks.

## Schritt 6: Text mit Texturmuster füllen und umreißen

```csharp
// Text mit Texturmuster füllen
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Umrisstext mit Texturmuster
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

Abschließend füllen und umreißen wir den Text mit dem Texturmuster und verbessern so die optische Attraktivität Ihres Dokuments.

## Schritt 7: Dokument speichern und schließen

```csharp
// Aktuelle Seite schließen
document.ClosePage();

// Speichern Sie das Dokument
document.Save();
```

Stellen Sie sicher, dass Sie die aktuelle Seite schließen und das Dokument speichern, um die Änderungen zu übernehmen.

## Abschluss

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Page für .NET ein Texturkachelmuster auf ein PostScript-Dokument anwenden. Experimentieren Sie mit verschiedenen Bildern und Mustern, um Ihre PS-Dokumente noch individueller zu gestalten.

## FAQs

### F1: Kann ich andere Bildformate für das Texturmuster verwenden?

A1: Ja, Aspose.Page unterstützt verschiedene Bildformate. Stellen Sie die Kompatibilität mit der Bibliotheksdokumentation sicher.

### F2: Ist Aspose.Page mit .NET Core kompatibel?

A2: Ja, Aspose.Page ist sowohl mit .NET Framework als auch mit .NET Core kompatibel.

### F3: Wie kann ich die Größe des strukturierten Rechtecks anpassen?

 A3: Ändern Sie die Abmessungen im`RectangleF` Parameter während der Pfaderstellung.

### F4: Kann ich einem einzelnen Dokument mehrere Texturmuster hinzufügen?

A4: Ja, Sie können den Vorgang mit verschiedenen Bildern und Pfaden wiederholen.

### F5: Wo finde ich zusätzliche Ressourcen und Unterstützung?

 A5: Besuchen Sie die[Aspose.Page-Forum](https://forum.aspose.com/c/page/39) für Community-Unterstützung und erkunden Sie die[Dokumentation](https://reference.aspose.com/page/net/).
