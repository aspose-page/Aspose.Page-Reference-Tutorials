---
date: 2025-12-28
description: Erfahren Sie, wie Sie mit Aspose.Page ein XPS‑Dokument in Java erstellen
  und mühelos ein gekacheltes Bild hinzufügen – Schritt für Schritt.
linktitle: Add Tiled Image in Java XPS
second_title: Aspose.Page Java API
title: Wie man ein XPS-Dokument mit einem gekachelten Bild in Java erstellt
url: /de/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen eines XPS-Dokuments und Hinzufügen eines gekachelten Bildes in Java

## Einleitung
In der modernen Java-Entwicklung ist die Fähigkeit, **XPS-Dokumente** programmgesteuert zu erstellen, eine wertvolle Fähigkeit, besonders wenn Sie sie mit Grafiken wie gekachelten Bildern anreichern müssen. Aspose.Page für Java macht diesen Prozess unkompliziert und ermöglicht es Ihnen, sich auf das visuelle Design zu konzentrieren statt auf die Low‑Level-Dateiverarbeitung. In diesem Tutorial lernen Sie genau, wie man ein XPS-Dokument erstellt, **ein gekacheltes Bild hinzufügt** und das Ergebnis speichert, alles mit klaren, Schritt‑für‑Schritt‑Codebeispielen.

## Schnelle Antworten
- **Was macht Aspose.Page?** Es bietet eine High‑Level‑API zum Erzeugen und Manipulieren von XPS-Dokumenten in Java.  
- **Kann ich ein Bild kacheln?** Ja – verwenden Sie `XpsImageBrush` mit `XpsTileMode.Tile`.  
- **Brauche ich eine Lizenz?** Für den Produktionseinsatz ist eine temporäre oder kommerzielle Lizenz erforderlich.  
- **Welche Java-Version wird unterstützt?** Jede JDK 8+ ist kompatibel.  
- **Wie lange dauert die Implementierung?** Etwa 10–15 Minuten für ein einfaches gekacheltes Bild‑Szenario.

## Was bedeutet „XPS-Dokument erstellen“?
Eine XPS‑Datei (XML Paper Specification) ist ein festes Layout‑Dokumentformat, ähnlich wie PDF. Das programmgesteuerte Erstellen eines XPS‑Dokuments ermöglicht es Ihnen, druckbare, geräteunabhängige Dateien direkt aus Java‑Code zu erzeugen.

## Warum ein gekacheltes Bild hinzufügen?
Das Kacheln eines Bildes wiederholt die Grafik über einen definierten Bereich hinweg, was sich perfekt für Hintergründe, Wasserzeichen oder Musterfüllungen eignet. Mit Aspose.Page’s `XpsTileMode.Tile` können Sie dies mit nur wenigen Codezeilen erreichen.

## Voraussetzungen
1. **Java Development Kit (JDK)** – JDK 8 oder neuer installiert.  
2. **Aspose.Page für Java** – herunterladen von der [Website](https://releases.aspose.com/page/java/).  
3. **Ein beschreibbares Verzeichnis** – in dem die erzeugte XPS‑Datei gespeichert wird.

## Pakete importieren
Importieren Sie in Ihrem Java‑Projekt die erforderlichen Klassen:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Projekt einrichten
Fügen Sie die Aspose.Page‑JAR‑Dateien zu Ihrem Projekt‑Classpath hinzu und prüfen Sie, dass die Import‑Anweisungen ohne Fehler kompilieren.

### Schritt 2: XPS‑Dokument erstellen
Instanziieren Sie ein neues `XpsDocument`‑Objekt. Dies ist der Kern‑Container, der alle Seiten, Pfade und Ressourcen enthält.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Schritt 3: Pfad des gekachelten Bildes festlegen
Legen Sie das Bild, das Sie kacheln möchten (z. B. `R08LN_NN.jpg`), im Verzeichnis ab, das durch `dataDir` referenziert wird. Das Bild wird als Pinsel‑Muster verwendet.

### Schritt 4: Gekacheltes Bild hinzufügen
Erstellen Sie einen rechteckigen Pfad und füllen Sie ihn mit einem `XpsImageBrush`. Durch das Setzen des Tile‑Modus auf `Tile` wiederholt sich das Bild über das Rechteck.

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
Speichern Sie die XPS‑Datei auf dem Datenträger. Die Ausgabedatei enthält das von Ihnen gerade definierte gekachelte Bild.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Wiederholen Sie diese Schritte, wann immer Sie **ein gekacheltes Bild** zu anderen Seiten oder Formen im selben XPS‑Dokument hinzufügen müssen.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|---------|--------|
| Bild wird nicht angezeigt | Stellen Sie sicher, dass der Dateipfad (`dataDir + "R08LN_NN.jpg"`) korrekt ist und das Bild zugänglich ist. |
| Kachelmuster erscheint gestreckt | Passen Sie die Quell‑ und Ziel‑`Rectangle2D`‑Werte an, um die Kachelgröße zu steuern. |
| Deckkraft hat keinen Effekt | Stellen Sie sicher, dass die Deckkraft des Pinsels **nach** der Konfiguration des Tile‑Modus gesetzt wird. |

## Häufig gestellte Fragen

### Ist Aspose.Page mit allen Java‑Versionen kompatibel?
Aspose.Page ist so konzipiert, dass es mit verschiedenen Java‑Versionen funktioniert. Stellen Sie die Kompatibilität sicher, indem Sie die Dokumentation [hier](https://reference.aspose.com/page/java/) prüfen.

### Kann ich Aspose.Page für kommerzielle Projekte verwenden?
Ja, Aspose.Page bietet kommerzielle Lizenzen an. Kaufen Sie diese [hier](https://purchase.aspose.com/buy).

### Gibt es eine kostenlose Testversion?
Ja, erkunden Sie die Funktionen von Aspose.Page mit einer kostenlosen Testversion [hier](https://releases.aspose.com/).

### Wo finde ich Community‑Support und Diskussionen?
Beteiligen Sie sich an der Aspose.Page‑Community im [Forum](https://forum.aspose.com/c/page/39).

### Wie kann ich eine temporäre Lizenz für Aspose.Page erhalten?
Erwerben Sie eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2025-12-28  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
