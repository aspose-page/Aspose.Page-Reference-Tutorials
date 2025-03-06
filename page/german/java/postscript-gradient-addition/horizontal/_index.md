---
title: Fügen Sie einen horizontalen Verlauf in Java PostScript hinzu
linktitle: Fügen Sie einen horizontalen Verlauf in Java PostScript hinzu
second_title: Aspose.Page Java-API
description: Erfahren Sie, wie Sie mit Aspose.Page für Java einen horizontalen Farbverlauf in Java PostScript hinzufügen. Erstellen Sie mühelos visuell beeindruckende Dokumente.
weight: 11
url: /de/java/postscript-gradient-addition/horizontal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fügen Sie einen horizontalen Verlauf in Java PostScript hinzu

## Einführung
Willkommen zu diesem umfassenden Tutorial zum Hinzufügen eines horizontalen Farbverlaufs in Java PostScript mit Aspose.Page für Java. Aspose.Page ist eine leistungsstarke Java-Bibliothek, die Entwicklern die Arbeit mit PostScript und anderen Dokumentformaten ermöglicht. In diesem Tutorial führen wir Sie anhand von Schritt-für-Schritt-Beispielen durch den Prozess der Erstellung eines PostScript-Dokuments mit horizontalem Farbverlauf.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Java Development Kit (JDK) ist auf Ihrem Computer installiert.
- Aspose.Page für Java-Bibliothek. Sie können es hier herunterladen[Aspose.Page Java-Dokumentation](https://reference.aspose.com/page/java/).
## Pakete importieren
Beginnen Sie mit dem Importieren der erforderlichen Pakete in Ihr Java-Projekt. Diese Pakete sind für die Arbeit mit Aspose.Page von entscheidender Bedeutung.
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

```
## Schritt 1: Erstellen Sie ein Rechteck
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie einen Ausgabestream für ein PostScript-Dokument
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Erstellen Sie Speicheroptionen im A4-Format
PsSaveOptions options = new PsSaveOptions();
// Erstellen Sie ein neues PS-Dokument mit geöffneter Seite
PsDocument document = new PsDocument(outPsStream, options, false);
//Erstellen Sie ein Rechteck
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Schritt 2: Erstellen Sie eine horizontale lineare Farbverlaufsfarbe
```java
// Erstellen Sie horizontale lineare Farbverläufe. Skalierungskomponenten in der Transformation müssen der Breite und Höhe des Rechtecks entsprechen.
// Translationskomponenten sind Versätze des Rechtecks.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Farbe einstellen
document.setPaint(paint);
```
## Schritt 3: Füllen Sie das Rechteck
```java
// Füllen Sie das Rechteck
document.fill(rectangle);
```
## Schritt 4: Füllen Sie einen Text mit dem Farbverlauf
```java
// Füllen Sie einen Text mit dem Farbverlauf
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```
## Schritt 5: Streichen Sie einen Text mit dem Farbverlauf
```java
// Streichen Sie mit dem Farbverlauf über einen Text
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## Abschluss
Glückwunsch! Sie haben mit Aspose.Page für Java erfolgreich einen horizontalen Farbverlauf in Java PostScript hinzugefügt. Dieses Tutorial bietet Ihnen eine detaillierte Schritt-für-Schritt-Anleitung, die Sie bei der Erstellung optisch ansprechender PostScript-Dokumente unterstützt.
## Häufig gestellte Fragen
### Kann ich Aspose.Page für Java in kommerziellen Projekten verwenden?
Ja, Aspose.Page für Java kann in kommerziellen Projekten verwendet werden. Einzelheiten zur Lizenzierung finden Sie unter[Aspose.Kauf](https://purchase.aspose.com/buy).
### Gibt es eine kostenlose Testversion?
 Ja, Sie können auf eine kostenlose Testversion von Aspose.Page für Java zugreifen[Hier](https://releases.aspose.com/).
### Wo finde ich zusätzliche Dokumentation und Unterstützung?
 Besuche den[Aspose.Page Java-Dokumentation](https://reference.aspose.com/page/java/) für umfassende Ressourcen. Informationen zur Community-Unterstützung finden Sie unter[Aspose.Page-Forum](https://forum.aspose.com/c/page/39).
### Wie kann ich eine temporäre Lizenz erhalten?
 Eine temporäre Lizenz erhalten Sie bei[Aspose.Kauf](https://purchase.aspose.com/temporary-license/).
### Was sind die Systemanforderungen für Aspose.Page für Java?
 Siehe die[Dokumentation](https://reference.aspose.com/page/java/) für detaillierte Systemanforderungen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
