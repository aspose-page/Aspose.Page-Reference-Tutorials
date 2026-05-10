---
date: 2026-03-16
description: Lernen Sie, wie asp asp und wie man ein Bild zu XPS-Dokumenten in Java
  mit Aspose.Page hinzufügt. Dieser Leitfaden führt Sie schnell durch das Hinzufügen
  von Bildern.
linktitle: Add Image in Java XPS
second_title: Aspose.Page Java API
title: asp asp – Bild in Java XPS‑Dokumente einfügen mit Aspose.Page
url: /de/java/xps-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# asp asp – Bild zu Java XPS-Dokumenten mit Aspose.Page hinzufügen

Das Hinzufügen von Bildern zu XPS-Dateien ist ein häufiges Bedürfnis von Java‑Entwicklern, die Berichte, Rechnungen oder andere visuelle Dokumente anreichern möchten. In diesem Tutorial lernen Sie **wie man ein Bild hinzufügt** zu einem XPS-Dokument mithilfe der leistungsstarken Aspose.Page for Java‑Bibliothek, und Sie sehen, warum der **asp asp**‑Ansatz den Prozess zuverlässig und schnell macht. Wir gehen jeden Schritt durch, erklären, warum jede Zeile wichtig ist, und geben Ihnen praktische Tipps, um häufige Fallstricke zu vermeiden.

## Schnelle Antworten
- **Welche Bibliothek wird benötigt?** Aspose.Page for Java  
- **Kann ich mehrere Bilder hinzufügen?** Ja – wiederholen Sie die Bild‑Hinzufügungs‑Schritte für jedes Bild  
- **Unterstützte Bildformate?** TIFF, JPEG, PNG, GIF (und andere, die von .NET unterstützt werden)  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Evaluierung; eine kommerzielle Lizenz ist für die Produktion erforderlich  
- **Typische Implementierungszeit?** Etwa 10‑15 Minuten für das Einfügen eines einfachen Bildes  

## asp asp: Bilder zu XPS-Dokumenten hinzufügen
Die **asp asp**‑Methodik basiert auf einem einfachen, wiederholbaren Muster: ein Dokument erstellen, einen Pfad definieren, einen Image‑Brush anwenden und speichern. Dieses Muster hält Ihren Code sauber und erleichtert das spätere Einfügen zusätzlicher Grafiken.

## Was ist Aspose.Page für Java?
Aspose.Page ist eine dedizierte API, mit der Sie XPS‑ (XML Paper Specification) Dokumente erstellen, bearbeiten und rendern können, ohne den Microsoft XPS Viewer zu benötigen. Sie abstrahiert die Low‑Level‑Details des XPS‑Markups, sodass Sie sich auf das visuelle Layout Ihrer Dokumente konzentrieren können.

## Warum Bilder zu XPS hinzufügen?
- **Professionelles Aussehen:** Bilder wie Logos, Diagramme oder Produktfotos verleihen Ihren Dokumenten ein gehobenes Erscheinungsbild.  
- **Markenkonsistenz:** Das Einbetten Ihres Firmenlogos stellt sicher, dass jede erzeugte Rechnung oder jeder Bericht Ihre Marke trägt.  
- **Dynamischer Inhalt:** Sie können programmgesteuert QR‑Codes, Barcodes oder benutzergenerierte Grafiken zur Laufzeit einfügen.

## Einführung
Das Hinzufügen von Bildern zu XPS‑Dokumenten ist in vielen Java‑Anwendungen ein häufiges Bedürfnis, von der Berichtserstellung bis zur Dokumentenverarbeitung. Aspose.Page für Java vereinfacht diese Aufgabe, indem es effiziente Methoden bereitstellt, um Bilder nahtlos in Ihre XPS‑Dateien zu integrieren. In diesem Tutorial zeigen wir, wie Sie ein Bild zu einem XPS‑Dokument mit Aspose.Page für Java hinzufügen.

## Voraussetzungen
Bevor Sie in das Tutorial einsteigen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:
1. **Aspose.Page for Java Bibliothek** – Laden Sie die Aspose.Page for Java‑Bibliothek von der [Website](https://releases.aspose.com/page/java/) herunter und installieren Sie sie.  
2. **Java-Entwicklungsumgebung** – Stellen Sie sicher, dass Sie eine Java‑Entwicklungsumgebung auf Ihrem Rechner eingerichtet haben.

Jetzt gehen wir zu den nächsten Schritten über.

## Pakete importieren
Importieren Sie in Ihrem Java-Projekt die erforderlichen Aspose.Page for Java‑Pakete, um auf die benötigten Klassen und Methoden zuzugreifen.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.geom.Rectangle2D;
```

## Schritt 1: Dokumentverzeichnis einrichten
Definieren Sie den Pfad zu Ihrem Dokumentverzeichnis, in dem das XPS‑Dokument und die Bilddateien gespeichert werden.

```java
String dataDir = "Your Document Directory";
```

## Schritt 2: Neues XPS-Dokument erstellen
Initialisieren Sie ein neues XPS‑Dokument mit dem folgenden Code‑Snippet:

```java
XpsDocument doc = new XpsDocument();
```

## Schritt 3: Bild zu XPS-Dokument hinzufügen
Um ein Bild hinzuzufügen, erstellen Sie einen Pfad im XPS‑Dokument und setzen den Image‑Brush mit der bereitgestellten Bilddatei und den Koordinaten.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.setRenderTransform(doc.createMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f));
path.setFill(doc.createImageBrush(dataDir + "QL_logo_color.tif", new Rectangle2D.Double(0f, 0f, 258.24f, 56.64f), new Rectangle2D.Double(50f, 20f, 193.68f, 42.48f)));
```

## Schritt 4: Ergebnis-XPS-Dokument speichern
Speichern Sie das modifizierte XPS‑Dokument in Ihrem angegebenen Verzeichnis.

```java
doc.save(dataDir + "AddImage_out.xps");
```

Wiederholen Sie diese Schritte, um weitere Bilder hinzuzufügen oder die vorhandenen nach den Anforderungen Ihres Projekts anzupassen.

## Häufige Probleme und Lösungen
- **Bild erscheint verzerrt:** Stellen Sie sicher, dass das Quellrechteck (`new Rectangle2D.Double(0f, 0f, 258.24f, 56.64f)`) den tatsächlichen Abmessungen Ihres Bildes entspricht. Passen Sie das Zielrechteck an, um das Seitenverhältnis beizubehalten.  
- **Wasserzeichen erscheint:** Wenn Sie den Code ohne gültige Lizenz ausführen, fügt Aspose ein Wasserzeichen hinzu. Aktivieren Sie Ihre Lizenz frühzeitig in der Anwendung, um dies zu vermeiden.  
- **FileNotFoundException:** Stellen Sie sicher, dass `dataDir` auf den richtigen Ordner zeigt und dass der Bilddateiname (`QL_logo_color.tif`) mit der Datei auf der Festplatte übereinstimmt.

## Fazit
Herzlichen Glückwunsch! Sie haben erfolgreich **wie man ein Bild hinzufügt** zu einem XPS‑Dokument mit Aspose.Page für Java gelernt. Diese Fähigkeit ist unbezahlbar, um die visuelle Attraktivität Ihrer Java‑Anwendungen und Dokumente zu steigern. Durch das Befolgen des **asp asp**‑Musters können Sie dieses Beispiel leicht erweitern, um mehrere Grafiken einzufügen, sie dynamisch zu skalieren oder sogar Diagramme on‑the‑fly zu erzeugen.

### Häufig gestellte Fragen
### Kann ich mehrere Bilder zum selben XPS‑Dokument mit Aspose.Page für Java hinzufügen?
Ja, Sie können mehrere Bilder hinzufügen, indem Sie die in diesem Tutorial beschriebenen Schritte für jedes Bild wiederholen.

### Welche Bildformate werden von Aspose.Page für Java unterstützt?
Aspose.Page für Java unterstützt verschiedene Bildformate, darunter TIFF, JPEG, PNG und GIF.

### Gibt es eine Testversion von Aspose.Page für Java?
Ja, Sie können eine kostenlose Testversion von Aspose.Page für Java über [diesen Link](https://releases.aspose.com/) erhalten.

### Wie kann ich eine temporäre Lizenz für Aspose.Page für Java erhalten?
Sie können eine temporäre Lizenz über [diesen Link](https://purchase.aspose.com/temporary-license/) erhalten.

### Wo finde ich zusätzlichen Support oder kann über Probleme im Zusammenhang mit Aspose.Page für Java diskutieren?
Besuchen Sie das [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39), um Hilfe zu erhalten, Erfahrungen zu teilen und mit der Aspose.Page‑Community in Kontakt zu treten.

---

**Zuletzt aktualisiert:** 2026-03-16  
**Getestet mit:** Aspose.Page für Java 23.12 (zum Zeitpunkt des Schreibens die neueste Version)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}