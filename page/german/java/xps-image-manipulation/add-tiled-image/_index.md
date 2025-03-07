---
title: Fügen Sie ein gekacheltes Bild in Java XPS hinzu
linktitle: Fügen Sie ein gekacheltes Bild in Java XPS hinzu
second_title: Aspose.Page Java-API
description: Entdecken Sie die nahtlose Manipulation von Java XPS-Dokumenten mit Aspose.Page. Erfahren Sie mit dieser Schritt-für-Schritt-Anleitung, wie Sie mühelos gekachelte Bilder hinzufügen.
weight: 11
url: /de/java/xps-image-manipulation/add-tiled-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fügen Sie ein gekacheltes Bild in Java XPS hinzu

## Einführung
In der dynamischen Welt der Java-Entwicklung wächst der Bedarf an effizienter Dokumentenbearbeitung und -erstellung ständig. Aspose.Page für Java erweist sich als leistungsstarkes Tool, das Entwicklern die Möglichkeit bietet, nahtlos mit XPS-Dokumenten zu arbeiten. Dieses Tutorial konzentriert sich auf eine bestimmte Aufgabe – das Hinzufügen eines gekachelten Bildes zu einem Java XPS-Dokument.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1. Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem System installiert ist.
2.  Aspose.Page für Java: Laden Sie Aspose.Page für Java von herunter und installieren Sie es[Webseite](https://releases.aspose.com/page/java/).
3. Ihr Dokumentverzeichnis: Wählen oder erstellen Sie ein Verzeichnis, in dem Sie Ihr XPS-Dokument speichern möchten.
## Pakete importieren
Importieren Sie in Ihrem Java-Projekt die erforderlichen Pakete, um die Aspose.Page-Funktionen zu nutzen:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
Lassen Sie uns nun den Prozess des Hinzufügens eines gekachelten Bildes zu einem Java XPS-Dokument in klare, überschaubare Schritte unterteilen.
## Schritt 1: Richten Sie Ihr Projekt ein
Beginnen Sie mit der Einrichtung Ihres Java-Projekts und stellen Sie sicher, dass Aspose.Page für Java ordnungsgemäß integriert ist.
## Schritt 2: XPS-Dokument erstellen
Initialisieren Sie ein neues XPS-Dokument mit dem folgenden Code:
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie ein neues XPS-Dokument
XpsDocument doc = new XpsDocument();
```
## Schritt 3: Definieren Sie den Pfad für gekachelte Bilder
Geben Sie den Pfad zum gekachelten Bild an, das Sie dem XPS-Dokument hinzufügen möchten.
## Schritt 4: Gekacheltes Bild hinzufügen
Verwenden Sie den folgenden Codeausschnitt, um dem XPS-Dokument ein gekacheltes Bild hinzuzufügen:
```java
// Kachelbild
// Mit ImageBrush gefülltes Rechteck rechts oben unten
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```
## Schritt 5: Speichern Sie das Dokument
Speichern Sie abschließend das resultierende XPS-Dokument mit dem folgenden Code:
```java
// Speichern Sie das resultierende XPS-Dokument
doc.save(dataDir + "AddTiledImage_out.xps"); 
```
Wiederholen Sie diese Schritte, um mit Aspose.Page mühelos ein gekacheltes Bild in Ihr Java XPS-Dokument zu integrieren.
## Abschluss
Aspose.Page für Java optimiert den Prozess der Arbeit mit XPS-Dokumenten und bietet Entwicklern eine effiziente Lösung für die Dokumentbearbeitung. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie mühelos ein gekacheltes Bild zu Ihrem Java XPS-Dokument hinzufügen.

## FAQs
### Ist Aspose.Page mit allen Java-Versionen kompatibel?
 Aspose.Page ist für die Verwendung mit verschiedenen Java-Versionen konzipiert. Stellen Sie die Kompatibilität sicher, indem Sie die Dokumentation prüfen[Hier](https://reference.aspose.com/page/java/).
### Kann ich Aspose.Page für kommerzielle Projekte verwenden?
Ja, Aspose.Page bietet kommerzielle Lizenzen an. Kaufen Sie sie[Hier](https://purchase.aspose.com/buy).
### Gibt es eine kostenlose Testversion?
 Ja, erkunden Sie die Funktionen von Aspose.Page mit einer kostenlosen Testversion[Hier](https://releases.aspose.com/).
### Wo finde ich Community-Unterstützung und Diskussionen?
 Treten Sie mit der Aspose.Page-Community auf der Seite in Kontakt[Forum](https://forum.aspose.com/c/page/39).
### Wie kann ich eine temporäre Lizenz für Aspose.Page erhalten?
 Erwerben Sie eine temporäre Lizenz[Hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
