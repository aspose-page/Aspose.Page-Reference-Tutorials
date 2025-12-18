---
date: 2025-12-18
description: Erfahren Sie, wie Sie ein Raster und ein transparentes Rechteck in Java‑XPS‑Dokumenten
  mit Aspose.Page hinzufügen. Schritt‑für‑Schritt‑Anleitung zum effizienten Speichern
  von XPS‑Dokumenten.
linktitle: How to Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: Wie man ein Raster mit Visual Brush in Java hinzufügt
url: /de/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man ein Raster mit Visual Brush in Java hinzufügt

## Einführung
Wenn Sie **wie man ein Raster** zu Ihren Java‑generierten XPS‑Dokumenten hinzufügen möchten, sind Sie hier genau richtig. In diesem Tutorial führen wir Sie Schritt für Schritt durch das Hinzufügen eines Rasters mit einem Visual Brush, das Überlagern eines transparenten Rechtecks und schließlich das **Speichern des XPS‑Dokuments** mithilfe der Aspose.Page Java API. Am Ende haben Sie eine professionelle Visualisierung, die in Berichten, Rechnungen oder jeder dokumentintensiven Anwendung wiederverwendet werden kann.

## Schnellantworten
- **Was macht ein Visual Brush?** Er füllt einen definierten Bereich mit wiederverwendbarem visuellen Inhalt, ideal für wiederholende Muster wie Raster.  
- **Kann ich die Rasterfarbe ändern?** Ja – passen Sie die Einstellungen des Solid‑Color‑Brush an.  
- **Wie füge ich ein transparentes Rechteck über dem Raster hinzu?** Verwenden Sie `setOpacity` bei einem Pfad, der mit einer Vollfarbe gefüllt ist.  
- **Welche Methode speichert die Datei?** `doc.save(...)` schreibt die XPS‑Datei auf die Festplatte.  
- **Benötige ich eine Lizenz?** Für den Produktionseinsatz ist eine temporäre oder vollständige Lizenz erforderlich.

## Was ist ein Visual Brush Raster?
Ein Visual Brush ermöglicht es Ihnen, ein kleines visuelles Element (das Rastermuster) zu definieren und dieses dann über eine größere Fläche zu kacheln. Dieser Ansatz ist speichereffizienter, als jede Linie einzeln zu zeichnen, und liefert pixelgenaue Wiederholungen.

## Warum Aspose.Page für diese Aufgabe verwenden?
- **Cross‑platform** – Funktioniert auf jedem Betriebssystem, das Java unterstützt.  
- **High‑fidelity rendering** – Präzise Kontrolle über Farben, Transparenz und Kachelung.  
- **Keine externen Abhängigkeiten** – Alles wird über die Aspose.Page‑Bibliothek abgewickelt.

## Voraussetzungen
Bevor wir starten, stellen Sie sicher, dass Sie Folgendes haben:

- Grundkenntnisse in der Java‑Programmierung.  
- Aspose.Page‑Bibliothek installiert – Sie können sie von der [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) herunterladen.  
- JDK 8 oder höher auf Ihrer Entwicklungsmaschine eingerichtet.

## Pakete importieren
Importieren Sie zunächst die benötigten Klassen, damit der Compiler weiß, wo die von uns verwendeten Typen zu finden sind:

```java
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsTileMode;
import com.aspose.xps.XpsVisualBrush;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Projekt einrichten
Erstellen Sie eine neue `XpsDocument`‑Instanz und geben Sie den Ordner an, in dem die Ausgabedatei gespeichert werden soll.

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### Schritt 2: Magenta‑Raster‑Visual‑Brush erstellen
Wir definieren eine kleine magentafarbene Form, die über den Rasterbereich gekachelt wird.

```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### Schritt 3: Geometrie für den Raster‑Brush definieren
Richten Sie den rechteckigen Bereich ein, der das gekachelte Visual erhalten soll.

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### Schritt 4: Neues Canvas für das Dokument erstellen
Fügen Sie dem Dokument ein Canvas hinzu und positionieren Sie es dort, wo das Raster erscheinen soll.

```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### Schritt 5: Raster zum Canvas hinzufügen
Wenden Sie den Visual Brush auf die Geometrie an, um die Kachelung zu aktivieren.

```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### Schritt 6: Transparentes rotes Rechteck hinzufügen (sekundäre Funktion)
Hier demonstrieren wir das **Hinzufügen eines transparenten Rechtecks** über dem Raster zur Hervorhebung.

```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### Schritt 7: Ergebnis‑XPS‑Dokument speichern
Abschließend schreiben Sie das Dokument auf die Festplatte – dies ist der **Speichern‑XPS‑Dokument**‑Schritt.

```java
doc.save(dataDir + "AddGrid_out.xps");
```

Befolgen Sie diese Schritte, und Sie erhalten ein professionell aussehendes Raster mit einer transparenten Überlagerung, das vollständig programmgesteuert erzeugt wird.

## Häufige Probleme & Tipps

- **Falsche Kachelgröße:** Stellen Sie sicher, dass das für den Brush verwendete `Rectangle2D` der gewünschten Wiederholungsgröße entspricht; sonst kann das Muster gedehnt werden.  
- **Transparenz nicht angewendet:** Denken Sie daran, `setOpacity` für den Pfad aufzurufen, den Sie transparent machen möchten; es wirkt sich nicht auf den Brush selbst aus.  
- **Datei wird nicht gespeichert:** Prüfen Sie, ob `dataDir` auf einen bestehenden Ordner zeigt und Ihre Anwendung Schreibrechte hat.

## Häufig gestellte Fragen

**F: Ist Aspose.Page für die professionelle Dokumentenerstellung geeignet?**  
A: Ja, Aspose.Page ist eine robuste Bibliothek, die für die hochwertige XPS‑ und PDF‑Erstellung in Java entwickelt wurde.

**F: Kann ich die Rasterfarben mit Visual Brush anpassen?**  
A: Absolut! Ändern Sie die Parameter des `createColor`‑Aufrufs in der `setFill`‑Methode des Brushes auf beliebige RGBA‑Werte.

**F: Wo finde ich zusätzlichen Support für Aspose.Page?**  
A: Besuchen Sie das [Aspose.Page forum](https://forum.aspose.com/c/page/39) für Community‑Hilfe und offizielle Antworten.

**F: Gibt es eine kostenlose Testversion von Aspose.Page?**  
A: Ja, Sie können die [free trial](https://releases.aspose.com/) nutzen, um alle Funktionen vor dem Kauf zu testen.

**F: Wie kann ich eine temporäre Lizenz für Tests erhalten?**  
A: Holen Sie sich eine [temporary license](https://purchase.aspose.com/temporary-license/), die für Entwicklung und Evaluation funktioniert.

---

**Zuletzt aktualisiert:** 2025-12-18  
**Getestet mit:** Aspose.Page for Java 23.12 (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}