---
date: 2025-12-28
description: Erfahren Sie, wie Sie in Java mit Aspose.Page Bilder zu XPS‑Dokumenten
  hinzufügen. Dieser Schritt‑für‑Schritt‑Leitfaden zeigt Ihnen, wie Sie mühelos Bilder
  einfügen und Ihre Dokumentenverarbeitung verbessern.
linktitle: Add Image in Java XPS
second_title: Aspose.Page Java API
title: Wie man ein Bild zu Java XPS-Dokumenten hinzufügt – Eine einfache Anleitung
  mit Aspose.Page
url: /de/java/xps-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# So fügen Sie ein Bild zu Java XPS-Dokumenten mit Aspose.Page hinzu

Das Hinzufügen von Bildern zu XPS-Dateien ist ein häufiges Bedürfnis für Java‑Entwickler, die Berichte, Rechnungen oder andere visuelle Dokumente anreichern müssen. In diesem Tutorial erfahren Sie **wie man ein Bild hinzufügt** zu einem XPS‑Dokument mithilfe der leistungsstarken Aspose.Page‑Bibliothek für Java. Wir gehen jeden Schritt durch, erklären, warum jede Zeile wichtig ist, und geben Ihnen Tipps, um typische Fallstricke zu vermeiden.

## Quick Answers
- **Welche Bibliothek wird benötigt?** Aspose.Page for Java  
- **Kann ich mehrere Bilder hinzufügen?** Ja – wiederholen Sie die Bild‑Hinzufüg‑Schritte für jedes Bild  
- **Unterstützte Bildformate?** TIFF, JPEG, PNG, GIF (und andere, die von .NET unterstützt werden)  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Evaluierung; eine kommerzielle Lizenz ist für die Produktion erforderlich  
- **Typische Implementierungszeit?** Etwa 10‑15 Minuten für ein einfaches Bild‑Einfügen

## Introduction
Das Hinzufügen von Bildern zu XPS‑Dokumenten ist in vielen Java‑Anwendungen ein gängiges Anliegen, von der Berichtserstellung bis zur Dokumentenverarbeitung. Aspose.Page for Java vereinfacht diese Aufgabe, indem es effiziente Methoden bereitstellt, um Bilder nahtlos in Ihre XPS‑Dateien zu integrieren. In diesem Tutorial zeigen wir, wie Sie ein Bild zu einem XPS‑Dokument mit Aspose.Page for Java hinzufügen.

## Prerequisites
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:
1. **Aspose.Page for Java Library** – Laden Sie die Aspose.Page for Java‑Bibliothek von der [Website](https://releases.aspose.com/page/java/) herunter und installieren Sie sie.  
2. **Java Development Environment** – Stellen Sie sicher, dass Sie eine Java‑Entwicklungsumgebung auf Ihrem Rechner eingerichtet haben.

Jetzt gehen wir zu den nächsten Schritten über.

## Import Packages
Importieren Sie in Ihrem Java‑Projekt die erforderlichen Aspose.Page for Java‑Pakete, um auf die benötigten Klassen und Methoden zugreifen zu können.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.geom.Rectangle2D;
```

## Step 1: Set Up Document Directory
Definieren Sie den Pfad zu Ihrem Dokumenten‑Verzeichnis, in dem das XPS‑Dokument und die Bilddateien gespeichert werden.

```java
String dataDir = "Your Document Directory";
```

## Step 2: Create a New XPS Document
Initialisieren Sie ein neues XPS‑Dokument mit dem folgenden Code‑Snippet:

```java
XpsDocument doc = new XpsDocument();
```

## Step 3: Add Image to XPS Document
Um ein Bild hinzuzufügen, erstellen Sie einen Pfad im XPS‑Dokument und setzen den Image‑Brush mit der bereitgestellten Bilddatei und den Koordinaten.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.setRenderTransform(doc.createMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f));
path.setFill(doc.createImageBrush(dataDir + "QL_logo_color.tif", new Rectangle2D.Double(0f, 0f, 258.24f, 56.64f), new Rectangle2D.Double(50f, 20f, 193.68f, 42.48f)));
```

## Step 4: Save Resultant XPS Document
Speichern Sie das modifizierte XPS‑Dokument in dem von Ihnen angegebenen Verzeichnis.

```java
doc.save(dataDir + "AddImage_out.xps");
```

Wiederholen Sie diese Schritte, um weitere Bilder hinzuzufügen oder die vorhandenen nach den Anforderungen Ihres Projekts anzupassen.

## Conclusion
Herzlichen Glückwunsch! Sie haben erfolgreich **wie man ein Bild hinzufügt** zu einem XPS‑Dokument mit Aspose.Page for Java erlernt. Diese Fähigkeit ist unverzichtbar, um die visuelle Attraktivität Ihrer Java‑Anwendungen und Dokumente zu steigern.

### Frequently Asked Questions
### Kann ich mehrere Bilder zum selben XPS‑Dokument mit Aspose.Page for Java hinzufügen?
Ja, Sie können mehrere Bilder hinzufügen, indem Sie die in diesem Tutorial beschriebenen Schritte für jedes Bild wiederholen.

### Welche Bildformate werden von Aspose.Page for Java unterstützt?
Aspose.Page for Java unterstützt verschiedene Bildformate, darunter TIFF, JPEG, PNG und GIF.

### Gibt es eine Testversion von Aspose.Page for Java?
Ja, Sie können eine kostenlose Testversion von Aspose.Page for Java über [diesen Link](https://releases.aspose.com/) erhalten.

### Wie kann ich eine temporäre Lizenz für Aspose.Page for Java erhalten?
Sie können eine temporäre Lizenz über [diesen Link](https://purchase.aspose.com/temporary-license/) erhalten.

### Wo finde ich zusätzlichen Support oder Diskussionen zu Problemen mit Aspose.Page for Java?
Besuchen Sie das [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39), um Hilfe zu erhalten, Erfahrungen zu teilen und mit der Aspose.Page‑Community in Kontakt zu treten.

## Additional Tips & Common Pitfalls
- **Path Geometry Accuracy** – Stellen Sie sicher, dass die SVG‑artige Pfad‑Zeichenkette den Abmessungen Ihres Bildes entspricht; andernfalls kann das Bild gestreckt oder abgeschnitten erscheinen.  
- **Image Brush Scaling** – Die `createImageBrush`‑Methode verwendet Quell‑ und Ziel‑Rechtecke; das Anpassen dieser Werte ermöglicht eine präzise Steuerung von Positionierung und Skalierung.  
- **License Activation** – Wenn Sie den Code ohne gültige Lizenz ausführen, fügt Aspose dem erzeugten XPS‑File ein Wasserzeichen hinzu.

---

**Last Updated:** 2025-12-28  
**Tested With:** Aspose.Page for Java 23.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}