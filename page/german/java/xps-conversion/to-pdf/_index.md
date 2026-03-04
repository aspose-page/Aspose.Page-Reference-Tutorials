---
date: 2025-12-23
description: Erfahren Sie, wie Sie XPS in Java mit Aspose.Page in PDF konvertieren.
  Dieser Leitfaden zeigt die Schritt‑für‑Schritt‑Konvertierung, wie Sie PDF aus XPS
  rendern und PDF‑Seitenzahlen festlegen.
linktitle: How to Convert XPS to PDF in Java
second_title: Aspose.Page Java API
title: Wie man XPS in PDF in Java konvertiert
url: /de/java/xps-conversion/to-pdf/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man XPS in PDF in Java konvertiert

## Wie man XPS in PDF in Java konvertiert
Im Bereich der Java‑Entwicklung ist **wie man XPS in PDF konvertiert** eine häufige Frage. Egal, ob Sie ein Dokumenten‑Management‑System bauen oder druckbare Berichte erzeugen müssen, die zuverlässige Konvertierung von XPS‑Dateien kann ein echter Wendepunkt sein. Glücklicherweise macht Aspose.Page for Java das **PDF aus XPS rendern** mit nur wenigen Codezeilen unkompliziert.

## Schnellantworten
- **Welche Bibliothek übernimmt die Konvertierung?** Aspose.Page for Java.
- **Wie lange dauert die Implementierung?** Ungefähr 10‑15 Minuten für ein Basis‑Setup.
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht für die Evaluierung; für den Produktionseinsatz ist eine Lizenz erforderlich.
- **Kann ich nur ausgewählte Seiten konvertieren?** Ja – verwenden Sie die *specify PDF page numbers*‑Option.
- **Ist die Konvertierung verlustfrei?** Die Bibliothek bewahrt Vektorgrafiken und Texttreue.

## Was ist XPS‑zu‑PDF‑Konvertierung?
XPS (XML Paper Specification) ist Microsofts festes Layout‑Dokumentformat. Die Konvertierung in PDF ermöglicht das Teilen, Drucken oder Archivieren von Dokumenten mit dem universell anerkannten PDF‑Standard.

## Warum Aspose.Page for Java zum Rendern von PDF aus XPS verwenden?
- **Hohe Treue** – behält Vektorgrafiken, Schriftarten und Layout bei.
- **Fein abgestimmte Kontrolle** – Sie können Bildqualität, Kompression und sogar einzelne Seiten festlegen.
- **Keine externen Abhängigkeiten** – reines Java, funktioniert auf jeder Plattform, die JDK unterstützt.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie folgendes haben:

- **Java Development Kit (JDK)** – jede aktuelle Version (8+ empfohlen).
- **Aspose.Page for Java** – laden Sie die Bibliothek aus der offiziellen [Documentation](https://reference.aspose.com/page/java/) herunter.
- Eine XPS‑Datei, die Sie konvertieren möchten.

## Pakete importieren
Importieren Sie in Ihrem Java‑Projekt die benötigten Pakete, um mit Aspose.Page for Java zu arbeiten. Dieser Schritt ist entscheidend, um die für die XPS‑zu‑PDF‑Konvertierung erforderlichen Funktionen zu nutzen.

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Dokumentverzeichnis festlegen
Definieren Sie den Pfad zu dem Ordner, der Ihre Quell‑XPS‑Datei enthält.

```java
String dataDir = "Your Document Directory";
```

### Schritt 2: PDF‑Ausgabestream initialisieren
Erstellen Sie einen `FileOutputStream`, der das erzeugte PDF empfängt.

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

### Schritt 3: XPS‑Dokument laden
Laden Sie die XPS‑Datei mit Aspose.Page.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Schritt 4: PDF‑Speicheroptionen initialisieren  
Erzeugen Sie Optionen für die Konvertierung. Hier können Sie **PDF‑Seitenzahlen angeben**, die Bildqualität anpassen und die Kompression festlegen.

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);
options.setImageCompression(PdfImageCompression.Jpeg);
options.setTextCompression(PdfTextCompression.Flate);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### Schritt 5: PDF‑Rendergerät erstellen  
Richten Sie ein Render‑Gerät ein, das die PDF‑Ausgabe schreibt.

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### Schritt 6: Dokument speichern  
Speichern Sie schließlich das XPS‑Dokument als PDF unter Verwendung der konfigurierten Optionen und des Geräts.

```java
document.save(device, options);
```

Wiederholen Sie diese Schritte und passen Sie Dateipfade sowie Optionen an Ihr konkretes Szenario an.

## Wie man PDF‑Seitenzahlen beim Konvertieren von XPS angibt
Wenn Sie nur einen Teil der Seiten aus dem ursprünglichen XPS benötigen, füllen Sie das `setPageNumbers`‑Array mit den gewünschten Seitenindizes (beginnend bei 1). Das reduziert Dateigröße und Verarbeitungszeit.

## Häufige Probleme & Fehlersuche
- **FileNotFoundException** – Stellen Sie sicher, dass `dataDir` auf den richtigen Ordner zeigt und der XPS‑Dateiname stimmt.
- **LicenseException** – Für den Produktionseinsatz ist eine gültige Aspose.Page‑Lizenz erforderlich; andernfalls läuft die Bibliothek im Evaluierungsmodus mit Wasserzeichen.
- **Niedrige Bildqualität** – Erhöhen Sie `setJpegQualityLevel` oder wechseln Sie bei Bedarf zu verlustfreier Kompression.

## Häufig gestellte Fragen
### Kann ich XPS‑Dateien mit mehreren Seiten mithilfe von Aspose.Page for Java konvertieren?
Ja, Sie können **PDF‑Seitenzahlen angeben** in den `PdfSaveOptions` (siehe Schritt 4), um beliebige Seiten einzuschließen.

### Wo finde ich zusätzlichen Support oder kann Aspose.Page‑bezogene Fragen diskutieren?
Besuchen Sie das [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39) für Community‑Support und Diskussionen.

### Gibt es eine kostenlose Testversion für Aspose.Page for Java?
Ja, Sie können die Funktionen mit einem [Free Trial](https://releases.aspose.com/) erkunden.

### Wie kann ich eine temporäre Lizenz für Aspose.Page for Java erhalten?
Unter diesem [Link](https://purchase.aspose.com/temporary-license/) finden Sie Details zur temporären Lizenz.

### Wo kann ich die Aspose.Page for Java‑Lizenz kaufen?
Sie können die Lizenz [hier](https://purchase.aspose.com/buy) erwerben.

---

**Zuletzt aktualisiert:** 2025-12-23  
**Getestet mit:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}