---
title: Anpassen von Java PostScript – Hinzufügen von Rechtecken mit Aspose.Page
linktitle: Rechteck in Java PostScript hinzufügen
second_title: Aspose.Page Java-API
description: Entdecken Sie die Schritt-für-Schritt-Anleitung zum Hinzufügen lebendiger Rechtecke zu Java-PostScript-Dokumenten mit Aspose.Page für Java. Verbessern Sie Ihre Dokumentanpassung mühelos!
weight: 11
url: /de/java/postscript-shapes/add-rectangle/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Anpassen von Java PostScript – Hinzufügen von Rechtecken mit Aspose.Page

## Einführung
Möchten Sie Ihre Java-PostScript-Dokumente mit lebendigen Rechtecken aufwerten? Suchen Sie nicht weiter! In dieser Schritt-für-Schritt-Anleitung erfahren Sie, wie Sie mit Aspose.Page für Java Rechtecke zu Ihren PostScript-Dokumenten hinzufügen. Aspose.Page ist eine leistungsstarke Bibliothek, die robuste Funktionen für die Arbeit mit PostScript-Dateien bietet und somit eine ideale Wahl für Entwickler ist, die ihre Dokumente bearbeiten und anpassen möchten.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundlegendes Verständnis der Java-Programmierung.
-  Aspose.Page für Java-Bibliothek installiert. Wenn nicht, laden Sie es herunter[Aspose.Page für Java-Dokumentation](https://reference.aspose.com/page/java/).
- Eine auf Ihrem Computer eingerichtete Java-Entwicklungsumgebung.
## Pakete importieren
Beginnen Sie in Ihrem Java-Projekt mit dem Importieren der erforderlichen Pakete:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Tutorial: Rechtecke in Java PostScript hinzufügen
## Schritt 1: Farbe zum Füllen des Rechtecks festlegen
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie einen Ausgabestream für ein PostScript-Dokument
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Erstellen Sie Speicheroptionen im A4-Format
PsSaveOptions options = new PsSaveOptions();
// Erstellen Sie ein neues PS-Dokument mit geöffneter Seite
PsDocument document = new PsDocument(outPsStream, options, false);
// Stellen Sie die Farbe zum Füllen des Rechtecks ein
document.setPaint(Color.ORANGE);        
// Füllen Sie das erste Rechteck
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```
## Schritt 2: Legen Sie die Farbe für das Streichen des Rechtecks fest
```java
// Stellen Sie die Farbe zum Streichen des Rechtecks ein
document.setPaint(Color.RED);
// Hub einstellen
document.setStroke(new BasicStroke(3));
// Zeichnen (umreißen) Sie das zweite Rechteck
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```
## Schritt 3: Aktuelle Seite schließen und Dokument speichern
```java
// Aktuelle Seite schließen
document.closePage();
// Speichern Sie das Dokument
document.save();
```
Glückwunsch! Sie haben Ihrem Java-PostScript-Dokument mit Aspose.Page erfolgreich lebendige Rechtecke hinzugefügt.
## Abschluss
In diesem Tutorial haben wir den Prozess der Erweiterung Ihrer Java-PostScript-Dokumente mit Rechtecken mithilfe von Aspose.Page für Java untersucht. Diese leistungsstarke Bibliothek eröffnet Entwicklern, die ihre Dokumente mühelos anpassen und bearbeiten möchten, eine Welt voller Möglichkeiten.
Viel Spaß beim Experimentieren mit verschiedenen Formen und Farben, um Ihre Dokumente optisch ansprechend zu gestalten!
## Häufig gestellte Fragen

### Kann ich Aspose.Page für Java mit anderen Programmiersprachen verwenden?
Aspose.Page unterstützt hauptsächlich Java, ähnliche Bibliotheken sind jedoch auch für andere Sprachen verfügbar.
### Gibt es eine Testversion von Aspose.Page für Java?
 Ja, Sie können die Funktionen von Aspose.Page für Java mit dem erkunden[kostenlose Testversion](https://releases.aspose.com/).
### Wo finde ich zusätzliche Hilfe und Diskussionen?
 Besuche den[Aspose.Page-Forum](https://forum.aspose.com/c/page/39) um mit der Gemeinschaft in Kontakt zu treten und Hilfe zu erhalten.
### Wie kann ich eine temporäre Lizenz für Aspose.Page für Java erhalten?
 Holen Sie sich eine temporäre Lizenz[Hier](https://purchase.aspose.com/temporary-license/).
### Wo kann ich eine lizenzierte Version von Aspose.Page für Java erwerben?
 Kaufen Sie eine lizenzierte Version[Hier](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
