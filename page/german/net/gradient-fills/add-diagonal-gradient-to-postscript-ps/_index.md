---
date: 2026-02-23
description: Erfahren Sie, wie Sie einem PostScript‑Datei einen Farbverlauf hinzufügen,
  die PostScript‑Datei mit A4‑Seitengröße speichern und ein Rechteck mit Farbverlauf
  füllen, indem Sie Aspose.Page für .NET verwenden.
linktitle: Add Diagonal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Wie man einen Farbverlauf – Diagonalverlauf in PostScript (PS) mit Aspose.Page
  .NET hinzufügt
url: /de/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
weight: 10
---

Then the footer lines:

"---" keep.

"**Last Updated:** 2026-02-23" -> "**Zuletzt aktualisiert:** 2026-02-23"

"**Tested With:** Aspose.Page for .NET (latest stable release)" -> "**Getestet mit:** Aspose.Page for .NET (neueste stabile Version)"

"**Author:** Aspose" -> "**Autor:** Aspose"

Then closing shortcodes.

Make sure to keep all shortcodes unchanged.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# So fügen Sie einen Farbverlauf hinzu: Diagonalverlauf zu PostScript (PS) mit Aspose.Page .NET

## Einführung

Das Hinzufügen eines diagonalen Farbverlaufs zu einem PostScript (PS)-Dokument kann die visuelle Attraktivität erheblich steigern, insbesondere wenn Sie **wie man einen Farbverlauf hinzufügt**‑Effekte in technischen Berichten, Broschüren oder grafikintensiven Anwendungen benötigen. In diesem Tutorial sehen Sie genau, wie Sie einen Farbverlauf zu einer PostScript‑Datei hinzufügen, eine A4‑Seitengröße festlegen und ein Rechteck mit einem sanften Farbwechsel füllen, wobei Sie Aspose.Page für .NET verwenden.

## Schnelle Antworten
- **Welche Bibliothek wird benötigt?** Aspose.Page for .NET  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6  
- **Kann ich die Richtung des Farbverlaufs ändern?** Ja – drehen Sie die Pinsel‑Transformation wie im Code gezeigt  
- **Wie speichere ich das Ergebnis?** Verwenden Sie `PsDocument.Save()`, das eine PostScript‑Datei auf die Festplatte schreibt  
- **Wird für die Produktion eine Lizenz benötigt?** Ja, eine kommerzielle Lizenz schaltet die volle Funktionalität frei  

## Was ist ein diagonaler Farbverlauf in PostScript?

Ein diagonaler Farbverlauf ist ein linearer Farbwechsel, der in einem Winkel (typischerweise 45°) über eine Form verläuft. In PostScript wird dies erreicht, indem ein `LinearGradientBrush` mit einer benutzerdefinierten Transformationsmatrix angewendet wird, die den Farbverlauf dreht, skaliert und verschiebt, um das gewünschte Rechteck anzupassen.

## Warum Aspose.Page für Farbverlauf‑Füllungen verwenden?

Aspose.Page abstrahiert die Low‑Level‑PostScript‑Befehle und ermöglicht Ihnen die Arbeit mit vertrauten .NET‑Grafikobjekten. Sie können komplexe Füllungen erstellen, Seitenabmessungen festlegen und direkt in eine **save PostScript file** exportieren, ohne sich mit roher PS‑Syntax auseinandersetzen zu müssen.

## Voraussetzungen

- **Aspose.Page for .NET Library** – laden Sie sie [hier](https://releases.aspose.com/page/net/) herunter.  
- **Document Directory** – ein Ordner, in dem die erzeugte `*.ps`‑Datei geschrieben wird.

Jetzt, da wir die Grundlagen abgedeckt haben, gehen wir die Implementierung Schritt für Schritt durch.

## Namespaces importieren

Importieren Sie zunächst die Namespaces, die Ihnen Zugriff auf das EPS‑Gerät, Zeichen‑Hilfsprogramme und I/O‑Klassen geben.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Schritt 1: Ausgabestream für PostScript‑Dokument erstellen (PostScript‑Dokument erstellen)

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## Schritt 2: A4‑Seitengröße festlegen (Speicheroptionen)

```csharp
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();
```

## Schritt 3: Neues 1‑seitiges PS‑Dokument erstellen

```csharp
	// Create new 1-paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Schritt 4: Rechteckparameter definieren

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## Schritt 5: Grafikpfad erstellen

```csharp
	//Create graphics path from the first rectangle
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## Schritt 6: LinearGradientBrush erstellen (Rechteck‑Farbverlauf füllen)

```csharp
	//Create linear gradient brush with rectangle as bounds, start, and end colors
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## Schritt 7: Transform für Pinsel erstellen

```csharp
	//Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
	//Translation components are offsets of the rectangle                
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## Schritt 8: Transformationen auf Pinsel anwenden (Drehen, Skalieren, Verschieben)

```csharp
	//Rotate gradient, then scale and translate to get visible color transition in required rectangle
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## Schritt 9: Transform auf Pinsel setzen

```csharp
	//Set transform
	brush.Transform = brushTransform;
```

## Schritt 10: Paint setzen und Rechteck füllen

```csharp
	//Set paint
	document.SetPaint(brush);

	//Fill the rectangle
	document.Fill(path);
```

## Schritt 11: Aktuelle Seite schließen

```csharp
	//Close current page
	document.ClosePage();
```

## Schritt 12: Dokument speichern (PostScript‑Datei speichern)

```csharp
	//Save the document
	document.Save();
}
// ExEnd:1
```

## So speichern Sie die PostScript‑Datei

Der Aufruf `PsDocument.Save()` schreibt den vollständig erzeugten PostScript‑Inhalt in den Stream, den Sie in **Schritt 1** geöffnet haben. Nach Abschluss des `using`‑Blocks ist die Datei `DiagonaGradient_outPS.ps` im von Ihnen angegebenen Verzeichnis verfügbar.

## Häufige Anwendungsfälle

- **Technische Dokumentation**, die eine subtile Hintergrundschattierung benötigt.  
- **Marketing‑Broschüren**, bei denen ein diagonaler Farbverlauf ein modernes Aussehen verleiht.  
- **Automatisierte Berichtsgeneratoren**, die Druck‑PS‑Dateien on‑the‑fly erzeugen.  

## Fehlerbehebung & Tipps

- **Falsche Farben** – überprüfen Sie die an `LinearGradientBrush` übergebenen ARGB‑Werte.  
- **Farbverlauf nicht sichtbar** – stellen Sie sicher, dass die Transformationsmatrix korrekt rotiert und skaliert; der Aufruf `Rotate(-45)` setzt den diagonalen Winkel.  
- **Datei nicht erstellt** – prüfen Sie, ob `dataDir` auf einen vorhandenen Ordner zeigt und die Anwendung Schreibrechte hat.  

## Häufig gestellte Fragen

**F: Ist Aspose.Page mit allen .NET‑Frameworks kompatibel?**  
A: Aspose.Page unterstützt eine breite Palette von .NET‑Versionen, von .NET Framework 4.5+ bis .NET 6+, und gewährleistet damit eine große Kompatibilität.

**F: Kann ich die Farbverlauf‑Farben in Aspose.Page anpassen?**  
A: Ja, Sie können beim Erstellen von `LinearGradientBrush` beliebige ARGB‑Farben angeben, wodurch Sie die volle Kontrolle über Start‑ und Endtöne haben.

**F: Gibt es eine Testversion von Aspose.Page?**  
A: Ja, Sie können die Funktionen von Aspose.Page erkunden, indem Sie die Testversion [hier](https://releases.aspose.com/) herunterladen.

**F: Wie kann ich eine temporäre Lizenz für Aspose.Page erhalten?**  
A: Holen Sie sich eine temporäre Lizenz für Aspose.Page [hier](https://purchase.aspose.com/temporary-license/), um während der Evaluierung zusätzliche Funktionen freizuschalten.

**F: Wo finde ich Community‑Support für Aspose.Page?**  
A: Treten Sie mit der Aspose.Page‑Community im [Forum](https://forum.aspose.com/c/page/39) in Kontakt für Unterstützung und Diskussionen.

---

**Zuletzt aktualisiert:** 2026-02-23  
**Getestet mit:** Aspose.Page for .NET (neueste stabile Version)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}