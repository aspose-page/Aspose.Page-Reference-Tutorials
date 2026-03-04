---
date: 2025-12-21
description: Erfahren Sie, wie Sie die Auflösung beim Konvertieren von XPS zu BMP
  in Java mit Aspose.Page festlegen. Dieser Leitfaden zur Java‑Bildkonvertierung sorgt
  für hochwertige Ergebnisse.
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: Wie man die Auflösung beim Konvertieren von XPS zu BMP in Java festlegt
url: /de/java/xps-conversion/to-bmp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS nach BMP in Java konvertieren

## Einleitung
Willkommen zu dieser Schritt‑für‑Schritt‑Anleitung, **wie man die Auflösung einstellt**, wenn man XPS (XML Paper Specification)-Dateien in das BMP (Bitmap)-Format in Java mit Aspose.Page konvertiert. Aspose.Page für Java ist eine leistungsstarke Bibliothek, die umfassende Funktionen für die Arbeit mit XPS-Dokumenten bietet. In diesem Tutorial führen wir Sie durch den Prozess, XPS-Dateien mühelos in BMP‑Bilder zu konvertieren.

## Schnelle Antworten
- **Welche Bibliothek sollte ich verwenden?** Aspose.Page für Java bietet die vollständigsten XPS → BMP-Konvertierungsfunktionen.  
- **Kann ich die Bildqualität steuern?** Ja – verwenden Sie `BmpSaveOptions`, um die Auflösung und den Glättungsmodus festzulegen.  
- **Muss ich nur bestimmte Seiten konvertieren?** Absolut, `options.setPageNumbers()` ermöglicht die Auswahl konkreter Seiten.  
- **Ist dies eine echte Java-Bildkonvertierung?** Die API rendert XPS‑Seiten direkt zu Bitmap‑Daten, sodass keine Zwischenschritte nötig sind.  
- **Welche Java-Version wird unterstützt?** Alle modernen Java‑Versionen (8 und höher) sind kompatibel.

## Welchen Zweck hat das Einstellen der Auflösung?
Die Auflösung bestimmt die Anzahl der Punkte pro Zoll (DPI) im erzeugten BMP‑Bild. Ein höheres DPI liefert schärfere Bilder, was für den Druck oder detaillierte Grafikarbeiten entscheidend ist. Durch Anpassen der Auflösung erhalten Sie die volle Kontrolle über die Ausgabequalität Ihres **java convert xps**‑Workflows.

## Warum Aspose.Page für die XPS → BMP-Konvertierung verwenden?
- **Hohe Treue** – bewahrt die Vektorqualität des ursprünglichen XPS.  
- **Feinkörnige Kontrolle** – Sie können DPI, Glättung einstellen und sogar bestimmte Seiten zum Konvertieren auswählen.  
- **Keine externen Abhängigkeiten** – reines Java, keine nativen Bibliotheken erforderlich.  
- **Skalierbar** – funktioniert sowohl für Einzelseiten‑Dokumente als auch für große mehrseitige XPS‑Dateien.

## Voraussetzungen
Bevor Sie in den Konvertierungsprozess einsteigen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- **Java-Entwicklungsumgebung** – Java 8 oder neuer auf Ihrem Rechner installiert.  
- **Aspose.Page für Java‑Bibliothek** – Laden Sie die Aspose.Page für Java‑Bibliothek herunter und binden Sie sie in Ihr Projekt ein. Die Bibliothek finden Sie [hier](https://releases.aspose.com/page/java/).  
- **Beispiel‑XPS‑Datei** – Bereiten Sie ein Beispiel‑XPS‑Dokument vor, das Sie in BMP konvertieren möchten.

## Pakete importieren
Binden Sie die erforderlichen Aspose.Page‑Pakete in Ihren Java‑Code ein:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Wie man die Auflösung für die XPS‑zu‑BMP‑Konvertierung einstellt
Nachfolgend finden Sie eine prägnante, nummerierte Schritt‑für‑Schritt‑Anleitung, die genau zeigt, wo und wie die Auflösung eingestellt wird, sowie wie Sie **bestimmte Seiten konvertieren**.

### Schritt 1: XPS‑Dokument laden
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Schritt 2: Optionen initialisieren (Auflösung & Seitenauswahl)
```java
// Initialize options object with necessary parameters.
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);

// Primary setting – this is the **how to set resolution** part.
options.setResolution(300);               // 300 DPI for high‑quality output

// Optional: convert specific pages only (e.g., pages 1, 2, and 6)
options.setPageNumbers(new int[]{1, 2, 6});
```

### Schritt 3: Rendering‑Gerät erstellen
```java
// Create rendering device for BMP format
ImageDevice device = new ImageDevice();
```

### Schritt 4: Dokument mit Optionen speichern
```java
// Save XPS document to BMP using options and device
document.save(device, options);
```

### Schritt 5: Durch gerenderte Bilder iterieren und Dateien schreiben
```java
// Iterate through document partitions
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoBMP" + "_" + (i + 1) + "_" + (j + 1) + ".bmp");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```

Wiederholen Sie diese Schritte für jede weitere Anpassung oder Modifikation, die Sie im Konvertierungsprozess benötigen.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| **BMP‑Ausgabe von schlechter Qualität** | Stellen Sie sicher, dass `options.setResolution()` auf einen Wert ≥ 300 DPI gesetzt ist. |
| **Nur ein Teil des Dokuments wird konvertiert** | Stellen Sie sicher, dass `options.setPageNumbers()` alle gewünschten Seitenindizes enthält. |
| **OutOfMemoryError bei großen XPS‑Dateien** | Verarbeiten Sie das Dokument in kleineren Partitionen oder erhöhen Sie die JVM‑Heap‑Größe (`-Xmx`). |
| **Datei nicht gefunden** | Überprüfen Sie den Pfad `dataDir` und ob die Eingabe‑XPS‑Datei existiert. |

## Häufig gestellte Fragen
### F: Kann ich die Auflösung der BMP‑Bilder anpassen?
A: Ja, Sie können die Auflösung anpassen, indem Sie den Parameter `options.setResolution()` im Code ändern.

### F: Ist Aspose.Page mit verschiedenen Java‑Versionen kompatibel?
A: Ja, Aspose.Page unterstützt eine breite Palette von Java‑Versionen. Stellen Sie sicher, dass Sie eine kompatible Version installiert haben.

### F: Wie kann ich XPS‑Dateien aus einem bestimmten Seitenbereich konvertieren?
A: Verwenden Sie die Methode `options.setPageNumbers()`, um die Seitenzahlen anzugeben, die Sie konvertieren möchten.

### F: Gibt es weitere von Aspose.Page unterstützte Ausgabeformate?
A: Ja, Aspose.Page unterstützt verschiedene Ausgabeformate. Siehe die Dokumentation für eine vollständige Liste.

### F: Wo finde ich zusätzliche Hilfe oder Support?
A: Besuchen Sie das [Aspose.Page Forum](https://forum.aspose.com/c/page/39) für Community‑Support und Diskussionen.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Page for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}