---
date: 2026-04-24
description: Erfahren Sie, wie Sie ein XPS‑Dokument in Java mit einer radialen Farbverlauf‑Ellipse
  erstellen. Diese Schritt‑für‑Schritt‑Anleitung zeigt, wie Sie die Strichstärke festlegen
  und die Pfadgeometrie mit Aspose.Page definieren.
keywords:
- create xps document java
- set stroke thickness
- define path geometry
linktitle: Ellipse in Java XPS hinzufügen
second_title: Aspose.Page Java API
title: XPS-Dokument in Java erstellen – Radialen Farbverlauf‑Ellipse hinzufügen
url: /de/java/xps-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Radialverlauf‑Ellipse mit Aspose.Page hinzufügen

## Einleitung
In diesem Tutorial lernen Sie, wie Sie **create XPS document Java** mit einer schönen radialen Farbverlauf‑Kontur‑Ellipse mithilfe von Aspose.Page für Java erstellen. Aspose.Page ist eine robuste Bibliothek, die die Low‑Level‑XPS‑Details abstrahiert und Ihnen ermöglicht, sich auf das Design statt auf Dateiformat‑Details zu konzentrieren. Am Ende dieser Anleitung haben Sie eine einsatzbereite XPS‑Datei, die Sie in Berichten, Rechnungen oder jedem Dokument‑Generierungs‑Workflow einbetten können.

## Schnelle Antworten
- **Was erzeugt dieser Code?** Eine einseitige XPS‑Datei, die eine Ellipse mit einem mehrfarbigen radialen Farbverlauf enthält.  
- **Welche primäre API wird verwendet?** `Aspose.Page` für Java (`XpsDocument`, `XpsCanvas`, `XpsPath`, etc.).  
- **Benötige ich eine Lizenz, um das Beispiel auszuführen?** Eine temporäre Lizenz funktioniert für die Evaluierung; für die Produktion ist eine Voll‑Lizenz erforderlich.  
- **Welche Schlüsseleigenschaften setzen wir?** Stroke‑Brush (radialer Farbverlauf), Spread‑Methode, Gradient‑Stops und Stroke‑Dicke.  
- **Kann ich die Größe der Ellipse ändern?** Ja – ändern Sie die Pfadgeometrie‑Zeichenkette oder die Koordinaten des Gradient‑Brushes.

## Was bedeutet “create XPS document Java”?
Ein XPS‑Dokument in Java zu erstellen bedeutet, programmgesteuert eine XML Paper Specification (XPS)‑Datei – ein festes Layout‑Dokumentformat ähnlich PDF – direkt aus Java‑Code zu generieren. Aspose.Page stellt ein hoch‑level Objektmodell (`XpsDocument`, `XpsCanvas` usw.) bereit, das das XML‑Markup abstrahiert und den Prozess so einfach macht wie die Arbeit mit Standard‑Java‑Objekten.

## Warum einen radialen Farbverlauf‑Ellipse verwenden?
Ein radialer Farbverlauf vermittelt einen dreidimensionalen Eindruck, ideal für visuelle Highlights, Logos oder dekorative Elemente in Berichten. Im Vergleich zu einer einfarbigen Kontur verleiht der Verlauf Tiefe, ohne die Dateigröße wesentlich zu erhöhen, und das XPS‑Format bewahrt die Vektor‑Qualität bei jeder Skalierung.

## Voraussetzungen
- Java Development Kit (JDK) auf Ihrem Rechner installiert.  
- Aspose.Page for Java Bibliothek heruntergeladen. Sie können sie [hier](https://releases.aspose.com/page/java/) erhalten.  
- Ein Code‑Editor Ihrer Wahl (Eclipse, IntelliJ usw.) zum Schreiben und Ausführen von Java‑Code.

## Pakete importieren
Stellen Sie sicher, dass die erforderlichen Pakete in Ihrem Java‑Projekt importiert sind, um Aspose.Page zu nutzen. Fügen Sie die folgenden Import‑Anweisungen am Anfang Ihrer Java‑Datei hinzu:

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```

## Schritt 1: Dokumentverzeichnis einrichten
Definieren Sie den Pfad zu Ihrem Dokumentverzeichnis, in dem das XPS‑Dokument gespeichert wird:

```java
String dataDir = "Your Document Directory";
```

## Schritt 2: XPS‑Dokument erstellen
Initialisieren Sie ein neues XPS‑Dokument mit dem folgenden Code:

```java
XpsDocument doc = new XpsDocument();
```

## Schritt 3: Radiale Farbverlauf‑Stops definieren
Erstellen Sie eine Liste von Gradient‑Stops für die radial gestreckte Ellipse:

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```

## Schritt 4: Pfadgeometrie erstellen
Definieren Sie eine radial gestreckte Ellipse mithilfe von Pfadgeometrie:

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```

## Schritt 5: Canvas und Pfad hinzufügen
Fügen Sie dem Dokument ein neues Canvas hinzu und hängen Sie den Pfad mit der definierten Geometrie an:

```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```

## Schritt 6: Kontur und Farbverlauf festlegen
Konfigurieren Sie die Kontur des Pfads mit einem radialen Gradient‑Brush:

```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```

## Schritt 7: Konturstärke festlegen
Geben Sie die **set stroke thickness** des Pfads an:

```java
path.setStrokeThickness(12f);
```

## Schritt 8: Dokument speichern
Speichern Sie das resultierende XPS‑Dokument:

```java
doc.save(dataDir + "AddEllipse_out.xps");
```

Herzlichen Glückwunsch! Sie haben erfolgreich eine radialen Farbverlauf‑Kontur‑Ellipse hinzugefügt, während Sie **create XPS document Java** mit Aspose.Page erstellt haben.

## Häufige Probleme und Lösungen
| Problem | Warum es passiert | Lösung |
|-------|----------------|-----|
| **Ellipse erscheint flach** | Verwendung von `XpsSpreadMethod.Pad` anstelle von `Reflect` | Ändern Sie die Spread‑Methode zu `XpsSpreadMethod.Reflect` wie in Schritt 6 gezeigt. |
| **Keine Ausgabedatei** | `dataDir` verweist auf einen nicht vorhandenen Ordner | Stellen Sie sicher, dass das Verzeichnis existiert oder verwenden Sie einen absoluten Pfad. |
| **Farbverlauf‑Farben sehen falsch aus** | Falsche Reihenfolge der Gradient‑Stops | Überprüfen Sie, dass die `offset`‑Werte (0 → 1) monoton ansteigen. |
| **Kompilierungsfehler** | Fehlende Aspose.Page‑JARs im Klassenpfad | Fügen Sie `aspose-page-xx.jar` zu den Projektabhängigkeiten hinzu. |

## Häufig gestellte Fragen

**Q: Kann ich Aspose.Page für Java mit anderen Java‑Bibliotheken verwenden?**  
A: Ja, Aspose.Page für Java lässt sich nahtlos in andere Java‑Bibliotheken integrieren.

**Q: Ist Aspose.Page für die Verarbeitung großer Dokumentenmengen geeignet?**  
A: Absolut! Aspose.Page ist darauf ausgelegt, die Verarbeitung großer Dokumentenmengen effizient zu bewältigen.

**Q: Wo finde ich weitere Tutorials und Beispiele für Aspose.Page für Java?**  
A: Besuchen Sie die [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) für umfassende Tutorials und Beispiele.

**Q: Wie kann ich eine temporäre Lizenz für Aspose.Page für Java erhalten?**  
A: Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erhalten.

**Q: Gibt es Community‑Foren für Aspose.Page‑Diskussionen?**  
A: Ja, treten Sie dem [Aspose.Page community forum](https://forum.aspose.com/c/page/39) bei, um sich mit anderen Entwicklern auszutauschen und Unterstützung zu erhalten.

---

**Zuletzt aktualisiert:** 2026-04-24  
**Getestet mit:** Aspose.Page für Java 24.11 (aktuell zum Zeitpunkt der Erstellung)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}