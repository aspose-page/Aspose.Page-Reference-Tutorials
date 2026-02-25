---
date: 2026-02-25
description: Erfahren Sie, wie Sie ein XPS‑Dokument erstellen und einen linearen Farbverlauf
  mit Aspose.Page für .NET anwenden. Folgen Sie unserer Schritt‑für‑Schritt‑Anleitung,
  um die XPS‑Datei zu speichern.
linktitle: Add Vertical Gradient to XPS
second_title: Aspose.Page .NET API
title: Erstellen Sie ein XPS-Dokument mit vertikalem Farbverlauf mithilfe von Aspose.Page
url: /de/net/gradient-fills/add-vertical-gradient-to-xps/
weight: 15
---

 to keep spacing and line breaks.

Now produce final content with all translations.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vertikalen Farbverlauf zu XPS mit Aspose.Page für .NET hinzufügen

## Einführung

In diesem Tutorial **erstellen Sie ein XPS-Dokument**, das einen sanften vertikalen Farbverlauf enthält. Das Hinzufügen von Farbverläufen ist eine gängige Methode, XPS-Dateien professioneller wirken zu lassen – ideal für Berichte, Broschüren oder jegliche druckbaren Grafiken. Wir führen Sie durch jeden Schritt, von der Einrichtung des Projekts bis zum Speichern der finalen XPS-Datei, sodass Sie schnell einen linearen Farbverlauf auf jeden Pfad anwenden können.

## Schnelle Antworten
- **Worum geht es in diesem Tutorial?** Einen vertikalen linearen Farbverlauf zu einem Pfad in einem XPS-Dokument hinzufügen.  
- **Welche Bibliothek wird benötigt?** Aspose.Page für .NET.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Wie lange dauert die Implementierung?** Etwa 10‑15 Minuten für ein einfaches Beispiel.  
- **Kann ich das Ergebnis als XPS-Datei speichern?** Ja, die Methode `Save` schreibt die Datei auf die Festplatte.

## Was ist ein vertikaler Farbverlauf in XPS?

Ein vertikaler Farbverlauf ist ein Farbwechsel, der von der Oberseite einer Form bis zur Unterseite verläuft. In XPS wird dies mit einem **linearen Gradient-Pinsel** realisiert, der Start‑ und Endpunkte definiert, sowie einer Sammlung von Gradient-Stops, die die Farbe an bestimmten Positionen steuern.

## Warum Aspose.Page verwenden, um XPS-Dokumente mit Farbverläufen zu erstellen?

- **Vollständige .NET-Integration** – funktioniert mit .NET Framework, .NET Core und .NET 5/6+.  
- **Keine externen Abhängigkeiten** – das gesamte Rendering wird von der Bibliothek übernommen.  
- **Hohe Treue** – Farbverläufe werden exakt wie definiert gerendert und entsprechen der XPS-Spezifikation.  
- **Einfach zu warten** – klares Objektmodell für Pfade, Pinsel und Farben.

## Voraussetzungen

- Aspose.Page für .NET Bibliothek: Stellen Sie sicher, dass die Aspose.Page für .NET Bibliothek in Ihrer Entwicklungsumgebung installiert ist. Sie können sie [hier](https://releases.aspose.com/page/net/) herunterladen.
- Entwicklungsumgebung: Richten Sie eine .NET-Entwicklungsumgebung mit Ihrer bevorzugten IDE ein, z. B. Visual Studio.

Jetzt, da wir alles bereit haben, tauchen wir in den Code ein.

## Namespaces importieren

Fügen Sie in Ihrer .NET-Anwendung die erforderlichen Namespaces hinzu, um auf die Klassen und Methoden von Aspose.Page zuzugreifen.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Schritt 1: Dokumentverzeichnis einrichten

Definieren Sie den Ordner, in dem die erzeugte XPS-Datei gespeichert wird.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Schritt 2: Neues XPS-Dokument erstellen

Instanziieren Sie ein neues XPS-Dokument, das wir später mit einem mit einem Farbverlauf gefüllten Pfad befüllen werden.

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Schritt 3: Gradient-Stops definieren

Gradient-Stops bestimmen die Farben und deren Positionen entlang der Verlaufsgeraden. Hier erstellen wir fünf Stops, um einen sanften vertikalen Übergang zu erzeugen.

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExEnd:5
```

## Schritt 4: Pfad mit Farbverlauf erstellen

Wir zeichnen einen rechteckförmigen Pfad und wenden einen **linearen Gradient-Pinsel** an, der vertikal von Punkt (10, 110) zu Punkt (10, 200) verläuft. Der Pinsel erhält die zuvor definierten Gradient-Stops.

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Schritt 5: Ergebnis‑XPS-Dokument speichern

Schließlich schreiben wir das XPS-Dokument auf die Festplatte. Dieser **Speicherschritt für XPS-Dateien** erzeugt `AddVerticalGradient_outXPS.xps` in dem von Ihnen angegebenen Ordner.

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

**Pro Tipp:** Überprüfen Sie das Ergebnis, indem Sie die XPS-Datei im Windows XPS Viewer oder einem anderen Viewer öffnen, um sicherzustellen, dass der Farbverlauf wie erwartet angezeigt wird.

## Häufige Probleme & Fehlersuche

| Symptom | Wahrscheinliche Ursache | Lösung |
|---------|--------------------------|--------|
| Farbverlauf erscheint als einfarbig | Gradient-Stops wurden nicht zum Pinsel hinzugefügt | Stellen Sie sicher, dass `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` ausgeführt wird. |
| Datei beim Speichern nicht gefunden | `dataDir` verweist auf einen nicht vorhandenen Ordner | Erstellen Sie zunächst das Verzeichnis oder verwenden Sie einen absoluten Pfad. |
| Farben sehen anders aus | Farbwerte verwenden die ARGB-Reihenfolge; prüfen Sie die Kanalreihenfolge | Verwenden Sie `CreateColor(alpha, red, green, blue)` korrekt. |

## Häufig gestellte Fragen

**F: Ist Aspose.Page mit Visual Studio 2019 kompatibel?**  
A: Ja, Aspose.Page ist mit Visual Studio 2019 kompatibel. Stellen Sie sicher, dass Sie die richtige Version der Bibliothek installiert haben.

**F: Kann ich Aspose.Page für kommerzielle Projekte nutzen?**  
A: Ja, Aspose.Page kann für kommerzielle Projekte verwendet werden. Besuchen Sie [hier](https://purchase.aspose.com/buy), um Lizenzoptionen zu erkunden.

**F: Gibt es eine kostenlose Testversion?**  
A: Ja, Sie können eine kostenlose Testversion von Aspose.Page [hier](https://releases.aspose.com/) erhalten.

**F: Wo finde ich die Aspose.Page Dokumentation?**  
A: Die Dokumentation ist [hier](https://reference.aspose.com/page/net/) verfügbar.

**F: Wie kann ich Support erhalten oder Fragen stellen?**  
A: Besuchen Sie das [Aspose.Page Forum](https://forum.aspose.com/c/page/39) für Community‑Support.

## Fazit

Sie wissen jetzt, wie Sie mit Aspose.Page für .NET **ein XPS-Dokument erstellen**, **einen linearen Farbverlauf anwenden** und **die XPS-Datei speichern** können. Dieser Ansatz gibt Ihnen die volle Kontrolle über das visuelle Styling von XPS-Ausgaben, sodass Ihre druckbaren Dokumente hervorstechen.

---  

**Zuletzt aktualisiert:** 2026-02-25  
**Getestet mit:** Aspose.Page für .NET 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}