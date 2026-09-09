---
date: 2026-09-09
description: Erfahren Sie, wie Sie einen gradient in Java PostScript erstellen und
  einen gradient zu shape hinzufügen using Aspose.Page. Folgen Sie dieser step‑by‑step
  Anleitung mit code und tips.
keywords:
- how to create gradient
- add gradient to shape
- radial gradient Java
lastmod: 2026-09-09
linktitle: Java PostScript Radial Gradient mit Aspose.Page
og_description: Erfahren Sie, wie Sie einen gradient in Java PostScript erstellen
  und einen gradient zu shape hinzufügen using Aspose.Page. Folgen Sie dieser step‑by‑step
  Anleitung mit code und tips.
og_image_alt: 'Developer guide: create gradient in Java PostScript with radial fill
  using Aspose.Page'
og_title: Wie man einen gradient in Java PostScript mit radial fill erstellt
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create gradient in Java PostScript and add gradient to
    shape using Aspose.Page. Follow this step‑by‑step guide with code and tips.
  headline: How to create gradient in Java PostScript with radial fill
  type: TechArticle
- questions:
  - answer: The full API reference is available in the [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).
    question: Where can I find the documentation for Aspose.Page for Java?
  - answer: Grab the latest JAR from the [releases page](https://releases.aspose.com/page/java/).
    question: How can I download Aspose.Page for Java?
  - answer: Yes—download a trial version from the [Aspose free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Absolutely, request one from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for testing?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- radial gradient
- fill shape
title: Wie man einen gradient in Java PostScript mit radial fill erstellt
url: /de/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man einen Farbverlauf in Java PostScript mit radialer Füllung erstellt

## Einleitung
In diesem Tutorial lernen Sie **wie man Farbverläufe** in einem PostScript-Dokument mit Java und Aspose.Page erstellt. Wir gehen jeden Schritt durch – von der Projektkonfiguration bis zur Darstellung eines Kreises, der mit einem sanften radialen Farbverlauf gefüllt ist – sodass Sie **Farbverläufe zu Formen** sofort hinzufügen und die visuelle Qualität Ihrer Java-Anwendungen steigern können.

## Kurze Antworten
- **Was erstellt dieses Tutorial?** Eine PostScript-Datei (`.ps`) mit einem Kreis, der mit einem radialen Farbverlauf gefüllt ist.  
- **Welche Bibliothek wird benötigt?** Aspose.Page für Java (neueste Version).  
- **Wie lange dauert die Implementierung?** Ungefähr 10‑15 Minuten für ein funktionierendes Beispiel.  
- **Benötige ich eine Lizenz?** Für den Produktionseinsatz ist eine temporäre oder vollständige Lizenz erforderlich; eine kostenlose Testversion reicht für die Entwicklung.  
- **Kann ich den Code für PDF oder SVG wiederverwenden?** Ja – Aspose.Page unterstützt mehrere Ausgabeformate mit minimalen Änderungen.

## Wie man eine Form in PostScript mit einem Farbverlauf füllt
Sie können eine Form in PostScript mit einem radialen Farbverlauf füllen, indem Sie ein `PsDocument` erstellen, ein `RadialGradientPaint` definieren, es auf die Ziel‑Form anwenden und schließlich das Dokument speichern. Dieser kompakte Arbeitsablauf ermöglicht es Ihnen, professionell aussehende Vektorgrafiken ohne Rasterbilder zu erzeugen, und derselbe Code kann für PDF‑ oder SVG‑Ausgabe wiederverwendet werden. Der Prozess ist unkompliziert und funktioniert konsistent über alle unterstützten Formate hinweg.

## Was ist ein radialer Farbverlauf?
Ein radialer Farbverlauf verlagert Farben von einem zentralen Punkt nach außen und erzeugt dabei einen sanften, kreisförmigen Übergang. Er eignet sich ideal für Highlights, Schaltflächenhintergründe oder jede Darstellung, die einen natürlichen „Leuchteffekt“ benötigt. Durch Variation der Farb‑Stops und des Radius können Sie Beleuchtung, Tiefe und Materialeigenschaften in reiner Vektorform simulieren.

## Warum Aspose.Page für radiale Farbverläufe verwenden?
Aspose.Page ermöglicht es Ihnen, geräteunabhängige Vektorgrafiken mit einer einzigen Java‑API zu erzeugen. Es unterstützt über 50 Eingabe‑ und Ausgabeformate – darunter PostScript, PDF und SVG – und bewahrt dabei Farbgenauigkeit und Anti‑Aliasing für hochauflösende Ausgaben. Die Bibliothek bietet zudem einfach zu verwendende Gradient‑Klassen, sodass komplexe visuelle Effekte leicht implementiert werden können.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Grundlegende Kenntnisse in der Java‑Programmierung.  
- JDK 8 oder neuer, das auf Ihrem Rechner installiert ist.  
- Aspose.Page für Java Bibliothek (Download von der [Aspose.Page Java documentation](https://reference.aspose.com/page/java/)).  

## Pakete importieren
Zuerst importieren Sie die Klassen, die wir benötigen. Diese umfassen Standard‑AWT‑Grafiktypen und die Aspose.Page‑API.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Schritt 1: Dokumentverzeichnis einrichten
Definieren Sie den Ordner, in dem die erzeugte PostScript‑Datei gespeichert wird. Ersetzen Sie den Platzhalter durch einen tatsächlichen Pfad auf Ihrem System.

```java
String dataDir = "Your Document Directory";
```

## Schritt 2: Ausgabestream erstellen
FileOutputStream schreibt rohe Bytes in eine Datei und ermöglicht das Speichern binärer Daten. Das Öffnen eines Streams, der auf eine `.ps`‑Datei zielt, lässt Aspose.Page die erzeugten PostScript‑Daten direkt auf die Festplatte schreiben.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Schritt 3: Speicheroptionen erstellen
PsSaveOptions konfiguriert, wie eine PostScript‑Datei gespeichert wird, einschließlich Seitengröße und Kompression. Sie können diese Einstellungen anpassen, aber die Vorgaben sind für dieses Beispiel ausreichend.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Schritt 4: PS-Dokument erstellen
PsDocument repräsentiert ein PostScript‑Dokument im Speicher und bietet Methoden zum Hinzufügen von Seiten und Grafiken.

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Schritt 5: Einen Kreis erstellen
`Ellipse2D.Float` beschreibt eine Ellipsenform; wenn Breite = Höhe ist, wird sie zu einem perfekten Kreis. Dieses Objekt dient als Leinwand für unsere Farbverlauf‑Füllung.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Wie man einen Kreis mit Farbverlauf zeichnet
Um einen Kreis mit einem radialen Farbverlauf zu zeichnen, laden Sie ein `RadialGradientPaint` in den Grafik‑Context und füllen anschließend die zuvor definierte Ellipse. Dieser einzelne Vorgang malt die Form mit einem sanften Farbübergang vom Zentrum nach außen und erzeugt einen visuell ansprechenden Effekt.

## Schritt 6: Farbverlauffarben definieren
Bereiten Sie zwei Arrays vor: eines für die Farben, die im Farbverlauf erscheinen, und ein weiteres für die entsprechenden Bruchpositionen (0 = Zentrum, 1 = Rand).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Schritt 7: AffineTransform erstellen
AffineTransform ist eine Matrix, die Grafikobjekte verschieben, drehen, skalieren oder scheren kann. Hier skaliert und verschiebt sie den Farbverlauf, sodass er exakt in den Kreis passt.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Schritt 8: RadialGradientPaint erstellen
RadialGradientPaint erzeugt einen radialen Farbverlauf basierend auf einem Mittelpunkt, einem Radius und Farb‑Stops.

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## Schritt 9: Paint setzen und Kreis füllen
Wenden Sie das Gradient‑Paint auf das Dokument an und füllen Sie den zuvor definierten Kreis. Dies ist der Kern unseres **radialen Farbverlauf‑Beispiels** und zeigt, wie man **Formen mit einem Farbverlauf füllt**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Schritt 10: Seite schließen und Dokument speichern
Schließen Sie die Seite ab, schreiben Sie den Inhalt auf die Festplatte und schließen Sie den Stream. Ihre PostScript‑Datei ist nun bereit, mit jedem PS‑Viewer angezeigt zu werden.

```java
document.closePage();
document.save();
```

Herzlichen Glückwunsch! Sie haben erfolgreich ein Beispiel für einen radialen Farbverlauf in Java PostScript mit Aspose.Page erstellt. Sie verfügen nun über ein wiederverwendbares Muster für **Formen mit einem Farbverlauf füllen**, das auf andere Formen und Ausgabeformate angepasst werden kann.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|---------|----------|
| **FileNotFoundException** beim Öffnen des Ausgabestreams | Stellen Sie sicher, dass `dataDir` auf einen vorhandenen Ordner zeigt und Sie Schreibberechtigungen haben. |
| Farbverlauf sieht flach aus oder fehlt | Stellen Sie sicher, dass das `fractions`‑Array die gleiche Länge wie das `colors`‑Array hat und dass die `AffineTransform` korrekt skaliert. |
| Farben erscheinen invertiert | Vertauschen Sie die Reihenfolge der Farben im `colors`‑Array oder passen Sie die Koordinaten des `focus`‑Punkts an. |

## Häufig gestellte Fragen

**Q: Wo finde ich die Dokumentation für Aspose.Page für Java?**  
A: Die vollständige API‑Referenz ist in der [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/) verfügbar.

**Q: Wie kann ich Aspose.Page für Java herunterladen?**  
A: Laden Sie das neueste JAR von der [releases page](https://releases.aspose.com/page/java/) herunter.

**Q: Gibt es eine kostenlose Testversion?**  
A: Ja – laden Sie eine Testversion von der [Aspose free trial download page](https://releases.aspose.com/) herunter.

**Q: Kann ich eine temporäre Lizenz für Tests erhalten?**  
A: Natürlich, beantragen Sie eine von der [temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: Wo kann ich Community‑Support erhalten?**  
A: Nehmen Sie an der Diskussion im [Aspose.Page forum](https://forum.aspose.com/c/page/39) teil.

## Fazit
In diesem Leitfaden haben wir ein vollständiges **radiales Farbverlauf‑Beispiel** für ein PostScript‑Dokument mit Aspose.Page für Java erstellt. Durch das Befolgen der Schritte verfügen Sie nun über ein wiederverwendbares Muster für **Formen mit einem Farbverlauf füllen**, das Sie an PDF, SVG oder jedes andere von Aspose.Page unterstützte Format anpassen können. Experimentieren Sie mit verschiedenen Farben, Radien und Formen, um Ihre Java‑Grafikprojekte zu bereichern.

---

**Last Updated:** 2026-09-09  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose

## Verwandte Tutorials

- [Erstelle PostScript-Farbverlauf in Java – Vertikalen Farbverlauf hinzufügen](/page/java/postscript-gradient-addition/vertical/)
- [Erstelle Texturmuster in PostScript mit Aspose.Page für Java](/page/java/postscript-texture-patterns/)
- [Aspose.Page Transparenz‑Tutorial – Transparenz in Java PostScript hinzufügen](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}