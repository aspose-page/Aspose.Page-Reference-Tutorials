---
date: 2025-12-11
description: Erfahren Sie, wie Sie mit Aspose.Page in Java eine PostScript‑Ellipse
  erstellen. Diese Schritt‑für‑Schritt‑Anleitung zeigt Ihnen, wie Sie eine Ellipse
  mit Farbe füllen und eine Ellipse mit Java zeichnen.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Wie man eine PostScript‑Ellipse in Java mit Aspose.Page erstellt
url: /de/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man eine PostScript‑Ellipse in Java mit Aspose.Page erstellt

## Einführung
Das programmgesteuerte Erstellen einer **PostScript‑Ellipse** gibt Ihnen feinkörnige Kontrolle über Vektorgrafiken in Berichten, Rechnungen oder jedem druckbaren Dokument. In diesem Tutorial lernen Sie, wie Sie **PostScript‑Ellipse**‑Formen mit der Aspose.Page‑Bibliothek für Java erzeugen, eine Ellipse mit Farbe füllen und eine Ellipse umranden. Am Ende sind Sie bereit, benutzerdefinierte Grafiken direkt in Ihre PostScript‑Ausgabe einzubetten.

## Schnellantworten
- **Welche Bibliothek ist am besten zum Zeichnen von PostScript‑Grafiken in Java?** Aspose.Page für Java.  
- **Kann ich eine Ellipse mit einer Vollfarbe füllen?** Ja – verwenden Sie `document.setPaint(Color.YOUR_COLOR)` vor `fill`.  
- **Wie zeichne ich nur die Kontur einer Ellipse?** Setzen Sie die Farbe und den Stroke und rufen Sie dann `document.draw(...)` auf.  
- **Benötige ich eine Lizenz für den Produktionseinsatz?** Eine kommerzielle Lizenz ist erforderlich; eine temporäre Lizenz steht für Tests zur Verfügung.  
- **Welche Java‑Version wird unterstützt?** Jede Java‑8+ Runtime funktioniert mit der aktuellen Aspose.Page‑Version.

## Was ist eine PostScript‑Ellipse?
Eine PostScript‑Ellipse ist eine Vektorform, die durch ein umgebendes Rechteck definiert wird. Im Gegensatz zu Rasterbildern skaliert sie ohne Qualitätsverlust, was sie ideal für hochauflösenden Druck und PDF‑Konvertierung macht.

## Warum Aspose.Page zum Erstellen einer PostScript‑Ellipse verwenden?
- **Vollständige Kontrolle** über Zeichen‑Primitive (Linien, Kurven, Ellipsen).  
- **Plattformübergreifend** – funktioniert unter Windows, Linux und macOS.  
- **Keine externen Abhängigkeiten** – reine Java‑API, kein nativer Code.  
- **Einfache Integration** in bestehende Java‑Anwendungen und Build‑Tools.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. Eine funktionierende Java‑Entwicklungsumgebung (JDK 8 oder höher).  
2. Die Aspose.Page‑Bibliothek für Java in Ihrem Projekt eingebunden. Sie können sie **[hier](https://releases.aspose.com/page/java/)** herunterladen.  

## Pakete importieren
Importieren Sie in Ihrer Java‑Quelldatei die Klassen, die zum Zeichnen und Speichern von PostScript‑Inhalten erforderlich sind.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Das PostScript‑Dokument einrichten
Erzeugen Sie einen Output‑Stream, konfigurieren Sie die Seitengröße und instanziieren Sie ein `PsDocument`.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Schritt 2: Ellipse mit Farbe füllen
Setzen Sie die Farbe auf die gewünschte Füllfarbe und rufen Sie `fill` mit einer `Ellipse2D`‑Instanz auf.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Schritt 3: Ellipse mit Stroke umranden
Wechseln Sie die Farbe zum Stroke, definieren Sie einen `BasicStroke` für die Linienstärke und zeichnen Sie die Kontur der Ellipse.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Schritt 4: Dokument schließen und speichern
Beenden Sie die Seite und schreiben Sie die PostScript‑Datei auf die Festplatte.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Sie haben nun eine PostScript‑Datei, die zwei Ellipsen enthält – eine gefüllt mit Orange und eine umrandet in Rot. Experimentieren Sie gern mit anderen Koordinaten, Größen und Farben, um Ihre Design‑Anforderungen zu erfüllen.

## Häufige Stolperfallen und Fehlersuche
- **Falscher Dateipfad** – Stellen Sie sicher, dass `dataDir` mit einem Trennzeichen (`/` oder `\\`) endet, das zu Ihrem Betriebssystem passt.  
- **Fehlende Lizenz** – Ohne gültige Lizenz läuft die Bibliothek im Evaluierungsmodus und kann Wasserzeichen hinzufügen.  
- **Farbe wird nicht angewendet** – Denken Sie daran, `document.setPaint(...)` *vor* jedem `fill`‑ oder `draw`‑Aufruf zu setzen; die Farbeinstellung bleibt nicht automatisch über separate Vorgänge hinweg erhalten.

## Häufig gestellte Fragen

**F: Kann ich Aspose.Page für Java mit anderen Java‑Bibliotheken verwenden?**  
A: Ja, Aspose.Page für Java ist so konzipiert, dass es nahtlos mit anderen Java‑Bibliotheken zusammenarbeitet.

**F: Wie erhalte ich eine temporäre Lizenz für Aspose.Page für Java?**  
A: Holen Sie sich eine temporäre Lizenz **[hier](https://purchase.aspose.com/temporary-license/)** für Testzwecke.

**F: Ist Aspose.Page für kommerzielle Projekte geeignet?**  
A: Absolut! Besuchen Sie **[hier](https://purchase.aspose.com/buy)**, um Lizenzoptionen für den kommerziellen Einsatz zu erkunden.

**F: Wo kann ich Hilfe erhalten oder Fragen zu Aspose.Page stellen?**  
A: Treten Sie der Community im **[Aspose.Page‑Forum](https://forum.aspose.com/c/page/39)** bei für Diskussionen und Unterstützung.

**F: Gibt es kostenlose Ressourcen, um mehr über Aspose.Page für Java zu lernen?**  
A: Nutzen Sie die **[kostenlose Testversion](https://releases.aspose.com/)** und erkunden Sie Beispiele in der Dokumentation.

## Fazit
Aspose.Page für Java macht das **Erstellen von PostScript‑Ellipse**‑Grafiken unkompliziert, egal ob Sie eine einfache gefüllte Form oder eine komplexe umrandete Kontur benötigen. Mit den obigen Schritten können Sie schnell professionelle Vektorgrafiken zu jedem druckbaren Dokument hinzufügen. Für weiterführende Themen – wie das Kombinieren mehrerer Formen, das Anwenden von Farbverläufen oder die Konvertierung zu PDF – lesen Sie die offizielle **[Dokumentation](https://reference.aspose.com/page/java/)**.

---

**Zuletzt aktualisiert:** 2025-12-11  
**Getestet mit:** Aspose.Page für Java 24.11  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
