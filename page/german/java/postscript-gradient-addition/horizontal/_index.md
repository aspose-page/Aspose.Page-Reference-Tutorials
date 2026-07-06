---
date: 2026-02-13
description: Erfahren Sie, wie Sie in Java PostScript einen Farbverlauf mit Linear Gradient Paint Java
  und Aspose.Page für Java hinzufügen.
linktitle: How to Add Gradient in Java PostScript with Linear Gradient Paint
second_title: Aspose.Page Java API
title: Wie man in Java PostScript einen Farbverlauf mit Linear Gradient Paint hinzufügt
url: /de/java/postscript-gradient-addition/horizontal/
weight: 11
---

 hinzu"

Second heading "## Introduction" -> "## Einführung"

Paragraph: translate.

Need to keep **bold** formatting.

Also keep code block placeholders unchanged.

Lists: bullet points.

Table: translate headers and content but keep pipe formatting.

FAQ: translate Q and A but keep links unchanged.

Make sure to keep URLs unchanged.

Also keep "Last Updated" etc.

Let's craft translation.

Be careful with "Linear Gradient Paint Java" keep as is? Technical term maybe keep English, but we can keep as is. The instruction: keep technical terms in English. So keep "Linear Gradient Paint Java". Also keep "Aspose.Page for Java". Keep "JDK". Keep "API". Keep "class". Keep "code block placeholders". So translate surrounding text.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# So fügen Sie einen Farbverlauf in Java PostScript mit Linear Gradient Paint hinzu

## Einführung
In diesem umfassenden Tutorial erfahren Sie **wie Sie einen Farbverlauf** zu einem PostScript‑Dokument mit Java hinzufügen. Wir zeigen Ihnen, wie Sie einen schönen horizontalen Farbverlauf erstellen, indem Sie **Linear Gradient Paint Java** nutzen, eine Klasse, die Ihnen pixelgenaue Kontrolle über Farbübergänge gibt. Mit Aspose.Page for Java können Sie Farbverläufe sowohl auf Formen **als auch** auf Text anwenden und Ihren Dokumenten ein poliertes, auffälliges Aussehen verleihen.

## Schnellantworten
- **Welche Bibliothek wird benötigt?** Aspose.Page for Java (unterstützt Linear Gradient Paint Java).  
- **Wie lange dauert die Implementierung?** Etwa 10‑15 Minuten für einen einfachen Farbverlauf.  
- **Benötige ich eine Lizenz?** Für den Produktionseinsatz ist eine temporäre oder vollständige Lizenz erforderlich.  
- **Welche JDK‑Version funktioniert?** Java 8 oder neuer.  
- **Kann ich den Farbverlauf sowohl auf Formen als auch auf Text anwenden?** Ja – Sie können Formen füllen und Text mit demselben Farbverlauf füllen oder umranden.

## Was ist ein horizontaler Farbverlauf und warum verwenden?
Ein horizontaler Farbverlauf mischt Farben sanft von links nach rechts über eine Form oder einen Text. Er eignet sich ideal für moderne UI‑Elemente, hervorgehobene Überschriften oder dezente Hintergrundeﬂekte in Berichten. Mit **Linear Gradient Paint Java** können Sie die genauen Start‑ und Endfarben, die Opazität und die Skalierung festlegen, sodass das Ergebnis auf jedem Gerät scharf aussieht.

## Voraussetzungen
Bevor Sie in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

- Java Development Kit (JDK) auf Ihrem Rechner installiert.  
- Aspose.Page for Java‑Bibliothek. Sie können sie aus der [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) herunterladen.

## Pakete importieren
Beginnen Sie damit, die notwendigen Pakete in Ihrem Java‑Projekt zu importieren. Diese Importe geben Ihnen Zugriff auf Grafik‑Primitive, Farbverlauf‑Verarbeitung und die Aspose.Page‑API.

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

## Schritt 1: Ein Rechteck erstellen
Richten Sie zunächst den Ausgabestream, das Dokument und ein Rechteck ein, das den Farbverlauf aufnehmen wird.

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

## Schritt 2: Horizontalen Linear Gradient Paint erstellen
Hier bauen wir das **Linear Gradient Paint Java**‑Objekt, das einen horizontalen Farbübergang definiert. Der `AffineTransform` skaliert den Farbverlauf, sodass er zur Breite und Höhe des Rechtecks passt.

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

## Schritt 3: Das Rechteck füllen
Füllen Sie nun das Rechteck mit dem gerade definierten Farbverlauf.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Schritt 4: Text mit dem Farbverlauf füllen
Sie können denselben Farbverlauf auch auf Text anwenden und so einen eindrucksvollen visuellen Effekt erzeugen.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Schritt 5: Text mit dem Farbverlauf umranden
Zum Schluss umranden Sie Text, wobei der Farbverlauf als Strichfarbe verwendet wird.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Häufige Probleme und Lösungen
| Problem | Warum es passiert | Lösung |
|-------|----------------|-----|
| Der Farbverlauf erscheint gestreckt | Falsche Skalierung im `AffineTransform` | Stellen Sie sicher, dass Breite und Höhe des Transforms den Rechtecks‑Abmessungen (200 × 100 im Beispiel) entsprechen. |
| Farben wirken verblasst | Alpha‑Werte zu niedrig gesetzt | Erhöhen Sie den Alpha‑Wert (den vierten Parameter in `new Color(r,g,b,alpha)`). |
| Text ist nicht sichtbar | Paint wurde nicht gesetzt, bevor Text gezeichnet wurde | Rufen Sie `document.setPaint(paint)` **vor** allen `fillAndStrokeText`‑ oder `outlineText`‑Aufrufen auf. |

## Häufig gestellte Fragen
**F:** Kann ich Aspose.Page for Java in kommerziellen Projekten verwenden?  
**A:** Ja, Aspose.Page for Java kann in kommerziellen Projekten eingesetzt werden. Lizenzdetails finden Sie unter [Aspose.Purchase](https://purchase.aspose.com/buy).

**F:** Gibt es eine kostenlose Testversion?  
**A:** Ja, Sie können eine kostenlose Testversion von Aspose.Page for Java [hier](https://releases.aspose.com/) erhalten.

**F:** Wo finde ich weitere Dokumentation und Support?  
**A:** Besuchen Sie die [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) für umfassende Ressourcen. Für Community‑Support schauen Sie im [Aspose.Page forum](https://forum.aspose.com/c/page/39) nach.

**F:** Wie kann ich eine temporäre Lizenz erhalten?  
**A:** Eine temporäre Lizenz erhalten Sie über [Aspose.Purchase](https://purchase.aspose.com/temporary-license/).

**F:** Was sind die Systemanforderungen für Aspose.Page for Java?  
**A:** Die detaillierten Systemanforderungen finden Sie in der [Dokumentation](https://reference.aspose.com/page/java/).

---

**Zuletzt aktualisiert:** 2026-02-13  
**Getestet mit:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}