---
date: 2025-11-29
description: Erfahren Sie, wie Sie XPS in Java mit Aspose.Page Java als PDF speichern.
  Folgen Sie unserer Schritt‑für‑Schritt‑Anleitung für eine effiziente XPS‑zu‑PDF‑Konvertierung
  und PDF‑Komprimierungseinstellungen.
linktitle: Convert XPS to PDF in Java using Aspose.Page Java
second_title: Aspose.Page Java API
title: XPS in PDF mit Java und Aspose.Page Java konvertieren
url: /de/java/file-merging/xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS in PDF in Java mit Aspose.Page Java konvertieren

## Einleitung
In diesem Tutorial lernen Sie **wie Sie XPS in PDF in Java mit Aspose.Page Java konvertieren**, einer robusten Bibliothek, die für die Java‑Dokumentkonvertierung entwickelt wurde. Egal, ob Sie Rechnungen stapelweise verarbeiten, druckbare Berichte erzeugen oder einfach alte XPS‑Dateien migrieren müssen – Aspose.Page Java erledigt die Aufgabe schnell, zuverlässig und vollständig konfigurierbar.

## Schnelle Antworten
- **Welche Bibliothek übernimmt die XPS‑zu‑PDF‑Konvertierung?** Aspose.Page Java  
- **Wie lange dauert eine einfache Konvertierung?** In der Regel weniger als eine Sekunde für eine einseitige XPS‑Datei.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion funktioniert für die Evaluierung; für die Produktion ist eine Lizenz erforderlich.  
- **Kann ich die PDF‑Kompression steuern?** Ja – verwenden Sie `PdfSaveOptions`, um Bild‑ und Textkompression festzulegen.  
- **Welche Java‑Version wird benötigt?** Java 8 oder höher (JDK 11+ empfohlen).

## Was ist Aspose.Page Java?
Aspose.Page Java ist eine **leistungsstarke API**, die Entwicklern ermöglicht, XPS‑Dokumente programmgesteuert zu erstellen, zu bearbeiten und zu konvertieren. Sie unterstützt das Rendern von XPS zu PDF, PNG, JPEG und anderen Formaten und bietet feinkörnige Kontrolle über Ausgabeeinstellungen wie **PDF‑Kompression festlegen**.

## Warum Aspose.Page Java für die XPS‑zu‑PDF‑Konvertierung verwenden?
- **Zero‑Dependency‑Rendering** – keine nativen Bibliotheken oder externen Tools erforderlich.  
- **Genaues Layout‑Preserving** – die PDF‑Ausgabe spiegelt das ursprüngliche XPS‑Aussehen wider.  
- **Vollständige Kontrolle über die PDF‑Ausgabe** – Sie können Bildqualität anpassen, Kompressionsalgorithmen wählen und bestimmte Seiten zum Rendern auswählen.  
- **Plattformübergreifend** – funktioniert unter Windows, Linux und macOS mit jedem gängigen JDK.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java Development Kit (JDK) 8+** – das neueste JDK wird für Leistung und Sicherheit empfohlen.  
2. **Aspose.Page for Java Bibliothek** – laden Sie das JAR von der offiziellen [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) herunter.  
3. Eine **IDE** (IntelliJ IDEA, Eclipse, VS Code) oder ein einfacher Texteditor plus Befehlszeilen‑Build‑Tools (Maven/Gradle).  

## Pakete importieren
Fügen Sie die erforderlichen Importe zu Ihrer Java‑Klasse hinzu, damit Sie mit XPS‑Dokumenten und PDF‑Ausgabe arbeiten können.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.rendering.pdf.PdfDevice;
import com.aspose.xps.rendering.pdf.PdfSaveOptions;
import com.aspose.xps.rendering.pdf.PdfImageCompression;
import com.aspose.xps.rendering.pdf.PdfTextCompression;
import java.io.FileOutputStream;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Dokumentverzeichnis festlegen
Definieren Sie den Ordner, der Ihre Quell‑XPS‑Datei enthält und in dem das PDF gespeichert werden soll.

```java
String dataDir = "C:/MyDocuments/XpsFiles/";   // <-- replace with your actual path
```

### Schritt 2: PDF‑Ausgabestream initialisieren
Erstellen Sie einen `FileOutputStream`, der auf die Zieldatei PDF zeigt.

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

> **Pro‑Tipp:** Verwenden Sie `try‑with‑resources`, um den Stream automatisch zu schließen und Ressourcenlecks zu vermeiden.

### Schritt 3: XPS‑Dokument laden
Instanziieren Sie ein `XpsDocument`‑Objekt, indem Sie die Quell‑XPS‑Datei laden.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Schritt 4: PDF‑Speicheroptionen initialisieren (PDF‑Kompression festlegen)
Konfigurieren Sie, wie das PDF komprimiert werden soll. Dieser Schritt ermöglicht es Ihnen, **PDF‑Kompression** für Bilder und Text festzulegen, wodurch die Dateigröße reduziert wird, ohne die Qualität zu beeinträchtigen.

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);                         // maximum JPEG quality
options.setImageCompression(PdfImageCompression.Jpeg);   // compress images as JPEG
options.setTextCompression(PdfTextCompression.Flate);    // compress text streams
options.setPageNumbers(new int[] { 1, 2, 6 });            // optional: export only selected pages
```

> **Warum das wichtig ist:** Durch Anpassen der JPEG‑Qualität und der Kompressionstypen kann ein 10 MB‑PDF auf unter 2 MB verkleinert werden, während die visuelle Treue erhalten bleibt.

### Schritt 5: Rendering‑Gerät für das PDF‑Format erstellen
Das `PdfDevice` überträgt die gerenderten Seiten in den PDF‑Ausgabestream.

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### Schritt 6: Dokument speichern
Rendern Sie schließlich den XPS‑Inhalt nach PDF unter Verwendung der konfigurierten Optionen.

```java
document.save(device, options);
```

> **Ergebnis:** Nach der Ausführung erscheint `XPStoPDF.pdf` im Ordner `dataDir` und enthält die konvertierten Seiten mit den von Ihnen angegebenen Kompressionseinstellungen.

## Häufige Probleme & Lösungen
| Problem | Ursache | Lösung |
|---------|---------|--------|
| **`FileNotFoundException`** | Falscher `dataDir`‑Pfad | Überprüfen Sie, ob das Verzeichnis existiert und die Anwendung Lese‑/Schreibrechte hat. |
| **Leere PDF‑Seiten** | Fehlende `PdfDevice`‑Initialisierung | Stellen Sie sicher, dass `PdfDevice` mit demselben `FileOutputStream` erstellt wird, der für die Ausgabe verwendet wird. |
| **Große PDF‑Datei** | Standardkompression ist niedrig | Erhöhen Sie `setJpegQualityLevel` oder wechseln Sie zu `PdfImageCompression.Jpeg` mit einem niedrigeren Qualitätswert. |
| **Nur einige Seiten erscheinen** | `setPageNumbers`‑Filter schließt Seiten aus | Passen Sie das Array an, um alle benötigten Seiten einzuschließen, oder entfernen Sie den Aufruf, um alle Seiten zu exportieren. |

## Häufig gestellte Fragen

**Q: Ist Aspose.Page Java mit verschiedenen Java‑Versionen kompatibel?**  
A: Ja, Aspose.Page Java unterstützt Java 8 bis Java 21, einschließlich Oracle‑ und OpenJDK‑Distributionen.

**Q: Kann ich die Kompressionseinstellungen für das konvertierte PDF anpassen?**  
A: Absolut. Verwenden Sie `PdfSaveOptions`, um JPEG‑Qualität, Bildkompressionstyp und Textkompression wie in Schritt 4 gezeigt festzulegen.

**Q: Wo finde ich zusätzlichen Support oder Community‑Diskussionen?**  
A: Besuchen Sie das [Aspose.Page Forum](https://forum.aspose.com/c/page/39) für Community‑Hilfe, Code‑Beispiele und Fehlersuche.

**Q: Gibt es eine kostenlose Testversion für Aspose.Page?**  
A: Ja, Sie können eine voll funktionsfähige Testversion von der [Aspose‑Download‑Seite](https://releases.aspose.com/) herunterladen.

**Q: Wie kann ich eine temporäre Lizenz für Aspose.Page erhalten?**  
A: Eine temporäre Lizenz kann [hier](https://purchase.aspose.com/temporary-license/) angefordert werden.

## Fazit
Durch die Nutzung von **Aspose.Page Java** können Sie mühelos **XPS als PDF speichern** und jeden Aspekt der Ausgabe steuern, von der Seitenauswahl bis zur Kompression. Dieses Tutorial hat alles behandelt, was Sie benötigen, um die XPS‑zu‑PDF‑Konvertierung in Ihre Java‑Anwendungen zu integrieren – egal, ob Sie ein einmaliges Dienstprogramm oder eine groß angelegte Dokumentenverarbeitungspipeline bauen.

---

**Last Updated:** 2025-11-29  
**Tested With:** Aspose.Page for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}