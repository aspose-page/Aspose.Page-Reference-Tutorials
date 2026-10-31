---
date: 2026-10-31
description: Erfahren Sie, wie Sie paint color festlegen und ellipse in Java PostScript
  mit Aspose.Page füllen. Dieser Leitfaden zeigt, wie man ellipse füllt, die Kontur
  der ellipse zeichnet und stroke thickness festlegt, mit klaren code steps.
keywords:
- how to fill ellipse
- how to set paint color
- Aspose.Page Java ellipse
- PostScript drawing Java
lastmod: 2026-10-31
linktitle: Ellipse in Java PostScript hinzufügen
og_description: Erfahren Sie, wie Sie ellipse füllen und paint color in Java PostScript
  mit Aspose.Page festlegen. Folgen Sie step‑by‑step code, um gefüllte und umrandete
  ellipses in Sekunden zu zeichnen.
og_image_alt: Developer guide showing how to fill ellipse and set paint color in Java
  PostScript with Aspose.Page
og_title: Wie man ellipse füllt und paint color in Java PostScript festlegt
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  headline: How to fill ellipse and set paint color in Java PostScript
  type: TechArticle
- description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  name: How to fill ellipse and set paint color in Java PostScript
  steps:
  - name: Set up the PostScript document
    text: Create an output stream, configure page size, and instantiate a `PsDocument`.
      `PsDocument` is the core class that represents a PostScript file in memory.
      All drawing commands are routed through this object, and it handles page layout,
      resource management, and final file generation.
  - name: Fill ellipse – use set paint color
    text: To **fill ellipse**, you must first call `setPaint` with the desired fill
      color, then invoke `fill` with an `Ellipse2D` instance. `setPaint` sets the
      current drawing color used for subsequent fill or stroke operations. `Ellipse2D`
      defines the geometric bounds of the ellipse; its constructor takes th
  - name: Draw ellipse outline and set stroke thickness
    text: After filling, you can change the paint to a different color, define a `BasicStroke`
      to control line width, and draw the ellipse outline. `BasicStroke` specifies
      line width, dash pattern, and end‑cap style for drawing outlines. By adjusting
      its `width` property you control how bold the ellipse borde
  - name: Close and save the document
    text: Finalize the page and write the PostScript file to disk. Calling `document.close()`
      flushes all pending drawing commands and releases resources. The resulting `.ps`
      file can be opened with any PostScript viewer or converted to PDF. You now have
      a PostScript file that contains two ellipses—one filled
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to seamlessly integrate with other
      Java libraries.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Obtain a temporary license **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)**
      for testing purposes.
    question: How can I get a temporary license for Aspose.Page for Java?
  - answer: Absolutely! Visit **[the Aspose purchase page](https://purchase.aspose.com/buy)**
      to explore licensing options for commercial use.
    question: Is Aspose.Page suitable for commercial projects?
  - answer: Join the community at the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for discussions and assistance.
    question: Where can I seek help or discuss Aspose.Page‑related queries?
  - answer: Utilize the **[Aspose free trial page](https://releases.aspose.com/)**
      and explore examples in the documentation.
    question: Are there any free resources to learn more about Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript ellipse
- vector drawing
title: Wie man ellipse füllt und paint color in Java PostScript festlegt
url: /de/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Ellipse füllt und die Farbe festlegt in Java PostScript

## Einleitung
Wenn Sie beim Zeichnen von Vektorgrafiken **die Farbe festlegen** müssen, bietet Ihnen die Aspose.Page for Java Bibliothek die volle Kontrolle über jeden Strich und jede Füllung. In diesem Tutorial erfahren Sie, wie Sie **die Farbe festlegen**, **eine Ellipse füllen** und **die Kontur einer Ellipse zeichnen** mit einem einfachen, schrittweisen Ansatz. Am Ende können Sie hochwertige PostScript‑Ellipsen zu Rechnungen, Berichten oder jedem druckbaren Dokument hinzufügen.

## Schnelle Antworten
- **Welche Bibliothek ist am besten zum Zeichnen von PostScript‑Grafiken in Java?** Aspose.Page for Java.  
- **Kann ich eine Ellipse mit einer Vollfarbe füllen?** Ja – verwenden Sie `document.setPaint(Color.YOUR_COLOR)` vor `fill`.  
- **Wie zeichne ich nur die Kontur einer Ellipse?** Setzen Sie die Farbe und den Strich, dann rufen Sie `document.draw(...)` auf.  
- **Benötige ich eine Lizenz für den Produktionseinsatz?** Eine kommerzielle Lizenz ist erforderlich; eine temporäre Lizenz ist für Tests verfügbar.  
- **Welche Java‑Version wird unterstützt?** Jede Java 8+ Laufzeit funktioniert mit der aktuellen Aspose.Page‑Version.

## Was ist eine PostScript‑Ellipse?
Eine PostScript‑Ellipse ist eine Vektorform, die durch ein Begrenzungsrechteck definiert wird. Im Gegensatz zu Rasterbildern skaliert sie ohne Qualitätsverlust, was sie ideal für hochauflösenden Druck und PDF‑Konvertierung macht. Da die Form mathematisch beschrieben wird, kann sie in jeder Größe oder Auflösung gerendert werden, während scharfe Kanten und glatte Kurven erhalten bleiben.

## Warum Aspose.Page verwenden, um eine PostScript‑Ellipse zu erstellen?
Aspose.Page gibt Ihnen deterministische Kontrolle über jedes Zeichenprimitive. Es unterstützt **3 wichtige Betriebssysteme (Windows, Linux, macOS)**, **0 native Abhängigkeiten** und kann **50+ Vektor‑Primitives** pro Sekunde auf einem typischen Server rendern. Die Bibliothek ist reines Java, sodass Sie sie in jede Java 8+ Anwendung einbetten können, ohne zusätzliche native Bibliotheken.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie:

1. Eine funktionierende Java‑Entwicklungsumgebung (JDK 8 oder höher).  
2. Die Aspose.Page for Java Bibliothek zu Ihrem Projekt hinzugefügt haben. Sie können sie **[von der Aspose.Page for Java Release‑Seite](https://releases.aspose.com/page/java/)** herunterladen.  

## Pakete importieren
In Ihrer Java‑Quelldatei importieren Sie die Klassen, die zum Zeichnen und Speichern von PostScript‑Inhalten erforderlich sind.

Das `java.awt`‑Paket liefert die grundlegenden Grafiktypen wie `Color`, `Ellipse2D` und `BasicStroke`. Das `com.aspose.page`‑Paket stellt die Klasse `PsDocument` bereit, die PostScript‑Ausgabe schreibt.

- **`Color`** – repräsentiert eine sRGB‑Farbe, die zum Malen verwendet wird.  
- **`Ellipse2D`** – beschreibt eine Ellipsenform, definiert durch ein Begrenzungsrechteck.  
- **`BasicStroke`** – gibt Linienbreite, Strichmuster und Endkap‑Stil für das Zeichnen von Konturen an.  
- **`PsDocument`** – stellt ein PostScript‑Dokument dar und bietet Methoden zum Zeichnen von Grafiken und zum Verwalten von Seiten.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Wie man die Farbe für eine Ellipse festlegt
Der erste Schritt besteht darin, dem Dokument mitzuteilen, welche Farbe für die nächste Zeichenoperation verwendet werden soll. Die Methode `setPaint` legt eine Vollfarbe fest, die entweder für eine Füllung oder einen Strich angewendet wird, abhängig vom nachfolgenden Aufruf.

### Schritt 1: PostScript‑Dokument einrichten
Erzeugen Sie einen Ausgabestream, konfigurieren Sie die Seitengröße und instanziieren Sie ein `PsDocument`.

`PsDocument` ist die Kernklasse, die eine PostScript‑Datei im Speicher repräsentiert. Alle Zeichenbefehle werden über dieses Objekt geleitet, und es übernimmt Seitenlayout, Ressourcenverwaltung und die endgültige Dateigenerierung.

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

### Schritt 2: Ellipse füllen – setPaint‑Farbe verwenden
Um **eine Ellipse zu füllen**, müssen Sie zuerst `setPaint` mit der gewünschten Füllfarbe aufrufen und anschließend `fill` mit einer `Ellipse2D`‑Instanz ausführen.

`setPaint` legt die aktuelle Zeichenfarbe fest, die für nachfolgende Füll‑ oder Strich‑Operationen verwendet wird.  
`Ellipse2D` definiert die geometrischen Grenzen der Ellipse; ihr Konstruktor nimmt die X‑Y‑Koordinaten der oberen linken Ecke sowie Breite und Höhe entgegen.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Schritt 3: Ellipsenkontur zeichnen und Strichstärke festlegen
Nach dem Füllen können Sie die Farbe zu einer anderen ändern, ein `BasicStroke` definieren, um die Linienbreite zu steuern, und die Ellipsenkontur zeichnen.

`BasicStroke` gibt Linienbreite, Strichmuster und Endkap‑Stil für das Zeichnen von Konturen an. Durch Anpassen seiner `width`‑Eigenschaft bestimmen Sie, wie kräftig die Ellipsenrand erscheint.

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

Der Aufruf `document.close()` leert alle ausstehenden Zeichenbefehle und gibt Ressourcen frei. Die resultierende `.ps`‑Datei kann mit jedem PostScript‑Betrachter geöffnet oder in PDF konvertiert werden.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Sie haben nun eine PostScript‑Datei, die zwei Ellipsen enthält – eine mit Orange gefüllt und eine andere mit roter Kontur. Experimentieren Sie gern mit verschiedenen Koordinaten, Größen und Farben, um Ihren Design‑Anforderungen gerecht zu werden.

## Häufige Fallstricke und Fehlersuche
- **Falscher Dateipfad** – Stellen Sie sicher, dass `dataDir` mit einem Trennzeichen (`/` oder `\\`) endet, das zu Ihrem Betriebssystem passt.  
- **Fehlende Lizenz** – Ohne gültige Lizenz läuft die Bibliothek im Evaluierungsmodus und kann Wasserzeichen hinzufügen.  
- **Farbe wird nicht angewendet** – Denken Sie daran, `document.setPaint(...)` *vor* jedem `fill`‑ oder `draw`‑Aufruf zu setzen; die Farbeinstellung bleibt nicht automatisch über separate Operationen hinweg erhalten.

## Häufig gestellte Fragen

**F: Kann ich Aspose.Page for Java mit anderen Java‑Bibliotheken verwenden?**  
A: Ja, Aspose.Page for Java ist so konzipiert, dass es nahtlos mit anderen Java‑Bibliotheken integriert werden kann.

**F: Wie kann ich eine temporäre Lizenz für Aspose.Page for Java erhalten?**  
A: Holen Sie sich eine temporäre Lizenz **[von der Aspose‑Temporär‑Lizenz‑Seite](https://purchase.aspose.com/temporary-license/)** für Testzwecke.

**F: Ist Aspose.Page für kommerzielle Projekte geeignet?**  
A: Absolut! Besuchen Sie die **[Aspose‑Kaufseite](https://purchase.aspose.com/buy)**, um Lizenzoptionen für den kommerziellen Einsatz zu prüfen.

**F: Wo kann ich Hilfe erhalten oder Fragen zu Aspose.Page stellen?**  
A: Treten Sie der Community im **[Aspose.Page‑Forum](https://forum.aspose.com/c/page/39)** bei für Diskussionen und Unterstützung.

**F: Gibt es kostenlose Ressourcen, um mehr über Aspose.Page for Java zu lernen?**  
A: Nutzen Sie die **[Aspose‑Kostenlos‑Testseite](https://releases.aspose.com/)** und erkunden Sie Beispiele in der Dokumentation.

## Fazit
Aspose.Page for Java macht es unkompliziert, **die Farbe festzulegen**, **eine Ellipse zu füllen** und **die Kontur einer Ellipse zu zeichnen** – egal, ob Sie eine einfache gefüllte Form oder eine komplexe Strichgrafik benötigen. Mit den obigen Schritten können Sie schnell professionelle Vektorgrafiken zu jedem druckbaren Dokument hinzufügen. Für weiterführende Themen – wie das Kombinieren mehrerer Formen, das Anwenden von Farbverläufen oder die Konvertierung zu PDF – lesen Sie die offizielle **[Aspose.Page Java‑Dokumentation](https://reference.aspose.com/page/java/)**.

---

**Zuletzt aktualisiert:** 2026-10-31  
**Getestet mit:** Aspose.Page for Java 24.11  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man ein Rechteck in Java PostScript mit Aspose.Page zeichnet](/page/java/postscript-shapes/add-rectangle/)
- [Wie man Unicode‑Text in Java PostScript mit Aspose.Page hinzufügt](/page/java/postscript-text-manipulation/add-text-unicode/)
- [Radialen Farbverlauf in PostScript mit Aspose.Page for Java erstellen](/page/java/postscript-gradient-addition/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}