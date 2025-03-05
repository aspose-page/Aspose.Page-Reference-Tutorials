---
title: Vertikalen Farbverlauf in Java XPS hinzufügen
linktitle: Vertikalen Farbverlauf in Java XPS hinzufügen
second_title: Aspose.Page Java-API
description: Erfahren Sie, wie Sie mit Aspose.Page einen vertikalen Farbverlauf zu Java XPS-Dokumenten hinzufügen. Verbessern Sie mühelos die visuelle Attraktivität. Schritt-für-Schritt-Anleitung im Inneren.
type: docs
weight: 12
url: /de/java/xps-gradient-addition/vertical/
---
## Einführung
In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Page für Java einen vertikalen Farbverlauf in Java XPS hinzufügen. Das Hinzufügen von Farbverläufen zu Ihren XPS-Dokumenten kann die visuelle Attraktivität Ihrer Inhalte verbessern und sie ansprechender und ästhetisch ansprechender machen.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Eine funktionierende Java-Entwicklungsumgebung.
-  Aspose.Page für Java-Bibliothek. Sie können es herunterladen unter[Hier](https://releases.aspose.com/page/java/).
- Ein grundlegendes Verständnis der Java-Programmierung.
## Pakete importieren
Beginnen Sie mit dem Importieren der erforderlichen Pakete für Ihr Java-Projekt. Stellen Sie sicher, dass Sie die Aspose.Page for Java-Bibliothek in Ihre Projektabhängigkeiten aufgenommen haben.
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
        
// Importieren Sie Aspose.Page für Java
```
## Schritt 1: Initialisieren Sie das Dokument
Beginnen Sie mit der Initialisierung des XPS-Dokuments. Dies bildet die Grundlage für das Hinzufügen von Elementen wie Pfaden und Verläufen zu Ihrem Dokument.
```java
// Dokument initialisieren
XpsDocument doc = new XpsDocument();
```
## Schritt 2: Erstellen Sie einen Pfad mit vertikalem Verlauf
Lassen Sie uns nun einen Pfad mit einem vertikalen Farbverlauf erstellen. Dazu gehört die Definition der Pfadgeometrie und die Angabe der Gradientenstopps.
```java
// Erstellen Sie einen Pfad mit Geometrie
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Definieren Sie vertikale Gradientenstopps
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
//Wenden Sie den vertikalen Farbverlauf auf den Pfad an
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## Schritt 3: Speichern Sie das Dokument
Speichern Sie abschließend das XPS-Dokument mit dem hinzugefügten vertikalen Farbverlauf in Ihrem gewünschten Verzeichnis.
```java
// Speichern Sie das Dokument
doc.save(dataDir + "VerticalGradient.xps");
```
Glückwunsch! Sie haben mit Aspose.Page erfolgreich einen vertikalen Farbverlauf zu Ihrem Java XPS-Dokument hinzugefügt.
## Abschluss
Die Verbesserung Ihrer XPS-Dokumente mit Farbverläufen kann deren visuelle Attraktivität erheblich verbessern. Aspose.Page für Java vereinfacht diesen Prozess und ermöglicht Ihnen die einfache Erstellung beeindruckender Dokumente.

### FAQs
### Kann ich Aspose.Page für Java in kommerziellen Projekten verwenden?
 Ja, Aspose.Page für Java ist für die kommerzielle Nutzung verfügbar. Sie können es kaufen[Hier](https://purchase.aspose.com/buy).
### Gibt es eine kostenlose Testversion für Aspose.Page für Java?
 Ja, Sie können auf eine kostenlose Testversion zugreifen[Hier](https://releases.aspose.com/).
### Wo finde ich die Dokumentation für Aspose.Page für Java?
 Die Dokumentation ist verfügbar[Hier](https://reference.aspose.com/page/java/).
### Wie kann ich eine temporäre Lizenz für Aspose.Page für Java erhalten?
 Besorgen Sie sich eine temporäre Lizenz[Hier](https://purchase.aspose.com/temporary-license/).
### Benötigen Sie Hilfe oder haben Sie Fragen?
 Besuchen Sie die Aspose.Page-Community[Forum](https://forum.aspose.com/c/page/39).