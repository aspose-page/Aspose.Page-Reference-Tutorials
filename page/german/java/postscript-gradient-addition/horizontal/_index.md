---
date: 2026-09-04
description: Erfahren Sie, wie Sie einen horizontalen Java-Gradient in einer PostScript-Datei
  mit Linear Gradient Paint Java und Aspose.Page für Java erstellen. Schritt‑für‑Schritt‑Code,
  häufige Stolperfallen und FAQs.
keywords:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page Java
- PostScript gradient Java
lastmod: 2026-09-04
linktitle: Horizontalen Java-Gradient in PostScript mit Aspose erstellen
og_description: Erstellen Sie einen horizontalen Java-Gradient in PostScript mit Linear
  Gradient Paint Java. Dieses Aspose.Page‑Tutorial zeigt Ihnen die genauen Schritte,
  Voraussetzungen und Fehlerbehebungstipps in weniger als 15 Minuten.
og_image_alt: Screenshot of a Java PostScript file rendered with a horizontal gradient
  using Aspose.Page
og_title: Horizontalen Java-Gradient in PostScript mit Aspose erstellen
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to create horizontal gradient java in a PostScript file using
    Linear Gradient Paint Java with Aspose.Page for Java. Step‑by‑step code, common
    pitfalls, and FAQs.
  headline: Create horizontal gradient java in PostScript using Aspose
  type: TechArticle
- questions:
  - answer: Aspose.Page for Java (includes Linear Gradient Paint Java).
    question: What library is required?
  - answer: About 10‑15 minutes for a basic horizontal gradient.
    question: How long does implementation take?
  - answer: A temporary or full license is required for production use.
    question: Do I need a license?
  - answer: Java 8 or newer.
    question: Which JDK version works?
  - answer: Yes – the same `LinearGradientPaint` instance can fill shapes and be applied
      to text strokes or fills.
    question: Can I use the gradient on both shapes and text?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page
- Java PostScript
title: Horizontalen Java-Gradient in PostScript mit Aspose erstellen
url: /de/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man einen horizontalen Farbverlauf in Java PostScript mit Linear Gradient Paint hinzufügt

## Einführung
In diesem umfassenden Tutorial lernen Sie **wie man einen horizontalen Farbverlauf in Java** in einem PostScript-Dokument erstellt, indem Sie die **Linear Gradient Paint Java**-Klasse verwenden, die mit Aspose.Page für Java geliefert wird. Wir führen Sie durch jeden Schritt – von der Einrichtung des Projekts bis zur Darstellung des Farbverlaufs auf Formen und Text – damit Sie in wenigen Minuten polierte, druckfertige Grafiken erzeugen können. Egal, ob Sie eine Reporting-Engine, ein Design‑Automatisierungstool oder einen benutzerdefinierten Druckertreiber erstellen, bietet Ihnen dieser Leitfaden den genauen Code, den Sie benötigen.

## Schnelle Antworten
- **Welche Bibliothek wird benötigt?** Aspose.Page for Java (enthält Linear Gradient Paint Java).  
- **Wie lange dauert die Implementierung?** Etwa 10‑15 Minuten für einen einfachen horizontalen Farbverlauf.  
- **Benötige ich eine Lizenz?** Eine temporäre oder vollständige Lizenz ist für den Produktionseinsatz erforderlich.  
- **Welche JDK-Version funktioniert?** Java 8 oder neuer.  
- **Kann ich den Farbverlauf sowohl für Formen als auch für Text verwenden?** Ja – dieselbe `LinearGradientPaint`-Instanz kann Formen füllen und auf Textstriche oder -füllungen angewendet werden.

## Was ist ein horizontaler Farbverlauf und warum ihn verwenden?
Ein horizontaler Farbverlauf mischt Farben vom linken Rand eines Objekts bis zum rechten Rand und erzeugt einen sanften Übergang, der Tiefe und visuelles Interesse hinzufügt. Er ist ideal für moderne UI‑Komponenten, hervorgehobene Überschriften oder dezente Hintergrundschattierungen in PDF‑ oder PostScript‑Berichten. Die Verwendung von **Linear Gradient Paint Java** ermöglicht Ihnen die präzise Steuerung von Start‑ und Endfarben, Transparenz und Skalierung, sodass das Ergebnis auf jedem Gerät oder Drucker scharf aussieht.

## Voraussetzungen
Bevor Sie in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

- Java Development Kit (JDK) auf Ihrem Rechner installiert.  
- Aspose.Page für Java Bibliothek. Sie können sie von der [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) herunterladen.

## Pakete importieren
Beginnen Sie damit, die erforderlichen Pakete in Ihrem Java‑Projekt zu importieren. Diese Importe geben Ihnen Zugriff auf Grafik‑Primitive, Farbverlauf‑Verarbeitung und die Aspose.Page‑API.

Die Klasse `PsDocument` repräsentiert ein PostScript‑Dokument, auf das Sie Grafiken zeichnen können.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Schritt 1: ein Rechteck erstellen
Zuerst richten Sie den Ausgabestream, das Dokument und ein Rechteck ein, das den Farbverlauf enthält.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Schritt 2: horizontalen linearen Farbverlauf erstellen
`LinearGradientPaint` ist die Kernklasse, die einen linearen Farbübergang definiert.  
Die Klasse `LinearGradientPaint` stellt ein Paint‑Objekt dar, das einen Farbverlauf entlang einer geraden Linie rendert; Sie geben Start‑/Endpunkte, Farb‑Stops und optional ein `AffineTransform` an, um ihn an Ihre Form anzupassen.

```java
// Create horizontal linear gradient paint. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Set paint
document.setPaint(paint);
```

## Schritt 3: das Rechteck füllen
Füllen Sie nun das Rechteck mit dem gerade definierten Farbverlauf.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Schritt 4: Text mit dem Farbverlauf füllen
Sie können denselben Farbverlauf auch auf Text anwenden und so einen eindrucksvollen visuellen Effekt erzeugen.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Schritt 5: Text mit dem Farbverlauf umranden
Zum Schluss umranden Sie Text, indem Sie den Farbverlauf als Strichfarbe verwenden.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Häufige Probleme und Lösungen
| Problem | Warum es auftritt | Lösung |
|-------|----------------|-----|
| Farbverlauf erscheint gestreckt | Falsche Skalierung des `AffineTransform` | Stellen Sie sicher, dass Breite und Höhe der Transformation den Abmessungen des Rechtecks entsprechen (200 × 100 im Beispiel). |
| Farben wirken verblasst | Alpha‑Werte zu niedrig eingestellt | Erhöhen Sie die Alpha‑Komponente (den vierten Wert in `new Color(r,g,b,alpha)`). |
| Text ist nicht sichtbar | Paint nicht gesetzt, bevor Text gezeichnet wird | Rufen Sie `document.setPaint(paint)` **vor** allen Aufrufen von `fillAndStrokeText` oder `outlineText` auf. |

## Häufig gestellte Fragen
**Q:** Kann ich Aspose.Page für Java in kommerziellen Projekten verwenden?  
**A:** Ja, Aspose.Page für Java kann in kommerziellen Projekten verwendet werden. Für Lizenzdetails besuchen Sie die Seite [Aspose.Purchase](https://purchase.aspose.com/buy).

**Q:** Gibt es eine kostenlose Testversion?  
**A:** Ja, Sie können eine kostenlose Testversion von Aspose.Page für Java auf der Seite [Aspose.Page for Java free trial](https://releases.aspose.com/) erhalten.

**Q:** Wo finde ich zusätzliche Dokumentation und Support?  
**A:** Besuchen Sie die [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) für umfassende Ressourcen. Für Community‑Hilfe schauen Sie im [Aspose.Page forum](https://forum.aspose.com/c/page/39) nach.

**Q:** Wie kann ich eine temporäre Lizenz erhalten?  
**A:** Sie können eine temporäre Lizenz von der Seite [Aspose.Purchase temporary license page](https://purchase.aspose.com/temporary-license/) erhalten.

**Q:** Was sind die Systemanforderungen für Aspose.Page für Java?  
**A:** Siehe die [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) für detaillierte Systemanforderungen.

---

**Zuletzt aktualisiert:** 2026-09-04  
**Getestet mit:** Aspose.Page for Java 24.11  
**Autor:** Aspose

## Verwandte Tutorials

- [PostScript-Farbverlauf in Java erstellen – Vertikalen Farbverlauf hinzufügen](/page/java/postscript-gradient-addition/vertical/)
- [Wie man einen Farbverlauf hinzufügt: Diagonaler Farbverlauf in Java PostScript mit Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [PostScript-Farbverlauf erstellen – Radialer Farbverlauf in Java](/page/java/postscript-gradient-addition/radial1/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}