---
title: Fügen Sie mit Aspose.Page eine radiale Verlaufsellipse hinzu
linktitle: Ellipse in Java XPS hinzufügen
second_title: Aspose.Page Java-API
description: Entdecken Sie die Schritt-für-Schritt-Anleitung zum Hinzufügen einer Ellipse mit radialem Farbverlauf in Java XPS mithilfe von Aspose.Page für Java. Verbessern Sie Ihre Dokumentenerstellung mühelos.
type: docs
weight: 10
url: /de/java/xps-shapes/add-ellipse/
---
## Einführung
Willkommen zu unserer Schritt-für-Schritt-Anleitung zum Hinzufügen einer Ellipse in Java XPS mit Aspose.Page für Java. Aspose.Page ist eine leistungsstarke Java-Bibliothek, die es Entwicklern ermöglicht, mühelos mit XPS-Dokumenten zu arbeiten. In diesem Tutorial führen wir Sie durch den Prozess der Erstellung einer Ellipse mit radialem Farbverlauf und deren Speicherung als XPS-Dokument.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Java Development Kit (JDK) ist auf Ihrem Computer installiert.
-  Aspose.Page für Java-Bibliothek heruntergeladen. Du kannst es bekommen[Hier](https://releases.aspose.com/page/java/).
- Ein Code-Editor Ihrer Wahl (Eclipse, IntelliJ usw.) zum Schreiben und Ausführen von Java-Code.
## Pakete importieren
Stellen Sie sicher, dass Sie die erforderlichen Pakete in Ihr Java-Projekt importiert haben, um Aspose.Page zu verwenden. Fügen Sie die folgenden Importanweisungen am Anfang Ihrer Java-Datei hinzu:
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
## Schritt 1: Dokumentenverzeichnis einrichten
Definieren Sie den Pfad zu Ihrem Dokumentverzeichnis, in dem das XPS-Dokument gespeichert wird:
```java
String dataDir = "Your Document Directory";
```
## Schritt 2: XPS-Dokument erstellen
Initialisieren Sie ein neues XPS-Dokument mit dem folgenden Code:
```java
XpsDocument doc = new XpsDocument();
```
## Schritt 3: Definieren Sie radiale Gradientenstopps
Erstellen Sie eine Liste mit Verlaufsstopps für die Ellipse mit radialem Verlaufsstrich:
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```
## Schritt 4: Pfadgeometrie erstellen
Definieren Sie eine Ellipse mit radialem Verlaufsstrich mithilfe der Pfadgeometrie:
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```
## Schritt 5: Leinwand und Pfad hinzufügen
Fügen Sie dem Dokument eine neue Leinwand hinzu und hängen Sie den Pfad mit der definierten Geometrie an:
```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```
## Schritt 6: Legen Sie Strich und Verlauf fest
Konfigurieren Sie den Strich des Pfads mit einem radialen Verlaufspinsel:
```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```
## Schritt 7: Strichstärke einstellen
Geben Sie die Strichstärke des Pfads an:
```java
path.setStrokeThickness(12f);
```
## Schritt 8: Speichern Sie das Dokument
Speichern Sie das resultierende XPS-Dokument:
```java
doc.save(dataDir + "AddEllipse_out.xps");
```
Glückwunsch! Sie haben mit Aspose.Page für Java erfolgreich eine Ellipse mit radialem Farbverlauf in Java XPS hinzugefügt.
## Abschluss
In diesem Tutorial haben wir die Schritte zum Erstellen eines XPS-Dokuments mit einer optisch ansprechenden, radial verlaufenden Ellipse untersucht. Aspose.Page für Java vereinfacht die Manipulation von XPS-Dokumenten und stellt Entwicklern ein leistungsstarkes Toolset zur Verfügung.
## Häufig gestellte Fragen
### Kann ich Aspose.Page für Java mit anderen Java-Bibliotheken verwenden?
Ja, Aspose.Page für Java kann nahtlos in andere Java-Bibliotheken integriert werden.
### Ist Aspose.Page für die Verarbeitung umfangreicher Dokumente geeignet?
Absolut! Aspose.Page wurde für die effiziente Verarbeitung umfangreicher Dokumente entwickelt.
### Wo finde ich weitere Tutorials und Beispiele für Aspose.Page für Java?
 Besuche den[Aspose.Page für Java-Dokumentation](https://reference.aspose.com/page/java/)für umfassende Tutorials und Beispiele.
### Wie kann ich eine temporäre Lizenz für Aspose.Page für Java erhalten?
 Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).
### Gibt es Community-Foren für Aspose.Page-Diskussionen?
 Ja, treten Sie dem bei[Aspose.Page-Community-Forum](https://forum.aspose.com/c/page/39) um mit anderen Entwicklern in Kontakt zu treten und Unterstützung zu erhalten.