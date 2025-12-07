---
date: 2025-12-07
description: Erfahren Sie, wie Sie in Java PostScript einen horizontalen Farbverlauf
  mit Linear Gradient Paint Java und Aspose.Page für Java hinzufügen.
language: de
linktitle: Add Gradient in Java PostScript using Linear Gradient Paint Java
second_title: Aspose.Page Java API
title: Verlauf in Java PostScript mit Linear‑Gradient‑Paint hinzufügen
url: /java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Verlauf in Java PostScript mit Linear Gradient Paint Java hinzufügen

## Einführung
In diesem umfassenden Tutorial erfahren Sie, wie Sie einen schönen horizontalen Verlauf in einem PostScript-Dokument erstellen, indem Sie **Linear Gradient Paint Java** nutzen. Aspose.Page for Java erleichtert die Arbeit mit PostScript, PDF und anderen Vektorformaten, und die Klasse `LinearGradientPaint` bietet Ihnen eine feinkörnige Kontrolle über Farbübergänge. Am Ende dieses Leitfadens können Sie Verläufe auf Formen **und** Text rendern, wodurch Ihre Dokumente ein professionelles, auffälliges Aussehen erhalten.

## Schnelle Antworten
- **Welche Bibliothek wird benötigt?** Aspose.Page for Java (unterstützt Linear Gradient Paint Java).  
- **Wie lange dauert die Implementierung?** Etwa 10‑15 Minuten für einen einfachen Verlauf.  
- **Benötige ich eine Lizenz?** Für den Produktionseinsatz ist eine temporäre oder vollständige Lizenz erforderlich.  
- **Welche JDK-Version funktioniert?** Java 8 oder neuer.  
- **Kann ich den Verlauf sowohl für Formen als auch für Text verwenden?** Ja – Sie können Formen füllen und Text mit demselben Verlauf umranden oder füllen.

## Voraussetzungen
Bevor Sie in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

- Java Development Kit (JDK) auf Ihrem Rechner installiert.  
- Aspose.Page for Java Bibliothek. Sie können sie von der [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) herunterladen.

## Pakete importieren
Beginnen Sie damit, die erforderlichen Pakete in Ihrem Java-Projekt zu importieren. Diese Importe geben Ihnen Zugriff auf Grafikprimitive, Verlaufshandhabung und die Aspose.Page API.

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

## Schritt 1: Ein Rechteck erstellen
Zuerst richten Sie den Ausgabestream, das Dokument und ein Rechteck ein, das den Verlauf enthält.

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

## Schritt 2: Horizontalen Linear Gradient Paint erstellen
Hier erstellen wir das **Linear Gradient Paint Java** Objekt, das einen horizontalen Farbverlauf definiert. Der `AffineTransform` skaliert den Verlauf, um die Breite und Höhe des Rechtecks anzupassen.

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

## Schritt 3: Das Rechteck füllen
Füllen Sie nun das Rechteck mit dem gerade definierten Verlauf.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Schritt 4: Text mit dem Verlauf füllen
Sie können denselben Verlauf auch auf Text anwenden und damit einen eindrucksvollen visuellen Effekt erzeugen.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Schritt 5: Text mit dem Verlauf umranden
Abschließend umranden Sie Text, wobei Sie den Verlauf als Strichfarbe verwenden.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Häufige Probleme und Lösungen
| Problem | Warum es passiert | Lösung |
|---------|-------------------|--------|
| Verlauf erscheint gestreckt | Falsche Skalierung des `AffineTransform` | Stellen Sie sicher, dass die Breite und Höhe der Transformation den Abmessungen des Rechtecks entsprechen (200 × 100 im Beispiel). |
| Farben wirken verblasst | Alpha-Werte zu niedrig eingestellt | Erhöhen Sie die Alpha-Komponente (den vierten Wert in `new Color(r,g,b,alpha)`). |
| Text ist nicht sichtbar | Paint nicht gesetzt, bevor Text gezeichnet wird | Rufen Sie `document.setPaint(paint)` **vor** allen Aufrufen von `fillAndStrokeText` oder `outlineText` auf. |

## Häufig gestellte Fragen
### Kann ich Aspose.Page for Java in kommerziellen Projekten verwenden?
Ja, Aspose.Page for Java kann in kommerziellen Projekten verwendet werden. Für Lizenzdetails besuchen Sie [Aspose.Purchase](https://purchase.aspose.com/buy).

### Gibt es eine kostenlose Testversion?
Ja, Sie können eine kostenlose Testversion von Aspose.Page for Java [hier](https://releases.aspose.com/) erhalten.

### Wo finde ich zusätzliche Dokumentation und Support?
Besuchen Sie die [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) für umfassende Ressourcen. Für Community‑Support schauen Sie im [Aspose.Page forum](https://forum.aspose.com/c/page/39) nach.

### Wie kann ich eine temporäre Lizenz erhalten?
Sie können eine temporäre Lizenz von [Aspose.Purchase](https://purchase.aspose.com/temporary-license/) erhalten.

### Was sind die Systemanforderungen für Aspose.Page for Java?
Siehe die [documentation](https://reference.aspose.com/page/java/) für detaillierte Systemanforderungen.

---

**Zuletzt aktualisiert:** 2025-12-07  
**Getestet mit:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}