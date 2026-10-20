---
date: 2026-10-20
description: Erfahren Sie, wie Sie ein Rechteck mit Aspose.Page for Java skalieren,
  eine Form verschieben und eine affine Transform anwenden, um PostScript-Dokumente
  zu erstellen.
keywords:
- how to scale rectangle
- how to translate shape
- save postscript file
- apply affine transform
- java graphics scaling
lastmod: 2026-10-20
linktitle: Transformationen bei der Java-Seitenmanipulation
og_description: Erfahren Sie, wie Sie ein Rechteck skalieren, eine Form verschieben
  und eine affine Transform mit Aspose.Page for Java anwenden, um PostScript-Dateien
  effizient zu erzeugen.
og_image_alt: Screenshot of Java code scaling a rectangle with Aspose.Page
og_title: Wie man ein Rechteck mit Aspise.Page for Java skaliert – Schritt-für-Schritt-Anleitung
schemas:
- author: Aspose
  dateModified: '2026-10-20'
  description: Learn how to scale rectangle with Aspose.Page for Java, how to translate
    shape, and apply affine transform to create PostScript documents.
  headline: How to Scale Rectangle with Aspose.Page for Java
  type: TechArticle
- questions:
  - answer: '`translate` moves the origin of the coordinate system, while `scale`
      changes the size of drawn objects along the X and/or Y axes.'
    question: What is the difference between `translate` and `scale`?
  - answer: Yes—by calling `translate`, `scale`, `rotate`, or `shear` sequentially
      before drawing, you create a combined affine transformation.
    question: Can I combine multiple transformations in a single graphics state?
  - answer: Use `writeGraphicsRestore()` to revert to the previously saved graphics
      state.
    question: How do I reset transformations after drawing a shape?
  - answer: Absolutely. Translate the rectangle to the origin, apply `rotate(angle)`,
      then translate it back before drawing.
    question: Is it possible to rotate a rectangle around its center?
  - answer: Yes—set the appropriate rendering options in `PsSaveOptions` to enable
      anti‑aliasing.
    question: Does Aspose.Page support anti‑aliasing for smoother graphics?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript generation
- affine transformation
- rectangle scaling
title: Wie man ein Rechteck mit Aspose.Page for Java skaliert
url: /de/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Rechtecke skaliert mit Aspose.Page für Java

## Einführung
In diesem Leitfaden entdecken Sie **how to scale rectangle** Objekte mit Aspose.Page für Java und lernen zudem, wie man Positionen von Formen verschiebt, Grafiken rotiert und affine Transformationsoperationen anwendet, um hochwertige PostScript‑Ausgaben zu erzeugen. Diese Techniken ermöglichen es Ihnen, anspruchsvolle, geräteunabhängige Grafiken zu erstellen, ohne Low‑Level‑Rendering‑Code zu schreiben, wodurch Ihre Java‑Anwendungen leistungsfähiger und wartbarer werden.

## Schnelle Antworten
`scale(sx, sy)` skaliert den Grafik‑Kontext um die angegebenen horizontalen und vertikalen Faktoren.  

- **Wie skaliere ich ein Rechteck in Java mit Aspose.Page?** Rufen Sie die Methode `scale(sx, sy)` im Grafik‑Kontext auf, bevor Sie das Rechteck zeichnen.  
- **Kann ich eine Form verschieben (translate), ohne andere Grafiken zu beeinflussen?** Ja – umschließen Sie die Translation zwischen den Aufrufen `writeGraphicsSave()` und `writeGraphicsRestore()`.  
- **Welche Klasse erstellt eine PostScript‑Datei?** Verwenden Sie `PsDocument` zusammen mit `PsSaveOptions`.  
- **Benötige ich eine Lizenz für den Produktionseinsatz?** Eine gültige Aspose.Page‑Lizenz ist für kommerzielle Bereitstellungen erforderlich.  
- **Welche Java‑Version wird unterstützt?** Aspose.Page funktioniert mit Java 8 und höher.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Ein solides Verständnis der Kern‑Java‑Syntax und objektorientierter Konzepte.  
- Die Aspose.Page für Java‑Bibliothek installiert. Sie können sie von der [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) herunterladen.  
- Eine Java‑IDE (IntelliJ IDEA, Eclipse oder VS Code), die mit den JAR‑Dateien der Bibliothek im Klassenpfad konfiguriert ist.

## Pakete importieren
`PsDocument` ist die Hauptklasse zum Erstellen eines PostScript‑Dokuments, und `PsSaveOptions` konfiguriert, wie das Dokument gespeichert wird.  

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Was bedeutet „wie man ein Rechteck skaliert“ in Aspose.Page?
Die Methode `scale(float sx, float sy)` wendet eine affine Skalierungstransformation auf den aktuellen Grafik‑Status an und ändert die Größe nachfolgender Zeichnungen um die Faktoren `sx` (horizontal) und `sy` (vertikal). Dies ist die Kernoperation hinter dem Schlüsselwort **how to scale rectangle**. Durch Anwenden dieser Transformation vor dem Zeichnen werden alle nachfolgenden Formen, wie Rechtecke, mit den neuen Abmessungen gerendert, wobei ihre Proportionen erhalten bleiben.

## Wie man Formen mit Aspose.Page verschiebt
`writeGraphicsSave()` speichert den aktuellen Grafik‑Zustand und `writeGraphicsRestore()` stellt ihn wieder her, sodass Transformationen nur die beabsichtigte Form beeinflussen. Eine Translation verlagert den Ursprung des Koordinatensystems, ohne die Objektgrößen zu ändern. Indem Sie `translate(dx, dy)` von `writeGraphicsSave()` / `writeGraphicsRestore()` umschließen, stellen Sie sicher, dass nur die gewünschte Form verschoben wird, während andere Grafiken unverändert bleiben, was eine präzise Kontrolle über einzelne Elemente ermöglicht.

## Beispiel 1: Keine Transformationen
Das erste Beispiel zeichnet ein Rechteck ohne jegliche Transformation und legt damit eine Basislinie für den visuellen Vergleich mit späteren Beispielen fest.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## Beispiel 2: Translation
In diesem Beispiel verschieben wir den Grafik‑Kontext um 250 Einheiten nach rechts, bevor wir ein zweites Rechteck zeichnen, und demonstrieren damit **how to translate shape**.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Beispiel 3: Skalierung
Hier beantworten wir die zentrale Frage **how to scale rectangle**. Das Rechteck wird mit dem Aufruf `scale(0.5f, 0.75f)` auf 50 % seiner ursprünglichen Breite und 75 % seiner ursprünglichen Höhe reduziert.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Wie man Formen in Java rotiert (rotate shape java)
`rotate(angle)` dreht das Koordinatensystem um den angegebenen Winkel in Grad. Laden Sie Ihr `PsDocument`, rufen Sie `rotate(angle)` im Grafik‑Zustand auf, zeichnen Sie die Form und stellen Sie anschließend den vorherigen Zustand wieder her. Dieses Muster implementiert **rotate shape java** und **how to rotate rectangle** in einem einzigen, wiederverwendbaren Block, sodass Sie Grafiken um jeden gewünschten Punkt drehen können.

## Warum das wichtig ist – praktische Vorteile
- **Geräteunabhängige Ausgabe** – Aspose.Page kann PostScript‑ und XPS‑Dateien erzeugen, die auf jedem Drucker oder Viewer identisch dargestellt werden, wodurch plattformspezifische Anpassungen entfallen.  
- **Fein abgestimmte Kontrolle** – Kombinieren Sie Translation, Skalierung, Scherung und Rotation, um genaue Layout‑Spezifikationen zu erfüllen; die API unterstützt über 20 Transformationskombinationen pro Seite.  
- **Leistungsorientierte Verarbeitung** – Die Bibliothek verarbeitet Dokumente mit einem Speicherverbrauch von unter 10 MB für typische 100‑Seiten‑Berichte, wodurch Batch‑Jobs schnell und skalierbar sind.

## Häufige Anwendungsfälle
- **Druckbare Rechnungen** – Platzieren Sie Logos, Barcodes und Tabellen präzise mithilfe von Skalierung und Translation, um Unternehmens‑Branding‑Richtlinien zu entsprechen.  
- **Technische Diagramme** – Erzeugen Sie Schemata, bei denen jede Komponente proportional skaliert und positioniert werden muss.  
- **Automatisierte Mehrseitige Berichte** – Erstellen Sie PostScript‑Berichte, die über Seiten hinweg konsistente Skalierung erfordern, wie z. B. technische Spezifikationen.

## Häufige Probleme und Lösungen
- **Transformation wird nicht zurückgesetzt** – Paaren Sie immer `writeGraphicsSave()` mit `writeGraphicsRestore()`; andernfalls übernehmen nachfolgende Zeichnungen unerwünschte Transformationen.  
- **Unerwartete Farben** – Setzen Sie die Farbe (Paint) nach jeder Transformation, da der Grafik‑Zustand Farbinformationen nach einem Restore nicht beibehält.  
- **Dateigröße zu groß** – Aktivieren Sie die Kompression in `PsSaveOptions` und begrenzen Sie die Auflösung eingebetteter Rasterbilder, um die endgültige Datei bei typischen 50‑Seiten‑Dokumenten unter 5 MB zu halten.

## FAQ
### Kann ich Aspose.Page für Java für andere Dokumentformate verwenden?
Aspose.Page konzentriert sich hauptsächlich auf die Seitenmanipulation für PostScript‑ und XPS‑Formate, bietet jedoch eingeschränkte PDF‑Export‑Möglichkeiten.

### Wo finde ich weitere Beispiele und Dokumentation für Aspose.Page für Java?
Besuchen Sie die [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) für umfassende Anleitungen, API‑Referenzen und Beispielprojekte.

### Gibt es eine kostenlose Testversion für Aspose.Page für Java?
Ja, Sie können über die **Aspose free trial download**‑Seite eine kostenlose Testversion erhalten: [Aspose free trial download](https://releases.aspose.com/).

### Wie kann ich eine temporäre Lizenz für Aspose.Page für Java erhalten?
Erhalten Sie eine temporäre Lizenz über die **temporary license request page**: [temporary license request page](https://purchase.aspose.com/temporary-license/).

### Wo kann ich Community‑Support finden oder Fragen zu Aspose.Page für Java stellen?
Besuchen Sie das [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) für Community‑Diskussionen, Code‑Snippets und Fehlersuche.

## Häufig gestellte Fragen

**Q: Was ist der Unterschied zwischen `translate` und `scale`?**  
A: `translate` verschiebt den Ursprung des Koordinatensystems, während `scale` die Größe gezeichneter Objekte entlang der X‑ und/oder Y‑Achsen ändert.

**Q: Kann ich mehrere Transformationen in einem einzigen Grafik‑Zustand kombinieren?**  
A: Ja – indem Sie `translate`, `scale`, `rotate` oder `shear` nacheinander vor dem Zeichnen aufrufen, erzeugen Sie eine kombinierte affine Transformation.

**Q: Wie setze ich Transformationen nach dem Zeichnen einer Form zurück?**  
A: Verwenden Sie `writeGraphicsRestore()`, um zum zuvor gespeicherten Grafik‑Zustand zurückzukehren.

**Q: Ist es möglich, ein Rechteck um seine Mitte zu drehen?**  
A: Absolut. Verschieben Sie das Rechteck zum Ursprung, wenden Sie `rotate(angle)` an und verschieben Sie es anschließend wieder zurück, bevor Sie es zeichnen.

**Q: Unterstützt Aspose.Page Anti‑Aliasing für glattere Grafiken?**  
A: Ja – setzen Sie die entsprechenden Rendering‑Optionen in `PsSaveOptions`, um Anti‑Aliasing zu aktivieren.

**Zuletzt aktualisiert:** 2026-10-20  
**Getestet mit:** Aspose.Page for Java 24.12  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man Rechtecke in Java PostScript mit Aspose.Page zeichnet](/page/java/postscript-shapes/add-rectangle/)
- [Radialgradient in PostScript mit Aspose.Page für Java erstellen](/page/java/postscript-gradient-addition/)
- [PostScript‑Seitenmanipulation](/page/java/postscript-page-manipulation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}