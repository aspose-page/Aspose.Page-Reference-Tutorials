---
date: 2026-01-20
description: Fügen Sie mühelos Seitenzahlen zu PDFs hinzu, während Sie XPS‑Dokumente
  zu hochwertigen PDFs zusammenführen, mit Aspose.Page für .NET. Folgen Sie unserer
  Schritt‑für‑Schritt‑Anleitung, um XPS in PDF zu konvertieren.
linktitle: Merge XPS Documents into PDF
second_title: Aspose.Page .NET API
title: Seitenzahlen zu PDF hinzufügen – XPS zu PDF zusammenführen mit Aspose.Page
url: /de/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Seitenzahlen zu PDF hinzufügen – XPS zu PDF zusammenführen mit Aspose.Page

## Einleitung

Wenn Sie **Seitenzahlen zu PDF hinzufügen** müssen, während Sie XPS‑Dateien zusammenführen, macht Aspose.Page für .NET den Vorgang mühelos. In diesem Tutorial führen wir Sie durch ein vollständiges, produktionsreifes Beispiel, das ein XPS‑Dokument in ein hochqualitatives PDF konvertiert, Ihnen die Kontrolle über die Bildkompression ermöglicht und automatisch Seitenzahlen in das endgültige PDF einfügt. Am Ende haben Sie ein wiederverwendbares Snippet, das Sie in jedes C#‑Projekt einbinden können.

## Schnelle Antworten
- **Kann ich Seitenzahlen hinzufügen, wenn ich XPS zu PDF zusammenführe?** Ja – die Eigenschaft `PdfSaveOptions.PageNumbers` erledigt genau das.  
- **Welche Bibliothek übernimmt die Konvertierung?** Aspose.Page für .NET.  
- **Benötige ich eine Lizenz für den Produktionseinsatz?** Eine gültige Aspose.Page‑Lizenz ist erforderlich; eine temporäre Lizenz ist für Tests verfügbar.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+ und .NET 5/6+.  
- **Ist ein hochqualitatives Bildausgabe möglich?** Absolut – setzen Sie `JpegQualityLevel` auf 100 und wählen Sie `PdfImageCompression.Jpeg`.

## Voraussetzungen

Bevor Sie in das Tutorial einsteigen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Aspose.Page für .NET: Stellen Sie sicher, dass die Aspose.Page‑Bibliothek installiert ist. Sie können sie von [hier](https://releases.aspose.com/page/net/) herunterladen.
- Dokumentdateien: Haben Sie das XPS‑Dokument (`input.xps`) in Ihrem angegebenen Verzeichnis bereit.

## Namespaces importieren

Fügen Sie in Ihrem .NET‑Projekt die erforderlichen Namespaces für die Arbeit mit Aspose.Page hinzu:

```csharp
using Aspose.Page.XPS;
```

Dieser Schritt stellt sicher, dass Sie Zugriff auf die Klassen und Methoden haben, die für die Dokumentkonvertierung erforderlich sind.

## Wie man Seitenzahlen zu PDF hinzufügt, wenn XPS‑Dokumente zusammengeführt werden

Die Sammlung `PdfSaveOptions.PageNumbers` ermöglicht es Ihnen, genau festzulegen, welche Seiten (oder Seitenbereiche) im Ausgabepdf erscheinen sollen. Indem Sie sie mit den gewünschten Seitenzahlen füllen, fügt Aspose.Page automatisch die korrekte Nummerierung ein.

### Schritt 1: Streams initialisieren

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

Dieser Schritt beinhaltet das Einrichten der Eingabe‑ und Ausgabestreams für die XPS‑ und PDF‑Dateien. Stellen Sie sicher, dass die richtigen Pfade und Dateinamen verwendet werden.

### Schritt 2: XPS‑Dokument laden

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

Hier laden wir das XPS‑Dokument in das Objekt `XpsDocument`, um es für die weitere Verarbeitung vorzubereiten.

### Schritt 3: Speicheroptionen initialisieren (XPS zu PDF zusammenführen)

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }   // <-- adds page numbers PDF
};
// ExEnd:5
```

Passen Sie das Objekt `PdfSaveOptions` nach Ihren Vorlieben an, indem Sie Parameter wie Bildkompression, Textkompression und die **Seitenzahlen** festlegen, die im endgültigen PDF erscheinen sollen. Das Setzen von `JpegQualityLevel` auf 100 gewährleistet **hochwertige PDF‑Bilder**.

### Schritt 4: Rendering‑Gerät erstellen

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

Das `PdfDevice` ist das Werkzeug, das für das Rendern des XPS‑Dokuments in das PDF‑Format verantwortlich ist.

### Schritt 5: Dokument speichern (C# XPS zu PDF)

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

Speichern Sie schließlich das Dokument mithilfe des Rendering‑Geräts und der angegebenen Optionen. Das Ausgabepdf enthält die ausgewählten Seiten mit automatisch hinzugefügten Seitenzahlen.

## Warum Aspose.Page für diese Konvertierung verwenden?

- **Zuverlässigkeit** – Verarbeitet komplexe XPS‑Funktionen ohne Qualitätsverlust.  
- **Leistung** – Stream‑basierte Verarbeitung vermeidet das Laden ganzer Dateien in den Speicher.  
- **Flexibilität** – Feinkörnige Kontrolle über Bildqualität, Kompression und Seitenzahlen.  
- **Plattformübergreifend** – Funktioniert unter Windows, Linux und macOS mit .NET Core.

## Häufige Probleme und Lösungen

| Problem | Lösung |
|-------|----------|
| **Ausgabe‑PDF ist leer** | Stellen Sie sicher, dass der Pfad zur XPS‑Datei korrekt ist und die Datei nicht beschädigt ist. |
| **Seitenzahlen erscheinen nicht** | Stellen Sie sicher, dass `PageNumbers` auf die korrekten nullbasierten Seitenindizes gesetzt ist (z. B. `new int[] {1,2,6}`). |
| **Bilder von niedriger Qualität** | Erhöhen Sie `JpegQualityLevel` und wählen Sie `PdfImageCompression.Jpeg`. |
| **Große XPS‑Dateien verursachen Speicherbelastung** | Verarbeiten Sie das XPS in kleineren Abschnitten oder erhöhen Sie das Speicherlimit der Anwendung. |

## Häufig gestellte Fragen

### F1: Kann ich mehrere XPS‑Dateien zu einem einzigen PDF zusammenführen?

A1: Ja, das können Sie. Passen Sie einfach den Parameter `PageNumbers` in den `PdfSaveOptions` an, um die gewünschten Seiten aus verschiedenen XPS‑Dateien einzuschließen, oder laden Sie jede XPS‑Datei nacheinander und rufen Sie `document.Save` auf demselben `PdfDevice` auf.

### F2: Ist eine temporäre Lizenz für Aspose.Page für .NET verfügbar?

A2: Ja, Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) für Testzwecke erhalten.

### F3: Gibt es Beschränkungen bezüglich der Dateigröße bei der Verwendung von Aspose.Page für die Dokumentkonvertierung?

A3: Aspose.Page für .NET legt keine strengen Beschränkungen für die Dateigröße fest, aber optimale Leistung wird bei vernünftig großen Dateien erzielt. Bei sehr großen XPS‑Dokumenten sollten Sie in Erwägung ziehen, sie in Streams zu verarbeiten, um den Speicherverbrauch zu reduzieren.

### F4: Kann ich das Ausgabepdf weiter anpassen, z. B. Wasserzeichen oder Anmerkungen hinzufügen?

A4: Ja, Aspose.Page für .NET bietet umfangreiche Funktionen zur PDF‑Manipulation. Nach der Konvertierung können Sie die Aspose.PDF‑Bibliothek verwenden, um Wasserzeichen, Anmerkungen oder andere Verbesserungen hinzuzufügen.

### F5: Unterstützt Aspose.Page für .NET die plattformübergreifende Entwicklung?

A5: Ja, Aspose.Page für .NET ist so konzipiert, dass es nahtlos auf verschiedenen Plattformen funktioniert, einschließlich Windows, Linux und macOS, wenn es mit .NET Core oder .NET 5/6 verwendet wird.

**Zuletzt aktualisiert:** 2026-01-20  
**Getestet mit:** Aspose.Page 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}