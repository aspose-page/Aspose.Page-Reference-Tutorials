---
date: 2026-01-20
description: Erfahren Sie, wie Sie ein XPS‑Dokument erstellen, ein Rechteck hinzufügen
  und die XPS‑Datei mit Aspose.Page für .NET in dieser Schritt‑für‑Schritt‑Anleitung
  speichern.
linktitle: Add Rectangle to XPS Document
second_title: Aspose.Page .NET API
title: 'XPS-Dokument erstellen: Rechteck hinzufügen mit Aspose.Page für .NET'
url: /de/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS-Dokument erstellen: Rechteck mit Aspose.Page für .NET hinzufügen

## Einführung

In diesem Tutorial **erstellen Sie XPS‑Dokumente** und zeichnen ein Rechteck darin mithilfe der Bibliothek Aspose.Page für .NET. Das Hinzufügen von Formen wie Rechtecken ist ein gängiger Bedarf, wenn Sie Rechnungen, Berichte oder benutzerdefinierte Grafiken programmgesteuert erzeugen müssen. Folgen Sie den untenstehenden Schritten und Sie haben in wenigen Minuten eine einsatzbereite XPS‑Datei.

## Schnellantworten
- **Was kann ich erzeugen?** XPS‑Dokumente mit Vektorgrafiken und Text.  
- **Welche Bibliothek?** Aspose.Page für .NET (Kostenlose Testversion verfügbar).  
- **Wie lange dauert es?** Etwa 5‑10 Minuten für Implementierung und Ausführung.  
- **Benötige ich eine Lizenz?** Für den Produktionseinsatz ist eine temporäre Lizenz erforderlich.  
- **Kann ich das Ergebnis als XPS‑Datei speichern?** Ja – die `Save`‑Methode schreibt eine **XPS‑Datei** auf die Festplatte.

## Was bedeutet „XPS‑Dokument erstellen”?

Ein XPS‑Dokument zu erstellen bedeutet, programmgesteuert eine Seitenbeschreibung im XML‑Paper‑Specification‑Format zu erzeugen. Die resultierende Datei ist auflösungsunabhängig und ideal für den Druck sowie die hochqualitative Anzeige auf verschiedenen Plattformen.

## Warum Aspose.Page zum Erstellen von XPS‑Dokumenten verwenden?

- **Vollständige .NET‑Unterstützung** – funktioniert mit .NET Framework, .NET Core und .NET 5/6+.  
- **Umfangreiche Zeichen‑API** – beinhaltet Pfadgeometrie, Pinsel, Stifte und Textverarbeitung.  
- **Keine externen Abhängigkeiten** – alles läuft im Prozess ohne Office oder Acrobat.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Aspose.Page für .NET** – laden Sie es [hier](https://releases.aspose.com/page/net/) herunter.  
2. **Ein beschreibbarer Ordner**, in dem die erzeugten XPS‑Dateien gespeichert werden.

## Namespaces importieren

Importieren Sie in Ihrem .NET‑Projekt die erforderlichen Namespaces:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Schritt 1: Das Dokumentenverzeichnis festlegen

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

> **Pro Tipp:** Verwenden Sie einen absoluten Pfad oder `Path.Combine`, um Pfad‑Separator‑Probleme auf verschiedenen Betriebssystemen zu vermeiden.

## Schritt 2: Ein neues XPS‑Dokument erstellen

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

An diesem Punkt haben Sie ein **XPS‑Dokument**‑Objekt erstellt, das alle Zeichen‑Elemente aufnehmen wird.

## Schritt 3: Ein Rechteck hinzufügen (mit create path geometry)

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

Der Aufruf `CreatePathGeometry` **erstellt Pfadgeometrie**, die die Kontur des Rechtecks definiert. Sie können die SVG‑ähnliche Befehlszeichenfolge anpassen, um andere Formen zu zeichnen.

## Schritt 4: Das Dokument speichern (XPS‑Datei speichern)

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Durch den Aufruf von `Save` wird die **XPS‑Datei** an dem von Ihnen angegebenen Ort geschrieben.

Herzlichen Glückwunsch! Sie haben erfolgreich ein **XPS‑Dokument** erstellt, ein Rechteck hinzugefügt und die Datei gespeichert.

## Häufige Probleme und Lösungen

| Problem | Grund | Lösung |
|---------|-------|--------|
| `FileNotFoundException` bei `doc.Save` | `dataDir` verweist auf einen nicht existierenden Ordner | Stellen Sie sicher, dass das Verzeichnis existiert, oder erstellen Sie es mit `Directory.CreateDirectory(dataDir)`. |
| Rechteck nicht sichtbar | Fehlendes Stroke‑Farbprofil oder fehlerhafte Pfadgeometrie | Überprüfen Sie den Pfad zur ICC‑Datei und die Geometrie‑Zeichenfolge (`M … Z`). |
| Leistungsabfall bei großen Dokumenten | Zu viele einzelne `AddPath`‑Aufrufe | Bündeln Sie Zeichenoperationen oder verwenden Sie wiederverwendbare Pinsel‑/Stift‑Objekte. |

## Häufig gestellte Fragen

**F: Ist Aspose.Page mit allen .NET‑Anwendungen kompatibel?**  
A: Ja, Aspose.Page ist so konzipiert, dass es nahtlos mit allen .NET‑Anwendungen funktioniert.

**F: Wo finde ich die Dokumentation zu Aspose.Page für .NET?**  
A: Die Dokumentation ist [hier](https://reference.aspose.com/page/net/) verfügbar.

**F: Kann ich Aspose.Page für .NET kostenlos testen, bevor ich kaufe?**  
A: Ja, Sie können eine kostenlose Testversion [hier](https://releases.aspose.com/) erhalten.

**F: Wie kann ich eine temporäre Lizenz für Aspose.Page für .NET erhalten?**  
A: Besuchen Sie [diesen Link](https://purchase.aspose.com/temporary-license/), um eine temporäre Lizenz zu erhalten.

**F: Wo finde ich Community‑Support oder kann Fragen zu Aspose.Page für .NET stellen?**  
A: Besuchen Sie das [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39) für Community‑Support.

---

**Zuletzt aktualisiert:** 2026-01-20  
**Getestet mit:** Aspose.Page 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}