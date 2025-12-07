---
date: 2025-12-07
description: Erfahren Sie, wie Sie ein Rechteck skalieren, eine Form verschieben und
  eine affine Transformation in Java mit Aspose.Page anwenden, um PostScript‑Dokumente
  zu erstellen.
language: de
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Wie man ein Rechteck skaliert und Transformationen mit Aspose.Page anwendet
url: /java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Rechtecke skaliert und Transformationen mit Aspose.Page anwendet

## Einleitung
Willkommen zu einem umfassenden Leitfaden zur Nutzung der leistungsstarken Funktionen von **Aspose.Page for Java**, um eine Vielzahl von Seiten‑Transformationen durchzuführen. In diesem Tutorial lernen Sie **how to scale rectangle**, Formen zu verschieben, Objekte zu drehen und **apply affine transform**‑Techniken beim Erstellen eines **PostScript document** anzuwenden. Diese Möglichkeiten ermöglichen es Ihnen, reichhaltige, grafikintensive Java‑Anwendungen zu bauen, ohne sich mit Low‑Level‑Rendering‑Code befassen zu müssen.

## Schnelle Antworten
- **Wie skaliere ich ein Rechteck in Java mit Aspose.Page?** Verwenden Sie die Methode `document.scale()` bevor Sie die Form zeichnen.  
- **Kann ich eine Form (translate) verschieben, ohne andere Grafiken zu beeinflussen?** Ja – speichern Sie den Grafik‑Zustand, rufen Sie `document.translate(x, y)` auf, zeichnen Sie und stellen Sie dann den Zustand wieder her.  
- **Welche Klasse erstellt eine PostScript‑Datei?** `PsDocument` zusammen mit `PsSaveOptions`.  
- **Benötige ich eine Lizenz für den Produktionseinsatz?** Eine gültige Aspose.Page‑Lizenz ist für kommerzielle Deployments erforderlich.  
- **Welche Java‑Version wird unterstützt?** Aspose.Page funktioniert mit Java 8 und höher.

## Voraussetzungen
Bevor wir in die Schritt‑für‑Schritt‑Anleitung eintauchen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:

- Grundlegende Kenntnisse in der Java‑Programmierung.  
- Aspose.Page for Java‑Bibliothek installiert. Sie können sie aus der [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) herunterladen.  
- Eine Java‑Entwicklungsumgebung (IDE) auf Ihrem Rechner eingerichtet.

## Pakete importieren
In Ihrem Java‑Projekt importieren Sie die notwendigen Pakete, um Aspose.Page for Java zu nutzen:

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Was bedeutet „how to scale rectangle“ in Aspose.Page?
Das Skalieren eines Rechtecks ändert seine Größe entlang der X‑ und Y‑Achsen, während die Form erhalten bleibt. Aspose.Page stellt die Methode `scale(float sx, float sy)` bereit, die einen **affine transform** auf den aktuellen Grafik‑Zustand anwendet. Dies ist die Kerntechnik hinter dem Schlüsselwort **how to scale rectangle**.

## Wie man Formen mit Aspose.Page verschiebt
Das Verschieben (Translation) einer Form ändert ihre Position, ohne ihre Abmessungen zu verändern. Das ist das Wesentliche von **how to translate shape**. Indem Sie den Grafik‑Zustand speichern, `translate(dx, dy)` anwenden, die Form zeichnen und anschließend den Zustand wiederherstellen, bleiben andere Objekte unbeeinflusst.

## Beispiel 1: Keine Transformationen
Das erste Beispiel zeichnet ein einfaches Rechteck ohne angewandte Transformation. Dies dient als Basislinie für den Vergleich mit späteren Beispielen.

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
Hier demonstrieren wir **how to translate shape**, indem wir den Grafik‑Kontext um 250 Einheiten nach rechts verschieben, bevor wir ein zweites Rechteck zeichnen.

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
Dieses Beispiel beantwortet die zentrale Frage **how to scale rectangle**. Wir verkleinern das Rechteck auf 50 % seiner ursprünglichen Breite und 75 % seiner ursprünglichen Höhe.

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
Rotation ist eine weitere gängige affine Operation. Während die Code‑Snippets für die Rotation aus Gründen der Kürze weggelassen wurden, ist das Muster identisch: Grafik‑Zustand speichern, `document.rotate(angle)` aufrufen, die Form zeichnen und anschließend den Zustand wiederherstellen. Dies demonstriert **rotate shape java** und **how to rotate rectangle** in der Praxis.

## Warum Aspose.Page für diese Transformationen verwenden?
- **Device‑independent**: Geräteunabhängig – einmal schreiben, PostScript oder XPS ohne plattformspezifischen Code erzeugen.  
- **Fine‑grained control**: Feinkörnige Kontrolle – direkter Zugriff auf den Grafik‑Zustand ermöglicht die Kombination von Translation, Skalierung, Scherung und Rotation.  
- **Performance**: Leistung – API mit geringem Overhead, geeignet für die Stapelverarbeitung großer Dokumente.  

## Häufige Anwendungsfälle
- Erstellung druckbarer Rechnungen mit dynamischen Barcodes und Logos.  
- Erstellung technischer Diagramme, bei denen präzise Skalierung und Positionierung erforderlich sind.  
- Automatisierung der Erstellung mehrseitiger Berichte im PostScript‑Format.

## Fazit
In diesem Tutorial haben wir verschiedene Transformationen in der Java‑Seitenmanipulation mit Aspose.Page for Java untersucht, wobei wir uns auf **how to scale rectangle**, **how to translate shape** und weitere affine Operationen konzentriert haben. Durch das Befolgen dieser Beispiele können Sie Ihre Java‑Anwendungen mit fortgeschrittenen Seitenmanipulations‑Funktionen erweitern und **create PostScript document**‑Ausgaben erzeugen, die professionellen Veröffentlichungsstandards entsprechen.

## FAQ
### Kann ich Aspose.Page for Java für andere Dokumentformate verwenden?
Aspose.Page konzentriert sich hauptsächlich auf die Seitenmanipulation für PostScript‑ und XPS‑Formate.

### Wo finde ich weitere Beispiele und Dokumentation für Aspose.Page for Java?
Besuchen Sie die [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) für umfassende Informationen.

### Gibt es eine kostenlose Testversion von Aspose.Page for Java?
Ja, Sie können eine kostenlose Testversion [hier](https://releases.aspose.com/) erhalten.

### Wie kann ich eine temporäre Lizenz für Aspose.Page for Java erhalten?
Erhalten Sie eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/).

### Wo kann ich Community‑Support erhalten oder Fragen zu Aspose.Page for Java stellen?
Besuchen Sie das [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) für Community‑Diskussionen.

## Häufig gestellte Fragen

**Q: Was ist der Unterschied zwischen `translate` und `scale`?**  
A: `translate` verschiebt den Ursprung des Koordinatensystems, während `scale` die Größe gezeichneter Objekte entlang der X‑ und/oder Y‑Achse ändert.

**Q: Kann ich mehrere Transformationen in einem einzigen Grafik‑Zustand kombinieren?**  
A: Ja – indem Sie `translate`, `scale`, `rotate` oder `shear` nacheinander vor dem Zeichnen aufrufen, erzeugen Sie eine kombinierte affine Transformation.

**Q: Wie setze ich Transformationen nach dem Zeichnen einer Form zurück?**  
A: Verwenden Sie `document.writeGraphicsRestore()`, um zum zuvor gespeicherten Grafik‑Zustand zurückzukehren.

**Q: Ist es möglich, ein Rechteck um sein Zentrum zu drehen?**  
A: Absolut. Verschieben Sie das Rechteck zum Ursprung, wenden Sie `rotate(angle)` an und verschieben Sie es anschließend zurück, bevor Sie es zeichnen.

**Q: Unterstützt Aspose.Page Anti‑Aliasing für glattere Grafiken?**  
A: Ja – setzen Sie die entsprechenden Rendering‑Optionen in `PsSaveOptions`, um Anti‑Aliasing zu aktivieren.

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Page for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}