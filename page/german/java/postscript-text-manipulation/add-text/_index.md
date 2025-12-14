---
date: 2025-12-14
description: Erfahren Sie, wie Sie die Textfarbe in Java mit Aspose.Page für Java
  festlegen, Text zu PostScript hinzufügen und Konturtext für eine umfangreiche Dokumentgestaltung
  anwenden.
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: Textfarbe in Java mit Aspose.Page festlegen – Leitfaden zur Textmanipulation
url: /de/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Set Text Color Java with Aspose.Page – Text Manipulation Guide

## Einleitung
Willkommen zu unserem Schritt‑für‑Schritt‑Leitfaden zum **set text color java**, während Sie mit PostScript‑Dateien unter Verwendung von Aspose.Page für Java arbeiten. Aspose.Page für Java ist eine leistungsstarke Bibliothek, die Entwicklern ermöglicht, **generate postscript file**‑Dokumente zu erstellen, Schriftarten zu manipulieren und Text präzise zu formatieren. In diesem Tutorial lernen Sie, wie Sie Text hinzufügen, dessen Farbe ändern, die Größe anpassen und sogar **apply stroke text** für ein professionelles Aussehen anwenden.

## Schnelle Antworten
- **Welche Bibliothek ermöglicht es mir, Textfarbe in Java festzulegen?** Aspose.Page für Java.  
- **Kann ich Systemschriftarten und benutzerdefinierte Schriftarten verwenden?** Ja, beide werden unterstützt.  
- **Wie ändere ich die Textgröße?** Durch Angabe der Schriftgröße beim Erstellen von `Font` oder `DrFont`.  
- **Ist es möglich, Text gleichzeitig zu umreißen und zu füllen?** Absolut – verwenden Sie `fillAndStrokeText`.  
- **Welches Ausgabeformat erzeugt dieses Tutorial?** Ein PostScript (`.ps`)‑Dokument.

## Was bedeutet „set text color java“?
Das Festlegen der Textfarbe in Java bedeutet, das `Color`‑Objekt zu definieren, das die Rendering‑Engine (hier Aspose.Page) beim Zeichnen von Zeichen auf einer Seite verwendet. Dieser Vorgang ist entscheidend, um visuell unterscheidbare Dokumente zu erstellen, insbesondere beim programmatischen Erzeugen von **postscript documents**.

## Warum Aspose.Page für Java verwenden?
- **Full control** über die PostScript‑Erstellung, ohne dass ein nativer PostScript‑Interpreter erforderlich ist.  
- **Support for both system and external fonts**, sodass Sie jede benötigte Typografie einbetten können.  
- **Easy API** zum Füllen, Umranden und **fill and stroke text**, die Ihnen Flexibilität beim Styling bietet.  
- **Cross‑platform**‑Kompatibilität – einmal schreiben, überall ausführen, wo Java läuft.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie:

- Grundkenntnisse in der Java‑Programmierung.  
- Die Aspose.Page für Java‑Bibliothek installiert haben. Sie können sie von der [Aspose.Page for Java download page](https://releases.aspose.com/page/java/) herunterladen.  
- Die erforderlichen Schriftarten im angegebenen Ordner verfügbar sind. Weitere Details finden Sie in der [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).

## Pakete importieren
Importieren Sie in Ihrem Java‑Projekt die erforderlichen Pakete für Aspose.Page für Java:

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

## Schritt 1: Dokument einrichten
Zunächst erstellen wir ein neues **PostScript document** und konfigurieren die Ausgabeeinstellungen.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// A text to write to PS file
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Wie man Textfarbe in Java mit Systemschriftart festlegt
Nun demonstrieren wir **set text color java** mit einer vom System bereitgestellten Schriftart.

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **Tipp:** Die Methode `fillText` verwendet automatisch die aktuelle Farbe, wenn Sie kein `Color`‑Argument übergeben, das standardmäßig schwarz ist.

## Verwendung einer benutzerdefinierten Schriftart und Ändern der Textgröße
Sie können außerdem **change text size** und eine benutzerdefinierte Schriftart verwenden, die in Ihrem Schriftarten‑Ordner gespeichert ist.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Umranden (Stroke) von Text – Stroke Text anwenden
Das Umranden von Text verleiht ihm eine klare Kante. Hier **apply stroke text** mithilfe eines `BasicStroke`.

```java
// Using system font for outlining text
document.outlineText(str, font, 50, 300);
// Outline text with blue‑violet colored 2‑points width pen
Stroke stroke = new BasicStroke(2);
Color strokeColor = new Color(138, 43, 226); // blue‑violet
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```

## Umranden von Text mit benutzerdefinierter Schriftart
Die gleiche Technik funktioniert mit benutzerdefinierten Schriftarten.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Schritt 6: Dokument speichern
Abschließend schließen Sie die Seite und schreiben die Datei auf die Festplatte.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Häufige Probleme & Lösungen
| Problem | Lösung |
|-------|----------|
| **Font not found** | Stellen Sie sicher, dass die Schriftdatei in `necessary_fonts` abgelegt ist und der Ordnerpfad korrekt über `options.setAdditionalFontsFolders` hinzugefügt wurde. |
| **Color not applied** | Vergewissern Sie sich, dass Sie die Überladung von `fillText` oder `outlineText` aufrufen, die ein `Color`‑Argument enthält. |
| **Stroke appears too thin** | Erhöhen Sie die Breite von `BasicStroke` (z. B. `new BasicStroke(3)`). |
| **Document not opening** | Bestätigen Sie, dass die erzeugte `.ps`‑Datei mit der richtigen Erweiterung gespeichert wurde und Ihr Viewer PostScript unterstützt. |

## Häufig gestellte Fragen

**Q:** Kann ich meine eigenen benutzerdefinierten Schriftarten mit Aspose.Page für Java verwenden?  
A: Ja, Sie können benutzerdefinierte Schriftarten verwenden, indem Sie den Schriftartnamen und die Größe in der `DrFont`‑Klasse angeben.

**Q:** Wie kann ich die Farbe des Textes ändern?  
A: Sie können die gewünschte Farbe über die `Color`‑Klasse festlegen, wenn Sie den Text füllen oder umrahmen.

**Q:** Ist es möglich, mehrere Seiten zu einem PostScript‑Dokument hinzuzufügen?  
A: Absolut! Sie können mehrere Seiten erzeugen, indem Sie die Schritte zur Dokumenterstellung und zum Speichern wiederholen.

**Q:** Welchen Zweck hat die Klasse `ExternalFontCache`?  
A: `ExternalFontCache` wird verwendet, um benutzerdefinierte Schriftarten abzurufen und sicherzustellen, dass sie für die Textmanipulation verfügbar sind.

**Q:** Kann ich unterschiedliche Striche auf den umrandeten Text anwenden?  
A: Ja, Sie können die Breite und Farbe des Strichs mithilfe der `Stroke`‑Klasse bzw. der `Color`‑Klasse anpassen.

## Fazit
Herzlichen Glückwunsch! Sie wissen jetzt, wie Sie **set text color java** durchführen, Schriftgrößen ändern, **apply stroke text** anwenden und **create postscript document**‑Dateien mit Aspose.Page für Java erstellen. Experimentieren Sie mit verschiedenen Schriftarten, Farben und Umrandungsstilen, um professionell aussehende PostScript‑Ausgaben zu erzeugen.

---

**Last Updated:** 2025-12-14  
**Tested With:** Aspose.Page for Java 23.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}