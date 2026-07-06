---
date: 2026-02-13
description: Erfahren Sie, wie Sie in Java mit Aspose.Page einen PostScript‑Verlauf
  erstellen. Diese Schritt‑für‑Schritt‑Anleitung zeigt Ihnen, wie Sie mühelos einen
  vertikalen Verlauf zu Ihren PostScript‑Dokumenten hinzufügen.
linktitle: Add Vertical Gradient in Java PostScript
second_title: Aspose.Page Java API
title: PostScript-Gradient in Java erstellen – Vertikalen Gradient hinzufügen
url: /de/java/postscript-gradient-addition/vertical/
weight: 14
---

.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PostScript‑Verlauf in Java erstellen – Vertikalen Verlauf hinzufügen

## Einleitung
In diesem umfassenden Tutorial lernen Sie, wie Sie **einen PostScript‑Verlauf in Java** mit Aspose.Page für Java erstellen. Das Hinzufügen eines vertikalen Verlaufs kann Ihre Dokumente lebendiger und professioneller wirken lassen, und mit nur wenigen Codezeilen erzielen Sie beeindruckende visuelle Effekte. Wir führen Sie Schritt für Schritt durch den Prozess, erklären, warum jedes Detail wichtig ist, und geben Ihnen praktische Tipps, um häufige Fallstricke zu vermeiden. Am Ende dieses Leitfadens können Sie PostScript‑Dateien erzeugen, die sanfte, auffällige vertikale Farbverläufe enthalten.

## Schnelle Antworten
- **Welche Bibliothek wird benötigt?** Aspose.Page für Java  
- **Kann ich Farben anpassen?** Ja, jedes `java.awt.Color` kann verwendet werden  
- **Wird Rotation unterstützt?** Ja, Sie können den Verlauf mit einem `AffineTransform` rotieren  
- **Welches Ausgabeformat wird erzeugt?** Eine standardmäßige PostScript‑Datei (.ps)  
- **Benötige ich eine Lizenz für die Produktion?** Ja, eine kommerzielle Lizenz ist erforderlich  

## Warum einen vertikalen Verlauf zu einem PostScript‑Dokument hinzufügen?
Vertikale Verläufe verleihen Ihren Seiten Tiefe, ohne die Dateigröße zu erhöhen. Sie sind ideal für:

* Kopf‑ oder Fußzeilen von Berichten, die einen dezenten Hintergrund benötigen.  
* Hervorhebung von Abschnitten in technischen Handbüchern oder White‑Papers.  
* Moderne Optik für Diagramme, Grafiken oder Werbeflyer.

Da der Verlauf vektorbasiert definiert ist, bleibt die Ausgabe bei jeder Auflösung scharf.

## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:
- Java Development Kit (JDK) auf Ihrem Rechner installiert.  
- Aspose.Page für Java‑Bibliothek. Sie können sie [hier](https://releases.aspose.com/page/java/) herunterladen.

## Pakete importieren
Importieren Sie in Ihrem Java‑Projekt die notwendigen Pakete, um loszulegen:
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

Jetzt gehen wir den Prozess des Hinzufügens eines vertikalen Verlaufs Schritt für Schritt durch.

## Wie man einen PostScript‑Verlauf in Java erstellt
Im Folgenden finden Sie eine Schritt‑für‑Schritt‑Anleitung, die genau zeigt, wie Sie **einen PostScript‑Verlauf in Java** mit der Aspose.Page‑API erstellen.

### Schritt 1: Richten Sie Ihr Dokumentenverzeichnis ein
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Schritt 2: Erstellen Sie einen Ausgabestream für das PostScript‑Dokument
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### Schritt 3: Erstellen Sie Speicheroptionen mit A4‑Größe
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### Schritt 4: Erstellen Sie ein neues PS‑Dokument
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Schritt 5: Erstellen Sie ein Rechteck
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### Schritt 6: Richten Sie Farben und Bruchteile für den Verlauf ein
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### Schritt 7: Erstellen Sie die Verlaufstransformation
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### Schritt 8: Erstellen Sie ein vertikales lineares Gradient‑Paint
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### Schritt 9: Setzen Sie das Paint und füllen Sie das Rechteck
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### Schritt 10: Schließen Sie die aktuelle Seite und speichern Sie das Dokument
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Herzlichen Glückwunsch! Sie haben erfolgreich einen vertikalen Verlauf zu Ihrem Java‑PostScript‑Dokument mit Aspose.Page für Java hinzugefügt.

## Häufige Probleme und Lösungen
- **Verlauf erscheint flach:** Stellen Sie sicher, dass die Skalierung des `AffineTransform` den Rechteckabmessungen entspricht.  
- **Farben wirken ausgewaschen:** Vergewissern Sie sich, dass Sie den richtigen `ColorSpaceType` (SRGB) verwenden und das Bruchteils‑Array von 0,0 bis 1,0 sortiert ist.  
- **Datei wird nicht erzeugt:** Prüfen Sie, ob das Ausgabeverzeichnis (`dataDir`) existiert und die Anwendung Schreibrechte hat.  

## Häufig gestellte Fragen
### Kann ich Aspose.Page für Java mit anderen Java‑Bibliotheken verwenden?
Ja, Aspose.Page für Java ist so konzipiert, dass es nahtlos mit anderen Java‑Bibliotheken zusammenarbeitet.

### Gibt es eine kostenlose Testversion für Aspose.Page für Java?
Ja, Sie können eine kostenlose Testversion [hier](https://releases.aspose.com/) erhalten.

### Wo finde ich zusätzliche Dokumentation?
Detaillierte Dokumentation ist [hier](https://reference.aspose.com/page/java/) verfügbar.

### Wie kann ich Aspose.Page für Java erwerben?
Sie können Aspose.Page für Java [hier](https://purchase.aspose.com/buy) kaufen.

### Gibt es ein Forum für Aspose.Page‑Diskussionen?
Ja, Sie können dem Community‑Forum [hier](https://forum.aspose.com/c/page/39) beitreten.

## Zusätzliche häufig gestellte Fragen

**Q: Kann ich andere Verlaufsrichtungen (horizontal, diagonal) erstellen?**  
A: Absolut. Passen Sie die Start‑ und Endpunkte in `LinearGradientPaint` an und ändern Sie den Rotationswinkel im `AffineTransform`.

**Q: Funktioniert das auch mit PDF‑Ausgabe?**  
A: Die gleiche Verlauf‑Logik kann angewendet werden, wenn Sie mit `PdfSaveOptions` anstelle von `PsSaveOptions` speichern.

**Q: Wie ändere ich die Größe des Verlaufs dynamisch?**  
A: Berechnen Sie die Rechteckabmessungen zur Laufzeit und übergeben Sie diese Werte sowohl an `Rectangle2D` als auch an den Konstruktor von `AffineTransform`.

---

**Zuletzt aktualisiert:** 2026-02-13  
**Getestet mit:** Aspose.Page für Java 24.11 (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}