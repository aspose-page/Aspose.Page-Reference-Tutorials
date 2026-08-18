---
date: 2026-02-18
description: Erfahren Sie, wie Sie die Farbe festlegen und eine PostScript‑Ellipse
  in Java mit Aspose.Page erstellen. Dieser Leitfaden zeigt, wie man eine Ellipse
  in Java füllt, die Kontur der Ellipse zeichnet und die Strichstärke einstellt.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Farbe festlegen, um eine PostScript‑Ellipsе in Java zu zeichnen
url: /de/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Set paint color to draw PostScript ellipse in Java

## Einleitung
Wenn Sie beim Zeichnen von Vektorgrafiken **Farbe festlegen** müssen, bietet Ihnen die Aspose.Page for Java Bibliothek die volle Kontrolle über jeden Strich und jede Füllung. In diesem Tutorial erfahren Sie, wie Sie **Farbe festlegen**, **Ellipse in Java füllen** und **Ellipseumriss zeichnen** mit einem einfachen, schrittweisen Ansatz. Am Ende können Sie hochwertige PostScript-Ellipsen zu Rechnungen, Berichten oder jedem druckbaren Dokument hinzufügen.

## Schnelle Antworten
- **Welche Bibliothek ist am besten zum Zeichnen von PostScript-Grafiken in Java?** Aspose.Page for Java.  
- **Kann ich eine Ellipse mit einer Vollfarbe füllen?** Ja – verwenden Sie `document.setPaint(Color.YOUR_COLOR)` vor `fill`.  
- **Wie zeichne ich nur den Umriss einer Ellipse?** Setzen Sie die Farbe und den Strich, dann rufen Sie `document.draw(...)` auf.  
- **Benötige ich eine Lizenz für den Produktionseinsatz?** Eine kommerzielle Lizenz ist erforderlich; eine temporäre Lizenz ist für Tests verfügbar.  
- **Welche Java-Version wird unterstützt?** Jede Java‑8‑+ Laufzeit funktioniert mit der aktuellen Aspose.Page‑Version.

## Was ist eine PostScript-Ellipse?
Eine PostScript-Ellipse ist eine Vektorform, die durch ein Begrenzungsrechteck definiert wird. Im Gegensatz zu Rasterbildern skaliert sie ohne Qualitätsverlust, was sie ideal für hochauflösenden Druck und PDF‑Konvertierung macht.

## Warum Aspose.Page verwenden, um eine PostScript-Ellipse zu erstellen?
- **Vollständige Kontrolle** über Zeichenprimitive (Linien, Kurven, Ellipsen).  
- **Plattformübergreifend** – funktioniert unter Windows, Linux und macOS.  
- **Keine externen Abhängigkeiten** – reine Java‑API, kein nativer Code.  
- **Einfache Integration** mit bestehenden Java‑Anwendungen und Build‑Tools.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. Eine funktionierende Java‑Entwicklungsumgebung (JDK 8 oder neuer).  
2. Die Aspose.Page for Java Bibliothek zu Ihrem Projekt hinzugefügt. Sie können sie **[hier](https://releases.aspose.com/page/java/)** herunterladen.  

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

## Wie man die Farbe für eine Ellipse festlegt
Das Festlegen der Farbe ist der erste Schritt vor jeder Füll‑ oder Strich‑Operation. Die Methode `setPaint` bestimmt die Farbe, die für den nächsten Zeichenbefehl verwendet wird.

### Schritt 1: PostScript-Dokument einrichten
Erstellen Sie einen Ausgabestream, konfigurieren Sie die Seitengröße und instanziieren Sie ein `PsDocument`.

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

### Schritt 2: Wie man eine Ellipse füllt – Farbe festlegen
Um **eine Ellipse zu füllen**, müssen Sie zuerst `setPaint` mit der gewünschten Füllfarbe aufrufen und anschließend `fill` mit einer `Ellipse2D`‑Instanz ausführen.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Schritt 3: Ellipseumriss zeichnen und Strichstärke festlegen
Nach dem Füllen können Sie die Farbe zu einer anderen ändern, ein `BasicStroke` definieren, um die Linienbreite zu steuern, und den Ellipseumriss zeichnen.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Schritt 4: Dokument schließen und speichern
Schließen Sie die Seite ab und schreiben Sie die PostScript‑Datei auf die Festplatte.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Sie haben jetzt eine PostScript‑Datei, die zwei Ellipsen enthält – eine mit Orange gefüllt und eine andere mit rotem Umriss. Experimentieren Sie gern mit verschiedenen Koordinaten, Größen und Farben, um Ihren Designanforderungen zu entsprechen.

## Häufige Fallstricke und Fehlersuche
- **Falscher Dateipfad** – Stellen Sie sicher, dass `dataDir` mit einem Trennzeichen (`/` oder `\\`) endet, das für Ihr Betriebssystem geeignet ist.  
- **Fehlende Lizenz** – Ohne gültige Lizenz läuft die Bibliothek im Evaluierungsmodus und kann Wasserzeichen hinzufügen.  
- **Farbe nicht angewendet** – Denken Sie daran, `document.setPaint(...)` *vor* jedem `fill`‑ oder `draw`‑Aufruf zu setzen; die Farbeinstellung bleibt nicht automatisch über separate Vorgänge hinweg erhalten.

## Häufig gestellte Fragen

**Q: Kann ich Aspose.Page für Java mit anderen Java‑Bibliotheken verwenden?**  
A: Ja, Aspose.Page for Java ist so konzipiert, dass es nahtlos mit anderen Java‑Bibliotheken integriert werden kann.

**Q: Wie kann ich eine temporäre Lizenz für Aspose.Page für Java erhalten?**  
A: Holen Sie sich eine temporäre Lizenz **[hier](https://purchase.aspose.com/temporary-license/)** für Testzwecke.

**Q: Ist Aspose.Page für kommerzielle Projekte geeignet?**  
A: Auf jeden Fall! Besuchen Sie **[hier](https://purchase.aspose.com/buy)**, um Lizenzoptionen für die kommerzielle Nutzung zu erkunden.

**Q: Wo kann ich Hilfe erhalten oder Aspose.Page‑bezogene Fragen diskutieren?**  
A: Treten Sie der Community im **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** bei für Diskussionen und Unterstützung.

**Q: Gibt es kostenlose Ressourcen, um mehr über Aspose.Page für Java zu lernen?**  
A: Nutzen Sie die **[kostenlose Testversion](https://releases.aspose.com/)** und erkunden Sie Beispiele in der Dokumentation.

## Fazit
Aspose.Page for Java macht es einfach, **Farbe festzulegen**, **Ellipse zu füllen** und **Ellipseumriss zu zeichnen** – egal, ob Sie eine einfache gefüllte Form oder eine komplexe Strichgrafik benötigen. Mit den obigen Schritten können Sie schnell professionelle Vektorgrafiken zu jedem druckbaren Dokument hinzufügen. Für weiterführende Themen – wie das Kombinieren mehrerer Formen, das Anwenden von Farbverläufen oder das Konvertieren zu PDF – siehe die offizielle **[Dokumentation](https://reference.aspose.com/page/java/)**.

---

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}