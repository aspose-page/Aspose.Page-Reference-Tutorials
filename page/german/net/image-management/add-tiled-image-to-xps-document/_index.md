---
date: 2026-03-03
description: Erfahren Sie, wie Sie Aspose.Page für .NET verwenden, um Bilder in XPS‑Dokumenten
  zu kacheln. Diese Schritt‑für‑Schritt‑Anleitung zeigt, wie man Bilder effizient
  kachelt und die visuelle Attraktivität steigert.
linktitle: Add Tiled Image to XPS Document
second_title: Aspose.Page .NET API
title: Wie man Aspose.Page verwendet, um ein gekacheltes Bild zu einem XPS-Dokument
  hinzuzufügen
url: /de/net/image-management/add-tiled-image-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Aspose.Page verwendet, um ein gekacheltes Bild zu einem XPS-Dokument hinzuzufügen

## Einleitung

Wenn Sie sich fragen **wie man Aspose** verwendet, um Ihren XPS-Dateien einen reicheren visuellen Stil zu verleihen, sind Sie hier genau richtig. In diesem Tutorial führen wir Sie durch die genauen Schritte, die erforderlich sind, um **ein Bild zu kacheln** innerhalb eines XPS-Dokuments mit Aspose.Page für .NET. Am Ende haben Sie einen wiederverwendbaren Code‑Snippet, den Sie in jedes .NET‑Projekt einbinden können, um gekachelte Bildgrafiken on‑the‑fly zu erstellen.

## Schnelle Antworten
- **Welche Bibliothek wird benötigt?** Aspose.Page for .NET  
- **Welche Methode erstellt den gekachelten Pinsel?** `CreateImageBrush` mit `TileMode = XpsTileMode.Tile`  
- **Kann ich die Deckkraft steuern?** Ja – setzen Sie `path.Fill.Opacity` (z. B. 0.5f)  
- **Brauche ich eine Lizenz für Tests?** Eine temporäre Lizenz funktioniert für die Evaluierung; eine Voll‑Lizenz ist für die Produktion erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6!

## Was ist Aspose.Page und warum Bilder kacheln?

Aspose.Page ist eine leistungsstarke API, die Entwicklern ermöglicht, XPS, PDF und andere seitenbasierte Formate zu erzeugen, zu bearbeiten und zu rendern, ohne Microsoft Office zu benötigen. Das Kacheln eines Bildes – das Wiederholen einer Bitmap über einer Form – hilft Ihnen, große Flächen mit Mustern, Wasserzeichen oder Hintergrundtexturen zu füllen, während die Dateigröße gering bleibt.

## Wie man Aspose.Page verwendet, um Bilder in XPS-Dokumenten zu kacheln

Im Folgenden finden Sie ein komplettes, sofort ausführbares Beispiel. Jeder Schritt wird in einfacher Sprache erklärt, bevor der entsprechende Code‑Block folgt, sodass Sie **verstehen**, warum jede Zeile wichtig ist.

### Voraussetzungen

- **Aspose.Page for .NET** – Laden Sie die Bibliothek von der offiziellen Seite [hier](https://reference.aspose.com/page/net/) herunter und binden Sie sie ein.  
- **Entwicklungsumgebung** – Visual Studio (jede Edition) oder eine andere .NET‑IDE Ihrer Wahl.

### Namespaces importieren

Zuerst bringen Sie die erforderlichen Namespaces in den Gültigkeitsbereich, damit der Compiler weiß, wo die XPS‑Klassen zu finden sind.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

### Schritt 1: Das Dokumentverzeichnis festlegen

Geben Sie an, wo die erzeugte XPS‑Datei und das Quellbild gespeichert werden sollen. Ersetzen Sie den Platzhalter durch einen tatsächlichen Ordner auf Ihrem Rechner.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Schritt 2: Ein neues XPS‑Dokument erstellen

Instanziieren Sie ein leeres XPS‑Dokument, das die gekachelte Grafik enthalten wird.

```csharp
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Schritt 3: Ein gekacheltes Bild hinzufügen

Hier erstellen wir einen rechteckigen Pfad, füllen ihn mit einem `ImageBrush` und setzen den Pinsel auf den Kachelmodus. Die Eigenschaft `TileMode` weist die Engine an, das Bild sowohl horizontal als auch vertikal zu wiederholen. Passen Sie die Rechteckkoordinaten oder das Quellbild nach Bedarf für Ihr Szenario an.

```csharp
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

### Schritt 4: Das resultierende XPS‑Dokument speichern

Abschließend schreiben Sie das Dokument auf die Festplatte. Die Ausgabedatei kann mit jedem XPS‑Viewer geöffnet oder weiter mit Aspose.Page verarbeitet werden.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

## Häufige Probleme & Tipps

- **Pfad‑Fehler** – Stellen Sie sicher, dass `dataDir` mit einem abschließenden Schrägstrich endet oder verwenden Sie `Path.Combine`, um fehlende Trennzeichen zu vermeiden.  
- **Bildgrößen‑Unstimmigkeiten** – Das Quellbild sollte groß genug für den Kachelbereich sein; andernfalls kann das Muster gestreckt erscheinen.  
- **Deckkraft nicht sichtbar** – Einige Viewer ignorieren die Deckkraft bei XPS; testen Sie mit einem Viewer, der XPS‑Rendering vollständig unterstützt (z. B. XPS Viewer unter Windows).

## Häufig gestellte Fragen

### Q1: Ist Aspose.Page mit allen .NET‑Entwicklungsumgebungen kompatibel?

A: Ja, Aspose.Page funktioniert mit Visual Studio, Rider, VS Code und jeder IDE, die .NET unterstützt.

### Q2: Kann ich die Deckkraft des gekachelten Bildes anpassen?

A: Absolut. Das Beispiel setzt `path.Fill.Opacity = 0.5f;` – Sie können den Float‑Wert zwischen 0 (transparent) und 1 (undurchsichtig) ändern.

### Q3: Gibt es weitere Kachelmodi in Aspose.Page für .NET?

A: Ja. Neben `XpsTileMode.Tile` können Sie `FlipX`, `FlipY` und `FlipXY` verwenden, um gespiegelte Muster zu erzeugen.

### Q4: Wie gehe ich mit temporären Lizenzen für Aspose.Page um?

A: Siehe die Seite für [temporäre Lizenzen](https://purchase.aspose.com/temporary-license/) auf der Aspose‑Website für Details zum Erhalt und zur Anwendung einer Testlizenz.

### Q5: Wo kann ich Hilfe erhalten oder mich mit der Aspose.Page‑Community vernetzen?

A: Besuchen Sie das [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39), um Fragen zu stellen, Snippets zu teilen und von anderen Entwicklern zu lernen.

### Q6: Kann ich diesen Ansatz verwenden, um einen Wasserzeichen‑Effekt zu erzeugen?

A: Ja. Durch Verringern der Deckkraft und Auswahl eines halbtransparenten Bildes funktioniert der gekachelte Pinsel perfekt als wiederholendes Wasserzeichen.

## Fazit

Sie wissen jetzt **wie man Aspose** verwendet, um einem XPS‑Dokument ein gekacheltes Bild hinzuzufügen, die Deckkraft zu steuern und das Ergebnis für die weitere Verwendung zu speichern. Diese Technik ist ideal für Hintergrundmuster, Wasserzeichen oder jede Situation, in der ein wiederholendes Grafik‑Element visuelles Interesse erzeugt, ohne die Dateigröße zu erhöhen. Experimentieren Sie gern mit verschiedenen Formen, Bildern und Kachelmodi, um den Bedürfnissen Ihres Projekts gerecht zu werden.

---

**Zuletzt aktualisiert:** 2026-03-03  
**Getestet mit:** Aspose.Page for .NET (neueste Version)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}