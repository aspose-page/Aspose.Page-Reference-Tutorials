---
date: 2026-01-05
description: Erfahren Sie, wie Sie XPS‑Dokumente mit Aspose.Page für .NET zuschneiden.
  Diese Schritt‑für‑Schritt‑Anleitung zeigt Ihnen, wie Sie XPS‑Dateien effizient erstellen,
  bearbeiten und speichern.
linktitle: Clipping XPS
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

Willkommen zu diesem umfassenden Tutorial zum **Zuschneiden von XPS** mit Aspose.Page für .NET! In diesem Leitfaden führen wir Sie durch den Prozess des Erstellens, Manipulierens und Speicherns von XPS-Dokumenten mit der Bibliothek. XPS, oder XML Paper Specification, ist ein standardisiertes und offenes Dokumentformat, und Aspose.Page für .NET bietet leistungsstarke Werkzeuge zur Arbeit mit XPS-Dokumenten in Ihren .NET-Anwendungen.

## Schnelle Antworten
- **Was ist das Zuschneiden von XPS?** Anwenden einer geometrischen Maske (Clip), um den sichtbaren Bereich von XPS‑Canvas‑Elementen zu begrenzen.  
- **Welche Bibliothek ist dafür am besten geeignet?** Aspose.Page für .NET bietet eine voll ausgestattete API für die XPS‑Erstellung und das Zuschneiden.  
- **Voraussetzungen?** Visual Studio, .NET‑Runtime und die Aspose.Page für .NET‑Bibliothek.  
- **Wie lange dauert die Implementierung?** Ungefähr 10‑15 Minuten für ein einfaches Zuschneideszenario.  
- **Kann ich das in der Produktion einsetzen?** Ja, mit einer gültigen Aspose‑Lizenz (Testversion verfügbar).

## Was bedeutet „XPS zuschneiden“?
Das Zuschneiden in XPS funktioniert, indem eine **Clip‑Geometrie** (z. B. ein Kreis oder Rechteck) definiert und einem Canvas zugewiesen wird. Alles, was außerhalb dieser Geometrie gezeichnet wird, wird nicht gerendert, sodass Sie anspruchsvolle Seitenlayouts wie maskierte Bilder, benutzerdefinierte Formen oder fokussierte Inhaltsbereiche erstellen können.

## Warum Aspose.Page für .NET zum Zuschneiden von XPS verwenden?
- **Vollständige Kontrolle** über Canvas‑Transformationen, Pfadgeometrien und Pinsel.  
- **Keine externen Abhängigkeiten** – alles läuft innerhalb Ihrer .NET‑Anwendung.  
- **Plattformübergreifende** Unterstützung für .NET Framework, .NET Core und .NET 5/6+.  
- **Hohe Leistung** mit einer leichten API, die gültige XPS‑Dateien schreibt.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Visual Studio auf Ihrem Rechner installiert.  
- Aspose.Page für .NET‑Bibliothek zu Ihrem Projekt hinzugefügt. Sie können sie [hier](https://releases.aspose.com/page/net/) herunterladen.  
- Grundkenntnisse der Programmiersprache C#.

## Namespaces importieren

Um die Funktionalitäten von Aspose.Page für .NET zu nutzen, müssen Sie die erforderlichen Namespaces in Ihr Projekt importieren. Folgen Sie diesen Schritten:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Nun zerlegen wir den Beispielcode, den Sie bereitgestellt haben, in mehrere Schritte.

## Schritt 1: Dokumentverzeichnis-Pfad festlegen.

```csharp
string dataDir = "Your Document Directory";
```

Stellen Sie sicher, dass Sie „Your Document Directory“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis ersetzen.

## Schritt 2: Ein neues XPS-Dokument erstellen.

```csharp
XpsDocument doc = new XpsDocument();
```

Damit wird ein neues XPS-Dokument erstellt, mit dem Sie arbeiten werden.

## Schritt 3: Das Haupt-Canvas erstellen.

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

Dieser Schritt erstellt das Haupt-Canvas, das für alle Seitenelemente gemeinsam verwendet wird.

## Schritt 4: Linke und obere Versätze im Haupt-Canvas festlegen.

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

Passen Sie die linken und oberen Versätze nach Ihren Anforderungen an.

## Schritt 5: Eine Rechteck-Pfadgeometrie erstellen.

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

Damit wird eine Pfadgeometrie für ein Rechteck erzeugt.

## Schritt 6: Eine Füllung für Rechtecke erstellen.

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

Definieren Sie die Füllfarbe für die Rechtecke.

## Schritt 7: Ein weiteres Canvas mit Clip zum Haupt-Canvas hinzufügen.

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

Dieser Schritt fügt ein weiteres Canvas zum Haupt-Canvas hinzu.

## Schritt 8: Eine Kreisgeometrie für den Clip erstellen.

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

Damit wird eine kreisförmige Clip‑Geometrie erzeugt und auf das zweite Canvas angewendet.

## Schritt 9: Ein Rechteck im zweiten Canvas erstellen und füllen.

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Dieser Schritt erstellt ein Rechteck im zweiten Canvas und füllt es.

## Schritt 10: Das zweite Canvas mit einem umrandeten Rechteck zum Haupt-Canvas hinzufügen.

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

Damit wird ein weiteres Canvas zum Haupt-Canvas hinzugefügt.

## Schritt 11: Ein Rechteck im dritten Canvas erstellen und umranden.

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

Damit wird ein Rechteck im dritten Canvas erstellt und mit einem Strich versehen.

## Schritt 12: Das resultierende XPS-Dokument speichern.

```csharp
doc.Save(dataDir + "output2.xps");
```

Damit wird das XPS-Dokument im angegebenen Verzeichnis gespeichert.

## Häufige Probleme und Lösungen
- **Ungültiger Pfad** – Stellen Sie sicher, dass `dataDir` mit einem Backslash (`\\`) endet oder verwenden Sie `Path.Combine`.  
- **Clip wird nicht angewendet** – Überprüfen Sie, ob die Clip‑Geometrie‑Zeichenfolge korrekt formatiert ist; ein fehlendes Leerzeichen kann dazu führen, dass der Clip ignoriert wird.  
- **Lizenz‑Ausnahme** – In einem Nicht‑Evaluierungs‑Build fügen Sie vor dem Erstellen des Dokuments eine gültige Aspose‑Lizenz hinzu, um Laufzeitausnahmen zu vermeiden.

## Häufig gestellte Fragen

### Q1: Kann ich Aspose.Page für .NET mit anderen Dokumentformaten verwenden?

A1: Aspose.Page für .NET konzentriert sich hauptsächlich auf XPS‑Dokumente, aber Aspose bietet weitere Bibliotheken für verschiedene Dokumentformate an.

### Q2: Ist Aspose.Page für .NET für Anfänger geeignet?

A2: Ja, Aspose.Page für .NET ist benutzerfreundlich gestaltet, und Anfänger können seine Funktionen mit entsprechender Dokumentation schnell erfassen.

### Q3: Wo finde ich weitere Beispiele und Ressourcen?

A3: Besuchen Sie die [Dokumentation](https://reference.aspose.com/page/net/) und das [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39) für umfangreiche Ressourcen und Beispiele.

### Q4: Wie kann ich eine temporäre Lizenz für Aspose.Page für .NET erhalten?

A4: Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erhalten.

### Q5: Gibt es eine kostenlose Testversion von Aspose.Page für .NET?

A5: Ja, Sie können die kostenlose Testversion [hier](https://releases.aspose.com/) erkunden.

## Zusätzliche häufig gestellte Fragen

**Q: Kann ich mehrere Clip‑Geometrien auf einem einzigen Canvas kombinieren?**  
A: Ja, Sie können ein komplexes `PathGeometry` zuweisen, das mehrere Unterpfade enthält, und es der `Clip`‑Eigenschaft zuweisen, wodurch eine geschichtete Maskierung ermöglicht wird.

**Q: Beeinflusst das Zuschneiden die PDF‑Konvertierung?**  
A: Wenn Sie das XPS später mit Aspose.PDF in PDF konvertieren, bleibt die Clip‑Geometrie erhalten, sodass das visuelle Ergebnis identisch bleibt.

**Q: Ist es möglich, das Zuschneiden in XPS zu animieren?**  
A: XPS selbst unterstützt keine Animationen; Sie können jedoch eine Reihe von XPS‑Seiten mit unterschiedlichen Clip‑Formen erzeugen, um eine Bewegung zu simulieren.

**Letzte Aktualisierung:** 2026-01-05  
**Getestet mit:** Aspose.Page 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}