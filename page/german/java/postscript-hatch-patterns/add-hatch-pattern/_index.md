---
date: 2025-12-08
description: Erfahren Sie, wie Sie Schraffurmuster zu Java‑PostScript‑Dokumenten mit
  Aspose.Page Java hinzufügen. Diese Schritt‑für‑Schritt‑Anleitung zeigt Ihnen, wie
  Sie Schraffurgrafiken effizient einfügen.
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: 'Aspose.Page Java: Schraffurmuster in Java-PostScript hinzufügen'
url: /de/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hatch‑Muster in Java PostScript hinzufügen

## Einführung
Wenn Sie mit **Aspose.Page Java** arbeiten und Ihre PostScript‑Ausgabe mit strukturierten Grafiken anreichern möchten, sind Hatch‑Muster eine schnelle und flexible Lösung. In diesem Tutorial zeigen wir Ihnen **wie Sie Hatch‑Designs** zu einem PostScript‑Dokument hinzufügen, erklären, warum sie nützlich sind, und liefern ein vollständiges, sofort ausführbares Code‑Beispiel. Am Ende können Sie mit nur wenigen Java‑Zeilen visuell ansprechende, mit Schraffur gefüllte Formen und Texte erstellen.

## Schnelle Antworten
- **Welche Bibliothek benötige ich?** Aspose.Page für Java (das “aspose page java” SDK).  
- **Welchen visuellen Effekt fügen wir hinzu?** Hatch‑Muster (z. B. diagonale Linien, Kreuzschraffur).  
- **Benötige ich eine Lizenz, um das Beispiel auszuführen?** Eine kostenlose Testversion reicht für die Entwicklung; für die Produktion ist eine Lizenz erforderlich.  
- **Wie viele Codezeilen?** Etwa 70 Zeilen, aufgeteilt in klare Schritte.  
- **Kann ich denselben Ansatz für PDFs verwenden?** Ja – Aspose.Page unterstützt mehrere Ausgabeformate, einschließlich PDF.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- **Java‑Entwicklungsumgebung** – JDK 8 oder höher und eine IDE Ihrer Wahl.  
- **Aspose.Page für Java‑Bibliothek** – Laden Sie das neueste JAR von der offiziellen Seite [here](https://releases.aspose.com/page/java/).  
- **Schreibzugriff** auf einen Ordner, in dem die erzeugte PostScript‑Datei gespeichert wird.

## Pakete importieren
Zuerst importieren Sie die erforderlichen Klassen in Ihr Projekt. Diese Importe geben Ihnen Zugriff auf Zeichenprimitive, Farbverwaltung und die Aspose.Page‑API.

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

## Schritt 1: Anfangsparameter festlegen
Erstellen Sie den Ausgabestream, konfigurieren Sie die Seitengröße (A4) und definieren Sie einige Layout‑Variablen, die beim Zeichnen jedes mit Schraffur gefüllten Quadrats wiederverwendet werden.

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

## Schritt 2: Grafik‑Zustand speichern und verschieben
Das Speichern des Grafik‑Zustands ermöglicht es uns, später zum ursprünglichen Koordinatensystem zurückzukehren, während `translate` den Ursprung zu einem praktischen Startpunkt verschiebt.

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Schritt 3: Quadrat für jedes Muster erstellen
Definieren Sie ein wiederverwendbares Rechteck, das jede mit Schraffur gefüllte Zelle darstellt.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Schritt 4: Stift für die Kontur des Muster‑Quadrats einrichten
Ein `BasicStroke` von 2 Punkten liefert eine klare Kontur um jedes Quadrat.

```java
BasicStroke stroke = new BasicStroke(2);
```

## Schritt 5: Durch Hatch‑Muster iterieren
Durchlaufen Sie jeden Wert im `HatchStyle`‑Enum, füllen Sie jedes Quadrat mit der entsprechenden Textur und zeichnen Sie anschließend dessen Kontur. Dies ist der Kern der **Hinzufügen von Hatch‑Muster**‑Funktionalität.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Schritt 6: Grafik‑Zustand wiederherstellen
Kehren Sie nach dem Zeichnen des Rasters von Quadraten zum ursprünglichen Koordinatensystem zurück.

```java
document.writeGraphicsRestore();
```

## Schritt 7: Text mit Hatch‑Muster füllen
Hier zeigen wir, wie man Text mit einer Schraffur‑Textur füllt. Das Beispiel füllt das Wort „ABC“ mit einem diagonalen Kreuz‑Muster.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Schritt 8: Text mit Hatch‑Muster umreißen
Jetzt umreißen wir denselben Text, diesmal mit einem 70 %‑Schraffur‑Stil und einer dickeren Kontur.

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Schritt 9: Dokument schließen und speichern
Schließen Sie die Seite ab, schreiben Sie die Datei auf die Festplatte und geben Sie Ressourcen frei.

```java
document.closePage();
document.save();
```

Befolgen Sie diese Schritte, und Sie erhalten eine PostScript‑Datei, die ein vollständiges Set von Schraffur‑Mustern sowohl auf Formen als auch auf Text anwendet – alles angetrieben von **aspose page java**.

## Warum Hatch‑Muster mit Aspose.Page Java verwenden?
- **Visuelle Unterscheidung** – Schraffur‑Füllungen funktionieren selbst, wenn Drucker nur monochrome Ausgaben unterstützen.  
- **Leistung** – Texturen werden on‑the‑fly erzeugt, sodass Sie große Bilddateien vermeiden.  
- **Cross‑Format‑Unterstützung** – Der gleiche Code kann mit minimalen Änderungen PDF, EPS oder SVG erzeugen.

## Häufige Stolperfallen & Tipps
- **Dateipfad‑Fehler** – Stellen Sie sicher, dass `dataDir` mit dem passenden Pfadtrenner (`/` oder `\`) endet.  
- **Nicht unterstützte Farben** – Einige ältere PostScript‑Interpreter können bestimmte Farbräume nicht verarbeiten; verwenden Sie für maximale Kompatibilität einfaches RGB.  
- **Lizenz‑Warnungen** – Das Ausführen des Beispiels ohne gültige Lizenz fügt dem Ergebnis ein Wasserzeichen hinzu.

## Fazit
Das Einbinden von Schraffur‑Mustern kann die Lesbarkeit und Ästhetik technischer Zeichnungen, Karten oder jeglicher von Java erzeugter Grafiken erheblich verbessern. Mit **Aspose.Page Java** erhalten Sie eine kompakte API, die die Low‑Level‑PostScript‑Befehle abstrahiert, sodass Sie sich auf das Design statt auf Dateiformat‑Eigenheiten konzentrieren können.

## Häufig gestellte Fragen

**F: Kann ich Aspose.Page Java mit anderen Java‑Frameworks verwenden?**  
A: Ja, die Bibliothek ist framework‑agnostisch und funktioniert mit Spring, Jakarta EE, Android (eingeschränkt) und reinem Java SE.

**F: Gibt es eine Testversion für Aspose.Page Java?**  
A: Absolut. Laden Sie eine kostenlose 30‑Tage‑Testversion [here](https://releases.aspose.com/).

**F: Wie erhalte ich eine temporäre Lizenz für die Entwicklung?**  
A: Fordern Sie eine temporäre Lizenz [here](https://purchase.aspose.com/temporary-license/) an. Sie entfernt Evaluations‑Wasserzeichen.

**F: Wo finde ich weitere Tutorials und Community‑Support?**  
A: Besuchen Sie das offizielle Forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) für zusätzliche Beispiele und Fragen‑Antworten.

**F: Gibt es eine umfassende Dokumentation für alle Klassen und Methoden?**  
A: Ja, die vollständige API‑Referenz ist verfügbar [here](https://reference.aspose.com/page/java/).

---

**Last Updated:** 2025-12-08  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
