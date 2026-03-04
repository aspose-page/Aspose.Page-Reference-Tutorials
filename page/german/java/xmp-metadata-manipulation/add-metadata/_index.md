---
date: 2025-12-20
description: Erfahren Sie, wie Sie XMP‑Metadaten zu EPS‑Dateien mit dem Aspose Page‑Java‑Tutorial
  hinzufügen. Folgen Sie dieser Schritt‑für‑Schritt‑Anleitung, um Ihr Dokumentenmanagement
  zu verbessern.
linktitle: Add Metadata in XMP using Java
second_title: Aspose.Page Java API
title: Aspose Page Java Tutorial – XMP‑Metadaten zu EPS‑Dateien hinzufügen
url: /de/java/xmp-metadata-manipulation/add-metadata/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Metadaten in XMP mit Java hinzufügen

## Einleitung
In diesem **aspose page java tutorial** lernen Sie, wie Sie die Metadaten Ihres Dokuments erweitern, indem Sie XMP‑Informationen mit Java hinzufügen. Diese Schritt‑für‑Schritt‑Anleitung führt Sie durch das Lesen einer bestehenden EPS‑Datei, das Extrahieren ihrer XMP‑Metadaten und das Speichern der Änderungen zurück auf die Festplatte mit der Aspose.Page for Java‑Bibliothek. Am Ende des Tutorials verfügen Sie über ein solides, wiederverwendbares Muster für die Arbeit mit XMP in jedem EPS‑Workflow.

## Schnelle Antworten
- **Welche Bibliothek wird benötigt?** Aspose.Page for Java  
- **Kann ich XMP zu jeder EPS‑Datei hinzufügen?** Ja – die API erstellt einen neuen XMP‑Block, falls noch keiner existiert.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion reicht für die Evaluierung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Welche Java‑Version wird unterstützt?** Java 8 und höher.  
- **Wie lange dauert die Implementierung?** In der Regel unter 10 Minuten für ein einfaches Metadaten‑Update.

## Übersicht des Aspose Page Java Tutorials
Dieses Tutorial demonstriert die Kernschritte, die Sie benötigen, um XMP‑Metadaten in EPS‑Dateien zu manipulieren. Das Verständnis dieser Schritte hilft Ihnen, die Metadaten‑Verarbeitung in größere Dokument‑Verarbeitungspipelines zu integrieren, die Durchsuchbarkeit zu verbessern und Industriestandards für das digitale Asset‑Management zu erfüllen.

## Voraussetzungen
Bevor wir in das Tutorial einsteigen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Grundkenntnisse in der Java‑Programmierung.  
- Aspose.Page for Java Bibliothek installiert. Sie können sie [hier](https://releases.aspose.com/page/java/) herunterladen.  
- Eine EPS‑Datei, die Sie ändern möchten.

## Pakete importieren
Importieren Sie zunächst die notwendigen Pakete in Ihr Java‑Programm:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```

## Schritt 1: XMP‑Metadaten abrufen
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created using values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

Ersetzen Sie `"Your Document Directory"` durch den tatsächlichen Pfad, in dem Ihre Dokumente gespeichert sind.

## Schritt 2: CreatorTool‑Wert abrufen
```java
// Get "CreatorTool" value
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Schritt 3: CreateDate‑Wert abrufen
```java
// Get "CreateDate" value
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Schritt 4: Titel‑Wert abrufen
```java
// Get "Title" value
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```

## Schritt 5: Format‑Wert abrufen
```java
// Get "format" value
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Schritt 6: Creator‑Wert abrufen
```java
// Get "creator" value
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```

## Schritt 7: MetadataDate‑Wert abrufen
```java
// Get "MetadataDate" value
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```

## Schritt 8: Dokument mit neuen XMP‑Metadaten speichern
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Save document with new XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

Vergessen Sie schließlich nicht, den Eingabe‑EPS‑Stream zu schließen:

```java
// Close input EPS stream
psStream.close();
```

Jetzt haben Sie erfolgreich Metadaten zu Ihrer EPS‑Datei mit Aspose.Page for Java hinzugefügt!

## Fazit
In diesem **aspose page java tutorial** haben wir untersucht, wie man XMP‑Metadaten zu einer EPS‑Datei mit der Aspose.Page for Java‑Bibliothek hinzufügt. Diese leistungsstarke API ermöglicht es, Dokumentmetadaten programmgesteuert zu manipulieren, wodurch Sie Ihre Assets organisiert und durchsuchbar halten.

## Häufig gestellte Fragen

**Q: Ist Aspose.Page for Java kostenlos zu verwenden?**  
A: Aspose.Page for Java ist ein kommerzielles Produkt. Sie können seine Funktionen über eine kostenlose Testversion [hier](https://releases.aspose.com/) erkunden.

**Q: Wo finde ich die Dokumentation für Aspose.Page for Java?**  
A: Die Dokumentation ist [hier](https://reference.aspose.com/page/java/) verfügbar.

**Q: Wie kann ich eine temporäre Lizenz für Aspose.Page for Java erhalten?**  
A: Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erhalten.

**Q: Welche Dateiformate unterstützt Aspose.Page for Java?**  
A: Aspose.Page for Java unterstützt verschiedene Formate, darunter EPS, PDF und XPS.

**Q: Kann ich Aspose.Page for Java kaufen?**  
A: Ja, Sie können Aspose.Page for Java [hier](https://purchase.aspose.com/buy) erwerben.

**Q: Wie gehe ich mit großen EPS‑Dateien um, wenn ich Metadaten hinzufüge?**  
A: Verarbeiten Sie die Datei in einem Streaming‑Verfahren (wie gezeigt), um den Speicherverbrauch gering zu halten, und schließen Sie Streams umgehend.

**Q: Kann ich vorhandene XMP‑Felder ändern, anstatt sie nur zu lesen?**  
A: Absolut – Sie können `xmp.put(key, value)` verwenden, um Einträge zu aktualisieren oder neue hinzuzufügen, bevor Sie speichern.

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}