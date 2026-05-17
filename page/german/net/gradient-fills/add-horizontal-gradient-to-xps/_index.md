---
date: 2026-02-25
description: Erfahren Sie, wie Sie mit Aspose.Page für .NET einen XPS‑Verlauf mit
  horizontaler Füllung erstellen. Steigern Sie die visuelle Attraktivität Ihrer Dokumente
  mühelos.
linktitle: Add Horizontal Gradient to XPS
second_title: Aspose.Page .NET API
title: 'XPS-Gradient erstellen: Horizontale Füllung mit Aspose.Page für .NET'
url: /de/net/gradient-fills/add-horizontal-gradient-to-xps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen Sie XPS-Gradient – Horizontalen Gradient zu XPS mit Aspose.Page für .NET hinzufügen

## Einleitung

In diesem Tutorial erstellen Sie **XPS gradient**‑Füllungen, die horizontal über Ihre Seiten verlaufen. Das Hinzufügen eines horizontalen Gradients kann ein XPS‑Dokument sofort professioneller und ansprechender wirken lassen, besonders bei Berichten, Broschüren oder anderen visuell‑reichen Ausgaben. Wir führen Sie durch den gesamten Prozess mit Aspose.Page für .NET, von der Einrichtung der Umgebung bis zum Speichern der finalen XPS‑Datei.

## Schnelle Antworten
- **Was wird in diesem Tutorial behandelt?** Hinzufügen eines horizontalen Gradients zu einem XPS‑Dokument mit Aspose.Page für .NET.  
- **Welche Bibliothek wird benötigt?** Aspose.Page für .NET (jede aktuelle Version).  
- **Benötige ich eine Lizenz?** Eine Testversion reicht für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Wie lange dauert die Implementierung?** Etwa 5–10 Minuten für einen einfachen Gradient.  
- **Kann ich die Gradient‑Richtung ändern?** Ja – passen Sie die Start‑/Endpunkte des `LinearGradientBrush` an.

## Wie man XPS gradient mit Aspose.Page für .NET erstellt

Im Folgenden finden Sie eine Schritt‑für‑Schritt‑Anleitung, die erklärt, **warum** jede Codezeile existiert, nicht nur **was** sie tut. Folgen Sie einfach in Visual Studio oder Ihrem bevorzugten .NET‑Editor.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. **Aspose.Page für .NET Bibliothek:** Vergewissern Sie sich, dass die Aspose.Page für .NET‑Bibliothek in Ihrer Entwicklungsumgebung installiert ist. Sie können sie von der [Aspose.Page für .NET Documentation](https://reference.aspose.com/page/net/) herunterladen.

2. **Entwicklungsumgebung:** Richten Sie eine geeignete Entwicklungsumgebung ein, inklusive eines Code‑Editors wie Visual Studio.

## Namespaces importieren

Importieren Sie die notwendigen Namespaces in Ihr Projekt. Diese Namespaces sind essenziell für die Arbeit mit Aspose.Page für .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Nun zerlegen wir das bereitgestellte Beispiel in mehrere Schritte.

## Schritt 1: Dokumentverzeichnis‑Pfad festlegen

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Schritt 2: Neues XPS‑Dokument erstellen

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Schritt 3: Gradient‑Stops initialisieren

```csharp
// ExStart:5
// Initialize List of XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## Schritt 4: Neuen Pfad erstellen

```csharp
// ExStart:6
// Create new path by defining geometry in abbreviation form
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Schritt 5: Ergebnis‑XPS‑Dokument speichern

```csharp
// ExStart:7
// Save resultant XPS document
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

Jetzt haben Sie erfolgreich einen horizontalen Gradient zu Ihrem XPS‑Dokument mit Aspose.Page für .NET hinzugefügt.

## Häufige Probleme und Lösungen

| Problem | Grund | Lösung |
|---------|-------|--------|
| Gradient erscheint als einfarbig | Gradient‑Stops wurden nicht korrekt hinzugefügt | Stellen Sie sicher, dass `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` nach dem Setzen des Brushes ausgeführt wird. |
| Gespeicherte Datei ist leer | `dataDir` verweist auf einen nicht existierenden Ordner | Überprüfen Sie, ob der Ordner existiert, oder verwenden Sie einen absoluten Pfad. |
| Kompilierungsfehler bei `PointF` | Fehlende `System.Drawing`‑Referenz | Fügen Sie eine Referenz zu `System.Drawing.Common` hinzu (für .NET Core/5+). |

## FAQ's

### Q1: Wo finde ich die Aspose.Page für .NET Dokumentation?

A1: Die Dokumentation finden Sie [hier](https://reference.aspose.com/page/net/).

### Q2: Wie lade ich Aspose.Page für .NET herunter?

A2: Die Bibliothek können Sie von der [Aspose.Page für .NET download page](https://releases.aspose.com/page/net/) herunterladen.

### Q3: Wo kann ich Aspose.Page für .NET kaufen?

A3: Sie können Aspose.Page für .NET auf der [purchase page](https://purchase.aspose.com/buy) erwerben.

### Q4: Gibt es eine kostenlose Testversion?

A4: Ja, Sie erhalten eine kostenlose Testversion [hier](https://releases.aspose.com/).

### Q5: Wie erhalte ich eine temporäre Lizenz für Aspose.Page für .NET?

A5: Eine temporäre Lizenz erhalten Sie über [diesen Link](https://purchase.aspose.com/temporary-license/).

## Häufig gestellte Fragen

**Q: Kann ich diese Gradiententechnik mit XPS‑Dokumenten verwenden, die bereits Bilder enthalten?**  
A: Absolut. Der Gradient wird auf einer Pfadebene angewendet, sodass vorhandene Bilder unverändert bleiben.

**Q: Ist es möglich, stattdessen einen vertikalen Gradient zu erstellen?**  
A: Ja. Ändern Sie die Start‑ und Endpunkte des `LinearGradientBrush`, sodass die Y‑Koordinaten unterschiedlich sind, während X konstant bleibt.

**Q: Unterstützt Aspose.Page .NET Core?**  
A: Die Bibliothek ist vollständig kompatibel mit .NET Core, .NET 5 und neueren Versionen.

**Q: Wie kann ich denselben Gradient auf mehreren Seiten wiederverwenden?**  
A: Erstellen Sie den `XpsLinearGradientBrush` einmal, speichern Sie ihn in einer Variable und weisen Sie ihn den Pfaden auf jeder Seite zu.

## Fazit

Die Aufwertung Ihrer XPS‑Dokumente mit Gradients verbessert nicht nur die optische Attraktivität, sondern sorgt auch für ein ansprechenderes Benutzererlebnis. Mit Aspose.Page für .NET können Sie **XPS gradient**‑Füllungen schnell und zuverlässig erstellen und Ihren Berichten, Broschüren oder E‑Books einen professionellen Schliff verleihen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2026-02-25  
**Getestet mit:** Aspose.Page für .NET 24.11  
**Autor:** Aspose  

---