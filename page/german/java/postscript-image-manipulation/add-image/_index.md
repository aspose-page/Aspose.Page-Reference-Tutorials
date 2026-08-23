---
date: 2026-08-23
description: Erfahren Sie, wie Sie aspose.page Bildmanipulation Java verwenden, um
  Bilder in PostScript-Dateien einzubetten und zu drehen, mit klaren Java‑Beispielen.
keywords:
- aspose.page image manipulation java
- add image postscript java
- java postscript image rotation
- aspose.page java tutorial
- image embedding java
lastmod: 2026-08-23
linktitle: Bild in Java‑PostScript hinzufügen
og_description: Erfahren Sie, wie Sie aspose.page Bildmanipulation Java verwenden,
  um Bilder in PostScript-Dateien einzubetten und zu drehen, mit schritt‑für‑schritt
  Java‑Code‑Beispielen.
og_image_alt: Guide showing Java code to add and rotate images in PostScript using
  Aspose.Page
og_title: Wie man aspose.page Bildmanipulation Java verwendet, um ein Bild hinzuzufügen
schemas:
- author: Aspose
  dateModified: '2026-08-23'
  description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  headline: How to use aspose.page image manipulation java to add image
  type: TechArticle
- description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  name: How to use aspose.page image manipulation java to add image
  steps:
  - name: write graphics save
    text: Saving the graphics state isolates your transformations so you can revert
      later. This is equivalent to the `gsave` operator in raw PostScript.
  - name: translate and transform (translate and rotate image)
    text: First, create a `BufferedImage` from the source file, then build an `AffineTransform`
      that translates the image to the desired coordinates and rotates it around its
      centre. `AffineTransform.rotate` expects an angle in radians, so convert degrees
      with `Math.toRadians(degrees)`. **AffineTransform** is
  - name: add image to document
    text: After configuring the transform, draw the image onto the current page. The
      library automatically converts the `BufferedImage` into an appropriate PostScript
      image stream.
  - name: write graphics restore
    text: Calling restore (`grestore`) returns the graphics state to what it was before
      the save, ensuring subsequent drawing commands are not affected by the previous
      transformation.
  - name: close current page and save
    text: Finish the page, close the document, and write the output file to disk.
      You can repeat the above sequence to embed additional images, adjusting the
      translation coordinates and rotation angle each time.
  type: HowTo
- questions:
  - answer: The core library is Java‑only, but Aspose provides equivalent APIs for
      .NET, C++, and Python, each tailored to its platform.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can access the free trial **[Aspose.Page free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for community assistance.
    question: Where can I find community support and discussions related to Aspose.Page
      for Java?
  - answer: You can buy the library **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.
    question: Are there any additional resources for purchasing Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image manipulation
- postscript
- image rotation
- java tutorial
title: Wie man aspose.page Bildmanipulation Java verwendet, um ein Bild hinzuzufügen
url: /de/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man aspose.page Bildmanipulation Java verwendet, um ein Bild hinzuzufügen

## Einführung
In diesem Tutorial lernen Sie, **aspose.page Bildmanipulation Java** zu verwenden, um PostScript‑Dateien zu erstellen, Rasterbilder einzubetten und Übersetzungs‑ und Rotations‑Transformationen anzuwenden. Am Ende des Leitfadens können Sie pixelgenaue PostScript‑Ausgaben aus Java erzeugen – ideal für automatisierte Berichte, Druckpipelines oder jeden Workflow, der eine präzise Bildplatzierung in einem PostScript‑Dokument erfordert.

## Schnelle Antworten
- **Welche Bibliothek wird benötigt?** Aspose.Page for Java  
- **Kann ich mehrere Bilder hinzufügen?** Ja – wiederholen Sie die Transformations‑ und Zeichen‑Schritte für jedes Bild  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion funktioniert für Tests; für die Produktion ist eine Lizenz erforderlich  
- **Welche Java‑Version wird unterstützt?** Java 8 und neuer  
- **Wird Bildrotation unterstützt?** Absolut – verwenden Sie `AffineTransform.rotate()`  

## Was ist aspose.page Bildmanipulation Java?
`aspose.page Bildmanipulation Java` ist die Aspose.Page‑API, die es Ihnen ermöglicht, programmgesteuert PostScript‑Dokumente aus Java‑Code zu erstellen, zu bearbeiten und zu rendern, einschließlich voller Kontrolle über Bildplatzierung, Skalierung und Rotation. Mit dieser API vermeiden Sie Low‑Level‑PostScript‑Syntax und lassen die Bibliothek die Formatkonvertierung und das Einbetten intern übernehmen.

## Warum aspose.page für Bildmanipulation verwenden?
Aspose.Page bietet **50+ Bildformate** (einschließlich JPEG, PNG, BMP, TIFF) und kann sie in PostScript einbetten, ohne das gesamte Dokument in den Speicher zu laden, wodurch die Verarbeitung von Dateien mit Hunderten von Seiten möglich ist, während der Speicherverbrauch auf typischen Servern unter 100 MB bleibt. Die High‑Level‑API abstrahiert komplexe PostScript‑Befehle, sodass Sie prägnanten Java‑Code anstelle von rohen PS‑Operatoren schreiben.

## Voraussetzungen
- Java Development Kit (JDK) 8 oder neuer installiert.  
- Aspose.Page for Java Bibliothek – laden Sie sie **[Aspose.Page for Java download page](https://releases.aspose.com/page/java/)** herunter.  
- Grundlegende Kenntnisse der Java‑Syntax und objektorientierten Programmierung.

## Was ist create postscript java?
Das Erstellen einer PostScript‑Datei aus Java bedeutet, programmgesteuert ein `.ps`‑Dokument zu erzeugen, das Seitenlayout, Vektorgrafiken und Rasterbilder mittels der PostScript‑Sprache beschreibt. Aspose.Page übersetzt Ihre Java‑Aufrufe in gültige PostScript‑Anweisungen, sodass Sie druckfertige Dateien ohne separaten PostScript‑Interpreter produzieren können.

## Wie man ein Bild Schritt für Schritt mit Translation und Rotation hinzufügt

Laden Sie Ihr Bild, wenden Sie ein `AffineTransform` an und zeichnen Sie es auf die Seite. Die folgenden Schritte beschreiben die genaue Reihenfolge, die Sie befolgen müssen.

### Schritt 1: Grafikzustand speichern
Das Speichern des Grafikzustands isoliert Ihre Transformationen, sodass Sie später zurücksetzen können. Dies entspricht dem `gsave`‑Operator in rohem PostScript.

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Schritt 2: Übersetzen und transformieren (Bild übersetzen und rotieren)
Erstellen Sie zunächst ein `BufferedImage` aus der Quelldatei, dann bauen Sie ein `AffineTransform`, das das Bild zu den gewünschten Koordinaten verschiebt und um seine Mitte rotiert. `AffineTransform.rotate` erwartet einen Winkel in Radianten, also konvertieren Sie Grad mit `Math.toRadians(degrees)`.

**AffineTransform** ist eine Java‑Klasse, die eine 2‑D‑affine Transformation wie Translation, Rotation, Skalierung oder Scherung darstellt.  
**BufferedImage** ist eine Java‑Klasse, die ein Bild im Speicher als Raster von Pixeln speichert.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

### Schritt 3: Bild zum Dokument hinzufügen
Nach der Konfiguration der Transformation zeichnen Sie das Bild auf die aktuelle Seite. Die Bibliothek konvertiert das `BufferedImage` automatisch in einen geeigneten PostScript‑Bildstrom.

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

### Schritt 4: Grafikzustand wiederherstellen
Das Aufrufen von restore (`grestore`) stellt den Grafikzustand wieder her, wie er vor dem Speichern war, sodass nachfolgende Zeichenbefehle nicht von der vorherigen Transformation beeinflusst werden.

```java
document.drawImage(image, transform, null);
```

### Schritt 5: aktuelle Seite schließen und speichern
Beenden Sie die Seite, schließen Sie das Dokument und schreiben Sie die Ausgabedatei auf die Festplatte.

```java
document.writeGraphicsRestore();
```

Sie können die obige Sequenz wiederholen, um weitere Bilder einzubetten, wobei Sie jedes Mal die Übersetzungskoordinaten und den Rotationswinkel anpassen.

## Häufige Probleme und Lösungen
- **FileNotFoundException:** Überprüfen Sie, dass `dataDir` mit einem Dateiseparator (`/` oder `\\`) endet und dass der Bilddateiname exakt übereinstimmt.  
- **ImageIO.read gibt null zurück:** Stellen Sie sicher, dass das Bildformat in der unterstützten Liste (JPEG, PNG, BMP, GIF, TIFF) enthalten ist.  
- **Falscher Rotationswinkel:** `AffineTransform.rotate` arbeitet mit Radianten; verwenden Sie `Math.toRadians(degrees)`, um von Grad zu konvertieren.  
- **Speicherspitzen bei großen Seiten:** Verwenden Sie `Document.save` mit `saveOptions.setCompress(true)`, um den Speicherverbrauch zu reduzieren.

## Häufig gestellte Fragen

**F: Kann ich Aspose.Page für Java mit anderen Programmiersprachen verwenden?**  
A: Die Kernbibliothek ist nur für Java, aber Aspose bietet äquivalente APIs für .NET, C++ und Python, jeweils an die Plattform angepasst.

**F: Gibt es eine kostenlose Testversion für Aspose.Page für Java?**  
A: Ja, Sie können die kostenlose Testversion **[Aspose.Page free trial page](https://releases.aspose.com/)** nutzen.

**F: Wie kann ich eine temporäre Lizenz für Aspose.Page für Java erhalten?**  
A: Sie können eine temporäre Lizenz über die **[temporary license request page](https://purchase.aspose.com/temporary-license/)** erhalten.

**F: Wo finde ich Community‑Support und Diskussionen zu Aspose.Page für Java?**  
A: Besuchen Sie das **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** für Community‑Unterstützung.

**F: Gibt es weitere Ressourcen zum Kauf von Aspose.Page für Java?**  
A: Sie können die Bibliothek über die **[Aspose.Page purchase page](https://purchase.aspose.com/buy)** erwerben.

## Fazit
Sie haben nun ein vollständiges, durchgängiges Beispiel für **aspose.page Bildmanipulation Java**, das eine PostScript‑Datei erstellt, ein Bild übersetzt und rotiert und das Ergebnis speichert. Erkunden Sie die vollständige **[documentation](https://reference.aspose.com/page/java/)**, um erweiterte Funktionen wie Vektorgrafiken, benutzerdefinierte Seitengrößen und Textdarstellung zu entdecken.

---

**Letzte Aktualisierung:** 2026-08-23  
**Getestet mit:** Aspose.Page for Java 23.11  
**Autor:** Aspose  








```java
document.closePage();
document.save();
```

## Verwandte Tutorials

- [Wie man PostScript mit Aspose.Page Java API in PDF konvertiert](/page/java/postscript-conversion/to-pdf/)
- [Wie man einen Farbverlauf hinzufügt: Diagonalverlauf in Java PostScript mit Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Wie man ein Schraffurmuster in Java PostScript mit Aspose.Page hinzufügt](/page/java/postscript-hatch-patterns/add-hatch-pattern/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}