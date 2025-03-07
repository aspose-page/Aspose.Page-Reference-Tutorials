---
title: Aspose.Page Java-Textmanipulation
linktitle: Fügen Sie Text in Java PostScript hinzu
second_title: Aspose.Page Java-API
description: Entdecken Sie die Leistungsfähigkeit von Aspose.Page für Java in unserem Tutorial zum Hinzufügen von Text zu PostScript-Dokumenten. Lernen Sie, System- und benutzerdefinierte Schriftarten problemlos zu verwenden.
weight: 10
url: /de/java/postscript-text-manipulation/add-text/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java-Textmanipulation

## Einführung
Willkommen zu unserer Schritt-für-Schritt-Anleitung zum Hinzufügen von Text in Java PostScript mit Aspose.Page für Java. Aspose.Page für Java ist eine leistungsstarke Bibliothek, die Entwicklern die einfache Bearbeitung von PostScript-Dokumenten ermöglicht. In diesem Tutorial führen wir Sie durch den Prozess des Hinzufügens von Text, der Verwendung von System- und benutzerdefinierten Schriftarten, dem Umreißen von Text und dem Einfügen von Strichen für ein optisch ansprechendes Ergebnis.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Grundkenntnisse der Java-Programmierung.
-  Aspose.Page für Java-Bibliothek installiert. Sie können es hier herunterladen[Aspose.Page für Java-Downloadseite](https://releases.aspose.com/page/java/).
-  Erforderliche Schriftarten sind im angegebenen Ordner verfügbar. Weitere Informationen finden Sie im[Aspose.Page für Java-Dokumentation](https://reference.aspose.com/page/java/).
## Pakete importieren
Importieren Sie in Ihrem Java-Projekt die erforderlichen Pakete für Aspose.Page für Java:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```
## Schritt 1: Richten Sie das Dokument ein
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Erstellen Sie einen Ausgabestream für ein PostScript-Dokument
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Erstellen Sie Speicheroptionen im A4-Format
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// Ein Text zum Schreiben in eine PS-Datei
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Erstellen Sie ein neues einseitiges PS-Dokument
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Schritt 2: Systemschriftart zum Füllen von Text verwenden
```java
// Verwenden der Systemschriftart zum Füllen von Text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Text mit Standardfarbe oder bereits definierter Farbe (Schwarz) füllen
document.fillText(str, font, 50, 100);
// Füllen Sie den Text mit blauer Farbe
document.fillText(str, font, 50, 150, Color.BLUE);
```
## Schritt 3: Benutzerdefinierte Schriftart zum Füllen von Text verwenden
```java
// Verwenden einer benutzerdefinierten Schriftart zum Füllen von Text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Text mit Standardfarbe oder bereits definierter Farbe (Schwarz) füllen
document.fillText(str, drFont, 50, 200);
// Füllen Sie den Text mit blauer Farbe
document.fillText(str, drFont, 50, 250, Color.BLUE);
```
## Schritt 4: Text mit Systemschrift umreißen
```java
// Verwenden der Systemschriftart zum Umreißen von Text
document.outlineText(str, font, 50, 300);
// Umreißen Sie den Text mit einem blauvioletten 2-Punkt-Stift
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Füllen Sie den Text mit orangefarbener Farbe und zeichnen Sie ihn mit einem blauen Stift mit 2 Spitzen Breite
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```
## Schritt 5: Text mit benutzerdefinierter Schriftart umreißen
```java
// Verwenden einer benutzerdefinierten Schriftart zum Umreißen von Text
document.outlineText(str, drFont, 50, 450);
// Umreißen Sie den Text mit einem blauvioletten 2-Punkt-Stift
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Füllen Sie den Text mit orangefarbener Farbe und zeichnen Sie ihn mit einem blauen Stift mit 2 Spitzen Breite
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```
## Schritt 6: Speichern Sie das Dokument
```java
// Aktuelle Seite schließen
document.closePage();
// Speichern Sie das Dokument
document.save();
```
## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Page für Java Text in Java PostScript hinzufügen. Experimentieren Sie mit verschiedenen Schriftarten, Farben und Gliederungsoptionen, um Ihr Dokument weiter aufzuwerten.
## Häufig gestellte Fragen
### Kann ich mit Aspose.Page für Java meine eigenen benutzerdefinierten Schriftarten verwenden?
 Ja, Sie können benutzerdefinierte Schriftarten verwenden, indem Sie den Namen und die Größe der Schriftart im angeben`DrFont` Klasse.
### Wie kann ich die Farbe des Textes ändern?
 Mit können Sie die gewünschte Farbe einstellen`Color` Klasse beim Ausfüllen oder Umreißen des Textes.
### Ist es möglich, einem PostScript-Dokument mehrere Seiten hinzuzufügen?
Absolut! Sie können mehrere Seiten erstellen, indem Sie die Schritte zum Erstellen und Speichern des Dokuments wiederholen.
###  Was ist der Zweck des`ExternalFontCache` class?
`ExternalFontCache` wird verwendet, um benutzerdefinierte Schriftarten abzurufen und sicherzustellen, dass sie für die Textbearbeitung verfügbar sind.
### Kann ich dem umrissenen Text unterschiedliche Striche hinzufügen?
 Ja, Sie können die Breite und Farbe des Strichs mithilfe von anpassen`Stroke` Klasse und`Color` Klasse bzw.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
