---
date: 2026-09-09
description: Erfahren Sie, wie Sie radial gradient in Java PostScript mit Aspose.Page
  erstellen. Diese Schritt‑für‑Schritt‑Anleitung zeigt Ihnen, wie Sie einen color
  stops gradient hinzufügen, radii festlegen und schnell eine PS‑Datei erzeugen.
keywords:
- how to create radial gradient
- add color stops gradient
- Aspose.Page Java
- Java PostScript gradient
- radial gradient tutorial
lastmod: 2026-09-09
linktitle: Radial gradients in Java meistern
og_description: Erfahren Sie, wie Sie radial gradient in Java PostScript mit Aspose.Page
  erstellen. Diese Anleitung erklärt, wie Sie einen color stops gradient hinzufügen,
  radii festlegen und in wenigen Minuten eine PS‑Datei erzeugen.
og_image_alt: Guide showing how to add a radial gradient to a Java PostScript file
  with Aspose.Page
og_title: Wie man radial gradient in Java PostScript erstellt
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  headline: How to create radial gradient in Java PostScript
  type: TechArticle
- description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  name: How to create radial gradient in Java PostScript
  steps:
  - name: create a rectangle and open a PS document
    text: '`PsDocument` is Aspose.Page''s class that represents a PostScript document
      and provides methods to draw shapes, text, and images. We start by creating
      an output stream, configuring the page size (A4 by default), and defining a
      rectangle that will host the gradient. > **Pro tip:** Adjust the rectangle'
  - name: define colors and fractions
    text: 'A radial gradient is built from *color stops* (the colors) and *fractions*
      (the relative positions of those stops). Here we create an array of six colors
      and their corresponding fractions. > **Why this matters:** By tweaking `fractions`
      you control how quickly the colors transition, enabling subtle '
  - name: create radial gradient paint
    text: '`RadialGradientPaint` is the core class that describes a radial color gradient,
      including center point, radius, focus point, fractions, colors, cycle method,
      and color space. Now we build the `RadialGradientPaint` object using the arrays
      defined above. > **Note:** `transform` can be `null` if you do'
  - name: set paint and fill the rectangle
    text: With the paint ready, we tell the `PsDocument` to use it and then fill the
      rectangle we defined earlier. At this point the PostScript page contains a rectangle
      smoothly filled with the radial gradient we configured.
  - name: close and save the document
    text: Finally, close the current page and write the file to disk. Open `RadialGradient1_outPS.ps`
      in any PostScript viewer (e.g., Ghostscript) and you’ll see the gradient rendered
      exactly as defined.
  type: HowTo
- questions:
  - answer: Yes. A commercial license is required for production use. You can purchase
      one from the [Aspose licensing page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for Java in commercial projects?
  - answer: The full documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find the official API reference?
  - answer: Absolutely. Download a trial version from the [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is a free trial available for testing?
  - answer: A temporary license can be requested from the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Join the Aspose.Page community forum at [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- radial gradient
- Aspose.Page
- Java PostScript
- gradient programming
- color stops
title: Wie man radial gradient in Java PostScript erstellt
url: /de/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man radialen Farbverlauf in Java PostScript mit Aspose.Page erstellt

## Einführung
Wenn Sie einen **radialen Farbverlauf** in einer PostScript-Datei erstellen müssen, sind Sie hier genau richtig. In diesem Tutorial führen wir Sie Schritt für Schritt durch die Erstellung eines PostScript-Dokuments, das einen sanften radialen Farbverlauf enthält, mithilfe von **Aspose.Page for Java**. Am Ende verstehen Sie die API, sehen ein vollständiges ausführbares Beispiel und wissen, wie Sie Farben, Positionen und Radien für jedes Design‑Szenario anpassen können.

## Schnelle Antworten
- **Welche Bibliothek erstellt radiale Farbverläufe in PostScript?** Aspose.Page for Java.  
- **Wie lange dauert die Implementierung?** Etwa 10‑15 Minuten für ein einfaches Beispiel.  
- **Benötige ich eine Lizenz, um den Code auszuführen?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Welche Java-Version wird unterstützt?** Java 8 oder höher.  
- **Kann ich die Form des Farbverlaufs ändern?** Ja – passen Sie den Radius und den Mittelpunkt im `RadialGradientPaint`‑Konstruktor an.

## Wie man radialen Farbverlauf in Java erstellt

Laden Sie Ihr Java‑Projekt, importieren Sie die erforderlichen Klassen und folgen Sie der nachstehenden Schritt‑für‑Schritt‑Anleitung. Die Kernantwort lautet, dass Sie ein `RadialGradientPaint` mit Ihren Farb‑Stops instanziieren und es dann auf ein Rechteck anwenden, das auf einem `PsDocument` gezeichnet wird. Dieser Zwei‑Objekt‑Ansatz übernimmt alle Low‑Level‑PostScript‑Befehle für Sie.

## Was ist ein radialer Farbverlauf?
`RadialGradientPaint` ist eine Java‑AWT‑Klasse, die einen kreisförmigen Farbwechsel von einem zentralen Punkt nach außen definiert. Sie erzeugt eine sanfte Mischung mehrerer Farb‑Stops und ist ideal für Spotlights, weiche Hintergründe oder jeden Effekt, bei dem Farben von einem Fokuspunkt ausstrahlen.

## Warum Aspose.Page für radiale Farbverläufe verwenden?
Aspose.Page gibt Ihnen die vollständige programmgesteuerte Kontrolle über die PostScript‑Ausgabe, während es das schwere Heben der Low‑Level‑PS‑Syntax übernimmt. Es unterstützt **50+ Eingabe‑ und Ausgabeformate**, kann Dokumente mit mehreren hundert Seiten rendern, ohne die gesamte Datei in den Speicher zu laden, und läuft auf jedem Betriebssystem, das Java 8+ unterstützt. Diese quantifizierte Fähigkeit macht es zu einer zuverlässigen Wahl für Enterprise‑Grafik‑Generierung.

## Voraussetzungen
- **Java Development Kit (JDK) 8+** – prüfen Sie mit `java -version`.  
- **Aspose.Page for Java** – laden Sie das neueste JAR von der offiziellen [Aspose.Page Download-Seite](https://releases.aspose.com/page/java/) herunter.  
- **IDE Ihrer Wahl** – Eclipse, IntelliJ IDEA oder VS Code mit Java‑Erweiterungen.  
- **Ein beschreibbarer Ordner** – in dem die erzeugte `.ps`‑Datei gespeichert wird.

## Pakete importieren
Zuerst importieren wir die Klassen, die wir benötigen. Das `java.awt`‑Paket stellt die Gradient‑Paint‑Objekte bereit, während `com.aspose.eps` die Klassen zur Handhabung von PostScript‑Dokumenten enthält.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Rechteck erstellen und ein PS‑Dokument öffnen
`PsDocument` ist Aspose.Page‑Klasse, die ein PostScript‑Dokument repräsentiert und Methoden zum Zeichnen von Formen, Text und Bildern bereitstellt. Wir beginnen damit, einen Output‑Stream zu erstellen, die Seitengröße (standardmäßig A4) zu konfigurieren und ein Rechteck zu definieren, das den Farbverlauf aufnehmen wird.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **Profi‑Tipp:** Passen Sie die Koordinaten des Rechtecks (`200, 100, 200, 200`) an, um den Farbverlauf an beliebiger Stelle auf der Seite zu positionieren.

### Schritt 2: Farben und Bruchteile definieren
Ein radialer Farbverlauf wird aus *Farb‑Stops* (den Farben) und *Bruchteilen* (den relativen Positionen dieser Stops) aufgebaut. Hier erstellen wir ein Array aus sechs Farben und den zugehörigen Bruchteilen.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Warum das wichtig ist:** Durch Anpassen der `fractions` steuern Sie, wie schnell die Farben wechseln, was subtile oder dramatische Effekte ermöglicht.

### Schritt 3: Radialen Farbverlauf erstellen
`RadialGradientPaint` ist die Kernklasse, die einen radialen Farbverlauf beschreibt, einschließlich Mittelpunkt, Radius, Fokuspunkt, Bruchteile, Farben, Zyklus‑Methode und Farbraum. Jetzt bauen wir das `RadialGradientPaint`‑Objekt mithilfe der oben definierten Arrays.

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **Hinweis:** `transform` kann `null` sein, wenn Sie keine zusätzliche Skalierung oder Rotation benötigen. Experimentieren Sie gern mit `AffineTransform` für schiefe Farbverläufe.

### Schritt 4: Farbe setzen und das Rechteck füllen
Mit dem fertigen Paint teilen wir dem `PsDocument` mit, es zu verwenden, und füllen anschließend das zuvor definierte Rechteck.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

An diesem Punkt enthält die PostScript‑Seite ein Rechteck, das sanft mit dem von uns konfigurierten radialen Farbverlauf gefüllt ist.

### Schritt 5: Dokument schließen und speichern
Abschließend schließen wir die aktuelle Seite und schreiben die Datei auf die Festplatte.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Öffnen Sie `RadialGradient1_outPS.ps` in einem beliebigen PostScript‑Betrachter (z. B. Ghostscript) und Sie sehen den Farbverlauf exakt wie definiert gerendert.

## Häufige Probleme & Lösungen
| Symptom | Wahrscheinliche Ursache | Lösung |
|---------|--------------------------|--------|
| Gradient erscheint als einfarbig | `fractions`‑Array beginnt nicht bei `0.0f` oder endet nicht bei `1.0f` | Stellen Sie sicher, dass das erste Fraction `0.0f` und das letzte `1.0f` ist. |
| Farben wirken ausgewaschen | Verwendung des falschen `ColorSpaceType` | Wechseln Sie zu `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` für lebendigere Ausgabe. |
| Keine Ausgabedatei erzeugt | `FileOutputStream`‑Pfad ist ungültig oder nicht beschreibbar | Stellen Sie sicher, dass `dataDir` existiert und die Anwendung Schreibrechte hat. |

## Häufig gestellte Fragen

**F: Kann ich Aspose.Page for Java in kommerziellen Projekten verwenden?**  
A: Ja. Für die Produktion ist eine kommerzielle Lizenz erforderlich. Sie können eine Lizenz auf der [Aspose‑Lizenzierungsseite](https://purchase.aspose.com/buy) erwerben.

**F: Wo finde ich die offizielle API‑Referenz?**  
A: Die vollständige Dokumentation ist verfügbar unter [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**F: Gibt es eine kostenlose Testversion zum Testen?**  
A: Absolut. Laden Sie eine Testversion von der [Aspose.Page Releases‑Seite](https://releases.aspose.com/) herunter.

**F: Wie erhalte ich eine temporäre Lizenz für die Evaluierung?**  
A: Eine temporäre Lizenz kann auf der [temporären Lizenz‑Anforderungsseite](https://purchase.aspose.com/temporary-license/) angefordert werden.

**F: Wo finde ich Community‑Support?**  
A: Treten Sie dem Aspose.Page Community‑Forum bei: [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## Fazit
Sie wissen jetzt **wie man radialen Farbverlauf** in einem Java‑PostScript‑Dokument mit Aspose.Page erstellt. Durch Anpassen der Rechteckgröße, der Farb‑Stops und des Farbverlauf‑Radius können Sie unzählige visuelle Effekte erzeugen – von dezenten Hintergrundfüllungen bis hin zu kräftigen Spotlights. Experimentieren Sie gern mit verschiedenen `AffineTransform`‑Werten, um den Farbverlauf zu drehen oder zu kippen, und kombinieren Sie diese Technik mit Text und Bildern für reichhaltigere PDF‑ oder EPS‑Ausgaben.

---

**Last Updated:** 2026-09-09  
**Getestet mit:** Aspose.Page for Java latest (as of writing)  
**Autor:** Aspose

## Verwandte Tutorials

- [Form mit Farbverlauf füllen: Java PostScript Radial Beispiel](/page/java/postscript-gradient-addition/radial2/)
- [PostScript-Farbverlauf in Java erstellen – Vertikalen Farbverlauf hinzufügen](/page/java/postscript-gradient-addition/vertical/)
- [Aspose.Page Transparenz‑Tutorial – Transparenz in Java PostScript hinzufügen](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}