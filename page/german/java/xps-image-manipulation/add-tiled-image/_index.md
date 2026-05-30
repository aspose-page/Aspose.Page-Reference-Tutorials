---
date: 2026-05-30
description: Erfahren Sie, wie Sie ein XPS-Dokument in Java mit Aspose.Page erstellen
  und ein gekacheltes Bild mühelos hinzufügen – Schritt für Schritt. So erstellen
  Sie XPS-Dateien schnell.
keywords:
- how to create xps
- add tiled image java
- Aspose.Page XPS tutorial
linktitle: Gekacheltes Bild in Java XPS hinzufügen
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  headline: How to Create XPS Document with a Tiled Image in Java
  type: TechArticle
- description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  name: How to Create XPS Document with a Tiled Image in Java
  steps:
  - name: Set Up Your Project
    text: Add the Aspose.Page JAR files to your project’s classpath and verify the
      import statements compile without errors.
  - name: Create XPS Document
    text: '`XpsDocument` is the core container that holds pages, paths, and resources.
      Instantiate it with the desired page size, then you can start adding graphical
      elements.'
  - name: Define the Tiled Image Path
    text: Place the image you want to tile (e.g., `R08LN_NN.jpg`) inside the directory
      referenced by `dataDir`. The image will be used as a brush pattern.
  - name: Add Tiled Image
    text: Create a rectangular path and fill it with an `XpsImageBrush`. By setting
      the tile mode to `Tile`, the image repeats across the rectangle. Adjust the
      source and destination rectangles to control tile size and positioning.
  - name: Save the Document
    text: Persist the XPS file to disk. The output file will contain the tiled image
      you just defined and can be opened with any XPS viewer. Repeat these steps whenever
      you need to **add tiled image** to other pages or shapes within the same XPS
      document.
  type: HowTo
- questions:
  - answer: It provides a high‑level API to generate and manipulate XPS documents
      in Java.
    question: What does Aspose.Page do?
  - answer: Yes – use `XpsImageBrush` with `XpsTileMode.Tile`.
    question: Can I tile an image?
  - answer: A temporary or commercial license is required for production use.
    question: Do I need a license?
  - answer: Any JDK 8+ is compatible.
    question: What Java version is supported?
  - answer: Roughly 10–15 minutes for a basic tiled‑image scenario.
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.Page Java API
title: Wie man ein XPS-Dokument mit einem gekachelten Bild in Java erstellt
url: /de/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man ein XPS-Dokument mit einem gekachelten Bild in Java erstellt

## Einleitung
Das programmgesteuerte Erstellen von XPS-Dokumenten ist eine Kernkompetenz für Java‑Entwickler, die druckbare, geräteunabhängige Ausgaben benötigen. **Wie man XPS**‑Dateien effizient erstellt, wird von Aspose.Page für Java beantwortet, das die low‑level‑Details der XML Paper Specification abstrahiert und Ihnen ermöglicht, sich auf das visuelle Design zu konzentrieren. In diesem Leitfaden sehen Sie genau, wie Sie ein XPS‑Dokument erstellen, ein gekacheltes Bild als Hintergrund oder Muster hinzufügen und das Ergebnis speichern – alles mit kompaktem, produktionsreifem Code.

## Schnelle Antworten
- **Was macht Aspose.Page?** Es stellt eine High‑Level‑API zum Erzeugen und Manipulieren von XPS‑Dokumenten in Java bereit.  
- **Kann ich ein Bild kacheln?** Ja – verwenden Sie `XpsImageBrush` mit `XpsTileMode.Tile`.  
- **Benötige ich eine Lizenz?** Für den Produktionseinsatz ist eine temporäre oder kommerzielle Lizenz erforderlich.  
- **Welche Java‑Version wird unterstützt?** Jede JDK 8+ ist kompatibel.  
- **Wie lange dauert die Implementierung?** Ungefähr 10–15 Minuten für ein einfaches Kachel‑Bild‑Szenario.

## Was bedeutet „XPS‑Dokument erstellen“?
`XpsDocument` ist das Top‑Level‑Objekt von Aspose.Page, das eine einzelne XPS‑Datei im Speicher repräsentiert. Es kapselt Seiten, Ressourcen und Metadaten und ermöglicht Ihnen, das Dokument programmgesteuert zu bauen. Ein XPS‑Dokument zu erstellen bedeutet, diese Klasse zu instanziieren, visuelle Elemente hinzuzufügen und schließlich `save` aufzurufen, um die Fixed‑Layout‑Datei auf die Festplatte zu schreiben. Dieser Ansatz eliminiert manuelle XML‑Verarbeitung und garantiert die Einhaltung der XML Paper Specification.

## Warum ein gekacheltes Bild hinzufügen?
Kacheln wiederholt eine Grafik über einen definierten Bereich, was ideal für Hintergründe, Wasserzeichen oder Musterfüllungen ist. Mit `XpsTileMode.Tile` wiederholt sich das Bild automatisch, ohne dass Sie es manuell duplizieren müssen, wodurch Entwicklungszeit gespart und ein konsistentes Rendering auf jedem Gerät sichergestellt wird. Gekachelte Bilder halten die Dateigröße zudem gering, da dieselbe Bitmap‑Ressource wiederverwendet statt mehrfach eingebettet wird.

## Voraussetzungen
Bevor Sie starten, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java Development Kit (JDK)** – JDK 8 oder neuer installiert.  
2. **Aspose.Page für Java** – Download von der [Website](https://releases.aspose.com/page/java/).  
3. **Ein beschreibbares Verzeichnis** – in dem die erzeugte XPS‑Datei gespeichert wird.

## Pakete importieren
Importieren Sie in Ihrem Java‑Projekt die notwendigen Klassen:

`XpsDocument` ist das Hauptobjekt, das eine XPS‑Datei repräsentiert.  
`XpsImageBrush` malt Formen mithilfe einer Bildquelle.  
`XpsTileMode` gibt an, wie ein Bild gekachelt wird.  
`Rectangle2D` beschreibt ein rechteckiges Gebiet für die Positionierung.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Projekt einrichten
Fügen Sie die Aspose.Page‑JAR‑Dateien dem Klassenpfad Ihres Projekts hinzu und prüfen Sie, ob die Import‑Anweisungen ohne Fehler kompilieren.

### Schritt 2: XPS‑Dokument erstellen
`XpsDocument` ist der Kerncontainer, der Seiten, Pfade und Ressourcen hält. Instanziieren Sie ihn mit der gewünschten Seitengröße, dann können Sie grafische Elemente hinzufügen.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Schritt 3: Pfad zum gekachelten Bild festlegen
Platzieren Sie das Bild, das Sie kacheln möchten (z. B. `R08LN_NN.jpg`), im Verzeichnis, auf das `dataDir` verweist. Das Bild wird als Pinsel‑Muster verwendet.

### Schritt 4: Gekacheltes Bild hinzufügen
Erzeugen Sie einen rechteckigen Pfad und füllen Sie ihn mit einem `XpsImageBrush`. Durch Setzen des Tile‑Modus auf `Tile` wiederholt sich das Bild über das Rechteck. Passen Sie die Quell‑ und Ziel‑`Rectangle2D`‑Werte an, um die Kachelgröße und Positionierung zu steuern.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### Schritt 5: Dokument speichern
Persistieren Sie die XPS‑Datei auf der Festplatte. Die Ausgabedatei enthält das gerade definierte gekachelte Bild und kann mit jedem XPS‑Viewer geöffnet werden.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Wiederholen Sie diese Schritte, wann immer Sie **ein gekacheltes Bild** zu anderen Seiten oder Formen im selben XPS‑Dokument hinzufügen müssen.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| Bild wird nicht angezeigt | Prüfen Sie, ob der Dateipfad (`dataDir + "R08LN_NN.jpg"`) korrekt ist und das Bild zugänglich ist. |
| Kachel‑Muster wirkt gestreckt | Passen Sie die Quell‑ und Ziel‑`Rectangle2D`‑Werte an, um die Kachelgröße zu steuern. |
| Transparenz hat keine Wirkung | Stellen Sie sicher, dass die Deckkraft des Pinsels **nach** der Konfiguration des Tile‑Modus gesetzt wird. |

## Häufig gestellte Fragen

**F:** Ist Aspose.Page mit allen Java‑Versionen kompatibel?  
**A:** Aspose.Page unterstützt Java 8 bis Java 21; die vollständige Kompatibilitätsmatrix finden Sie [hier](https://reference.aspose.com/page/java/).

**F:** Kann ich Aspose.Page für kommerzielle Projekte nutzen?  
**A:** Ja, für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich. Kaufoptionen sind [hier](https://purchase.aspose.com/buy) aufgeführt.

**F:** Gibt es eine kostenlose Testversion?  
**A:** Eine voll funktionsfähige Testversion kann von der Aspose‑Release‑Seite [hier](https://releases.aspose.com/) heruntergeladen werden.

**F:** Wo finde ich Community‑Support?  
**A:** Treten Sie dem Aspose.Page‑Community‑Forum unter [forum](https://forum.aspose.com/c/page/39) bei, um Fragen zu stellen und Beispiele zu teilen.

**F:** Wie erhalte ich eine temporäre Lizenz für Evaluationen?  
**A:** Temporäre Lizenzen werden auf Anfrage über das Aspose‑Portal [hier](https://purchase.aspose.com/temporary-license/) bereitgestellt.

## Fazit
Sie haben nun einen vollständigen, produktionsreifen Workflow, **wie man XPS**‑Dokumente mit gekachelten Bildern mithilfe von Aspose.Page für Java erstellt. Durch die Nutzung von `XpsImageBrush` und `XpsTileMode.Tile` können Sie reichhaltige, wiederholbare Grafiken erzeugen, ohne die Dateigröße zu erhöhen. Experimentieren Sie mit unterschiedlichen Kachelgrößen, Transparenzstufen und Formen, um anspruchsvolle Dokumentlayouts zu bauen. Als nächster Schritt können Sie Vektorformen oder Text‑Overlays hinzufügen, um Ihre XPS‑Dateien weiter zu verfeinern.

---

**Zuletzt aktualisiert:** 2026-05-30  
**Getestet mit:** Aspose.Page für Java 24.12 (neueste)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [How to Add Image to Java XPS Documents – A Simple Guide with Aspose.Page](/page/java/xps-image-manipulation/add-image/)
- [Aspose.Page Java - Add Pages to XPS Tutorial](/page/java/xps-page-manipulation/add-page/)
- [Convert XPS to PDF in Java using Aspose.Page Java](/page/java/file-merging/xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}