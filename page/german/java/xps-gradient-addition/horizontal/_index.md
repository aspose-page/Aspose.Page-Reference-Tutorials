---
title: Fügen Sie einen horizontalen Farbverlauf in Java XPS hinzu
linktitle: Fügen Sie einen horizontalen Farbverlauf in Java XPS hinzu
second_title: Aspose.Page Java-API
description: Erfahren Sie, wie Sie mit Aspose.Page XPS-Dokumenten in Java einen beeindruckenden horizontalen Farbverlauf hinzufügen. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für eine nahtlose Integration.
weight: 11
url: /de/java/xps-gradient-addition/horizontal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fügen Sie einen horizontalen Farbverlauf in Java XPS hinzu

## Einführung
Willkommen bei dieser Schritt-für-Schritt-Anleitung zum Hinzufügen eines horizontalen Farbverlaufs in Java XPS mit Aspose.Page für Java. Aspose.Page für Java ist eine leistungsstarke Bibliothek, die Entwicklern die nahtlose Arbeit mit XPS-Dokumenten (XML Paper Specification) ermöglicht.
In diesem Tutorial führen wir Sie durch den Prozess der Erstellung einer Java-Anwendung zum Hinzufügen eines horizontalen Farbverlaufs zu einem XPS-Dokument. Befolgen Sie die nachstehenden Schritte, um dies ganz einfach zu erreichen.
## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1. Java-Entwicklungsumgebung: Stellen Sie sicher, dass Java auf Ihrem System installiert ist. Wenn nicht, laden Sie die neueste Version von Java herunter und installieren Sie sie[java.com](https://www.java.com).
2.  Aspose.Page für Java-Bibliothek: Sie benötigen die Aspose.Page für Java-Bibliothek. Sie können es hier herunterladen[Aspose.Page für Java-Dokumentation](https://reference.aspose.com/page/java/).
## Pakete importieren
Beginnen Sie mit dem Importieren der erforderlichen Pakete für Ihre Java-Anwendung. Binden Sie die Aspose.Page for Java-Bibliothek in Ihr Projekt ein. Sie können dies tun, indem Sie die folgenden Codezeilen hinzufügen:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```
## Schritt 1: Dokument initialisieren
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
//Dokument initialisieren
XpsDocument doc = new XpsDocument();
```
## Schritt 2: Erstellen Sie einen horizontalen Farbverlauf
```java
// Horizontaler Farbverlauf
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```
## Schritt 3: Pfad mit Farbverlauf hinzufügen
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```
## Schritt 4: Speichern Sie das Dokument
```java
doc.save(dataDir + "HorizontalGradient.xps");
```
Wiederholen Sie diese Schritte nach Bedarf und passen Sie die Parameter entsprechend Ihren spezifischen Anforderungen an.
## Abschluss
Glückwunsch! Sie haben mit Aspose.Page für Java erfolgreich einen horizontalen Farbverlauf zu einem XPS-Dokument hinzugefügt. Dieses Tutorial bietet eine umfassende Anleitung für Entwickler, die ihre Java-Anwendungen mit Farbverlaufseffekten verbessern möchten.
## FAQs
### F: Kann ich mehrere Farbverläufe in einem einzigen XPS-Dokument anwenden?
Ja, Sie können mehrere Pfade mit unterschiedlichen Farbverläufen hinzufügen, um komplexe Designs zu erstellen.
### F: Ist Aspose.Page mit den neuesten Java-Versionen kompatibel?
Aspose.Page für Java wird regelmäßig aktualisiert, um die Kompatibilität mit den neuesten Java-Versionen sicherzustellen.
### F: Sind in Aspose.Page andere Verlaufstypen verfügbar?
Ja, neben linearen Farbverläufen unterstützt Aspose.Page auch radiale Farbverläufe für vielfältigere Effekte.
### F: Kann ich die Farben und Positionen von Verlaufsstopps anpassen?
Absolut! Sie haben die volle Kontrolle über die Farben und Positionen jedes Verlaufsstopps.
### F: Gibt es ein Community-Forum für Aspose.Page, in dem ich Hilfe suchen kann?
 Ja, Sie können die besuchen[Aspose.Page-Forum](https://forum.aspose.com/c/page/39) um mit der Community in Kontakt zu treten und Hilfe zu erhalten.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
