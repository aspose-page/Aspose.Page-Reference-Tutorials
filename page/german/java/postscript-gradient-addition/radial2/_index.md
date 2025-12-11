---
date: 2025-12-08
description: Erfahren Sie, wie Sie ein Beispiel für einen radialen Farbverlauf in
  Java PostScript mit Aspose.Page erstellen. Schritt‑für‑Schritt‑Anleitung mit vollständigem
  Code und Fehlersuche.
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 'Beispiel für radialen Farbverlauf: Java PostScript mit Aspose.Page'
url: /de/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Radial Gradient Beispiel: Java PostScript mit Aspose.Page

## Einleitung
In diesem Tutorial erstellen Sie ein **Radial Gradient Beispiel** für ein PostScript‑Dokument mit Aspose.Page für Java. Wir führen Sie Schritt für Schritt durch den gesamten Prozess – von der Einrichtung des Projekts bis zum Rendern eines Kreises, der mit einem sanften radialen Farbverlauf gefüllt ist – damit Sie sofort auffällige Grafiken zu Ihren Java‑Anwendungen hinzufügen können.

## Schnelle Antworten
- **Was erstellt dieses Tutorial?** Eine PostScript‑Datei (`.ps`) mit einem Kreis, der einen radialen Farbverlauf enthält.  
- **Welche Bibliothek wird benötigt?** Aspose.Page für Java (neueste Version).  
- **Wie lange dauert die Implementierung?** Etwa 10‑15 Minuten für ein funktionierendes Beispiel.  
- **Benötige ich eine Lizenz?** Für den Produktionseinsatz ist eine temporäre oder vollständige Lizenz erforderlich; eine kostenlose Testversion funktioniert für die Entwicklung.  
- **Kann ich den Code für PDF oder SVG wiederverwenden?** Ja – Aspose.Page unterstützt mehrere Ausgabeformate mit minimalen Änderungen.

## Was ist ein Radial Gradient?
Ein Radial Gradient überträgt Farben von einem zentralen Punkt nach außen und erzeugt dabei einen weichen, kreisförmigen Übergang. Er eignet sich ideal für Highlights, Button‑Hintergründe oder jede visuelle Darstellung, die einen natürlichen „Leuchteffekt“ benötigt.

## Warum Aspose.Page für Radial Gradients verwenden?
- **Geräteunabhängiges Rendering** – funktioniert identisch auf PostScript, PDF, SVG und mehr.  
- **Vollständige Java‑Integration** – kein nativer Code, nur reine Java‑APIs.  
- **Hochwertige Ausgabe** – unterstützt Anti‑Aliasing und Farb‑Raum‑Kontrolle.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Grundlegende Kenntnisse in der Java‑Programmierung.  
- JDK 8 oder neuer auf Ihrem Rechner installiert.  
- Aspose.Page für Java Bibliothek (Download von der [Aspose.Page Java‑Dokumentation](https://reference.aspose.com/page/java/)).  

## Pakete importieren
Zuerst importieren wir die Klassen, die wir benötigen. Dazu gehören Standard‑AWT‑Grafiktypen und die Aspose.Page‑API.

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
Öffnen Sie einen `FileOutputStream`, der auf die Ziel‑`.ps`‑Datei zeigt. Dieser Stream liefert die von Aspose.Page erzeugten Binärdaten.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Schritt 3: Speicheroptionen erstellen
Instanziieren Sie `PsSaveOptions`. Sie können Seitengröße, Kompression usw. anpassen, aber die Vorgaben reichen für dieses Beispiel aus.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Schritt 4: PS-Dokument erstellen
Erzeugen Sie das `PsDocument`‑Objekt und übergeben Sie den Ausgabestream sowie die Speicheroptionen. Das Flag `false` weist Aspose.Page an, nicht automatisch eine Seite zu öffnen (wir erledigen das manuell).

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Schritt 5: Einen Kreis erstellen
Wir zeichnen einen Kreis mit `Ellipse2D.Float`. Die Parameter sind `(x, y, width, height)`. Durch Setzen von `width = height` entsteht ein perfekter Kreis.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Schritt 6: Gradient‑Farben definieren
Bereiten Sie zwei Arrays vor: eines für die Farben, die im Gradient erscheinen, und ein weiteres für die entsprechenden Bruchstellen (0 = Mitte, 1 = Rand).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Schritt 7: AffineTransform erstellen
Der `AffineTransform` skaliert und verschiebt den Gradient, sodass er in unseren Kreis passt. Die Matrix `(scaleX, 0, 0, scaleY, translateX, translateY)` erledigt diese Aufgabe.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Schritt 8: Radial Gradient Paint erstellen
Jetzt bauen wir das `RadialGradientPaint`‑Objekt. Es erhält den Mittelpunkt, den Radius, den Fokuspunkt, die Farb‑Bruchstellen, das Farb‑Array, die Zyklus‑Methode, den Farbraum und den zuvor definierten Transform.

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
Wenden Sie das Gradient‑Paint auf das Dokument an und füllen Sie den zuvor definierten Kreis. Dies ist der Kern unseres **Radial Gradient Beispiels**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Schritt 10: Seite schließen und Dokument speichern
Schließen Sie die Seite, schreiben Sie den Inhalt auf die Festplatte und schließen Sie den Stream. Ihre PostScript‑Datei ist nun bereit, mit jedem PS‑Viewer angezeigt zu werden.

```java
document.closePage();
document.save();
```

Herzlichen Glückwunsch! Sie haben erfolgreich ein Radial Gradient Beispiel in Java PostScript mit Aspose.Page erstellt.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|---------|--------|
| **FileNotFoundException** beim Öffnen des Ausgabestreams | Stellen Sie sicher, dass `dataDir` auf einen vorhandenen Ordner zeigt und Sie Schreibrechte besitzen. |
| Gradient sieht flach aus oder fehlt | Stellen Sie sicher, dass das `fractions`‑Array die gleiche Länge wie das `colors`‑Array hat und dass der `AffineTransform` korrekt skaliert. |
| Farben erscheinen invertiert | Vertauschen Sie die Reihenfolge der Farben im `colors`‑Array oder passen Sie die Koordinaten des `focus`‑Punktes an. |

## Häufig gestellte Fragen

**Q: Wo finde ich die Dokumentation für Aspose.Page für Java?**  
A: Die vollständige API‑Referenz ist [hier](https://reference.aspose.com/page/java/) verfügbar.

**Q: Wie kann ich Aspose.Page für Java herunterladen?**  
A: Laden Sie das neueste JAR von der [Releases‑Seite](https://releases.aspose.com/page/java/) herunter.

**Q: Gibt es eine kostenlose Testversion?**  
A: Ja – laden Sie eine Testversion [hier](https://releases.aspose.com/) herunter.

**Q: Kann ich eine temporäre Lizenz für Tests erhalten?**  
A: Natürlich, beantragen Sie eine von der [temporären Lizenzseite](https://purchase.aspose.com/temporary-license/).

**Q: Wo finde ich Community‑Support?**  
A: Nehmen Sie an der Diskussion im [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39) teil.

## Fazit
In diesem Leitfaden haben wir ein vollständiges **Radial Gradient Beispiel** für ein PostScript‑Dokument mit Aspose.Page für Java erstellt. Durch Befolgen der Schritte besitzen Sie nun ein wiederverwendbares Muster zur Erstellung anspruchsvoller Verläufe, das Sie leicht auf PDF, SVG oder andere unterstützte Formate übertragen können. Experimentieren Sie mit unterschiedlichen Farben, Radien und Formen, um Ihre Java‑Grafikprojekte zu bereichern.

---

**Last Updated:** 2025-12-08  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}