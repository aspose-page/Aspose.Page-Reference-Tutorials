---
date: 2026-03-05
description: Erfahren Sie, wie Sie ein Raster mit Visual Brush in Java und Aspose.Page
  hinzufügen. Folgen Sie der Schritt‑für‑Schritt‑Anleitung, um die Dokumentvisualisierung
  mühelos zu verbessern.
linktitle: Add Grid using Visual Brush in Java
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
Wenn Sie **wie man ein Raster** zu Ihren Java‑generierten Dokumenten hinzufügen möchten, macht Aspose.Page’s Visual Brush‑Feature das überraschend einfach. In diesem Tutorial gehen wir Schritt für Schritt durch, erklären, warum ein Visual Brush ideal für Rastermuster ist, und zeigen Ihnen ein komplettes, ausführbares Beispiel.

## Schnelle Antworten
- **Was ist ein Visual Brush?** Ein wiederverwendbares visuelles Element, das gekachelt oder gestreckt werden kann, um einen Bereich zu füllen.  
- **Warum ein Raster verwenden?** Raster helfen, Layouts zu strukturieren, Hintergrundmuster zu erzeugen oder Abschnitte in XPS‑Dokumenten hervorzuheben.  
- **Voraussetzungen?** Java JDK, Aspose.Page für Java und ein grundlegendes Verständnis von Java‑Grafik.  
- **Wie lange dauert die Implementierung?** Etwa 10‑15 Minuten, sobald die Bibliothek eingerichtet ist.  
- **Kann ich Farben anpassen?** Ja – Sie steuern Füllfarben, Transparenz und Kachelgröße direkt im Code.

## Warum Visual Brush zum Hinzufügen eines Rasters verwenden?
Visual Brush ermöglicht es Ihnen, ein kleines visuelles Element (die „Kachel“) einmal zu definieren und dann über jede Form hinweg zu wiederholen. Dieser Ansatz ist speichereffizient und hält Ihren Code sauber, besonders wenn Sie dasselbe Muster auf mehrere Leinwände anwenden müssen.

## Voraussetzungen
Bevor wir in den Code eintauchen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Grundlegendes Verständnis der Java‑Programmierung.  
- Aspose.Page‑Bibliothek installiert. Sie können sie aus der [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) herunterladen.  
- Java Development Kit (JDK) auf Ihrem Rechner installiert.

## Pakete importieren
Stellen Sie sicher, dass die notwendigen Pakete in Ihrem Java‑Projekt importiert sind:
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

### Schritt 1: Projekt einrichten
Zuerst erstellen Sie eine `XpsDocument`‑Instanz und geben den Ordner an, in dem die Ausgabe gespeichert werden soll.
```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### Schritt 2: Magenta‑Raster‑Visual‑Brush erstellen
Wir bauen eine kleine magentafarbene Kachel, die wiederholt wird. Die Pfadgeometrie definiert die Form der Kachel.
```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### Schritt 3: Geometrie für den Magenta‑Raster‑Visual‑Brush definieren
Hier beschreiben wir den Bereich, der den gekachelten Brush erhalten soll.
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### Schritt 4: Neue Leinwand erstellen
Eine frische Leinwand wird dem Dokument hinzugefügt, und wir wenden eine Translations‑Transformation an, damit das Raster an der gewünschten Stelle erscheint.
```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### Schritt 5: Raster zur Leinwand hinzufügen
Jetzt binden wir den Visual Brush an die Geometrie und setzen den Kachelmodus.
```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### Schritt 6: Rotes transparentes Rechteck hinzufügen
Um das Schichten zu demonstrieren, überlagern wir ein halbtransparentes rotes Rechteck über dem Raster.
```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### Schritt 7: Ergebnis‑XPS‑Dokument speichern
Abschließend schreiben wir die XPS‑Datei auf die Festplatte.
```java
doc.save(dataDir + "AddGrid_out.xps");
```

Befolgen Sie diese Schritte, und Sie fügen erfolgreich ein optisch ansprechendes Raster mit Visual Brush in Ihrer Java‑Anwendung unter Verwendung von Aspose.Page hinzu.

## Häufige Anwendungsfälle
- **Berichts‑Hintergründe:** Subtile Rastermuster zu Finanz‑ oder Ingenieur‑Berichten hinzufügen, um die Lesbarkeit zu verbessern.  
- **Design‑Vorlagen:** Wiederverwendbare Seitenvorlagen erstellen, bei denen dasselbe Raster über mehrere Seiten hinweg wiederholt wird.  
- **Abschnitte hervorheben:** Farbige Raster überlagern, um bestimmte Dokumentbereiche hervorzuheben.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| **Raster erscheint gestreckt** | Stellen Sie sicher, dass `TileMode` auf `XpsTileMode.Tile` gesetzt ist und dass Quell‑ und Ziel‑Rechtecke dieselbe Größe haben. |
| **Farben wirken falsch** | Vergewissern Sie sich, dass Sie die korrekten RGBA‑Werte beim Erstellen des SolidColorBrush verwenden (`createColor(alpha, red, green, blue)`). |
| **Dokument wird nicht gespeichert** | Prüfen Sie, ob `dataDir` auf einen existierenden, beschreibbaren Ordner zeigt und ob Sie die entsprechenden Dateisystem‑Berechtigungen besitzen. |

## Fazit
Herzlichen Glückwunsch! Sie haben **wie man ein Raster** mit Aspose.Page’s Visual Brush in Java hinzugefügt. Diese Technik gibt Ihnen feinkörnige Kontrolle über die Musterdarstellung, während Ihr Code sauber und wartbar bleibt.

## Häufig gestellte Fragen
### Ist Aspose.Page für die professionelle Dokumentenerstellung geeignet?
Ja, Aspose.Page ist eine robuste Bibliothek, die für die professionelle Dokumentenerstellung in Java konzipiert ist.

### Kann ich die Rasterfarben mit Visual Brush anpassen?
Absolut! Visual Brush ermöglicht das Malen mit verschiedenen Farben und bietet damit Flexibilität bei der Anpassung.

### Wo finde ich zusätzlichen Support für Aspose.Page?
Besuchen Sie das [Aspose.Page forum](https://forum.aspose.com/c/page/39) für Community‑Support und Diskussionen.

### Gibt es eine kostenlose Testversion von Aspose.Page?
Ja, Sie können die [free trial](https://releases.aspose.com/) nutzen, um die Funktionen von Aspose.Page zu erkunden.

### Wie kann ich eine temporäre Lizenz für Aspose.Page erhalten?
Erwerben Sie eine [temporary license](https://purchase.aspose.com/temporary-license/) für Testzwecke.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2026-03-05  
**Getestet mit:** Aspose.Page for Java (latest release)  
**Autor:** Aspose  

---