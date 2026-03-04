---
date: 2025-12-23
description: Mühelos **XPS in PNG konvertieren** in Java mit Aspose.Page. Dieser Leitfaden
  zeigt, wie man XPS in Bilddateien rendert, mit einer zuverlässigen, entwicklerfreundlichen
  Lösung.
linktitle: Convert XPS to PNG in Java
second_title: Aspose.Page Java API
title: XPS nach PNG in Java konvertieren
url: /de/java/xps-conversion/to-png/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS nach PNG in Java konvertieren

## Einführung
In der dynamischen Welt der Softwareentwicklung entsteht häufig der Bedarf, **XPS nach PNG** (XML Paper Specification zu Portable Network Graphics) zu **konvertieren**. Um diese Aufgabe nahtlos in Java zu erledigen, bietet Aspose.Page eine leistungsstarke Lösung. In diesem Tutorial führen wir Sie durch den Prozess der Konvertierung von XPS zu PNG mit Aspose.Page für Java.

## Schnellantworten
- **Welche Bibliothek übernimmt die Konvertierung?** Aspose.Page für Java  
- **Welche Formate sind beteiligt?** XPS (Quelle) → PNG (Ausgabe)  
- **Benötige ich eine Lizenz für den Produktionseinsatz?** Ja, eine kommerzielle Lizenz ist erforderlich  
- **Kann ich die Bildauflösung festlegen?** Ja, über `PngSaveOptions.setResolution()`  
- **Ist es möglich, bestimmte Seiten auszuwählen?** Absolut – geben Sie die Seitennummern im Options‑Objekt an  

## Warum XPS nach PNG konvertieren?
Das Rendern von XPS zu Bilddateien ist nützlich, wenn Sie Dokumente im Web anzeigen, in Berichte einbetten oder Vorschaubilder (Thumbnails) erzeugen möchten. PNG bietet verlustfreie Kompression und breite Browserunterstützung, was es zu einer idealen Wahl für hochwertige visuelle Darstellungen von XPS‑Inhalten macht.

## Voraussetzungen
Bevor wir ins Tutorial einsteigen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1. **Java Development Kit (JDK):** Vergewissern Sie sich, dass das JDK auf Ihrem System installiert ist.  
2. **Aspose.Page für Java:** Laden Sie die Aspose.Page‑Bibliothek herunter und installieren Sie sie. Den Download‑Link finden Sie [hier](https://releases.aspose.com/page/java/).  
3. **Integrated Development Environment (IDE):** Wählen Sie eine Java‑kompatible IDE wie IntelliJ IDEA oder Eclipse.  

## Wie man XPS nach PNG in Java konvertiert
Im Folgenden finden Sie eine Schritt‑für‑Schritt‑Anleitung, die erklärt, **wie XPS‑Dokumente** in PNG‑Bilder umgewandelt werden, inklusive Code‑Snippets, die Sie direkt in Ihr Projekt übernehmen können.

### Pakete importieren
Importieren Sie in Ihrem Java‑Projekt die notwendigen Pakete, um die Funktionen von Aspose.Page zu nutzen. Fügen Sie die folgenden Import‑Anweisungen am Anfang Ihrer Java‑Datei ein:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

### Schritt 1: Dokumentverzeichnis festlegen
Definieren Sie den Ordner, der Ihre Quell‑XPS‑Datei enthält, und den Zielordner, in dem die PNG‑Dateien gespeichert werden sollen.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Schritt 2: XPS‑Dokument laden
Erzeugen Sie eine `XpsDocument`‑Instanz, die die Quell‑XPS‑Datei lädt.

```java
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Schritt 3: Optionen initialisieren
Konfigurieren Sie die PNG‑Ausgabeoptionen. Hier können Sie Glättung, Auflösung und die zu rendernden Seiten festlegen.

```java
// Initialize options object with necessary parameters.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### Schritt 4: Rendering‑Gerät erstellen
Erzeugen Sie ein `ImageDevice`, das die gerenderten Bilddaten hält.

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

### Schritt 5: Speichern und iterieren
Rendern Sie das XPS‑Dokument und schreiben Sie jedes erzeugte PNG‑Byte‑Array in eine Datei auf dem Datenträger.

```java
// Save XPS document to PNG using options and device
document.save(device, options);
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Close the Stream
        imageStream.close();
    }
}
```

Durch Befolgen dieser Schritte können Sie **XPS mühelos in Bilddateien** im PNG‑Format mit Aspose.Page für Java rendern.

## Fazit
Zusammenfassend vereinfacht Aspose.Page für Java den XPS‑zu‑PNG‑Konvertierungsprozess und bietet Entwicklern ein zuverlässiges und effizientes Werkzeug. Integrieren Sie diese Bibliothek in Ihre Java‑Projekte, um Aufgaben der Dokumentenmanipulation zu optimieren.

## Weitere häufig gestellte Fragen

**F: Kann ich nur ausgewählte Seiten einer XPS‑Datei konvertieren?**  
A: Absolut. Verwenden Sie die Methode `setPageNumbers` in `PngSaveOptions`, um die zu rendernden Seiten anzugeben.

**F: Welche Bildauflösung wird für hochwertige PNGs empfohlen?**  
A: Eine Auflösung von 300 dpi bietet ein gutes Gleichgewicht zwischen Qualität und Dateigröße, kann aber über `options.setResolution()` angepasst werden.

**F: Unterstützt die API eine multithreaded Konvertierung für große Dokumente?**  
A: Ja, Sie können die Konvertierungslogik in parallelen Threads ausführen, wobei jeder Thread eine andere Seite oder Dokumenten­partition verarbeitet.

**F: Wie gehe ich mit dem Speicherverbrauch um, wenn ich sehr große XPS‑Dateien konvertiere?**  
A: Verarbeiten Sie die Seiten sequenziell und schließen Sie den `FileOutputStream` nach jedem Schreibvorgang, wie im Beispielcode gezeigt.

**F: Gibt es eine Möglichkeit, benutzerdefinierte Metadaten zu den erzeugten PNG‑Dateien hinzuzufügen?**  
A: Während `PngSaveOptions` keine direkten Metadaten‑Felder bereitstellt, können Sie das PNG anschließend mit gängigen Bildbibliotheken nachträglich bearbeiten, um Metadaten einzubetten.

---

**Zuletzt aktualisiert:** 2025-12-23  
**Getestet mit:** Aspose.Page für Java 24.12 (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}