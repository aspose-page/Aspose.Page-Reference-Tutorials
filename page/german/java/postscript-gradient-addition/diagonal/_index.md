---
date: 2026-02-13
description: Verbessern Sie Ihre Java‑PostScript‑Dokumente mit diagonalen Verläufen
  mithilfe von Aspose.Page Java. Erfahren Sie, wie Sie mit LinearGradientPaint in
  Java Farbeffekte hinzufügen und mühelos lebendige Farbverläufe erstellen.
linktitle: 'How to Add Gradient: Diagonal Gradient in Java PostScript using Aspose.Page
  Java'
second_title: Aspose.Page Java API
title: 'So fügen Sie einen Farbverlauf hinzu: Diagonaler Farbverlauf in Java‑PostScript
  mit Aspose.Page Java'
url: /de/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Diagonalen Farbverlauf in Java PostScript mit Aspose.Page Java hinzufügen

## Einführung
Wenn Sie einer PostScript‑Datei einen sanften diagonalen Farbverlauf hinzufügen möchten, macht **Aspose.Page Java** das überraschend einfach. In diesem Tutorial führen wir Sie **schrittweise durch das Hinzufügen von Gradient**‑Effekten, wobei wir die Klasse `LinearGradientPaint` aus Java 2D verwenden. Am Ende haben Sie ein sofort ausführbares Snippet, das ein PostScript‑Dokument mit einem lebendigen diagonalen Farbverlauf erzeugt.

## Wie man in Java PostScript einen Gradient hinzufügt
Ein Gradient mag wie eine rein grafische Aufgabe klingen, doch mit Aspose.Page erhalten Sie die volle Kontrolle über die zugrunde liegenden PostScript‑Befehle, während Sie rein in Java bleiben. Dieser Abschnitt erklärt, warum der Ansatz funktioniert und welchen Nutzen Sie im Vergleich zum manuellen Schreiben von rohem PostScript haben.

## Schnellantworten
- **Welche Bibliothek wird benötigt?** Aspose.Page für Java.  
- **Welche Klasse erzeugt den Gradient?** `LinearGradientPaint`.  
- **Kann ich die Farben ändern?** Ja – passen Sie das `Color[]`‑Array an.  
- **Benötige ich eine Lizenz für die Produktion?** Eine kommerzielle Lizenz ist erforderlich; ein kostenloser Testzeitraum ist verfügbar.  
- **Wie lange dauert die Implementierung?** Etwa 10 Minuten für einen einfachen Gradient.

## Was ist Aspose.Page Java?
Aspose.Page Java ist eine leistungsstarke API, die Entwicklern ermöglicht, PostScript‑ und PDF‑Dateien zu erzeugen, zu bearbeiten und zu konvertieren, ohne externe Software zu benötigen. Sie stellt die vollständigen Grafik‑Fähigkeiten der PostScript‑Sprache über eine saubere, objektorientierte Java‑Schnittstelle bereit.

## Warum einen diagonalen Gradient verwenden?
Ein diagonaler Gradient verleiht Diagrammen, Bannern oder jedem grafischen Element, das einen modernen Look benötigt, Tiefe und visuelles Interesse. Da der Gradient von einer Ecke zur gegenüberliegenden verläuft, eignet er sich gut für Hintergründe, Button‑Skins und dekorative Formen.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Java Development Kit (JDK) 8 oder höher.  
- Eine IDE wie Eclipse, IntelliJ IDEA oder VS Code.  
- **Aspose.Page für Java**‑Bibliothek – laden Sie die neueste Version von der [offiziellen Download‑Seite](https://releases.aspose.com/page/java/) herunter.

## Pakete importieren
Zuerst importieren Sie die Java 2D‑ und Aspose‑Klassen, die Sie benötigen. Diese Importe geben Ihnen Zugriff auf Farbbibliotheken, geometrische Formen, Gradient‑Painting und die PostScript‑Dokument‑API.

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

## Schritt 1: Ausgabestream für das PostScript‑Dokument erstellen
Wir beginnen damit, den Ordner zu definieren, in dem die Datei gespeichert wird, und öffnen einen `FileOutputStream`. Dieser Stream empfängt die erzeugten PostScript‑Daten.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## Schritt 2: Speicheroptionen mit A4‑Größe erstellen
`PsSaveOptions` ermöglicht das Festlegen von Seitengröße, Auflösung und weiteren Ausgabe‑Einstellungen. Hier verwenden wir die Standard‑A4‑Größe.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## Schritt 3: Neues PS‑Dokument erstellen
Instanziieren Sie ein `PsDocument` mit dem Ausgabestream und den Speicheroptionen. Das Flag `false` teilt dem Konstruktor mit, dass nicht automatisch eine neue Seite geöffnet wird – das erledigen wir später.

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Schritt 4: Rechteck erstellen
Definieren Sie das Rechteck, das die Gradient‑Füllung erhalten soll. Die Position des Rechtecks (200, 100) und die Größe (200 × 100) wurden gewählt, damit der Gradient gut sichtbar ist.

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Schritt 5: Gradient‑Transformation erstellen
Ein `AffineTransform` lässt uns den Gradient drehen, skalieren und verschieben, sodass er diagonal über das Rechteck verläuft. Die nachfolgende Rechnung ermittelt die Hypotenuse und passt das Skalierungs‑Verhältnis entsprechend an.

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

## Schritt 6: Diagonalen linearen Gradient‑Paint erstellen
Hier ist der Kern von **wie man einen Gradient hinzufügt** – wir bauen ein `LinearGradientPaint`, das von der oberen linken zur unteren rechten Ecke des Rechtecks reicht, unter Verwendung der zuvor definierten Transformation. `MultipleGradientPaint.CycleMethod.NO_CYCLE` sorgt dafür, dass sich der Gradient nicht wiederholt.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## Schritt 7: Paint setzen und das Rechteck füllen
Wenden Sie den Gradient‑Paint auf das Dokument an und füllen Sie die Rechteck‑Form. Dieser Schritt rendert den diagonalen Farbverlauf auf der PostScript‑Seite.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Schritt 8: Aktuelle Seite schließen und Dokument speichern
Zum Schluss schließen wir die Seite, leeren den Stream und speichern die Datei. Die resultierende Datei `DiagonalGradient_outPS.ps` kann mit jedem PostScript‑Viewer geöffnet werden.

```java
// Close current page and save the document
document.closePage();
document.save();
```

## Häufige Probleme & Tipps
- **Gradient wirkt flach** – prüfen Sie den Rotationswinkel; eine Drehung von 45° erzeugt einen echten Diagonalverlauf.  
- **Farben wirken ausgewaschen** – stellen Sie sicher, dass Sie `MultipleGradientPaint.ColorSpaceType.SRGB` für eine präzise Farbdarstellung verwenden.  
- **Datei‑nicht‑gefunden‑Fehler** – prüfen Sie, ob `dataDir` auf einen existierenden Ordner zeigt und die Anwendung Schreibrechte besitzt.

## Häufig gestellte Fragen

**F: Kann ich diese Bibliothek für andere Grafik‑Operationen in Java verwenden?**  
A: Ja, Aspose.Page für Java bietet ein vollständiges Set an Zeichen‑Primitiven, Text‑Rendering und Bild‑Verarbeitungs‑Funktionen.

**F: Gibt es eine kostenlose Testversion von Aspose.Page Java?**  
A: Absolut. Sie können eine voll funktionsfähige Testversion von der [Aspose‑Test‑Seite](https://releases.aspose.com/) herunterladen.

**F: Wo finde ich die Dokumentation für Aspose.Page Java?**  
A: Die offizielle API‑Referenz ist [hier](https://reference.aspose.com/page/java/) verfügbar.

**F: Wie kann ich eine Lizenz für Aspose.Page Java erwerben?**  
A: Lizenzen können direkt über das [Aspose‑Kaufportal](https://purchase.aspose.com/buy) erworben werden.

**F: Benötigen Sie Unterstützung oder haben Sie Fragen?**  
A: Besuchen Sie das von der Community betriebene [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39) für Hilfe von Aspose‑Ingenieuren und anderen Entwicklern.

---

**Zuletzt aktualisiert:** 2026-02-13  
**Getestet mit:** Aspose.Page für Java 24.12 (neueste)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}