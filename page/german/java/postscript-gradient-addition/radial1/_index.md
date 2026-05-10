---
date: 2026-02-13
description: Lernen Sie, wie Sie mit Aspose.Page für Java einen PostScript‑Verlauf
  mit einem radialen Farbverlauf und Farbstopps erstellen. Diese Schritt‑für‑Schritt‑Anleitung
  zeigt Ihnen, wie Sie Farbstopps‑Verläufe in Ihren Dokumenten hinzufügen.
linktitle: Mastering Radial Gradients in Java
second_title: Aspose.Page Java API
title: PostScript-Gradient erstellen – Radialer Gradient in Java
url: /de/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# So fügen Sie einen radialen Farbverlauf in Java PostScript mit Aspose.Page hinzu

## Einführung
Wenn Sie jemals einen **PostScript‑Farbverlauf** mit einem sanften, auffälligen Farbübergang erstellen mussten, ist das Erlernen, wie man einen radialen Farbverlauf hinzufügt, der perfekte Ausgangspunkt. In diesem Tutorial führen wir Sie Schritt für Schritt durch die Erstellung einer PostScript‑Datei, die einen schönen radialen Farbverlauf enthält, mithilfe der **Aspose.Page for Java**‑Bibliothek. Am Ende verstehen Sie die API, sehen ein vollständiges ausführbares Beispiel und wissen, wie Sie Farben, Positionen und Radien anpassen können, um jedes Design zu erfüllen.

## Schnelle Antworten
- **Welche Bibliothek erstellt radiale Farbverläufe in PostScript?** Aspose.Page for Java.  
- **Wie lange dauert die Implementierung?** Etwa 10‑15 Minuten für ein einfaches Beispiel.  
- **Benötige ich eine Lizenz, um den Code auszuführen?** Eine kostenlose Testversion reicht für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Welche Java‑Version wird unterstützt?** Java 8 oder höher.  
- **Kann ich die Form des Farbverlaufs ändern?** Ja – passen Sie den Radius und den Mittelpunkt im `RadialGradientPaint`‑Konstruktor an.

## So erstellen Sie einen PostScript‑Farbverlauf mit radialer Füllung
Im Folgenden finden Sie eine prägnante Schritt‑für‑Schritt‑Anleitung, die genau zeigt, wie man **PostScript‑Farbverlauf**‑Inhalte mit einer radialen Füllung erstellt. Jeder Schritt enthält eine kurze Erklärung, gefolgt vom ursprünglichen Code‑Block (unverändert).

## Was ist ein radialer Farbverlauf?
Ein radialer Farbverlauf malt Farben, die von einem zentralen Punkt nach außen strahlen und allmählich zu den Rändern hin verblassen. Im Gegensatz zu linearen Farbverläufen folgt der Farbübergang einem kreisförmigen (oder elliptischen) Muster, das sich ideal für Hervorhebungen, Spotlights oder sanfte Hintergrundfüllungen eignet.

## Warum Aspose.Page für radiale Farbverläufe verwenden?
- **Vollständige Kontrolle über die PostScript‑Ausgabe** – keine Notwendigkeit, Low‑Level‑PS‑Befehle von Hand zu erstellen.  
- **Plattformübergreifend** – funktioniert auf jedem Betriebssystem, das Java ausführt.  
- **Umfangreiches Farbmanagement** – unterstützt mehrere Farbstopps, verschiedene Farbräume und Zyklus‑Methoden.  
- **Integrationsbereit** – lässt sich mit anderen Aspose.Page‑Funktionen wie Text, Bildern und Vektorformen kombinieren.

## Voraussetzungen
Bevor wir in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes bereit haben:

- **Java Development Kit (JDK) 8+** – prüfen Sie mit `java -version`.  
- **Aspose.Page for Java** – laden Sie das neueste JAR von der offiziellen [Aspose.Page download page](https://releases.aspose.com/page/java/) herunter.  
- **IDE Ihrer Wahl** – Eclipse, IntelliJ IDEA oder VS Code mit Java‑Erweiterungen.  
- **Ein beschreibbarer Ordner** – in dem die erzeugte `.ps`‑Datei gespeichert wird.

## Pakete importieren
Zuerst importieren wir die benötigten Klassen. Das `java.awt`‑Paket stellt die Gradient‑Paint‑Objekte bereit, während `com.aspose.eps` die Klassen zur Handhabung von PostScript‑Dokumenten enthält.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Erstellen Sie ein Rechteck und öffnen Sie ein PS‑Dokument
Wir beginnen damit, einen Ausgabestream zu erstellen, die Seitengröße (standardmäßig A4) zu konfigurieren und ein Rechteck zu definieren, das den Farbverlauf enthält.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **Profi‑Tipp:** Passen Sie die Koordinaten des Rechtecks (`200, 100, 200, 200`) an, um den Farbverlauf an beliebiger Stelle auf der Seite zu positionieren.

### Schritt 2: Farben und Bruchteile definieren
Ein radialer Farbverlauf wird aus *Farbstopps* (den Farben) und *Bruchteilen* (den relativen Positionen dieser Stopps) aufgebaut. Hier erstellen wir ein Array aus sechs Farben und den zugehörigen Bruchteilen.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Warum das wichtig ist:** Durch Anpassen von `fractions` steuern Sie, wie schnell die Farben übergehen, was subtile oder dramatische Effekte ermöglicht.

Wenn Sie **Farbstopps‑Verlauf hinzufügen** müssen, sind die Arrays `colors` und `fractions` entscheidend. Sie können die Einträge nach Belieben neu anordnen, hinzufügen oder entfernen, um Ihr visuelles Design anzupassen.

### Schritt 3: RadialGradientPaint erstellen
Jetzt erstellen wir das Objekt `RadialGradientPaint`. Der Konstruktor nimmt den Mittelpunkt des Farbverlaufs, den Radius, den Fokus‑Punkt, die Bruchteile, die Farben, die Zyklus‑Methode, den Farbraum und eine optionale Transformation entgegen.

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **Hinweis:** `transform` kann `null` sein, wenn Sie keine zusätzliche Skalierung oder Rotation benötigen. Experimentieren Sie gern mit `AffineTransform` für schiefe Farbverläufe.

### Schritt 4: Paint setzen und das Rechteck füllen
Nachdem das Paint bereit ist, weisen wir das `PsDocument` an, es zu verwenden, und füllen anschließend das zuvor definierte Rechteck.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

Zu diesem Zeitpunkt enthält die PostScript‑Seite ein Rechteck, das sanft mit dem von uns konfigurierten radialen Farbverlauf gefüllt ist.

### Schritt 5: Dokument schließen und speichern
Abschließend schließen wir die aktuelle Seite und schreiben die Datei auf die Festplatte.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Öffnen Sie `RadialGradient1_outPS.ps` in einem beliebigen PostScript‑Betrachter (z. B. Ghostscript) und Sie sehen den Farbverlauf exakt wie definiert.

## Häufige Probleme & Lösungen
| Symptom | Wahrscheinliche Ursache | Lösung |
|---------|--------------------------|--------|
| Farbverlauf erscheint als einfarbige Fläche | `fractions`‑Array beginnt nicht bei `0.0f` oder endet nicht bei `1.0f` | Stellen Sie sicher, dass der erste Bruchwert `0.0f` und der letzte `1.0f` ist. |
| Farben wirken ausgewaschen | Falscher `ColorSpaceType` verwendet | Wechseln Sie zu `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` für lebendigere Ausgabe. |
| Keine Ausgabedatei erzeugt | `FileOutputStream`‑Pfad ist ungültig oder nicht beschreibbar | Überprüfen Sie, ob `dataDir` existiert und die Anwendung Schreibrechte hat. |

## Häufig gestellte Fragen

**F: Kann ich Aspose.Page für Java in kommerziellen Projekten verwenden?**  
A: Ja. Für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich. Sie können eine über die [Aspose licensing page](https://purchase.aspose.com/buy) erwerben.

**F: Wo finde ich die offizielle API‑Referenz?**  
A: Die vollständige Dokumentation ist [hier](https://reference.aspose.com/page/java/) verfügbar.

**F: Gibt es eine kostenlose Testversion zum Ausprobieren?**  
A: Auf jeden Fall. Laden Sie eine Testversion von der [Aspose.Page releases page](https://releases.aspose.com/) herunter.

**F: Wie erhalte ich eine temporäre Lizenz für die Evaluierung?**  
A: Eine temporäre Lizenz kann [hier](https://purchase.aspose.com/temporary-license/) angefordert werden.

**F: Wo finde ich Community‑Support?**  
A: Treten Sie dem Aspose.Page‑Community‑Forum bei: [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## Fazit
Sie wissen jetzt, **wie man einen radialen Farbverlauf** zu einem Java‑PostScript‑Dokument mit Aspose.Page hinzufügt. Durch Anpassen der Rechteckgröße, der Farbstopps und des Radius des Farbverlaufs können Sie unzählige visuelle Effekte erzeugen – von dezenten Hintergrundfüllungen bis hin zu kräftigen Spotlight‑Grafiken. Experimentieren Sie gern mit verschiedenen `AffineTransform`‑Werten, um den Farbverlauf zu drehen oder zu kippen, und kombinieren Sie diese Technik mit Text und Bildern für reichhaltigere PDF‑ oder EPS‑Ausgaben.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Page for Java latest (as of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}