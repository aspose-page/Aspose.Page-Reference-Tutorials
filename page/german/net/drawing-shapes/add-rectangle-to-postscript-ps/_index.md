---
date: 2026-01-18
description: Erfahren Sie, wie Sie ein PostScript‑Dokument in .NET erstellen und Rechtecke
  mit Aspose.Page für .NET hinzufügen. Schritt‑für‑Schritt‑Anleitung mit Codebeispielen.
linktitle: Add Rectangle to PostScript (PS)
second_title: Aspose.Page .NET API
title: Postscript‑Dokument .NET erstellen – Rechteck mit Aspose.Page hinzufügen
url: /de/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rechteck zu PostScript (PS) mit Aspose.Page für .NET hinzufügen

## Einführung

Wenn Sie **create postscript document .net** erstellen möchten, bietet Aspose.Page eine leistungsstarke Lösung zur Verarbeitung von PostScript-Dateien. In diesem Tutorial führen wir Sie Schritt für Schritt durch das Hinzufügen von Rechtecken zu einem PostScript-Dokument mit Aspose.Page für .NET und geben Ihnen eine solide Grundlage für die Erstellung anspruchsvollerer Grafiken.

## Schnelle Antworten
- **Welche Bibliothek benötige ich?** Aspose.Page for .NET.
- **Kann ich ein PostScript-Dokument von Grund auf neu erstellen?** Ja – die API ermöglicht das programmgesteuerte Erstellen von PS‑Dateien.
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Benötige ich für die Entwicklung eine Lizenz?** Eine kostenlose Testversion funktioniert für Tests; für die Produktion ist eine Lizenz erforderlich.
- **Wie lange dauert die Implementierung?** In der Regel unter 10 Minuten für einfache Formen.

## Was bedeutet das Erstellen eines PostScript-Dokuments in .NET?
Ein PostScript-Dokument in .NET zu erstellen bedeutet, programmgesteuert eine .ps‑Datei zu erzeugen, die den Seiteninhalt – Text, Grafiken oder Formen – beschreibt, wobei die Aspose.Page‑API verwendet wird. Dieser Ansatz ist ideal für serverseitige Grafikgenerierung, automatisierte Berichtserstellung oder jede Situation, in der Sie präzise Kontrolle über das Ausgabeformat benötigen.

## Warum Aspose.Page für .NET verwenden?
- **Vollständige Kontrolle über Grafiken** – Formen zeichnen, Farben setzen und Striche anwenden, ohne sich mit Low‑Level‑PS‑Syntax befassen zu müssen.
- **Plattformübergreifend** – funktioniert auf Windows-, Linux- und macOS‑Laufzeiten.
- **Keine externen Abhängigkeiten** – die Bibliothek übernimmt die gesamte PS‑Erzeugung intern.
- **Umfangreiche Dokumentation & Beispiele** – schnell einsatzbereit.

## Voraussetzungen

- **Aspose.Page for .NET Bibliothek** – herunterladen und installieren von [hier](https://releases.aspose.com/page/net/).
- **Entwicklungsumgebung** – Visual Studio, VS Code oder jede .NET‑kompatible IDE.

## Namespaces importieren

Bevor Sie mit dem Codieren beginnen, importieren Sie die Namespaces, die die erforderlichen Klassen bereitstellen:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Nun teilen wir das Beispiel in klare, nummerierte Schritte auf.

## Schritt 1: Dokumentverzeichnis einrichten

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Ersetzen Sie `"Your Document Directory"` durch den Ordner, in dem Sie die resultierende PS‑Datei speichern möchten.

## Schritt 2: Ausgabestream für das PostScript-Dokument erstellen

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Dieser Stream verweist auf **AddRectangle_outPS.ps**. Sie können die Datei nach Belieben umbenennen oder den Speicherort ändern.

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

## Häufige Probleme & Tipps

- **Falscher Dateipfad** – Stellen Sie sicher, dass `dataDir` mit einem Pfadtrennzeichen (`\\` oder `/`) endet oder verwenden Sie `Path.Combine`.
- **Fehlende Lizenz** – In einer Produktionsumgebung sollten Sie Ihre Aspose‑Lizenz vor dem Erstellen des Dokuments anwenden, um Evaluationswasserzeichen zu vermeiden.
- **Farbensichtbarkeit** – Wenn das Rechteck leer erscheint, prüfen Sie, ob die Farben des Pinsels oder Stifts im Kontrast zum Seitenhintergrund stehen.

## Häufig gestellte Fragen

**F:** Kann ich die Farben der Rechtecke anpassen?  
**A:** Natürlich. Ändern Sie die Werte `Color.Orange` oder `Color.Red` in den Konstruktoren von `SolidBrush` und `Pen` zu jedem gewünschten `System.Drawing.Color`.

**F:** Ist Aspose.Page mit anderen Dokumentformaten kompatibel?  
**A:** Ja. Neben PostScript unterstützt Aspose.Page auch die Erzeugung von XPS und EPS.

**F:** Wie kann ich Text zum selben Dokument hinzufügen?  
**A:** Verwenden Sie die Klasse `TextFragment`, um Text an gewünschten Koordinaten zu platzieren, und rufen Sie anschließend `document.Draw(textFragment)` auf.

**F:** Wo finde ich weitere Beispiele und die vollständige API‑Referenz?  
**A:** Durchsuchen Sie die Dokumentation [hier](https://reference.aspose.com/page/net/) und treten Sie der Community im [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39) bei.

**F:** Kann ich Aspose.Page vor dem Kauf testen?  
**A:** Ja, laden Sie eine kostenlose Testversion [hier](https://releases.aspose.com/) herunter. Für eine erweiterte Evaluierung sollten Sie eine [temporäre Lizenz](https://purchase.aspose.com/temporary-license/) in Betracht ziehen.

---

**Zuletzt aktualisiert:** 2026-01-18  
**Getestet mit:** Aspose.Page 24.12 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}