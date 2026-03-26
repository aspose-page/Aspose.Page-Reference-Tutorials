---
date: 2026-03-26
description: Lernen Sie, wie Sie mit .NET PostScript‑Dokumente mit Textur‑Kachelmustern
  mithilfe von Aspose.Page erstellen. Folgen Sie unserer Schritt‑für‑Schritt‑Anleitung,
  um Ihren PS‑Dateien reiche Texturen hinzuzufügen.
linktitle: Create PostScript .NET document with texture tiling
second_title: Aspose.Page .NET API
title: PostScript .NET‑Dokument mit Texturkachelung erstellen
url: /de/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen Sie ein PostScript‑.NET‑Dokument mit Texturkachelung

## So erstellen Sie ein PostScript‑Dokument .NET mit Texturkachelung

In diesem Tutorial lernen Sie, wie Sie ein **PostScript‑Dokument .NET** erstellen und es mit einem Texturkachel‑Muster mithilfe der Aspose.Page‑Bibliothek anreichern. Wir führen Sie Schritt für Schritt durch den Prozess – von der Projektkonfiguration bis zum Füllen und Umranden von Text mit dem Texturpinsel – sodass Sie in wenigen Minuten ansprechende PS‑Dateien erzeugen können.

## Schnelle Antworten
- **Welche Bibliothek wird verwendet?** Aspose.Page für .NET  
- **Kann ich .NET Core verwenden?** Ja, die Bibliothek unterstützt .NET Core und .NET 5/6  
- **Welche Bildformate funktionieren für die Textur?** Jedes von System.Drawing unterstützte Format (BMP, PNG, JPEG usw.)  
- **Wie lange dauert die Implementierung?** Etwa 10‑15 Minuten für ein einfaches Beispiel  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht für Tests; für den Produktionseinsatz ist eine Lizenz erforderlich  

## Voraussetzungen

- [Visual Studio](https://visualstudio.microsoft.com/) auf Ihrem Rechner installiert.  
- Grundkenntnisse in C#‑Programmierung.  
- Laden Sie die [Aspose.Page für .NET‑Bibliothek](https://releases.aspose.com/page/net/) herunter und installieren Sie sie.  
- Eine Bilddatei für das Texturmuster (z. B. **TestTexture.bmp**).

## Namespaces importieren

Importieren Sie in Ihrer C#‑Datei die benötigten Namespaces, damit der Compiler die verwendeten Typen findet:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Schritt 1: Dokumentverzeichnis festlegen

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Ersetzen Sie **Your Document Directory** durch den Ordner, in dem die erzeugte PS‑Datei gespeichert werden soll.

## Schritt 2: Ausgabestream für das PS‑Dokument erstellen

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

Dieser Block öffnet einen Dateistream, konfiguriert die Seitengröße (standardmäßig A4) und erzeugt eine neue **PsDocument**‑Instanz, auf der wir zeichnen werden.

## Schritt 3: Texturkachel‑Muster anwenden

```csharp
// Create a Bitmap object from the image file
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Create texture brush from the image
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    // Add scaling in X direction to the pattern
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Set this texture brush as the current paint
    document.SetPaint(brush);
}
```

Hier laden wir das Bitmap, verpacken es in einen **TextureBrush**, strecken es optional horizontal und weisen dem **PsDocument** an, diesen Pinsel für nachfolgende Zeichenoperationen zu verwenden.

## Schritt 4: Rechteck‑Pfad erstellen und füllen

```csharp
// Create rectangle path
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Fill rectangle
document.Fill(path);
```

Ein einfaches Rechteck wird definiert und mit dem zuvor gesetzten Texturpinsel gefüllt.

## Schritt 5: Kontur setzen und zeichnen

```csharp
// Get current paint
Brush paint = document.GetPaint();

// Set red stroke
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Stroke the rectangle
document.Draw(path);
```

Wir holen den aktuellen Paint (den Texturpinsel), erstellen einen roten Pen für die Kontur und zeichnen den Rand des Rechtecks.

## Schritt 6: Text mit Texturmuster füllen und umranden

```csharp
// Fill text with texture pattern                
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Outline text with texture pattern
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

Dieser Schritt demonstriert die **fill and stroke text**‑Funktion: Die Zeichen „ABC“ werden mit dem Texturpinsel gefüllt und anschließend umrissen, was einen eindrucksvollen visuellen Effekt erzeugt.

## Schritt 7: Dokument speichern und schließen

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Durch das Schließen der Seite werden die Zeichenbefehle finalisiert, und `Save()` schreibt die PostScript‑Datei auf die Festplatte.

## Häufige Probleme und Lösungen

- **Textur erscheint verzerrt** – Passen Sie die Werte der `Matrix` an, um die Skalierung in X‑ bzw. Y‑Richtung zu steuern.  
- **Bild nicht gefunden** – Stellen Sie sicher, dass `dataDir` auf den richtigen Ordner verweist und der Dateiname exakt (inklusive Groß‑/Kleinschreibung) übereinstimmt.  
- **Farben wirken falsch** – Denken Sie daran, dass PostScript einen geräteunabhängigen Farbraum verwendet; verwenden Sie `Color`‑Objekte, die korrekt gemappt werden.

## Häufig gestellte Fragen

**F:** Kann ich andere Bildformate für das Texturmuster verwenden?  
**A:** Ja, jedes von `System.Drawing.Bitmap` unterstützte Format (BMP, PNG, JPEG, GIF usw.) funktioniert.

**F:** Ist Aspose.Page mit .NET Core kompatibel?  
**A:** Absolut. Die Bibliothek läuft auf .NET Framework, .NET Core und .NET 5/6.

**F:** Wie ändere ich die Größe des texturierten Rechtecks?  
**A:** Passen Sie die Werte von `RectangleF` im Schritt zur Rechteckerstellung an (z. B. `new RectangleF(0, 0, 300, 150)`).

**F:** Kann ich mehrere Texturmuster in einem Dokument anwenden?  
**A:** Ja. Erstellen Sie einfach einen neuen `TextureBrush` mit einem anderen Bild und rufen Sie `SetPaint` erneut auf, bevor Sie die nächste Form oder den nächsten Text zeichnen.

**F:** Wo finde ich weitere Beispiele und die API‑Referenz?  
**A:** Besuchen Sie das [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39) für Community‑Hilfe und die offizielle [Dokumentation](https://reference.aspose.com/page/net/) für detaillierte API‑Nutzung.

## Fazit

Sie wissen jetzt, wie Sie ein **PostScript‑Dokument .NET** erstellen und ein Texturkachel‑Muster darauf anwenden, einschließlich des **fill and stroke text**‑Verfahrens. Experimentieren Sie mit verschiedenen Bildern, Skalierungsmatrizen und Zeichenprimitive, um individuell gestaltete PS‑Dateien für Berichte, Flyer oder andere grafikintensive Ausgaben zu erzeugen.

---

**Zuletzt aktualisiert:** 2026-03-26  
**Getestet mit:** Aspose.Page 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}