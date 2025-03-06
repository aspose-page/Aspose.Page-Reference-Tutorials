---
title: Fügen Sie einen vertikalen Farbverlauf in Java PostScript hinzu
linktitle: Fügen Sie einen vertikalen Farbverlauf in Java PostScript hinzu
second_title: Aspose.Page Java-API
description: Entdecken Sie die Schritt-für-Schritt-Anleitung zum Hinzufügen vertikaler Farbverläufe in Java PostScript mit Aspose.Page für Java. Werten Sie Ihre Dokumente mühelos mit lebendigen Bildern auf.
weight: 14
url: /de/java/postscript-gradient-addition/vertical/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fügen Sie einen vertikalen Farbverlauf in Java PostScript hinzu

## Einführung
Willkommen bei dieser Schritt-für-Schritt-Anleitung zum Hinzufügen eines vertikalen Farbverlaufs in Java PostScript mit Aspose.Page für Java. Wenn Sie Ihr Dokument mit auffälligen Farbverläufen aufwerten möchten, ist dieses Tutorial genau das Richtige für Sie. Aspose.Page für Java bietet leistungsstarke Tools zur nahtlosen Bearbeitung von PostScript-Dokumenten.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Java Development Kit (JDK) ist auf Ihrem Computer installiert.
-  Aspose.Page für Java-Bibliothek. Sie können es herunterladen[Hier](https://releases.aspose.com/page/java/).
## Pakete importieren
Importieren Sie in Ihrem Java-Projekt die erforderlichen Pakete, um loszulegen:
```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
Lassen Sie uns nun den Prozess des Hinzufügens eines vertikalen Farbverlaufs in Java PostScript in mehrere Schritte unterteilen.
## Schritt 1: Richten Sie Ihr Dokumentenverzeichnis ein
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
```
## Schritt 2: Ausgabestream für PostScript-Dokument erstellen
```java
// Erstellen Sie einen Ausgabestream für ein PostScript-Dokument
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```
## Schritt 3: Erstellen Sie Speicheroptionen im A4-Format
```java
// Erstellen Sie Speicheroptionen im A4-Format
PsSaveOptions options = new PsSaveOptions();
```
## Schritt 4: Erstellen Sie ein neues PS-Dokument
```java
// Erstellen Sie ein neues PS-Dokument mit geöffneter Seite
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Schritt 5: Erstellen Sie ein Rechteck
```java
//Erstellen Sie ein Rechteck
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Schritt 6: Richten Sie Farben und Brüche für den Farbverlauf ein
```java
// Erstellen Sie Arrays aus Farben und Brüchen für den Farbverlauf.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```
## Schritt 7: Erstellen Sie die Verlaufstransformation
```java
// Erstellen Sie die Verlaufstransformation. Skalierungskomponenten in der Transformation müssen der Breite und Höhe des Rechtecks entsprechen.
// Translationskomponenten sind Versätze des Rechtecks.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Drehen Sie den Farbverlauf um 90 Grad um einen Ursprung
transform.rotate(90 * (Math.PI / 180));
```
## Schritt 8: Erstellen Sie eine vertikale lineare Verlaufsfarbe
```java
// Erstellen Sie eine vertikale lineare Farbverlaufsfarbe.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## Schritt 9: Legen Sie die Farbe fest und füllen Sie das Rechteck
```java
// Farbe einstellen
document.setPaint(paint);
// Füllen Sie das Rechteck
document.fill(rectangle);
```
## Schritt 10: Aktuelle Seite schließen und Dokument speichern
```java
// Aktuelle Seite schließen
document.closePage();
// Speichern Sie das Dokument
document.save();
```
Glückwunsch! Sie haben mit Aspose.Page für Java erfolgreich einen vertikalen Farbverlauf zu Ihrem Java-PostScript-Dokument hinzugefügt.
## Abschluss
In diesem Tutorial haben wir den Prozess der Verbesserung Ihrer Dokumente mit lebendigen vertikalen Verläufen mithilfe von Aspose.Page für Java untersucht. Jetzt können Sie Ihre Dokumentenmanipulationen auf die nächste Stufe heben, indem Sie atemberaubende visuelle Elemente integrieren.
## Häufig gestellte Fragen
### Kann ich Aspose.Page für Java mit anderen Java-Bibliotheken verwenden?
Ja, Aspose.Page für Java ist so konzipiert, dass es nahtlos mit anderen Java-Bibliotheken zusammenarbeitet.
### Gibt es eine kostenlose Testversion für Aspose.Page für Java?
 Ja, Sie können eine kostenlose Testversion erhalten[Hier](https://releases.aspose.com/).
### Wo finde ich zusätzliche Dokumentation?
 Eine ausführliche Dokumentation ist verfügbar[Hier](https://reference.aspose.com/page/java/).
### Wie kann ich Aspose.Page für Java kaufen?
 Sie können Aspose.Page für Java erwerben[Hier](https://purchase.aspose.com/buy).
### Gibt es ein Forum für Aspose.Page-Diskussionen?
 Ja, Sie können dem Community-Forum beitreten[Hier](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
