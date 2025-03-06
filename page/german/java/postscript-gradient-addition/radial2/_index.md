---
title: Radialer Java-PostScript-Verlauf mit Aspose.Page
linktitle: Radialer Java-PostScript-Verlauf mit Aspose.Page
second_title: Aspose.Page Java-API
description: Entdecken Sie die Schritt-für-Schritt-Anleitung zum Hinzufügen von Radial Gradient in Java PostScript mit Aspose.Page für beeindruckende Grafiken in Ihren Java-Anwendungen.
weight: 13
url: /de/java/postscript-gradient-addition/radial2/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Radialer Java-PostScript-Verlauf mit Aspose.Page

## Einführung
Willkommen zu unserer Schritt-für-Schritt-Anleitung zum Hinzufügen von Radial Gradient 2 in Java PostScript mit Aspose.Page für Java. Dieses Tutorial führt Sie durch den Prozess der Erstellung eines PostScript-Dokuments mit einem schönen radialen Farbverlauf und bereichert Ihre Java-Anwendungen mit optisch ansprechenden Grafiken.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundkenntnisse der Java-Programmierung.
- Installiertes Java Development Kit (JDK) auf Ihrem Computer.
-  Aspose.Page für Java-Bibliothek, die Sie von der herunterladen können[Aspose.Page Java-Dokumentation](https://reference.aspose.com/page/java/).
## Pakete importieren
Importieren Sie in Ihrem Java-Projekt die erforderlichen Pakete für Aspose.Page:
```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Schritt 1: Dokumentenverzeichnis einrichten
Definieren Sie den Pfad zu Ihrem Dokumentenverzeichnis:
```java
String dataDir = "Your Document Directory";
```
## Schritt 2: Ausgabestream erstellen
Erstellen Sie einen Ausgabestream für das PostScript-Dokument:
```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```
## Schritt 3: Speicheroptionen erstellen
Erstellen Sie Speicheroptionen im A4-Format:
```java
PsSaveOptions options = new PsSaveOptions();
```
## Schritt 4: PS-Dokument erstellen
Erstellen Sie ein neues PS-Dokument mit geöffneter Seite:
```java
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Schritt 5: Erstellen Sie einen Kreis
Definieren Sie einen Kreis mit der Klasse Ellipse2D.Float:
```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```
## Schritt 6: Verlaufsfarben definieren
Erstellen Sie Arrays aus Farben und Brüchen für den radialen Farbverlauf:
```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```
## Schritt 7: AffineTransform erstellen
Erstellen Sie eine AffineTransform für den radialen Farbverlauf:
```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```
## Schritt 8: Erstellen Sie eine radiale Verlaufsfarbe
Erstellen Sie ein RadialGradientPaint mit den angegebenen Parametern:
```java
RadialGradientPaint paint = new RadialGradientPaint(new Point2D.Float(64, 64), 68, new Point2D.Float(24, 24),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## Schritt 9: Legen Sie Farbe fest und füllen Sie den Kreis
Tragen Sie die Farbe auf und füllen Sie den Kreis mit dem radialen Farbverlauf:
```java
document.setPaint(paint);
document.fill(circle);
```
## Schritt 10: Seite schließen und Dokument speichern
Schließen Sie die aktuelle Seite und speichern Sie das Dokument:
```java
document.closePage();
document.save();
```
Glückwunsch! Sie haben Radial Gradient 2 erfolgreich in Java PostScript mit Aspose.Page für Java hinzugefügt.
## Abschluss
In diesem Tutorial haben wir untersucht, wie Sie Ihre Java-Anwendungen mit radialen Verläufen in PostScript-Dokumenten verbessern können. Aspose.Page für Java bietet leistungsstarke Tools zum Erstellen atemberaubender Grafiken, mit denen Sie Ihre Java-Projekte auf die nächste Stufe heben können.
## FAQs
### F: Wo finde ich die Dokumentation für Aspose.Page für Java?
 A: Die Dokumentation ist verfügbar[Hier](https://reference.aspose.com/page/java/).
### F: Wie kann ich Aspose.Page für Java herunterladen?
 A: Sie können es von herunterladen[Veröffentlichungsseite](https://releases.aspose.com/page/java/).
### F: Gibt es eine kostenlose Testversion?
 A: Ja, Sie können auf die kostenlose Testversion zugreifen[Hier](https://releases.aspose.com/).
### F: Kann ich eine temporäre Lizenz für Aspose.Page für Java erhalten?
 A: Ja, Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).
### F: Wo kann ich Community-Unterstützung suchen und an Diskussionen teilnehmen?
 A: Besuchen Sie die[Aspose.Page-Forum](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
