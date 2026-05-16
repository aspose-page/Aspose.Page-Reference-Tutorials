---
date: 2026-02-15
description: Erfahren Sie, wie Sie ein Schraffurmuster zu Java‑PostScript‑Dateien
  mit Aspose.Page Java hinzufügen. Dieser Schritt‑für‑Schritt‑Leitfaden zeigt den
  vollständigen Code und Tipps.
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: Wie man ein Schraffurmuster in Java‑PostScript mit Aspose.Page hinzufügt
url: /de/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man ein Schraffurmuster in Java PostScript hinzufügt

## Einleitung
Wenn Sie mit **Aspose.Page Java** arbeiten und sich fragen, **wie man ein Schraffurmuster hinzufügt** zu Ihrer PostScript‑Ausgabe, sind Schraffurmuster eine schnelle und flexible Lösung. In diesem Tutorial führen wir Sie Schritt für Schritt durch **wie man Schraffur‑Designs hinzufügt** zu einem PostScript‑Dokument, erklären, warum sie nützlich sind, und geben Ihnen ein vollständiges, sofort ausführbares Code‑Beispiel. Am Ende können Sie mit nur wenigen Zeilen Java visuell ansprechende, schraffur‑gefüllte Formen und Texte erstellen.

## Kurzantworten
- **Welche Bibliothek benötige ich?** Aspose.Page for Java (das “aspose page java” SDK).  
- **Welchen visuellen Effekt fügen wir hinzu?** Schraffurmuster (z. B. diagonale Linien, Kreuzschraffur).  
- **Benötige ich eine Lizenz, um das Beispiel auszuführen?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine Lizenz erforderlich.  
- **Wie viele Codezeilen?** Etwa 70 Zeilen, aufgeteilt in klare Schritte.  
- **Kann ich denselben Ansatz für PDFs verwenden?** Ja – Aspose.Page unterstützt mehrere Ausgabeformate, einschließlich PDF.

## Wie man ein Schraffurmuster hinzufügt – Überblick
Schraffurmuster sind vektorbasierte Texturen, die bei jeder Auflösung sauber gerendert werden und sich gut für monochrome Drucker eignen. Mit Aspose.Page Java können Sie diese Muster auf Formen, Pfade und sogar Text anwenden, ohne sich mit Low‑Level‑PostScript‑Befehlen beschäftigen zu müssen.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- **Java-Entwicklungsumgebung** – JDK 8 oder höher und eine IDE Ihrer Wahl.  
- **Aspose.Page for Java Bibliothek** – Laden Sie das neueste JAR von der offiziellen Seite [here](https://releases.aspose.com/page/java/).  
- **Schreibzugriff** auf einen Ordner, in dem die erzeugte PostScript‑Datei gespeichert wird.

## Pakete importieren
Zuerst bringen Sie die benötigten Klassen in Ihr Projekt. Diese Importe geben Ihnen Zugriff auf Zeichen‑Primitiven, Farb‑Handling und die Aspose.Page‑API.

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

## Schritt 1: Anfangsparameter festlegen
Erstellen Sie den Ausgabestream, konfigurieren Sie die Seitengröße (A4) und definieren Sie einige Layout‑Variablen, die beim Zeichnen jedes schraffur‑gefüllten Quadrats wiederverwendet werden.

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

## Schritt 2: Grafikstatus speichern und übersetzen
Das Speichern des Grafikstatus ermöglicht es uns, später zum ursprünglichen Koordinatensystem zurückzukehren, während `translate` den Ursprung zu einem praktischen Startpunkt verschiebt.

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Schritt 3: Quadrat für jedes Muster erstellen
Definieren Sie ein wiederverwendbares Rechteck, das jede schraffur‑gefüllte Zelle repräsentiert.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Schritt 4: Stift für die Kontur des Musterquadrats einrichten
Ein `BasicStroke` von 2 Punkten liefert eine klare Kontur um jedes Quadrat.

```java
BasicStroke stroke = new BasicStroke(2);
```

## Schritt 5: Durch Schraffurmuster iterieren
Durchlaufen Sie jeden Wert im `HatchStyle`‑Enum, füllen Sie jedes Quadrat mit der entsprechenden Textur und zeichnen Sie anschließend dessen Kontur. Dies ist der Kern der **Hinzufügen‑von‑Schraffurmuster**‑Funktionalität.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Schritt 6: Grafikstatus wiederherstellen
Kehren Sie nach dem Zeichnen des Rasters von Quadraten zum ursprünglichen Koordinatensystem zurück.

```java
document.writeGraphicsRestore();
```

## Schritt 7: Text mit Schraffurmuster füllen
Hier demonstrieren wir, wie man Text mit einer Schraffur‑Textur malt. Das Beispiel füllt das Wort „ABC“ mit einem diagonal‑kreuz‑Muster.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Schritt 8: Text mit Schraffurmuster umranden
Jetzt umranden wir denselben Text, diesmal jedoch mit einem 70 %‑Schraffurstil und einem dickeren Strich.

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Schritt 9: Dokument schließen und speichern
Finalisieren Sie die Seite, schreiben Sie die Datei auf die Festplatte und geben Sie Ressourcen frei.

```java
document.closePage();
document.save();
```

Befolgen Sie diese Schritte, und Sie erhalten eine PostScript‑Datei, die ein komplettes Set von Schraffurmustern sowohl auf Formen als auch auf Text anwendet – alles angetrieben von **aspose page java**.

## Warum Schraffurmuster mit Aspose.Page Java verwenden?
- **Visuelle Unterscheidung** – Schraffurfüllungen funktionieren selbst, wenn Drucker nur monochrome Ausgabe unterstützen.  
- **Performance** – Texturen werden on‑the‑fly generiert, sodass Sie große Bilddateien vermeiden.  
- **Cross‑Format‑Unterstützung** – Der gleiche Code kann PDF, EPS oder SVG mit minimalen Änderungen ansteuern.

## Häufige Fallstricke & Tipps
- **Dateipfad‑Fehler** – Stellen Sie sicher, dass `dataDir` mit dem passenden Dateiseparator (`/` oder `\`) endet.  
- **Nicht unterstützte Farben** – Einige ältere PostScript‑Interpreter können bestimmte Farbräume nicht verarbeiten; verwenden Sie für maximale Kompatibilität einfaches RGB.  
- **Lizenzwarnungen** – Das Ausführen des Beispiels ohne gültige Lizenz fügt dem Ergebnis ein Wasserzeichen ein.

## Fazit
Die Integration von Schraffurmustern kann die Lesbarkeit und Ästhetik technischer Zeichnungen, Karten oder jeglicher von Java erzeugter Grafiken dramatisch verbessern. Mit **Aspose.Page Java** erhalten Sie eine kompakte API, die die Low‑Level‑PostScript‑Befehle abstrahiert und Ihnen ermöglicht, sich auf das Design statt auf Format‑Eigenheiten zu konzentrieren. Jetzt wissen Sie, **wie man ein Schraffurmuster hinzufügt** zu Ihren PostScript‑Dokumenten – experimentieren Sie mit verschiedenen `HatchStyle`‑Werten, um das gewünschte Aussehen zu erzielen.

## Häufig gestellte Fragen

**Q: Kann ich Aspose.Page Java mit anderen Java‑Frameworks verwenden?**  
A: Ja, die Bibliothek ist framework‑agnostisch und funktioniert mit Spring, Jakarta EE, Android (eingeschränkt) und reinem Java SE.

**Q: Ist eine Testversion für Aspose.Page Java verfügbar?**  
A: Absolut. Laden Sie eine kostenlose 30‑Tage‑Testversion [here](https://releases.aspose.com/) herunter.

**Q: Wie erhalte ich eine temporäre Lizenz für die Entwicklung?**  
A: Fordern Sie eine temporäre Lizenz [here](https://purchase.aspose.com/temporary-license/) an. Sie entfernt Evaluations‑Wasserzeichen.

**Q: Wo finde ich weitere Tutorials und Community‑Support?**  
A: Besuchen Sie das offizielle Forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) für zusätzliche Beispiele und Q&A.

**Q: Gibt es eine umfassende Dokumentation für alle Klassen und Methoden?**  
A: Ja, die vollständige API‑Referenz ist verfügbar [here](https://reference.aspose.com/page/java/).

**Q: Kann ich dasselbe Schraffurmuster stattdessen als PDF rendern?**  
A: Absolut. Ändern Sie die `PsSaveOptions` zu `PdfSaveOptions` (oder das Äquivalente) und der Rest des Codes bleibt unverändert.

**Q: Was soll ich tun, wenn die erzeugte Datei leer ist?**  
A: Vergewissern Sie sich, dass der Ausgabestream auf ein beschreibbares Verzeichnis zeigt und dass `document.save()` nach allen Zeichenoperationen aufgerufen wird.

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}