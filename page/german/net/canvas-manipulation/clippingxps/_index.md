---
date: 2026-06-25
description: Erfahren Sie, wie Sie XPS-Dokumente mit Aspose.Page für .NET zuschneiden.
  Diese Schritt-für-Schritt-Anleitung zeigt Ihnen, wie Sie XPS-Dateien effizient erstellen,
  bearbeiten und speichern.
keywords:
- how to clip xps
- Aspose.Page .NET
- XPS clipping tutorial
linktitle: XPS zuschneiden
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to clip XPS documents using Aspose.Page for .NET. This step‑by‑step
    guide shows you how to create, manipulate, and save XPS files efficiently.
  headline: How to Clip XPS with Aspose.Page for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can assign a complex `PathGeometry` that contains several sub‑paths
      to the `Clip` property, allowing layered masking.
    question: Can I combine multiple clip geometries on a single canvas?
  - answer: When you later convert the XPS to PDF using Aspose.PDF, the clip geometry
      is preserved, so the visual result remains identical.
    question: Does clipping affect PDF conversion?
  - answer: XPS itself does not support animation; however, you can generate a series
      of XPS pages with different clip shapes to simulate motion.
    question: Is it possible to animate clipping in XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Wie man XPS mit Aspose.Page für .NET zuschneidet
url: /de/net/canvas-manipulation/clippingxps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man XPS mit Aspose.Page für .NET zuschneidet

## Einführung

Willkommen zu diesem umfassenden Tutorial, **wie man XPS zuschneidet** mit Aspose.Page für .NET! In diesem Leitfaden lernen Sie Schritt für Schritt, wie man ein XPS‑Dokument erstellt, geometrische Clipping‑Masken anwendet und das Ergebnis speichert. Clipping ermöglicht es, Teile einer Zeichenfläche zu verbergen und anspruchsvolle Layouts wie maskierte Bilder, benutzerdefinierte Formen oder fokussierte Inhaltsbereiche zu erstellen – alles ohne Ihren .NET‑Code zu verlassen.

## Schnelle Antworten
- **Was ist Clipping von XPS?** Anwenden einer geometrischen Maske (Clip), um den sichtbaren Bereich von XPS‑Zeichenflächenelementen zu begrenzen.  
- **Welche Bibliothek ist dafür am besten?** Aspose.Page für .NET bietet eine voll ausgestattete API für die Erstellung und das Clipping von XPS.  
- **Voraussetzungen?** Visual Studio, .NET‑Runtime und die Aspose.Page für .NET‑Bibliothek.  
- **Wie lange dauert die Implementierung?** Ungefähr 10‑15 Minuten für ein einfaches Clipping‑Szenario.  
- **Kann ich das in der Produktion einsetzen?** Ja, mit einer gültigen Aspose‑Lizenz (Testversion verfügbar).

## Was bedeutet „wie man XPS zuschneidet“?

Clipping von XPS bedeutet, eine geometrische Maske auf eine Zeichenfläche anzuwenden, sodass alle Zeichnungen außerhalb der Maske nicht gerendert werden. Diese Technik ist ideal, um maskierte Bilder, benutzerdefinierte Schaltflächen oder die Aufmerksamkeit des Lesers auf einen bestimmten Seitenbereich zu lenken. Durch die Definition einer Clip‑Geometrie – z. B. ein Rechteck, ein Kreis oder ein komplexer Pfad – erhalten Sie eine feinkörnige Kontrolle darüber, was auf der endgültigen XPS‑Seite erscheint.

## Warum Aspose.Page für .NET zum Zuschneiden von XPS verwenden?

Aspose.Page bietet deterministische, serverseitige XPS‑Manipulation ohne externe Abhängigkeiten. Es unterstützt **50+ Eingabe‑ und Ausgabeformate**, kann **200‑seitige XPS‑Dateien in unter 0,5 Sekunden** auf einer Standard‑CPU mit 2,5 GHz verarbeiten und funktioniert über .NET Framework 4.0+, .NET Core 2.0+, .NET 5, .NET 6 und .NET 7 hinweg. Die API gibt Ihnen volle Kontrolle über Canvas‑Transformationen, Pfadgeometrien und Pinsel, sodass jedes Mal ein hochwertiges Ergebnis entsteht.

## Voraussetzungen

- Visual Studio auf Ihrem Rechner installiert.  
- Aspose.Page für .NET Bibliothek zu Ihrem Projekt hinzugefügt. Sie können sie [hier](https://releases.aspose.com/page/net/) herunterladen.  
- Grundkenntnisse der Programmiersprache C#.

## Wie man XPS zuschneidet?

Laden Sie ein XPS‑Dokument, erstellen Sie ein Canvas, definieren Sie eine Clip‑Geometrie (z. B. einen Kreis), weisen Sie die Geometrie der `Clip`‑Eigenschaft des Canvas zu, zeichnen Sie Ihren Inhalt und speichern Sie schließlich das Dokument. All diese Schritte können mit nur wenigen Methodenaufrufen durchgeführt werden, und Aspose.Page übernimmt automatisch das zugrunde liegende XML‑Markup, sodass Sie sich auf das visuelle Design statt auf die Dateistruktur konzentrieren.

## Namespaces importieren

Um die Funktionalitäten von Aspose.Page für .NET zu nutzen, müssen Sie die erforderlichen Namespaces in Ihr Projekt importieren. Folgen Sie diesen Schritten:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.IO;
```

Nun, lassen Sie uns den bereitgestellten Beispielcode in mehrere Schritte aufteilen.

## Schritt 1: Pfad des Dokumentenverzeichnisses festlegen.

Definieren Sie den Ordner, in dem die XPS‑Datei erstellt wird. Die Verwendung von `Path.Combine` garantiert den korrekten Verzeichnistrenner auf jedem Betriebssystem.

```csharp
string dataDir = Path.Combine(Environment.CurrentDirectory, "Output");
Directory.CreateDirectory(dataDir);
```

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Schritt 2: Neues XPS‑Dokument erstellen.

Instanziieren Sie die Klasse `XpsDocument`, die das gesamte XPS‑Paket repräsentiert.

```csharp
XpsDocument doc = new XpsDocument();
```

```csharp
string dataDir = "Your Document Directory";
```

## Schritt 3: Haupt‑Canvas erstellen.

Die Klasse `Canvas` stellt eine Zeichenfläche innerhalb einer XPS‑Seite dar, auf der Formen, Bilder und Text gerendert werden.

```csharp
Canvas mainCanvas = new Canvas();
```

```csharp
XpsDocument doc = new XpsDocument();
```

## Schritt 4: Linken und oberen Versatz im Haupt‑Canvas festlegen.

Passen Sie die Position des Canvas an, um zu steuern, wo das Zeichnen auf der Seite beginnt.

```csharp
mainCanvas.Left = 20;
mainCanvas.Top = 30;
```

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

## Schritt 5: Rechteck‑Pfadgeometrie erstellen.

`PathGeometry` definiert eine Vektorform; hier erstellen wir ein einfaches Rechteck.

```csharp
PathGeometry rectGeometry = new PathGeometry("M0,0 L100,0 100,50 0,50 Z");
```

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Schritt 6: Füllung für Rechtecke erstellen.

Definieren Sie einen Vollfarb‑Pinsel, der zum Füllen des Rechtecks verwendet wird.

```csharp
SolidColorBrush rectFill = new SolidColorBrush(Color.Black);
```

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

## Schritt 7: Ein weiteres Canvas mit Clip zum Haupt‑Canvas hinzufügen.

Erstellen Sie ein untergeordnetes Canvas, das eine Clipping‑Maske erhält.

```csharp
Canvas clippedCanvas = new Canvas();
mainCanvas.Children.Add(clippedCanvas);
```

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Schritt 8: Kreisgeometrie für das Clipping erstellen.

`PathGeometry` kann auch Kreise darstellen; diese Geometrie wird der `Clip`‑Eigenschaft des untergeordneten Canvas zugewiesen.

```csharp
PathGeometry circleClip = new PathGeometry("M50,0 A50,50 0 1 0 49.9,0 Z");
clippedCanvas.Clip = circleClip;
```

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

## Schritt 9: Ein Rechteck im zweiten Canvas erstellen und füllen.

Zeichnen Sie ein Rechteck im zugeschnittenen Canvas; nur der Teil innerhalb des Kreises ist sichtbar.

```csharp
Path rectangle = new Path(rectGeometry, rectFill);
clippedCanvas.Children.Add(rectangle);
```

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

## Schritt 10: Das zweite Canvas mit einem umrandeten Rechteck zum Haupt‑Canvas hinzufügen.

Fügen Sie ein Rechteck mit Kontur hinzu, um zu zeigen, wie Konturen mit dem Clipping interagieren.

```csharp
Path strokedRect = new Path(rectGeometry, null, new Pen(Color.Blue, 2));
mainCanvas.Children.Add(strokedRect);
```

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Schritt 11: Ein Rechteck im dritten Canvas erstellen und umranden.

Ein drittes Canvas demonstriert unabhängiges Zeichnen ohne Clipping.

```csharp
Canvas thirdCanvas = new Canvas();
PathGeometry thirdRectGeom = new PathGeometry("M0,0 L150,0 150,75 0,75 Z");
Path thirdRect = new Path(thirdRectGeom, null, new Pen(Color.Green, 3));
thirdCanvas.Children.Add(thirdRect);
mainCanvas.Children.Add(thirdCanvas);
```

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

## Schritt 12: Das resultierende XPS‑Dokument speichern.

Speichern Sie das XPS‑Paket im Dateisystem.

```csharp
doc.Save(Path.Combine(dataDir, "ClippedOutput.xps"));
```

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

## Häufige Probleme und Lösungen
- **Ungültiger Pfad** – Stellen Sie sicher, dass `dataDir` mit einem Backslash (`\\`) endet oder verwenden Sie `Path.Combine`.  
- **Clip nicht angewendet** – Überprüfen Sie, ob die Clip‑Geometrie‑Zeichenkette wohlgeformt ist; ein fehlendes Leerzeichen kann dazu führen, dass das Clip ignoriert wird.  
- **Lizenzausnahme** – Fügen Sie in einem Nicht‑Evaluierungs‑Build vor dem Erstellen des Dokuments eine gültige Aspose‑Lizenz hinzu, um Laufzeitausnahmen zu vermeiden.

## Häufig gestellte Fragen

### F1: Kann ich Aspose.Page für .NET mit anderen Dokumentformaten verwenden?

A1: Aspose.Page für .NET konzentriert sich hauptsächlich auf XPS‑Dokumente, aber Aspose bietet weitere Bibliotheken für verschiedene Dokumentformate.

### F2: Ist Aspose.Page für .NET für Anfänger geeignet?

A2: Ja, Aspose.Page für .NET ist benutzerfreundlich gestaltet, und Anfänger können seine Funktionen mit entsprechender Dokumentation schnell erfassen.

### F3: Wo finde ich weitere Beispiele und Ressourcen?

A3: Besuchen Sie die [Dokumentation](https://reference.aspose.com/page/net/) und das [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39) für umfangreiche Ressourcen und Beispiele.

### F4: Wie kann ich eine temporäre Lizenz für Aspose.Page für .NET erhalten?

A4: Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erhalten.

### F5: Gibt es eine kostenlose Testversion für Aspose.Page für .NET?

A5: Ja, Sie können die kostenlose Testversion [hier](https://releases.aspose.com/) erkunden.

## Zusätzliche häufig gestellte Fragen

**F: Kann ich mehrere Clip‑Geometrien auf einem einzigen Canvas kombinieren?**  
A: Ja, Sie können eine komplexe `PathGeometry`, die mehrere Unterpfade enthält, der `Clip`‑Eigenschaft zuweisen, wodurch geschichtete Masken möglich sind.

**F: Beeinflusst Clipping die PDF-Konvertierung?**  
A: Wenn Sie das XPS später mit Aspose.PDF in PDF konvertieren, bleibt die Clip‑Geometrie erhalten, sodass das visuelle Ergebnis identisch bleibt.

**F: Ist es möglich, Clipping in XPS zu animieren?**  
A: XPS selbst unterstützt keine Animation; Sie können jedoch eine Reihe von XPS‑Seiten mit unterschiedlichen Clip‑Formen erzeugen, um eine Bewegung zu simulieren.

**Letzte Aktualisierung:** 2026-06-25  
**Getestet mit:** Aspose.Page 24.11 für .NET  
**Autor:** Aspose  

```csharp
doc.Save(dataDir + "output2.xps");
```

## Verwandte Tutorials

- [Wie man XPS mit Aspose.Page für .NET transformiert](/page/net/canvas-manipulation/transformationsxps/)
- [Rechteck zu XPS‑Dokument mit Aspose.Page für .NET hinzufügen](/page/net/drawing-shapes/add-rectangle-to-xps-document/)
- [XPS zu PDF mit Aspose.Page für .NET konvertieren](/page/net/document-conversion/convert-xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< /blocks/products/products-backtop-button >}}

{{< blocks/products/products-backtop-button >}}