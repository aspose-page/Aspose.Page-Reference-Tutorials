---
date: 2026-09-04
description: Erfahren Sie, wie Sie in Java PostScript mit Aspose.Page Java einen Farbverlauf
  hinzufügen und diagonale Farbübergänge mit LinearGradientPaint für lebendige Dokumente
  erstellen.
keywords:
- how to add gradient
- diagonal gradient java
- Aspose.Page Java
- LinearGradientPaint
- Java PostScript graphics
lastmod: 2026-09-04
linktitle: 'So fügen Sie einen Farbverlauf hinzu: Diagonalverlauf in Java PostScript
  mit Aspose.Page Java'
og_description: Erfahren Sie, wie Sie in Java PostScript mit Aspose.Page Java einen
  Farbverlauf hinzufügen. Dieser Leitfaden zeigt Ihnen, wie Sie in wenigen Schritten
  einen diagonalen Farbverlauf mit LinearGradientPaint erstellen.
og_image_alt: Code example creating a diagonal gradient in a PostScript document using
  Aspose.Page for Java
og_title: So fügen Sie einen Farbverlauf in Java PostScript mit Aspose.Page Java hinzu
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to add gradient in Java PostScript with Aspose.Page Java,
    creating diagonal color transitions using LinearGradientPaint for vibrant documents.
  headline: 'How to add gradient: diagonal gradient in Java PostScript using Aspose.Page
    Java'
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for Java provides a full set of drawing primitives, text
      rendering, and image handling capabilities.
    question: Can I use this library for other graphic operations in Java?
  - answer: Absolutely. You can download a fully functional trial from the [Aspose
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page Java?
  - answer: The official API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find documentation for Aspose.Page Java?
  - answer: Licenses can be bought directly from the [Aspose purchase portal](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Page Java?
  - answer: Visit the community‑run [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for help from both Aspose engineers and fellow developers.
    question: Need assistance or have questions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- LinearGradientPaint
- document graphics
title: 'So fügen Sie einen Farbverlauf hinzu: Diagonalverlauf in Java PostScript mit
  Aspose.Page Java'
url: /de/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Diagonalen Farbverlauf in Java PostScript mit Aspose.Page Java hinzufügen

## Einführung
Wenn Sie eine PostScript‑Datei mit einem sanften diagonalen Farbverlauf anreichern möchten, macht **Aspose.Page Java** das überraschend einfach. In diesem Tutorial lernen Sie **wie man Farbverlauf‑Effekte** Schritt für Schritt hinzufügt, wobei die Klasse `LinearGradientPaint` aus Java 2D verwendet wird. Am Ende haben Sie ein sofort ausführbares Snippet, das ein PostScript‑Dokument mit einem lebendigen diagonalen Farbverlauf erstellt, und Sie verstehen, warum dieser Ansatz wartbarer ist als das manuelle Codieren von rohen PostScript‑Befehlen.

## Wie man einen Farbverlauf in Java PostScript hinzufügt
Einen Farbverlauf hinzuzufügen mag wie eine rein grafische Aufgabe klingen, aber mit Aspose.Page erhalten Sie die volle Kontrolle über die zugrunde liegenden PostScript‑Befehle, während Sie in reinem Java bleiben. Dieser Abschnitt erklärt, warum der Ansatz funktioniert und welchen Nutzen Sie im Vergleich zum manuellen Codieren von rohem PostScript haben.

## Schnelle Antworten
- **Welche Bibliothek wird benötigt?** Aspose.Page für Java.  
- **Welche Klasse erstellt den Farbverlauf?** `LinearGradientPaint`.  
- **Kann ich die Farben ändern?** Ja – ändern Sie das `Color[]`‑Array.  
- **Benötige ich eine Lizenz für die Produktion?** Eine kommerzielle Lizenz ist erforderlich; eine kostenlose Testversion ist verfügbar.  
- **Wie lange dauert die Implementierung?** Etwa 10 Minuten für einen einfachen Farbverlauf.

## Was ist Aspose.Page Java?
Aspose.Page Java ist eine voll ausgestattete API, die Entwicklern ermöglicht, PostScript‑ und PDF‑Dateien zu erzeugen, zu bearbeiten und zu konvertieren, ohne externe Software zu benötigen. Die Bibliothek unterstützt **mehr als 50 Eingabe‑ und Ausgabeformate** und kann Dokumente mit **mehr als 500 Seiten** verarbeiten, während der Speicherverbrauch unter 100 MB bleibt.

## Warum einen diagonalen Farbverlauf verwenden?
Ein diagonaler Farbverlauf verleiht Diagrammen, Bannern oder jedem grafischen Element, das einen modernen Look benötigt, Tiefe und visuelles Interesse. Da der Verlauf von einer Ecke zur gegenüberliegenden verläuft, eignet er sich gut für Hintergründe, Schaltflächen‑Skins und dekorative Formen und liefert ein professionelles Ergebnis ohne zusätzliche Bilddateien.

## Voraussetzungen
- Java Development Kit (JDK) 8 oder höher.  
- Eine IDE wie Eclipse, IntelliJ IDEA oder VS Code.  
- **Aspose.Page für Java**‑Bibliothek – laden Sie die neueste Version von der [offiziellen Download‑Seite](https://releases.aspose.com/page/java/) herunter.

## Pakete importieren
Das Paket `java.awt` stellt die Kern‑Grafikklassen bereit, während das Paket `com.aspose.page` Zugriff auf PostScript‑spezifische APIs gibt.

Die Klasse `LinearGradientPaint` ist die Brücke von Aspose.Page zur Java 2D‑Farbverlauf‑Funktionalität.  
`AffineTransform` ermöglicht Drehung und Skalierung des Farbverlaufs, sodass er diagonal ausgerichtet ist.

```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Schritt 1: Ausgabestream für PostScript‑Dokument erstellen
Zuerst definieren Sie den Ordner, in dem die Datei gespeichert wird, und öffnen einen `FileOutputStream`. Dieser Stream empfängt die erzeugten PostScript‑Daten.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## Schritt 2: Speicheroptionen mit A4‑Größe erstellen
`PsSaveOptions` ermöglicht es Ihnen, Seitengröße, Auflösung und weitere Ausgabeeinstellungen festzulegen. Hier verwenden wir die Standard‑A4‑Größe, die 595 × 842 Punkte bei 72 dpi beträgt.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## Schritt 3: Neues PS‑Dokument erstellen
Die Klasse `PsDocument` repräsentiert ein PostScript‑Dokument und bietet Methoden zum Erstellen von Seiten und zum Zeichnen von Grafiken.  
Instanziieren Sie ein `PsDocument` mit dem Ausgabestream und den Speicheroptionen. Das Flag `false` weist den Konstruktor an, nicht automatisch eine neue Seite zu öffnen – das erledigen wir später.

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Schritt 4: Ein Rechteck erstellen
Definieren Sie das Rechteck, das die Farbverlauf‑Füllung erhalten soll. Die Position des Rechtecks (200, 100) und die Größe (200 × 100) wurden gewählt, damit der Farbverlauf deutlich sichtbar ist.

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Schritt 5: Transformationsmatrix für den Farbverlauf erstellen
Ein `AffineTransform` ermöglicht es uns, den Farbverlauf zu drehen, zu skalieren und zu verschieben, sodass er diagonal über das Rechteck verläuft. Die nachstehende Rechnung berechnet die Hypotenuse und passt das Skalierungsverhältnis entsprechend an.

```java
// Create the gradient transform. Scale components must be equal to the rectangle width and height.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate gradient, then scale and translate for visible color transition
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```

## Schritt 6: Diagonale lineare Farbverlauf‑Paint erstellen
`LinearGradientPaint` ist die Kernklasse, die den Farbwechsel erzeugt. Sie erstreckt sich vom oberen linken zum unteren rechten Eck des Rechtecks und verwendet die zuvor definierte Transformation. `MultipleGradientPaint.CycleMethod.NO_CYCLE` stellt sicher, dass der Farbverlauf nicht wiederholt wird.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## Schritt 7: Paint setzen und das Rechteck füllen
Wenden Sie das Gradient‑Paint auf das Dokument an und füllen Sie die Rechteckform. Dieser Schritt rendert den diagonalen Farbverlauf auf die PostScript‑Seite.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Schritt 8: Aktuelle Seite schließen und Dokument speichern
Schließlich schließen Sie die Seite, leeren den Stream und speichern die Datei. Die resultierende Datei `DiagonalGradient_outPS.ps` kann mit jedem PostScript‑Betrachter geöffnet werden.

```java
// Close current page and save the document
document.closePage();
document.save();
```

## Häufige Probleme & Tipps
- **Der Farbverlauf erscheint flach** – prüfen Sie den Rotationswinkel; eine 45°‑Drehung erzeugt einen echten Diagonalverlauf.  
- **Farben wirken ausgewaschen** – stellen Sie sicher, dass Sie `MultipleGradientPaint.ColorSpaceType.SRGB` für eine genaue Farbdarstellung verwenden.  
- **Datei‑nicht‑gefunden‑Fehler** – prüfen Sie, ob `dataDir` auf einen bestehenden Ordner verweist und die Anwendung Schreibrechte hat.  
- **Große Dokumente verursachen Speicher‑Spikes** – verwenden Sie `PsSaveOptions.setCompress(true)`, um den Speicherverbrauch zu reduzieren.

## Häufig gestellte Fragen

**F: Kann ich diese Bibliothek für andere grafische Operationen in Java verwenden?**  
A: Ja, Aspose.Page für Java bietet ein vollständiges Set an Zeichen‑Primitiven, Text‑Rendering und Bildverarbeitungs‑Funktionen.

**F: Gibt es eine kostenlose Testversion für Aspose.Page Java?**  
A: Auf jeden Fall. Sie können eine voll funktionsfähige Testversion von der [Aspose‑Test‑Seite](https://releases.aspose.com/) herunterladen.

**F: Wo finde ich die Dokumentation für Aspose.Page Java?**  
A: Die offizielle API‑Referenz ist verfügbar unter [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**F: Wie kann ich eine Lizenz für Aspose.Page Java erwerben?**  
A: Lizenzen können direkt über das [Aspose‑Kauf‑Portal](https://purchase.aspose.com/buy) erworben werden.

**F: Benötigen Sie Unterstützung oder haben Sie Fragen?**  
A: Besuchen Sie das von der Community betriebene [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39) für Hilfe von Aspose‑Ingenieuren und anderen Entwicklern.

---

**Zuletzt aktualisiert:** 2026-09-04  
**Getestet mit:** Aspose.Page für Java 24.12 (neueste)  
**Autor:** Aspose

## Verwandte Tutorials

- [Radialen Farbverlauf in PostScript mit Aspose.Page für Java](/page/java/postscript-gradient-addition/)
- [Wie man einen Farbverlauf in Java PostScript mit Linear Gradient Paint hinzufügt](/page/java/postscript-gradient-addition/horizontal/)
- [PostScript‑Farbverlauf in Java erstellen – Vertikalen Farbverlauf hinzufügen](/page/java/postscript-gradient-addition/vertical/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}