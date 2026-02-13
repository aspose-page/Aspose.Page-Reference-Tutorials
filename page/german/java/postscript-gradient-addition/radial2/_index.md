---
date: 2026-02-13
description: Erfahren Sie, wie Sie Formen mit Farbverlauf füllen und Kreise mit Farbverlauf
  in Java PostScript mit Aspose.Page zeichnen. Schritt‑für‑Schritt‑Anleitung mit Code
  und Tipps.
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 'Form mit Farbverlauf füllen: Java PostScript Radialbeispiel'
url: /de/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Füllung einer Form mit Farbverlauf: Java PostScript Radialbeispiel

## Einführung
In diesem Tutorial lernen Sie, wie man **Form mit Farbverlauf füllen** kann, indem Sie ein Beispiel für einen radialen Farbverlauf für ein PostScript‑Dokument mit Aspose.Page für Java erstellen. Wir führen Sie durch jeden Schritt – von der Einrichtung des Projekts bis zur Darstellung eines Kreises, der mit einem sanften radialen Farbverlauf gefüllt ist – damit Sie sofort auffällige Grafiken zu Ihren Java‑Anwendungen hinzufügen können.

## Schnelle Antworten
- **Was erstellt dieses Tutorial?** Eine PostScript‑Datei (`.ps`) mit einem Kreis, der mit einem radialen Farbverlauf gefüllt ist.  
- **Welche Bibliothek wird benötigt?** Aspose.Page für Java (neueste Version).  
- **Wie lange dauert die Implementierung?** Ungefähr 10‑15 Minuten für ein funktionierendes Beispiel.  
- **Benötige ich eine Lizenz?** Für den Produktionseinsatz ist eine temporäre oder vollständige Lizenz erforderlich; eine kostenlose Testversion funktioniert für die Entwicklung.  
- **Kann ich den Code für PDF oder SVG wiederverwenden?** Ja – Aspose.Page unterstützt mehrere Ausgabeformate mit minimalen Änderungen.

## Wie man eine Form mit Farbverlauf in PostScript füllt
Bevor wir in den Code eintauchen, klären wir, warum das „Form mit Farbverlauf füllen“ wichtig ist. Durch die Verwendung von Farbverläufen erhalten Ihre Grafiken ein professionelles, dreidimensionales Aussehen, ohne dass Rasterbilder nötig sind. Mit Aspose.Page können Sie dieselbe Farbverlaufslogik auf jede Vektorform anwenden – Kreise, Rechtecke oder benutzerdefinierte Pfade – in allen unterstützten Ausgabeformaten (PostScript, PDF, SVG).

## Was ist ein radialer Farbverlauf?
Ein radialer Farbverlauf verlagert die Farben vom Mittelpunkt nach außen und erzeugt eine sanfte, kreisförmige Mischung. Er eignet sich ideal für Hervorhebungen, Schaltflächenhintergründe oder jede Darstellung, die einen natürlichen „Leuchteffekt“ benötigt.

## Warum Aspose.Page für radiale Farbverläufe verwenden?
- **Geräteunabhängiges Rendering** – funktioniert gleich auf PostScript, PDF, SVG und mehr.  
- **Vollständige Java‑Integration** – kein nativer Code, nur reine Java‑APIs.  
- **Hochwertige Ausgabe** – unterstützt Antialiasing und Farb‑Raum‑Kontrolle.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Grundlegende Kenntnisse in der Java‑Programmierung.  
- JDK 8 oder neuer auf Ihrem Rechner installiert.  
- Aspose.Page für Java Bibliothek (Download von der [Aspose.Page Java documentation](https://reference.aspose.com/page/java/)).  

## Pakete importieren
Zuerst importieren wir die benötigten Klassen. Diese umfassen Standard‑AWT‑Grafiktypen und die Aspose.Page‑API.

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

## Schritt 1: Dokumentverzeichnis einrichten
Definieren Sie den Ordner, in dem die erzeugte PostScript‑Datei gespeichert wird. Ersetzen Sie den Platzhalter durch einen tatsächlichen Pfad auf Ihrem System.

```java
String dataDir = "Your Document Directory";
```

## Schritt 2: Ausgabestream erstellen
Öffnen Sie einen `FileOutputStream`, der auf die Ziel‑`.ps`‑Datei zeigt. Dieser Stream liefert die von Aspose.Page erzeugten Binärdaten.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Schritt 3: Speicheroptionen erstellen
Instanziieren Sie `PsSaveOptions`. Sie können Seitengröße, Kompression usw. anpassen, aber die Vorgaben sind für dieses Beispiel ausreichend.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Schritt 4: PS‑Dokument erstellen
Erzeugen Sie das `PsDocument`‑Objekt und übergeben dabei den Ausgabestream sowie die Speicheroptionen. Das Flag `false` weist Aspose.Page an, nicht automatisch eine Seite zu öffnen (wir machen das manuell).

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Schritt 5: Einen Kreis erstellen
Wir zeichnen einen Kreis mit `Ellipse2D.Float`. Die Parameter sind `(x, y, width, height)`. Wenn Breite = Höhe gesetzt wird, entsteht ein perfekter Kreis.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Wie man einen Kreis mit Farbverlauf zeichnet
Jetzt, da wir eine Form haben, ist der nächste Schritt, **Kreis mit Farbverlauf zu zeichnen**. Durch das Anwenden eines `RadialGradientPaint` auf den Kreis wird die Fülloperation automatisch den von uns definierten Farbverlauf verwenden.

## Schritt 6: Farbverlauf‑Farben definieren
Bereiten Sie zwei Arrays vor: eines für die Farben, die im Farbverlauf erscheinen, und ein weiteres für die entsprechenden Bruchpositionen (0 = Mitte, 1 = Rand).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Schritt 7: AffineTransform erstellen
Der `AffineTransform` skaliert und verschiebt den Farbverlauf, damit er zu unserem Kreis passt. Die Matrix `(scaleX, 0, 0, scaleY, translateX, translateY)` erledigt diese Aufgabe.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Schritt 8: RadialGradientPaint erstellen
Jetzt erstellen wir das `RadialGradientPaint`‑Objekt. Es benötigt den Mittelpunkt, den Radius, den Fokus‑Punkt, die Farb‑Fraktionen, das Farb‑Array, die Zyklus‑Methode, den Farbraum und die zuvor definierte Transformation.

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

## Schritt 9: Paint setzen und Kreis füllen
Wenden Sie das Gradient‑Paint auf das Dokument an und füllen Sie den zuvor definierten Kreis. Dies ist der Kern unseres **radialen Farbverlauf‑Beispiels** und zeigt, wie man **Form mit Farbverlauf füllen** ausführt.

```java
document.setPaint(paint);
document.fill(circle);
```

## Schritt 10: Seite schließen und Dokument speichern
Schließen Sie die Seite ab, schreiben Sie den Inhalt auf die Festplatte und schließen Sie den Stream. Ihre PostScript‑Datei ist nun bereit, mit jedem PS‑Betrachter angezeigt zu werden.

```java
document.closePage();
document.save();
```

Herzlichen Glückwunsch! Sie haben erfolgreich ein Beispiel für einen radialen Farbverlauf in Java PostScript mit Aspose.Page erstellt. Sie verfügen nun über ein wiederverwendbares Muster für **Form mit Farbverlauf füllen**, das an andere Formen und Ausgabeformate angepasst werden kann.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|---------|----------|
| **FileNotFoundException** when opening the output stream | Überprüfen Sie, dass `dataDir` auf einen bestehenden Ordner zeigt und Sie Schreibrechte haben. |
| Gradient sieht flach aus oder fehlt | Stellen Sie sicher, dass das `fractions`‑Array mit der Länge des `colors`‑Arrays übereinstimmt und dass der `AffineTransform` korrekt skaliert. |
| Farben erscheinen invertiert | Vertauschen Sie die Reihenfolge der Farben im `colors`‑Array oder passen Sie die Koordinaten des `focus`‑Punkts an. |

## Häufig gestellte Fragen

**Q: Wo finde ich die Dokumentation für Aspose.Page für Java?**  
A: Die vollständige API‑Referenz ist [hier](https://reference.aspose.com/page/java/) verfügbar.

**Q: Wie kann ich Aspose.Page für Java herunterladen?**  
A: Laden Sie das neueste JAR von der [releases page](https://releases.aspose.com/page/java/) herunter.

**Q: Gibt es eine kostenlose Testversion?**  
A: Ja – laden Sie eine Testversion [hier](https://releases.aspose.com/) herunter.

**Q: Kann ich eine temporäre Lizenz für Tests erhalten?**  
A: Natürlich, beantragen Sie eine von der [temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: Wo kann ich Community‑Support erhalten?**  
A: Nehmen Sie an der Diskussion im [Aspose.Page forum](https://forum.aspose.com/c/page/39) teil.

## Fazit
In diesem Leitfaden haben wir ein vollständiges **radialen Farbverlauf‑Beispiel** für ein PostScript‑Dokument mit Aspose.Page für Java erstellt. Durch das Befolgen der Schritte besitzen Sie nun ein wiederverwendbares Muster für **Form mit Farbverlauf füllen**, das Sie an PDF, SVG oder jedes andere von Aspose.Page unterstützte Format anpassen können. Experimentieren Sie mit verschiedenen Farben, Radien und Formen, um Ihre Java‑Grafikprojekte zu bereichern.

---

**Last Updated:** 2026-02-13  
**Getestet mit:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}