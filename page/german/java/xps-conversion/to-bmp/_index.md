---
date: 2026-03-08
description: Lernen Sie, wie Sie XPS in BMP in Java konvertieren und die BMP‑Auflösung
  mit der Aspose.Page Java‑Bildkonvertierungsbibliothek festlegen. Dieser Leitfaden
  behandelt hochwertige Ausgaben und speicherschonende Tipps.
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: XPS in BMP in Java konvertieren – Auflösung für hochwertige Ausgabe festlegen
url: /de/java/xps-conversion/to-bmp/
weight: 10
---

-backtop-button >}}

Make sure to keep formatting exactly.

Check any stray spaces.

Now produce final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS in BMP in Java konvertieren

## Einleitung
Willkommen zu dieser Schritt‑für‑Schritt‑Anleitung, wie Sie **XPS in BMP** in Java konvertieren und die Auflösung für optimale Bildqualität mit Aspose.Page festlegen. Egal, ob Sie eine Druckpipeline aufbauen, Thumbnails erzeugen oder hochauflösende Grafiken benötigen, die Steuerung des DPI gibt Ihnen die Flexibilität, jede Anforderung zu erfüllen.

## Schnelle Antworten
- **Welche Bibliothek sollte ich verwenden?** Aspose.Page für Java ist die umfassendste **java image conversion library** für XPS → BMP.  
- **Kann ich die Bildqualität steuern?** Ja – verwenden Sie `BmpSaveOptions`, um die **BMP-Auflösung** und den Glättungsmodus festzulegen.  
- **Wie vermeide ich OutOfMemoryError in Java beim Verarbeiten großer XPS‑Dateien?** Rendern Sie Seiten in Partitionen oder erhöhen Sie den JVM‑Heap (`-Xmx`).  
- **Muss ich nur bestimmte Seiten konvertieren?** Absolut, `options.setPageNumbers()` ermöglicht das Auswählen genauer Seiten.  
- **Welche Java‑Versionen werden unterstützt?** Alle modernen Java‑Versionen (8 und höher) funktionieren nahtlos.

## Wofür dient das Einstellen der Auflösung?
Die Auflösung bestimmt die Anzahl der Punkte pro Zoll (DPI) im erzeugten BMP‑Bild. Ein höheres DPI liefert schärfere Bilder, was für den Druck oder detaillierte Grafikarbeiten unerlässlich ist. Das Anpassen der Auflösung gibt Ihnen die volle Kontrolle über die Ausgabequalität Ihres **convert xps to bmp**‑Workflows.

## Warum Aspose.Page für die XPS → BMP‑Konvertierung verwenden?
- **Hohe Treue** – bewahrt die Vektorqualität des ursprünglichen XPS.  
- **Fein abgestimmte Kontrolle** – Sie können DPI, Glättung einstellen und sogar bestimmte Seiten zur Konvertierung auswählen.  
- **Keine externen Abhängigkeiten** – reines Java, keine nativen Bibliotheken erforderlich.  
- **Skalierbar** – funktioniert sowohl für einseitige Dokumente als auch für große mehrseitige XPS‑Dateien.  

## Voraussetzungen
Bevor Sie in den Konvertierungsprozess eintauchen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- **Java-Entwicklungsumgebung** – Java 8 oder neuer auf Ihrem Rechner installiert.  
- **Aspose.Page für Java Bibliothek** – Laden Sie die Aspose.Page für Java Bibliothek herunter und binden Sie sie in Ihr Projekt ein. Die Bibliothek finden Sie [hier](https://releases.aspose.com/page/java/).  
- **Beispiel‑XPS‑Datei** – Bereiten Sie ein Beispiel‑XPS‑Dokument vor, das Sie in BMP konvertieren möchten.

## Pakete importieren
Binden Sie die erforderlichen Aspose.Page‑Pakete in Ihren Java‑Code ein:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Wie man die Auflösung für die XPS‑zu‑BMP‑Konvertierung festlegt
Nachfolgend finden Sie eine knappe, nummerierte Schritt‑für‑Schritt‑Anleitung, die genau zeigt, wo und wie die Auflösung eingestellt wird, sowie wie Sie **bestimmte Seiten konvertieren**.

### Schritt 1: XPS‑Dokument laden
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Schritt 2: Optionen initialisieren (Auflösung & Seitenauswahl)
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

Wiederholen Sie diese Schritte für jede zusätzliche Anpassung oder Modifikation, die Sie im Konvertierungsprozess benötigen.

## Wie man OutOfMemoryError in Java beim Konvertieren großer XPS‑Dateien vermeidet
- **In Partitionen verarbeiten** – Das Beispiel rendert das Dokument bereits in Partitionen (`device.getResult()`), was den Speicherbedarf reduziert.  
- **JVM‑Heap erhöhen** – Verwenden Sie das `-Xmx`‑Flag (z. B. `-Xmx2g`), um mehr Speicher für große Dokumente zuzuweisen.  
- **Ressourcen freigeben** – Rufen Sie `document.close()` auf, wenn Sie fertig sind, um native Ressourcen freizugeben.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|---------|--------|
| **BMP‑Ausgabe von geringer Qualität** | Stellen Sie sicher, dass `options.setResolution()` auf einen Wert ≥ 300 DPI gesetzt ist. |
| **Nur ein Teil des Dokuments wird konvertiert** | Stellen Sie sicher, dass `options.setPageNumbers()` alle gewünschten Seitenindizes enthält. |
| **OutOfMemoryError bei großen XPS‑Dateien** | Verarbeiten Sie das Dokument in kleineren Partitionen oder erhöhen Sie die JVM‑Heap‑Größe (`-Xmx`). |
| **Datei nicht gefunden** | Überprüfen Sie den Pfad `dataDir` und ob die Eingabe‑XPS‑Datei existiert. |

## Häufig gestellte Fragen
### Q: Kann ich die Auflösung der BMP‑Bilder anpassen?
A: Ja, Sie können die Auflösung anpassen, indem Sie den Parameter `options.setResolution()` im Code ändern.

### Q: Ist Aspose.Page mit verschiedenen Java‑Versionen kompatibel?
A: Ja, Aspose.Page unterstützt eine breite Palette von Java‑Versionen. Stellen Sie sicher, dass Sie eine kompatible Version installiert haben.

### Q: Wie kann ich XPS‑Dateien aus einem bestimmten Seitenbereich konvertieren?
A: Verwenden Sie die Methode `options.setPageNumbers()`, um die Seitenzahlen anzugeben, die Sie konvertieren möchten.

### Q: Gibt es weitere Ausgabeformate, die von Aspose.Page unterstützt werden?
A: Ja, Aspose.Page unterstützt verschiedene Ausgabeformate. Siehe die Dokumentation für eine umfassende Liste.

### Q: Wo finde ich zusätzliche Hilfe oder Support?
A: Besuchen Sie das [Aspose.Page Forum](https://forum.aspose.com/c/page/39) für Community‑Support und Diskussionen.

---

**Last Updated:** 2026-03-08  
**Tested With:** Aspose.Page for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}