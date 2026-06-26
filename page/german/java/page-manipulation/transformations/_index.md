---
date: 2026-02-07
description: Erfahren Sie, wie Sie ein Rechteck mit Aspose.Page für Java skalieren,
  wie Sie eine Form verschieben und eine affine Transformation anwenden, um PostScript‑Dokumente
  zu erstellen.
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Wie man ein Rechteck mit Aspose.Page für Java skaliert
url: /de/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man ein Rechteck mit Aspose.Page für Java skaliert

## Einleitung
Willkommen zu einem umfassenden Leitfaden zur Nutzung der leistungsstarken Funktionen von **Aspose.Page for Java**, um eine Vielzahl von Seiten‑transformationen durchzuführen. In diesem Tutorial lernen Sie **how to scale rectangle**, Formen zu verschieben, Objekte zu drehen und **apply affine transform**‑Techniken beim Erstellen eines **PostScript document**. Diese Möglichkeiten ermöglichen es Ihnen, reichhaltige, grafikintensive Java‑Anwendungen zu erstellen, ohne sich mit Low‑Level‑Rendering‑Code befassen zu müssen.

## Kurze Antworten
- **Wie skaliere ich ein Rechteck in Java mit Aspose.Page?** Verwenden Sie die Methode `document.scale()` bevor Sie die Form zeichnen.  
- **Kann ich eine Form (verschieben) bewegen, ohne andere Grafiken zu beeinflussen?** Ja – speichern Sie den Grafik‑Zustand, rufen Sie `document.translate(x, y)` auf, zeichnen Sie und stellen Sie dann den Zustand wieder her.  
- **Welche Klasse erstellt eine PostScript‑Datei?** `PsDocument` zusammen mit `PsSaveOptions`.  
- **Benötige ich eine Lizenz für den Produktionseinsatz?** Eine gültige Aspose.Page‑Lizenz ist für kommerzielle Bereitstellungen erforderlich.  
- **Welche Java‑Version wird unterstützt?** Aspose.Page funktioniert mit Java 8 und höher.

## Voraussetzungen
Bevor wir in die Schritt‑für‑Schritt‑Anleitung eintauchen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:

- Grundlegende Kenntnisse in der Java‑Programmierung.  
- Aspose.Page for Java Bibliothek installiert. Sie können sie von der [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) herunterladen.  
- Eine Java Integrated Development Environment (IDE) auf Ihrem Rechner eingerichtet.

## Pakete importieren
Importieren Sie in Ihrem Java‑Projekt die erforderlichen Pakete, um Aspose.Page für Java zu nutzen:

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Was bedeutet “how to scale rectangle” in Aspose.Page?
Das Skalieren eines Rechtecks ändert seine Größe entlang der X‑ und Y‑Achsen, während die Form erhalten bleibt. Aspose.Page stellt die Methode `scale(float sx, float sy)` bereit, die eine **affine transform** auf den aktuellen Grafik‑Zustand anwendet. Dies ist die Kern­technik hinter dem Schlüsselwort **how to scale rectangle**.

## Wie man eine Form mit Aspose.Page verschiebt
Das Verschieben (Translation) bewegt eine Form an einen neuen Ort, ohne ihre Abmessungen zu ändern. Das ist das Wesentliche von **how to translate shape**. Indem Sie den Grafik‑Zustand speichern, `translate(dx, dy)` anwenden, zeichnen und anschließend den Zustand wiederherstellen, bleiben andere Objekte unbeeinflusst.

## Beispiel 1: Keine Transformationen
Das erste Beispiel zeichnet ein einfaches Rechteck ohne angewandte Transformation. Dies dient als Basis für den Vergleich mit späteren Beispielen.

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
Hier demonstrieren wir **how to translate shape**, indem wir den Grafik‑Kontext 250 Einheiten nach rechts verschieben, bevor wir ein zweites Rechteck zeichnen.

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
Dieses Beispiel beantwortet die Hauptfrage **how to scale rectangle**. Wir verkleinern das Rechteck auf 50 % seiner ursprünglichen Breite und 75 % seiner Höhe.

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

## Wie man eine Form in Java rotiert (rotate shape java)
Rotation ist eine weitere gängige affine Operation. Während die Code‑Snippets für die Rotation aus Gründen der Kürze weggelassen werden, ist das Muster identisch: Grafik‑Zustand speichern, `document.rotate(angle)` aufrufen, die Form zeichnen und anschließend wiederherstellen. Dies demonstriert **rotate shape java** und **how to rotate rectangle** in der Praxis.

## Warum das wichtig ist – Praktische Vorteile
- **Geräteunabhängige Ausgabe** – Einmal schreiben und PostScript oder XPS ohne plattformspezifische Anpassungen erzeugen.  
- **Feinkörnige Kontrolle** – Translation, Skalierung, Scherung und Rotation kombinieren, um genaue Layout‑Anforderungen zu erfüllen.  
- **Leistungsorientiert** – API mit geringem Overhead, ideal für die Stapelverarbeitung großer Dokumente.  

## Typische Anwendungsfälle
- Erstellung druckbarer Rechnungen – zum Beispiel eine **printable invoice java**‑Lösung, die Logos und Barcodes präzise platziert.  
- Erstellung technischer Diagramme, bei denen präzises Skalieren und Positionieren erforderlich ist.  
- Automatisierung der Erstellung mehrseitiger Berichte im PostScript‑Format.  

## Typische Probleme und Lösungen
- **Transformation wird nicht zurückgesetzt** – Kombinieren Sie stets `document.writeGraphicsSave()` mit `document.writeGraphicsRestore()`, um unerwünschte Übertragungseffekte zu vermeiden.  
- **Unerwartete Farben** – Stellen Sie sicher, dass Sie die Farbe nach jeder Transformation setzen; der Grafik‑Zustand behält nach einem Restore nicht die vorherigen Farbeinstellungen.  
- **Dateigröße zu groß** – Verwenden Sie `PsSaveOptions`, um Kompression zu aktivieren oder die Bildauflösung zu reduzieren, wenn Rastergrafiken eingebettet werden.  

## FAQ's
### Kann ich Aspose.Page für Java für andere Dokumentformate verwenden?
Aspose.Page konzentriert sich hauptsächlich auf die Seitenmanipulation für PostScript‑ und XPS‑Formate.

### Wo finde ich weitere Beispiele und Dokumentation für Aspose.Page für Java?
Besuchen Sie die [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) für umfassende Informationen.

### Gibt es eine kostenlose Testversion für Aspose.Page für Java?
Ja, Sie können eine kostenlose Testversion [hier](https://releases.aspose.com/) erhalten.

### Wie kann ich eine temporäre Lizenz für Aspose.Page für Java erhalten?
Erhalten Sie eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/).

### Wo kann ich Community‑Support erhalten oder Fragen zu Aspose.Page für Java stellen?
Besuchen Sie das [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) für Community‑Diskussionen.

## Frequently Asked Questions

**Q: Was ist der Unterschied zwischen `translate` und `scale`?**  
A: `translate` verschiebt den Ursprung des Koordinatensystems, während `scale` die Größe der gezeichneten Objekte entlang der X‑ und/oder Y‑Achsen ändert.

**Q: Kann ich mehrere Transformationen in einem einzigen Grafik‑Zustand kombinieren?**  
A: Ja – indem Sie `translate`, `scale`, `rotate` oder `shear` nacheinander vor dem Zeichnen aufrufen, erzeugen Sie eine kombinierte affine Transformation.

**Q: Wie setze ich Transformationen zurück, nachdem ich eine Form gezeichnet habe?**  
A: Verwenden Sie `document.writeGraphicsRestore()`, um zum zuvor gespeicherten Grafik‑Zustand zurückzukehren.

**Q: Ist es möglich, ein Rechteck um seine Mitte zu rotieren?**  
A: Ja, definitiv. Verschieben Sie das Rechteck zum Ursprung, wenden Sie `rotate(angle)` an und verschieben Sie es anschließend wieder zurück, bevor Sie es zeichnen.

**Q: Unterstützt Aspose.Page Anti‑Aliasing für glattere Grafiken?**  
A: Ja – setzen Sie die entsprechenden Rendering‑Optionen in `PsSaveOptions`, um Anti‑Aliasing zu aktivieren.

---

**Zuletzt aktualisiert:** 2026-02-07  
**Getestet mit:** Aspose.Page for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}