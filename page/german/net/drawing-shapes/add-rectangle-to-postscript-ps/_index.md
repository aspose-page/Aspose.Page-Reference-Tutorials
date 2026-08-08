---
date: 2026-06-30
description: Erfahren Sie, wie Sie ein PostScript-Dokument in .NET erstellen und Rechtecke
  mit Aspose.Page für .NET hinzufügen. Schritt-für-Schritt-Anleitung mit Code-Beispielen.
keywords:
- create postscript document .net
- how to generate postscript file
- Aspose.Page rectangle
linktitle: Rechteck zu PostScript (PS) hinzufügen
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create postscript document .net and add rectangles using
    Aspose.Page for .NET. Step‑by‑step guide with code samples.
  headline: Create PostScript Document .NET – Add Rectangle Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page for .NET.
    question: What library do I need?
  - answer: Yes – the API lets you build PS files programmatically.
    question: Can I create a PostScript document from scratch?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: Typically under 10 minutes for basic shapes.
    question: How long does the implementation take?
  type: FAQPage
second_title: Aspose.Page .NET API
title: PostScript-Dokument .NET erstellen – Rechteck hinzufügen Aspose.Page
url: /de/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rechteck zu PostScript (PS) mit Aspose.Page für .NET hinzufügen

## Einleitung

Aspose.Page for .NET ist eine Bibliothek, die die programmgesteuerte Erstellung und Manipulation von PostScript-, EPS- und XPS-Dateien ermöglicht. Wenn Sie **postscript document .net erstellen** möchten, führt Sie dieses Tutorial durch das Hinzufügen von Rechtecken zu einem PostScript-Dokument mit Aspose.Page und gibt Ihnen eine solide Grundlage für die Erstellung komplexerer Grafiken.

## Schnelle Antworten
- **Welche Bibliothek benötige ich?** Aspose.Page for .NET.  
- **Kann ich ein PostScript-Dokument von Grund auf neu erstellen?** Ja – die API ermöglicht das programmgesteuerte Erstellen von PS-Dateien.  
- **Welche .NET-Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion funktioniert für Tests; für die Produktion ist eine Lizenz erforderlich.  
- **Wie lange dauert die Implementierung?** In der Regel weniger als 10 Minuten für Grundformen.

## Was ist das Erstellen eines postscript document .net?
Das Erstellen eines PostScript-Dokuments in .NET bedeutet, programmgesteuert eine `.ps`‑Datei zu erzeugen, die den Seiteninhalt – Text, Grafiken oder Formen – mithilfe der Aspose.Page‑API beschreibt. Dieser Ansatz ist ideal für serverseitige Grafikgenerierung, automatisierte Berichtserstellung oder jede Situation, in der Sie eine präzise Kontrolle über das Ausgabeformat benötigen.

## Warum Aspose.Page für .NET verwenden?
Aspose.Page unterstützt **30+ Grafikprimitive** und kann Dateien bis zu **500 MB** erzeugen, ohne das gesamte Dokument in den Speicher zu laden, und liefert Hochleistungs‑Rendering unter Windows, Linux und macOS. Es gibt Ihnen volle Kontrolle über Formen, Farben und Striche, während es die Notwendigkeit eliminiert, Low‑Level‑PostScript‑Code zu schreiben.

- **Vollständige Kontrolle über Grafiken** – Formen zeichnen, Farben festlegen und Striche anwenden, ohne sich mit Low‑Level‑PS‑Syntax auseinandersetzen zu müssen.  
- **Plattformübergreifend** – funktioniert unter Windows-, Linux- und macOS‑Laufzeiten.  
- **Keine externen Abhängigkeiten** – die Bibliothek übernimmt die gesamte PS‑Erzeugung intern.  
- **Umfangreiche Dokumentation & Beispiele** – schnell einsatzbereit.

## Voraussetzungen

- **Aspose.Page for .NET Bibliothek** – herunterladen und installieren von [here](https://releases.aspose.com/page/net/).  
- **Entwicklungsumgebung** – Visual Studio, VS Code oder jede .NET‑kompatible IDE.

## Namespaces importieren

Der Namespace `Aspose.Page` stellt die Kernklassen bereit, die Sie benötigen, wie `Document`, `Page`, `SolidBrush` und `Pen`. Importieren Sie ihn, bevor Sie mit dem Codieren beginnen.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Jetzt teilen wir das Beispiel in klare, nummerierte Schritte auf.

## Schritt 1: Dokumentverzeichnis einrichten

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Ersetzen Sie `"Your Document Directory"` durch den Ordner, in dem die resultierende PS‑Datei gespeichert werden soll.

## Schritt 2: Ausgabestream für das PostScript-Dokument erstellen

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Dieser Stream verweist auf **AddRectangle_outPS.ps**. Sie können die Datei nach Belieben umbenennen oder den Speicherort bei Bedarf ändern.

## Schritt 3: Speicheroptionen festlegen und das PS‑Dokument erstellen

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Hier teilen wir Aspose.Page mit, ein A4‑Seitenformat zu verwenden und ein einseitiges Dokument zu erstellen.

## Schritt 4: Gefülltes Rechteck hinzufügen

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

Wir definieren ein Rechteck bei (250, 100) mit einer Breite von 150 und einer Höhe von 100, setzen einen orangefarbenen Pinsel und füllen die Form.

## Schritt 5: Umrandetes Rechteck hinzufügen

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

Ein zweites Rechteck wird weiter unten auf der Seite erstellt, diesmal mit einem roten 3‑Punkt‑Strich.

## Schritt 6: Seite schließen und Dokument speichern

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Das Schließen der Seite finalisiert die Zeichnung, und `Save()` schreibt die PS‑Datei auf die Festplatte.

## Wie erstelle ich ein postscript document .net?
`Document` ist die Hauptklasse, die eine PostScript‑Datei in Aspose.Page repräsentiert. `SaveOptions` legt Einstellungen wie Seitengröße und Ausgabeformat für das Dokument fest. Laden Sie das `Document`‑Objekt, konfigurieren Sie `SaveOptions` für eine A4‑Seite, zeichnen Sie Ihre Formen mit `SolidBrush` oder `Pen` und rufen Sie anschließend `document.Save()` auf – der gesamte Arbeitsablauf erfordert nur wenige Codezeilen und läuft auf jeder unterstützten .NET‑Runtime. Dieses Muster ermöglicht das Erzeugen vollständig konformer PostScript‑Dateien, ohne rohen PS‑Code zu verwenden.

## Wie generiere ich eine postscript-Datei
Verwenden Sie die `SaveOptions`‑Klasse von Aspose.Page, um das Ausgabeformat als PostScript (`SaveFormat.PS`) festzulegen. Die Bibliothek streamt den Inhalt direkt in eine Datei oder einen Memory‑Stream, sodass Sie große Dokumente effizient erzeugen können, ohne übermäßigen Speicherverbrauch.

## Häufige Probleme & Tipps

- **Falscher Dateipfad** – Stellen Sie sicher, dass `dataDir` mit einem Pfadtrennzeichen (`\\` oder `/`) endet oder verwenden Sie `Path.Combine`.  
- **Fehlende Lizenz** – In einer Produktionsumgebung sollten Sie Ihre Aspose‑Lizenz vor dem Erstellen des Dokuments anwenden, um Evaluations‑Wasserzeichen zu vermeiden.  
- **Farbensichtbarkeit** – Wenn das Rechteck leer erscheint, prüfen Sie, ob die Pinsel‑ oder Stiftfarben im Kontrast zum Seitenhintergrund stehen.

## Häufig gestellte Fragen

**Q:** Kann ich die Farben der Rechtecke anpassen?  
**A:** Absolut. Ändern Sie die Werte `Color.Orange` oder `Color.Red` in den Konstruktoren von `SolidBrush` und `Pen` zu jeder gewünschten `System.Drawing.Color`.

**Q:** Ist Aspose.Page mit anderen Dokumentformaten kompatibel?  
**A:** Ja. Neben PostScript unterstützt Aspose.Page auch die Erzeugung von XPS und EPS.

**Q:** Wie kann ich Text zum selben Dokument hinzufügen?  
**A:** Verwenden Sie die Klasse `TextFragment`, um Text an gewünschten Koordinaten zu platzieren, und rufen Sie anschließend `document.Draw(textFragment)` auf.

**Q:** Wo finde ich weitere Beispiele und die vollständige API‑Referenz?  
**A:** Durchsuchen Sie die Dokumentation [here](https://reference.aspose.com/page/net/) und treten Sie der Community im [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39) bei.

**Q:** Kann ich Aspose.Page vor dem Kauf testen?  
**A:** Ja, laden Sie eine kostenlose Testversion [here](https://releases.aspose.com/) herunter. Für eine erweiterte Evaluierung sollten Sie eine [temporary license](https://purchase.aspose.com/temporary-license/) in Betracht ziehen.

**Zuletzt aktualisiert:** 2026-06-30  
**Getestet mit:** Aspose.Page 24.12 für .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Wie man ein PostScript-Dokument mit Aspose.Page für .NET erstellt](/page/net/document-creation/create-postscript-document/)
- [Bild zu PostScript (PS)-Dokument mit Aspose.Page hinzufügen](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Text zu PostScript (PS)-Dokument mit Aspose.Page hinzufügen](/page/net/text-manipulation/add-text-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}