---
date: 2025-12-11
description: Erfahren Sie, wie Sie Rechteckformen in Java PostScript mit Aspose.Page
  zeichnen. Diese Schritt‑für‑Schritt‑Anleitung zeigt, wie Sie die Farbe festlegen,
  die Rechteckfarbe in Java setzen und lebendige Grafiken erstellen.
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: Wie man ein Rechteck in Java PostScript mit Aspose.Page zeichnet
url: /de/java/postscript-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Rechtecke in Java PostScript mit Aspose.Page zeichnet

## Einleitung
Wenn Sie **how to draw rectangle** Formen in einer Java‑PostScript‑Datei benötigen, sind Sie hier genau richtig. In diesem Tutorial führen wir Sie durch die Verwendung von Aspose.Page für Java, um farbige Rechtecke hinzuzufügen, deren Füllung und Kontur zu steuern und das Ergebnis als PostScript‑Dokument zu speichern. Sie sehen genau **how to set paint**, wie man die Geometrie des Rechtecks definiert und warum dieser Ansatz ideal ist, um druckbare Grafiken programmgesteuert zu erzeugen.

## Schnelle Antworten
- **Welche Bibliothek wird benötigt?** Aspose.Page for Java  
- **Kann ich die Rechteckfarben ändern?** Ja – verwenden Sie `setPaint` mit jedem `java.awt.Color`  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion funktioniert zum Testen; für die Produktion ist eine Lizenz erforderlich  
- **Welche Seitengröße wird im Beispiel verwendet?** A4 (Standard `PsSaveOptions`)  
- **Ist der Code mit Java 8+ kompatibel?** Absolut – er verwendet Standard‑AWT‑Klassen  

## Voraussetzungen
- Grundlegendes Verständnis der Java‑Programmierung.  
- Aspose.Page for Java Bibliothek installiert. Falls nicht, laden Sie sie von der [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) herunter.  
- Eine Java‑Entwicklungsumgebung auf Ihrem Rechner eingerichtet.

## Pakete importieren
In Ihrem Java‑Projekt beginnen Sie mit dem Import der erforderlichen Pakete:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Wie man Rechtecke in Java PostScript zeichnet
Unten finden Sie den vollständigen Arbeitsablauf, aufgeteilt in klare Schritte. Jeder Schritt enthält eine kurze Erklärung, gefolgt vom ursprünglichen Code‑Block (unverändert).

### Schritt 1: Farbe für das Füllen des Rechtecks festlegen  
**How to set paint** – wir wählen eine orange Füllfarbe für das erste Rechteck.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Set paint for filling rectangle
document.setPaint(Color.ORANGE);        
// Fill the first rectangle
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```

### Schritt 2: Farbe für die Kontur des Rechtecks festlegen  
**Set rectangle color java** – jetzt ändern wir die Farbe zu Rot und definieren eine Strichbreite.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### Schritt 3: Aktuelle Seite schließen und Dokument speichern  
Nach dem Zeichnen schließen wir die Seite und speichern die Datei.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Warum Aspose.Page für Rechteckgrafiken verwenden?
- **Cross‑platform**: Erzeugt Standard‑PostScript, das auf jedem Drucker funktioniert.  
- **Fine‑grained control**: Sie können Füllfarben, Konturfarben und Linienbreiten unabhängig festlegen.  
- **No external dependencies**: Verwendet nur die integrierten AWT‑Geometrieklassen.  

## Häufige Probleme & Tipps
- **File path errors** – stellen Sie sicher, dass `dataDir` mit einem Dateiseparator endet (`/` oder `\\`).  
- **License exceptions** – die Testversion fügt ein Wasserzeichen hinzu; für den Produktionseinsatz benötigen Sie eine Voll‑Lizenz.  
- **Color visibility** – einige Drucker interpretieren bestimmte RGB‑Werte anders; testen Sie zuerst ein einfaches schwarzes Rechteck.  

## Fazit
In diesem Leitfaden haben wir gezeigt, wie man **how to draw rectangle** Formen in einem Java‑PostScript‑Dokument erstellt, **how to set paint** behandelt und demonstriert, wie man **set rectangle color java** mit Aspose.Page verwendet. Experimentieren Sie gern mit verschiedenen Formen, Farben und Linienstilen, um hochwertige druckbare Grafiken für Berichte, Rechnungen oder individuelle Drucke zu erzeugen.

## Häufig gestellte Fragen

### Kann ich Aspose.Page für Java mit anderen Programmiersprachen verwenden?
Aspose.Page unterstützt hauptsächlich Java, aber ähnliche Bibliotheken sind für andere Sprachen verfügbar.

### Gibt es eine Testversion von Aspose.Page für Java?
Ja, Sie können die Funktionen von Aspose.Page für Java mit der [free trial version](https://releases.aspose.com/) testen.

### Wo finde ich zusätzliche Hilfe und Diskussionen?
Besuchen Sie das [Aspose.Page forum](https://forum.aspose.com/c/page/39), um mit der Community zu interagieren und Unterstützung zu erhalten.

### Wie kann ich eine temporäre Lizenz für Aspose.Page für Java erhalten?
Erhalten Sie eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/).

### Wo kann ich eine lizenzierte Version von Aspose.Page für Java kaufen?
Kaufen Sie eine lizenzierte Version [hier](https://purchase.aspose.com/buy).

**Additional Q&A**

**Q:** *Can I change the rectangle size dynamically?*  
**A:** Ja – ändern Sie einfach die Parameter `Rectangle2D.Float(x, y, width, height)` bevor Sie `fill` oder `draw` aufrufen.

**Q:** *Is it possible to add text inside the rectangle?*  
**A:** Absolut. Nach dem Zeichnen des Rechtecks verwenden Sie `document.drawString(...)` mit der gewünschten Schriftart und Position.

**Q:** *Does Aspose.Page support other shapes like circles or polygons?*  
**A:** Ja, die API bietet Methoden wie `drawEllipse` und `drawPolygon` für verschiedene Vektorgrafiken.

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}