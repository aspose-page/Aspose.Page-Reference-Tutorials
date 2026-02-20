---
date: 2026-02-20
description: Erfahren Sie, wie Sie die Textfarbe in Java mit Aspose.Page für Java
  festlegen, die Schriftgröße in Java ändern, eine PostScript‑Datei erzeugen, Text
  füllen und umranden sowie benutzerdefinierte Schriften in Java verwenden, während
  Sie ein PostScript‑Dokument erstellen.
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: Textfarbe in Java mit Aspose.Page festlegen – Leitfaden zur Textmanipulation
url: /de/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Textfarbe in Java mit Aspose.Page – Leitfaden zur Textmanipulation

## Einführung
Willkommen zu unserem Schritt‑für‑Schritt‑Leitfaden zum **set text color java**, während Sie mit PostScript‑Dateien mithilfe von Aspose.Page für Java arbeiten. Aspose.Page für Java ist eine leistungsstarke Bibliothek, die Entwicklern ermöglicht, **create postscript document**‑Dateien zu erzeugen, Schriftarten zu manipulieren und Text präzise zu formatieren. In diesem Tutorial lernen Sie, wie Sie Text hinzufügen, dessen Farbe ändern, **change font size java** anpassen und sogar **apply fill and stroke text** für ein professionelles Erscheinungsbild anwenden.

## Schnelle Antworten
- **Welche Bibliothek ermöglicht das Festlegen der Textfarbe in Java?** Aspose.Page für Java.  
- **Kann ich System‑ und benutzerdefinierte Schriftarten verwenden?** Ja, beide werden unterstützt, und Sie können **use custom fonts java** problemlos einsetzen.  
- **Wie ändere ich die Textgröße?** Indem Sie die Schriftgröße beim Erzeugen des `Font`‑ oder `DrFont`‑Objekts angeben.  
- **Ist es möglich, Text gleichzeitig zu umreißen und zu füllen?** Absolut – verwenden Sie `fillAndStrokeText`.  
- **Welches Ausgabeformat erzeugt dieses Tutorial?** Ein PostScript‑Dokument (`.ps`), das Sie programmgesteuert **generate postscript file** können.

## Was bedeutet „set text color java“?
Die Textfarbe in Java festzulegen bedeutet, das `Color`‑Objekt zu definieren, das die Rendering‑Engine (hier Aspose.Page) beim Zeichnen von Zeichen auf einer Seite verwendet. Dieser Vorgang ist entscheidend, um visuell unterscheidbare Dokumente zu erstellen, insbesondere wenn Sie **generate postscript file** programmgesteuert erzeugen müssen.

## Warum Aspose.Page für Java verwenden?
- **Vollständige Kontrolle** über die PostScript‑Erzeugung ohne einen nativen Interpreter.  
- **Unterstützung für System‑ und externe Schriftarten**, sodass Sie jede gewünschte Typografie einbetten können.  
- **Einfache API**, um Text zu füllen, zu umreißen und **fill and stroke text** anzuwenden, was Ihnen Flexibilität beim Styling gibt.  
- **Plattformübergreifende** Kompatibilität – schreiben Sie einmal, führen Sie überall aus, wo Java läuft.  

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Grundkenntnisse in der Java‑Programmierung.  
- Die Aspose.Page für Java‑Bibliothek installiert. Sie können sie von der [Aspose.Page for Java download page](https://releases.aspose.com/page/java/) herunterladen.  
- Die erforderlichen Schriftarten im angegebenen Ordner verfügbar. Weitere Details finden Sie in der [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  

## Pakete importieren
Importieren Sie in Ihrem Java‑Projekt die notwendigen Pakete für Aspose.Page für Java:

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

## Schritt 1: Dokument einrichten
Zuerst erstellen wir ein neues **PostScript document** und konfigurieren die Ausgabeeinstellungen.

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

> **Tipp:** Die Methode `fillText` verwendet automatisch die aktuelle Farbe, wenn Sie kein `Color`‑Argument übergeben; standardmäßig ist dies Schwarz.

## Benutzerdefinierte Schriftart verwenden und Textgröße ändern
Sie können außerdem **change font size java** anpassen und eine benutzerdefinierte Schriftart aus Ihrem Schriftarten‑Ordner nutzen.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Text umranden (Stroke) – Stroke‑Text anwenden
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

## Text mit benutzerdefinierter Schriftart umranden
Die gleiche Technik funktioniert auch mit benutzerdefinierten Schriftarten.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Schritt 6: Dokument speichern
Abschließend schließen wir die Seite und schreiben die Datei auf die Festplatte.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Warum das wichtig ist
Die Möglichkeit, **set text color java** zu verwenden und Füllung mit Umriss zu kombinieren, gibt Ihnen die volle künstlerische Kontrolle über das endgültige PostScript‑Ergebnis. Ob Sie Rechnungen, Zertifikate oder individuelle Grafiken erzeugen – das Erstellen von **create postscript document**‑Dateien mit präzisem Styling reduziert den Nachbearbeitungsaufwand in Grafik‑Editoren.

## Häufige Probleme & Lösungen
| Problem | Lösung |
|---------|--------|
| **Font not found** | Stellen Sie sicher, dass die Schriftdatei im Ordner `necessary_fonts` liegt und der Pfad über `options.setAdditionalFontsFolders` korrekt hinzugefügt wurde. |
| **Color not applied** | Prüfen Sie, ob Sie die Überladung von `fillText` oder `outlineText` aufrufen, die ein `Color`‑Argument enthält. |
| **Stroke appears too thin** | Erhöhen Sie die Breite des `BasicStroke` (z. B. `new BasicStroke(3)`). |
| **Document not opening** | Vergewissern Sie sich, dass die erzeugte `.ps`‑Datei mit der richtigen Erweiterung gespeichert wurde und Ihr Viewer PostScript unterstützt. |

## Häufig gestellte Fragen

**Q:** Kann ich eigene benutzerdefinierte Schriftarten mit Aspose.Page für Java verwenden?  
A: Ja, Sie können **use custom fonts java** einsetzen, indem Sie den Schriftartnamen und die Größe in der `DrFont`‑Klasse angeben.

**Q:** Wie kann ich die Farbe des Textes ändern?  
A: Sie können die gewünschte Farbe über die `Color`‑Klasse setzen, wenn Sie den Text füllen oder umreißen.

**Q:** Ist es möglich, mehrere Seiten zu einem PostScript‑Dokument hinzuzufügen?  
A: Absolut! Sie können mehrere Seiten erzeugen, indem Sie die Dokumenterstellung und die Speicher‑Schritte wiederholen.

**Q:** Welchen Zweck hat die Klasse `ExternalFontCache`?  
A: `ExternalFontCache` wird verwendet, um benutzerdefinierte Schriftarten abzurufen und sicherzustellen, dass sie für die Textmanipulation verfügbar sind.

**Q:** Kann ich unterschiedliche Striche für den umrandeten Text anwenden?  
A: Ja, Sie können die Breite und Farbe des Strichs über die `Stroke`‑Klasse bzw. die `Color`‑Klasse anpassen.

## Fazit
Herzlichen Glückwunsch! Sie wissen jetzt, wie Sie **set text color java**, **change font size java**, **apply fill and stroke text** verwenden und **create postscript document**‑Dateien mit Aspose.Page für Java erzeugen. Experimentieren Sie mit verschiedenen Schriftarten, Farben und Umriss‑Stilen, um professionelle PostScript‑Ausgaben zu erstellen.

---

**Zuletzt aktualisiert:** 2026-02-20  
**Getestet mit:** Aspose.Page für Java 23.12 (neueste)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}