---
date: 2026-08-18
description: Erfahren Sie, wie Sie ein Schraffurmuster zu Java PostScript‑Dateien
  mit Aspose.Page Java hinzufügen. Diese Schritt‑für‑Schritt‑Anleitung zeigt den vollständigen
  Code und Tipps.
keywords:
- how to add hatch pattern
- Aspose.Page Java
- PostScript hatch patterns
- Java graphics API
lastmod: 2026-08-18
linktitle: Schraffurmuster in Java PostScript hinzufügen
og_description: Erfahren Sie, wie Sie ein Schraffurmuster in Java PostScript mit Aspose.Page
  hinzufügen. Folgen Sie diesem Schritt‑für‑Schritt‑Tutorial, um schnell schraffur‑gefüllte
  Grafiken zu erstellen.
og_image_alt: Screenshot of Java code adding hatch pattern to a PostScript file with
  Aspose.Page
og_title: Wie man ein Schraffurmuster in Java PostScript hinzufügt – Aspose.Page‑Leitfaden
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to add hatch pattern to Java PostScript files using Aspose.Page
    Java. This step‑by‑step guide shows the complete code and tips.
  headline: How to add hatch pattern in Java PostScript
  type: TechArticle
- questions:
  - answer: Yes, the library is framework‑agnostic and works with Spring, Jakarta
      EE, Android (limited), and plain Java SE.
    question: Can I use Aspose.Page Java with other Java frameworks?
  - answer: Absolutely. Download a free 30‑day trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is a trial version available for Aspose.Page Java?
  - answer: Request a temporary license [temporary license request page](https://purchase.aspose.com/temporary-license/).
      It removes evaluation watermarks.
    question: How do I obtain a temporary license for development?
  - answer: Visit the official forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39)
      for additional examples and Q&A.
    question: Where can I find more tutorials and community support?
  - answer: Yes, the full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Is there comprehensive documentation for all classes and methods?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Java
- Aspose.Page
- PostScript
- hatch pattern
title: Wie man ein Schraffurmuster in Java PostScript hinzufügt
url: /de/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man ein Schraffurmuster in Java PostScript hinzufügt

## Einleitung
Wenn Sie mit **Aspose.Page Java** arbeiten und sich fragen, **wie man ein Schraffurmuster** zu Ihrer PostScript-Ausgabe hinzufügt, sind Schraffurmuster eine schnelle und flexible Lösung. In diesem Tutorial führen wir Sie durch **wie man Schraffur‑Designs** zu einem PostScript-Dokument hinzufügt, erklären, warum sie nützlich sind, und geben Ihnen ein vollständiges, sofort ausführbares Code‑Beispiel. Am Ende können Sie visuell ansprechende, schraffur‑gefüllte Formen und Text mit nur wenigen Zeilen Java erstellen.

## Schnelle Antworten
- **Welche Bibliothek benötige ich?** Aspose.Page for Java (das “aspose page java” SDK).  
- **Welchen visuellen Effekt fügen wir hinzu?** Schraffurmuster (z. B. diagonale Linien, Kreuzschraffur).  
- **Benötige ich eine Lizenz, um das Beispiel auszuführen?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine Lizenz erforderlich.  
- **Wie viele Codezeilen?** Etwa 70 Zeilen, aufgeteilt in klare Schritte.  
- **Kann ich denselben Ansatz für PDFs verwenden?** Ja – Aspose.Page unterstützt mehrere Ausgabeformate, einschließlich PDF.

## Was ist ein Schraffurmuster?
Ein Schraffurmuster ist eine vektorbasierte Füllung, die aus wiederholten Linien oder Formen besteht und einen Textureffekt erzeugt. Da es mathematisch definiert ist, skaliert das Muster ohne Qualitätsverlust, was es ideal für hochauflösenden Druck und monochrome Ausgaben macht.

## Warum Schraffurmuster mit Aspose.Page Java verwenden?
Aspose.Page unterstützt **mehr als 10 Ausgabeformate** (einschließlich PostScript, PDF, EPS, SVG und XPS) und kann Schraffur‑Füllungen in Dokumenten bis zu **500 Seiten** rendern, ohne die gesamte Datei in den Speicher zu laden. Das bedeutet, Sie erhalten schnelle Leistung, geringen Speicherverbrauch und konsistente visuelle Ergebnisse über alle unterstützten Formate hinweg.

## Wie man ein Schraffurmuster hinzufügt – Übersicht
Schraffurmuster sind vektorbasierte Texturen, die bei jeder Auflösung sauber rendern und gut auf monochromen Druckern funktionieren. Mit Aspose.Page Java können Sie diese Muster auf Formen, Pfade und sogar Text anwenden, ohne sich mit Low‑Level‑PostScript‑Befehlen beschäftigen zu müssen.

## Voraussetzungen
- **Java-Entwicklungsumgebung** – JDK 8 oder höher und eine IDE Ihrer Wahl.  
- **Aspose.Page for Java Bibliothek** – Laden Sie das neueste JAR von der offiziellen **Aspose.Page for Java Download-Seite** [here](https://releases.aspose.com/page/java/).  
- Sie können auch andere Aspose‑Releases [here](https://releases.aspose.com/) durchsuchen.  
- **Schreibzugriff** auf einen Ordner, in dem die erzeugte PostScript‑Datei gespeichert wird.

## Pakete importieren
Die untenstehenden Importe umfassen Standard‑Java‑AWT‑Klassen für Grafik‑Primitive wie Farben, Striche und geometrische Formen sowie Aspose.Page‑Klassen, die das Dokumentenmodell, Schraffur‑Stil‑Definitionen und Speicheroptionen bereitstellen, die zum Erzeugen einer PostScript‑Datei erforderlich sind.  
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Was ist die `Document`‑Klasse?
Die `Document`‑Klasse ist das Top‑Level‑Objekt von Aspose.Page, das eine einzelne PostScript‑Datei im Speicher repräsentiert. Alle Zeichenoperationen werden über dieses Objekt ausgeführt.

## Wie richtet man den Ausgabestream ein?
Um die Ausgabe zu schreiben, erstellen Sie einen `FileOutputStream`, der auf den gewünschten Dateipfad zeigt; dieser Stream übernimmt das Low‑Level‑Byte‑Schreiben. `PsSaveOptions` konfiguriert, wie das Dokument gespeichert wird, einschließlich Seitengröße und Kompression. Anschließend instanziieren Sie ein `Document` mit einem `PsSaveOptions`‑Objekt, das Seitengröße, Kompression und weitere PostScript‑spezifische Einstellungen festlegt.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## Wie speichert man den Grafikstatus und verschiebt den Ursprung?
Das Speichern des Grafikstatus erfasst die aktuelle Transformationsmatrix, den Clipping‑Bereich und die Zeichenattribute, sodass Sie später zurückkehren können. Nach dem Speichern rufen Sie `translate(x, y)` auf dem Grafikobjekt auf, um den Ursprung an eine praktische Position für das Zeichnen des Rasters von Schraffur‑Quadraten zu verschieben.  
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Wie erstellt man ein wiederverwendbares Quadrat für jedes Muster?
`Rectangle2D` repräsentiert eine rechteckige Form, definiert durch Position und Größe. Durch das Erstellen einer einzigen Instanz, die den Zellabmessungen entspricht, können Sie sie für jedes schraffur‑gefüllte Quadrat wiederverwenden, wodurch die Objektallokation reduziert und die Zeichnungsschleife effizient bleibt.  
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Wie richtet man einen Stift für die Kontur des Mustersquadrats ein?
`BasicStroke` beschreibt die Kontur‑Dicke, das Strich‑Muster und die Endkappen für Vektorformen. Die Verwendung eines 2‑Punkt‑`BasicStroke` liefert einen klaren Rand um jede schraffur‑gefüllte Zelle, wodurch die Füllung visuell von benachbarten Quadraten getrennt wird.  
```java
BasicStroke stroke = new BasicStroke(2);
```

## Wie iteriert man über Schraffurmuster?
`HatchStyle` ist eine Aufzählung, die alle vordefinierten Schraffur‑Muster wie diagonal, Kreuz und gepunktet auflistet. Das Durchlaufen von `HatchStyle.values()` ermöglicht es, jedes Muster nacheinander anzuwenden, das Rechteck mit einem `HatchBrush` zu füllen und anschließend seine Kontur zu zeichnen.  
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Wie stellt man den Grafikstatus nach dem Zeichnen wieder her?
Der Aufruf von `restore()` auf dem Grafikobjekt stellt die Transformationsmatrix und die Zeichen­einstellungen auf den zuvor gespeicherten Zustand zurück, wodurch kumulative Verschiebungen oder Skalierungen die nachfolgenden Zeichenoperationen nicht beeinflussen. Das stellt sicher, dass späterer Inhalt vom ursprünglichen Koordinatensystem aus startet und Standardattribute verwendet.  
```java
document.writeGraphicsRestore();
```

## Wie füllt man Text mit einem Schraffurmuster?
`TextFragment` repräsentiert ein Textstück, das unabhängig positioniert und gestaltet werden kann. Durch das Zuweisen eines `HatchBrush` mit einem gewählten `HatchStyle` zur Füllung des Fragments werden die Textzeichen mit der Schraffur‑Textur statt einer einfarbigen Farbe gerendert.  
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Wie umrandet man Text mit einem anderen Schraffurstil?
`HatchBrush` kann auch zum Stroken verwendet werden. Um eine Kontur zu zeichnen, setzen Sie den Strich des Fragments auf einen `HatchBrush` mit einem anderen `HatchStyle` (z. B. 70 % Schraffur) und erhöhen die Strich‑Breite über `setStrokeWidth`. Dadurch wird die Textkontur mit einem eigenen Schraffurmuster gerendert, während das gefüllte Innere erhalten bleibt.  
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Wie schließt und speichert man das Dokument?
`document.save()` schreibt das im Speicher befindliche Dokument in den angegebenen Ausgabestream. Nach Abschluss aller Zeichenbefehle rufen Sie diese Methode auf und schließen anschließend den `FileOutputStream`, um Systemressourcen freizugeben und sicherzustellen, dass die Datei ordnungsgemäß auf die Festplatte geschrieben wird.  
```java
document.closePage();
document.save();
```

Befolgen Sie diese Schritte, und Sie erhalten eine PostScript‑Datei, die eine vollständige Reihe von Schraffur‑Mustern zeigt, die sowohl auf Formen als auch auf Text angewendet werden – alles angetrieben von **aspose page java**.

## Häufige Stolperfallen & Tipps
- **Dateipfad‑Fehler** – Stellen Sie sicher, dass `dataDir` mit dem passenden Dateiseparator endet (`/` oder `\`).  
- **Nicht unterstützte Farben** – Einige ältere PostScript‑Interpreter können bestimmte Farbräume nicht verarbeiten; verwenden Sie grundlegendes RGB für maximale Kompatibilität.  
- **Lizenz‑Warnungen** – Das Ausführen des Beispiels ohne gültige Lizenz fügt dem Ergebnis ein Wasserzeichen hinzu.

## Häufig gestellte Fragen

**Q: Kann ich Aspose.Page Java mit anderen Java‑Frameworks verwenden?**  
A: Ja, die Bibliothek ist framework‑agnostisch und funktioniert mit Spring, Jakarta EE, Android (eingeschränkt) und reinem Java SE.

**Q: Ist eine Testversion für Aspose.Page Java verfügbar?**  
A: Auf jeden Fall. Laden Sie eine kostenlose 30‑Tage‑Testversion [Aspose trial download page](https://releases.aspose.com/) herunter.

**Q: Wie erhalte ich eine temporäre Lizenz für die Entwicklung?**  
A: Fordern Sie eine temporäre Lizenz [temporary license request page](https://purchase.aspose.com/temporary-license/) an. Sie entfernt Evaluations‑Wasserzeichen.

**Q: Wo finde ich weitere Tutorials und Community‑Support?**  
A: Besuchen Sie das offizielle Forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) für weitere Beispiele und Fragen‑Antworten.

**Q: Gibt es eine umfassende Dokumentation für alle Klassen und Methoden?**  
A: Ja, die vollständige API‑Referenz ist verfügbar [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Kann ich dasselbe Schraffurmuster zu PDF statt zu PostScript rendern?**  
A: Absolut. Ändern Sie die `PsSaveOptions` zu `PdfSaveOptions` (oder dem Äquivalent) und der Rest des Codes bleibt unverändert.

**Q: Was soll ich tun, wenn die erzeugte Datei leer ist?**  
A: Stellen Sie sicher, dass der Ausgabestream auf ein beschreibbares Verzeichnis zeigt und dass `document.save()` nach allen Zeichenoperationen aufgerufen wird.

**Zuletzt aktualisiert:** 2026-08-18  
**Getestet mit:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Autor:** Aspose

## Verwandte Tutorials

- [Texturmuster in PostScript erstellen – Aspose.Page Java](/page/java/postscript-texture-patterns/)
- [Wie man einen Farbverlauf hinzufügt: Diagonaler Farbverlauf in Java PostScript mit Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Wie man PostScript mit der Aspose.Page Java API zu PDF konvertiert](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}