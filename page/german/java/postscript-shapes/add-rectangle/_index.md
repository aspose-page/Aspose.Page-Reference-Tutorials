---
date: 2026-02-18
description: Erfahren Sie, wie Sie Rechteckformen in Java PostScript mit Aspose.Page
  zeichnen. Diese Schritt‑für‑Schritt‑Anleitung zeigt, wie man Paint festlegt, die
  Rechteckfarbe in Java setzt und lebendige Grafiken erstellt, während erklärt wird,
  wie man Rechtecke effizient zeichnet.
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: Wie man ein Rechteck in Java PostScript mit Aspose.Page zeichnet
url: /de/java/postscript-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Rechtecke in Java PostScript mit Aspose.Page zeichnet

## Introduction
Wenn Sie **how to draw rectangle** Formen in einer Java PostScript-Datei benötigen, sind Sie hier richtig. In diesem Tutorial gehen wir Schritt für Schritt durch die Verwendung von Aspose.Page für Java, um farbige Rechtecke hinzuzufügen, deren Füllung und Kontur zu steuern und das Ergebnis als PostScript-Dokument zu speichern. Sie sehen genau **how to set paint**, wie man die Geometrie des Rechtecks definiert und warum dieser Ansatz ideal ist, um druckbare Grafiken programmgesteuert zu erzeugen. Am Ende des Leitfadens verstehen Sie auch den breiteren Kontext von **draw rectangle java** Techniken und wie sie in **java awt rectangle drawing** Workflows passen.

## Quick Answers
- **Welche Bibliothek wird benötigt?** Aspose.Page for Java  
- **Kann ich die Rechteckfarben ändern?** Ja – verwenden Sie `setPaint` mit jedem `java.awt.Color`  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion funktioniert zum Testen; für die Produktion ist eine Lizenz erforderlich  
- **Welche Seitengröße wird im Beispiel verwendet?** A4 (Standard `PsSaveOptions`)  
- **Ist der Code mit Java 8+ kompatibel?** Absolut – er verwendet Standard‑AWT‑Klassen  

## What Is “How to Draw Rectangle” in PostScript?
Das Zeichnen eines Rechtecks in einem PostScript-Dokument bedeutet, einen rechteckigen Bereich zu definieren und entweder zu füllen, seine Kontur zu zeichnen oder beides. Mit Aspose.Page können Sie dies mithilfe der bekannten **java awt rectangle drawing** Klassen tun, was den Code leicht lesbar und wartbar macht.

## Why Use Aspose.Page for Rectangle Graphics?
- **Plattformübergreifend**: Erzeugt Standard‑PostScript, das auf jedem Drucker funktioniert.  
- **Feinkörnige Kontrolle**: Sie können Füllfarben, Konturfarben und Linienbreiten unabhängig festlegen.  
- **Keine externen Abhängigkeiten**: Verwendet nur die integrierten AWT‑Geometrieklassen, sodass keine zusätzlichen Grafikbibliotheken nötig sind.  

## Prerequisites
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:
- Grundlegendes Verständnis von Java-Programmierung.  
- Aspose.Page for Java Bibliothek installiert. Falls nicht, laden Sie sie von der [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) herunter.  
- Eine Java-Entwicklungsumgebung auf Ihrem Rechner eingerichtet.

## Import Packages
In Ihrem Java‑Projekt beginnen Sie mit dem Import der notwendigen Pakete. Diese Importe geben Ihnen Zugriff auf die AWT‑Klassen `Color`, `BasicStroke` und `Rectangle2D` sowie auf die Kern‑Dokumenten‑Klassen von Aspose.Page.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step‑by‑Step Guide to Draw Rectangle in Java PostScript

### Step 1: Set Paint for Filling Rectangle  
**How to set paint** – wir wählen eine orange Füllfarbe für das erste Rechteck. Dies demonstriert die **set rectangle color java** Fähigkeit.

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

### Step 2: Set Paint for Stroking Rectangle  
**Set rectangle color java** – jetzt ändern wir die Farbe zu Rot und definieren eine Strichbreite. Dieser Teil des Beispiels zeigt, wie man **draw rectangle java** mit einer benutzerdefinierten Linienstärke zeichnet.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### Step 3: Close Current Page and Save Document  
Nach dem Zeichnen schließen wir die Seite und speichern die Datei. Das Schließen der Seite stellt sicher, dass alle Zeichenbefehle in den PostScript‑Strom geschrieben werden.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Common Use Cases for Rectangle Drawing
- **Rechnungs- oder Beleggenerierung** – Rechtecke dienen als Rahmen oder heben Abschnitte hervor.  
- **Etikettenerstellung** – farbige Kästen zeichnen, um Produktinformationen zu trennen.  
- **Einfache Diagramme** – gefüllte Rechtecke als Balkendiagramm‑Elemente verwenden.  
- **Benutzerdefinierte druckbare Formulare** – Rechtecke mit Text kombinieren, um Formularfelder zu erstellen.  

## Common Issues & Tips
- **Dateipfad‑Fehler** – stellen Sie sicher, dass `dataDir` mit einem Dateiseparator endet (`/` oder `\\`).  
- **Lizenzausnahmen** – die Testversion fügt ein Wasserzeichen hinzu; für den Produktionseinsatz benötigen Sie eine Voll‑Lizenz.  
- **Farb‑Sichtbarkeit** – einige Drucker interpretieren bestimmte RGB‑Werte anders; testen Sie zuerst ein einfaches schwarzes Rechteck.  
- **Speichernutzung** – bei großen Dokumenten sollten Sie den Stream nach jeder Seite leeren (`document.closePage()`).  

## Frequently Asked Questions

**Q:** *Kann ich Aspose.Page für Java mit anderen Programmiersprachen verwenden?*  
A: Aspose.Page unterstützt hauptsächlich Java, aber ähnliche Bibliotheken sind für andere Sprachen verfügbar.

**Q:** *Gibt es eine Testversion von Aspose.Page für Java?*  
A: Ja, Sie können die Funktionen von Aspose.Page für Java mit der [free trial version](https://releases.aspose.com/) erkunden.

**Q:** *Wo finde ich zusätzliche Hilfe und Diskussionen?*  
A: Besuchen Sie das [Aspose.Page forum](https://forum.aspose.com/c/page/39), um mit der Community in Kontakt zu treten und Unterstützung zu erhalten.

**Q:** *Wie kann ich eine temporäre Lizenz für Aspose.Page für Java erhalten?*  
A: Holen Sie sich eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/).

**Q:** *Wo kann ich eine lizenzierte Version von Aspose.Page für Java kaufen?*  
A: Kaufen Sie eine lizenzierte Version [hier](https://purchase.aspose.com/buy).

**Additional Q&A**

**Q:** *Kann ich die Größe des Rechtecks dynamisch ändern?*  
A: Ja – ändern Sie einfach die Parameter `Rectangle2D.Float(x, y, width, height)` bevor Sie `fill` oder `draw` aufrufen.

**Q:** *Ist es möglich, Text in das Rechteck einzufügen?*  
A: Absolut. Nach dem Zeichnen des Rechtecks verwenden Sie `document.drawString(...)` mit der gewünschten Schriftart und Position.

**Q:** *Unterstützt Aspose.Page andere Formen wie Kreise oder Polygone?*  
A: Ja, die API bietet Methoden wie `drawEllipse` und `drawPolygon` für verschiedene Vektorgrafiken.

## Conclusion
In diesem Leitfaden haben wir gezeigt, **how to draw rectangle** Formen in einem Java PostScript‑Dokument zu erzeugen, **how to set paint** erklärt und demonstriert, wie man **set rectangle color java** mit Aspose.Page verwendet. Sie haben nun eine solide Grundlage, um lebendige druckbare Grafiken zu erstellen, sei es für Rechnungen, Etiketten oder benutzerdefinierte Formulare. Experimentieren Sie gern mit verschiedenen Farben, Linienstilen und zusätzlichen AWT‑Formen, um Ihre Ausgabe zu bereichern.

---

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}