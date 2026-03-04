---
date: 2025-12-21
description: Erfahren Sie, wie Sie XMP‑Metadaten mit Java und Aspose.Page lesen. Diese
  Schritt‑für‑Schritt‑Anleitung zeigt Ihnen, wie Sie XMP im Dokumentformat auslesen
  und wichtige Eigenschaften extrahieren.
linktitle: How to Read XMP Metadata using Java
second_title: Aspose.Page Java API
title: Wie man XMP-Metadaten mit Java liest – Aspose.Page-Leitfaden
url: /de/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Metadaten aus XMP mit Java abrufen

## Wie man XMP‑Metadaten mit Java liest

Willkommen zu unserem Schritt‑für‑Schritt‑Tutorial, das **zeigt, wie man XMP**‑Metadaten mit Java und der Aspose.Page‑Bibliothek liest. XMP (Extensible Metadata Platform) ist ein weit verbreiteter Standard zum Einbetten umfangreicher Metadaten in Dokumente. Am Ende dieses Leitfadens können Sie XMP‑Metadaten aus Dokumentformaten lesen, Informationen zum Ersteller, Zeitstempel, Thumbnails und mehr extrahieren – und so intelligentere Dokumentanalyse‑Lösungen erstellen.

## Schnelle Antworten
- **Was bedeutet „how to read xmp“?** Es bezieht sich auf das programmgesteuerte Extrahieren von XMP‑Metadaten aus Dateien.  
- **Welche Bibliothek wird benötigt?** Aspose.Page für Java (verfügbar auf der Aspose‑Download‑Seite).  
- **Benötige ich eine Lizenz?** Für den Produktionseinsatz ist eine temporäre oder vollständige Lizenz erforderlich; ein kostenloser Testzeitraum ist verfügbar.  
- **Welche Java‑Version wird unterstützt?** Java 8 oder höher.  
- **Kann ich XMP aus anderen Formaten lesen?** Ja, Aspose.Page kann EPS, PDF und mehrere Bildformate, die XMP einbetten, verarbeiten.

## Voraussetzungen
Bevor Sie in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

- **Java Development Kit (JDK)** – Java 8+ installiert und auf Ihrem Rechner konfiguriert.  
- **Aspose.Page für Java** – Laden Sie die Bibliothek von der offiziellen Seite [here](https://releases.aspose.com/page/java/).  
- Eine EPS‑Datei, die XMP‑Metadaten enthält (z. B. `xmp1.eps`).  

## Pakete importieren
Importieren Sie in Ihrem Java‑Projekt die erforderlichen Pakete:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Schritt 1: Eingabestream der EPS‑Datei initialisieren
Legen Sie den Pfad zu Ihrem Dokumentverzeichnis fest und initialisieren Sie den Eingabestream der EPS‑Datei.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## Schritt 2: XMP‑Metadaten abrufen
Rufen Sie die XMP‑Metadaten aus der EPS‑Datei ab. Wenn die Datei keine XMP‑Metadaten enthält, wird ein neues Set mit Werten aus den PS‑Metadaten‑Kommentaren erzeugt.
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Schritt 3: CreatorTool‑Informationen extrahieren
Prüfen und geben Sie den Wert „CreatorTool“ aus den XMP‑Metadaten aus.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Schritt 4: CreateDate‑Informationen extrahieren
Prüfen und geben Sie den Wert „CreateDate“ aus den XMP‑Metadaten aus.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Schritt 5: Thumbnail‑Breite abrufen
Falls Thumbnails vorhanden sind, extrahieren und geben Sie die Breite des ersten Thumbnails aus.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Schritt 6: Format‑Informationen extrahieren
Prüfen und geben Sie den Wert „format“ aus den XMP‑Metadaten aus.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Schritt 7: DocumentID abrufen
Prüfen und geben Sie den Wert „DocumentID“ aus den XMP‑Metadaten aus.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Warum das wichtig ist
Das Lesen von XMP‑Metadaten ermöglicht es Ihnen, programmgesteuert Ursprung, Erstellungsdatum und weitere wesentliche Attribute eines Dokuments zu ermitteln, ohne es in einem Viewer zu öffnen. Das ist besonders nützlich für Batch‑Verarbeitung, Content‑Management‑Systeme und digitale Asset‑Pipelines, bei denen Metadaten die Indexierung und Suche steuern.

## Häufige Fallstricke & Tipps
- **Fehlendes XMP:** Einige EPS‑Dateien enthalten möglicherweise kein XMP. Der Aufruf `getXmpMetadata()` erzeugt ein minimales Set basierend auf vorhandenen PS‑Kommentaren, aber Sie erhalten keine vollständigen Metadaten, sofern sie nicht eingebettet sind.  
- **Thumbnail‑Arrays:** Der Schlüssel `xmp:Thumbnails` kann mehrere Einträge enthalten. Das Beispiel extrahiert nur das erste; iterieren Sie das Array, wenn Sie alle Thumbnails benötigen.  
- **Namespace‑Bewusstsein:** XMP‑Schlüssel verwenden Namespaces (z. B. `xmp:`, `dc:`). Stellen Sie sicher, dass Sie den genauen Schlüsselnamen referenzieren; andernfalls gibt `containsKey` false zurück.

## Häufig gestellte Fragen
### Kann ich Aspose.Page für Java mit anderen Programmiersprachen verwenden?
Ja, Aspose.Page unterstützt mehrere Sprachen, darunter Java, .NET und weitere. Weitere Informationen finden Sie in der [documentation](https://reference.aspose.com/page/java/).

### Ist eine kostenlose Testversion für Aspose.Page für Java verfügbar?
Ja, Sie können die kostenlose Testversion [here](https://releases.aspose.com/) nutzen.

### Wo finde ich Support für Aspose.Page für Java?
Besuchen Sie das [Aspose.Page forum](https://forum.aspose.com/c/page/39) für Community‑Support.

### Wie erhalte ich eine temporäre Lizenz für Aspose.Page für Java?
Sie können eine temporäre Lizenz [here](https://purchase.aspose.com/temporary-license/) erhalten.

### Gibt es zusätzliche Ressourcen für Aspose.Page für Java?
Entdecken Sie die vollständige [documentation](https://reference.aspose.com/page/java/) und laden Sie die Bibliothek [here](https://releases.aspose.com/page/java/) herunter.

## Zusätzliche FAQ
**F: Funktioniert dieser Ansatz mit PDF‑Dateien, die XMP enthalten?**  
A: Ja, Aspose.Page kann XMP aus PDF, EPS und mehreren Bildformaten lesen.

**F: Kann ich XMP‑Metadaten nach dem Lesen ändern?**  
A: Absolut. Das `XmpMetadata`‑Objekt ist veränderlich; Sie können Schlüssel hinzufügen, aktualisieren oder entfernen und dann das Dokument speichern.

**F: Gibt es eine Möglichkeit, alle Thumbnail‑Bilder zu extrahieren, nicht nur die Abmessungen?**  
A: Sie können die Binärdaten aus der Eigenschaft `xmpGImg:data` jedes Thumbnail‑Eintrags abrufen und in eine Datei schreiben.

## Fazit
Sie haben nun **gelernt, wie man XMP**‑Metadaten mit Java und Aspose.Page liest. Durch Befolgen dieser Schritte können Sie Ersteller‑Tools, Zeitstempel, Thumbnails, Format‑Informationen und Document‑IDs extrahieren – und erhalten so vollständige Einblicke in die eingebetteten Metadaten Ihrer EPS‑Dateien. Experimentieren Sie gern mit zusätzlichen XMP‑Namespaces, um noch reichhaltigere Daten für Ihre Anwendungen zu gewinnen.

---

**Zuletzt aktualisiert:** 2025-12-21  
**Getestet mit:** Aspose.Page for Java 24.12 (latest)  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
