---
date: 2026-05-25
description: Erfahren Sie, wie Sie XMP mit Aspose.Page und Java lesen. Dieser Schritt‑für‑Schritt‑Leitfaden
  zeigt das Extrahieren von XMP metadata, creator info, timestamps, thumbnails und
  mehr.
keywords:
- read xmp using aspose.page
- xmp metadata java
- aspose.page java
linktitle: So lesen Sie XMP Metadata mit Java
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to read xmp using aspose.page with Java. This step‑by‑step
    guide shows extracting XMP metadata, creator info, timestamps, thumbnails, and
    more.
  headline: Read XMP using Aspose.Page – Java Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page can read XMP from PDF, EPS, and several image formats.
    question: Does this approach work with PDF files that contain XMP?
  - answer: Absolutely. The `XmpMetadata` object is mutable; you can add, update,
      or remove keys and then save the document.
    question: Can I modify XMP metadata after reading it?
  - answer: You can retrieve the binary data from the `xmpGImg:data` property of each
      thumbnail entry and write it to a file.
    question: Is there a way to extract all thumbnail images, not just dimensions?
  type: FAQPage
second_title: Aspose.Page Java API
title: XMP mit Aspose.Page lesen – Java‑Leitfaden
url: /de/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Metadaten aus XMP mit Java abrufen

## Wie liest man XMP mit Aspose.Page (Java)?

Laden Sie die EPS‑Datei mit `new Document("file.eps")`—die `Document`‑Klasse repräsentiert eine geladene Datei. Rufen Sie `getXmpMetadata()` auf, das das XMP‑Paket extrahiert, und fragen Sie dann das zurückgegebene `XmpMetadata`‑Objekt ab – eine map‑ähnliche Schnittstelle für XMP‑Eigenschaften –, um die benötigten Schlüssel zu erhalten. Das ist alles, was zum Lesen von XMP mit Aspose.Page erforderlich ist. Die API abstrahiert das Low‑Level‑Parsing, sodass Sie in nur zwei Codezeilen eine gebrauchsfertige Karte von Eigenschaften erhalten.

Willkommen zu unserem Schritt‑für‑Schritt‑Tutorial, das zeigt, **wie man XMP**‑Metadaten mit Java und der Aspose.Page‑Bibliothek liest. XMP (Extensible Metadata Platform) ist ein weit verbreiteter Standard zum Einbetten umfangreicher Metadaten in Dokumente. Am Ende dieses Leitfadens können Sie XMP‑Metadaten von Dokumentformaten lesen, Erstellerinformationen, Zeitstempel, Thumbnails und mehr extrahieren – und so intelligentere Dokumentanalyse‑Lösungen erstellen.

## Schnelle Antworten
- **Was bedeutet „read XMP“?** Es bedeutet, das XMP‑Paket, das Metadaten in einer Datei speichert, programmgesteuert zu extrahieren.  
- **Welche Bibliothek wird benötigt?** Aspose.Page für Java (Download von der offiziellen Seite [here](https://releases.aspose.com/page/java/)).  
- **Benötige ich eine Lizenz?** Für den Produktionseinsatz ist eine temporäre oder vollständige Lizenz erforderlich; ein kostenloser Testzeitraum funktioniert für Evaluierungen.  
- **Welche Java‑Version wird unterstützt?** Java 8 oder höher.  
- **Kann ich XMP aus anderen Formaten lesen?** Ja – Aspose.Page extrahiert XMP aus EPS, PDF, JPEG, PNG und über 20 weiteren Formaten.

## Voraussetzungen
Bevor Sie in den Code eintauchen, stellen Sie sicher, dass Sie folgendes haben:

- **Java Development Kit (JDK)** – Java 8+ installiert und auf Ihrem Rechner konfiguriert.  
- **Aspose.Page für Java** – Laden Sie die Bibliothek von der offiziellen Seite [here](https://releases.aspose.com/page/java/) herunter.  
- Eine EPS‑Datei, die XMP‑Metadaten enthält (z. B. `xmp1.eps`).  

## Pakete importieren
Die Klasse `XmpMetadata` befindet sich im Namensraum `com.aspose.page.xmp`, während die Klasse `Document` in `com.aspose.page` liegt. Importieren Sie beide, damit Sie mit der EPS‑Datei und deren Metadaten arbeiten können.  
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Schritt 1: Eingabestream für EPS‑Datei initialisieren
Beginnen Sie damit, den Pfad zu Ihrem Dokumentenverzeichnis festzulegen und den Eingabe‑EPS‑Dateistream zu initialisieren.  
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## Schritt 2: XMP‑Metadaten abrufen
`XmpMetadata` ist das Objekt von Aspose.Page, das das aus einem Dokument extrahierte XMP‑Paket enthält. Rufen Sie es mit `document.getXmpMetadata()` ab. Fehlt das XMP in der Datei, erzeugt die API ein minimales Paket aus vorhandenen PostScript‑Kommentaren.  
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Schritt 3: CreatorTool‑Informationen extrahieren
Der Schlüssel `CreatorTool` befindet sich im Namensraum `xmp` und zeichnet die Anwendung auf, die die Datei erzeugt hat. Prüfen Sie dessen Vorhandensein und geben Sie den Wert aus.  
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Schritt 4: CreateDate‑Informationen extrahieren
`CreateDate` speichert den Zeitstempel, wann das Dokument ursprünglich erstellt wurde. Verwenden Sie das gleiche `containsKey`/`get`‑Muster, um es zu lesen.  
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Schritt 5: Thumbnail‑Breite abrufen
Falls Thumbnails vorhanden sind, enthält das Array `xmp:Thumbnails` einen oder mehrere Einträge. Jeder Eintrag enthält `width`, `height` und Binärdaten. Das Beispiel extrahiert die Breite des ersten Thumbnails.  
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Schritt 6: Formatinformationen extrahieren
Der Schlüssel `format` gibt das ursprüngliche Dateiformat an (z. B. „application/postscript“). Das ist nützlich, wenn Sie Quelltypen protokollieren oder validieren müssen.  
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Schritt 7: DocumentID abrufen
`DocumentID` ist ein eindeutiger Bezeichner, der von der Erstellungsanwendung zugewiesen wird. Er kann zur Duplikaterkennung in großen Asset‑Bibliotheken verwendet werden.  
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Warum das wichtig ist
Aspose.Page kann XMP aus **20+** Dateiformaten lesen und verarbeitet Dokumente bis zu **500 MB**, ohne die gesamte Datei in den Speicher zu laden, was Ihnen schnellen, ressourcenschonenden Zugriff auf wesentliche Metadaten ermöglicht. Diese Fähigkeit ist entscheidend für Batch‑Verarbeitungspipelines, Digital‑Asset‑Management‑Systeme und jede Lösung, die auf durchsuchbare, maschinenlesbare Dokumentattribute angewiesen ist.

## Häufige Fallstricke & Tipps
- **Fehlendes XMP:** Einige EPS‑Dateien enthalten möglicherweise kein XMP. Der Aufruf `getXmpMetadata()` erzeugt ein minimales Set basierend auf vorhandenen PS‑Kommentaren, aber Sie erhalten keine vollständigen Metadaten, sofern sie nicht eingebettet sind.  
- **Thumbnail‑Arrays:** Der Schlüssel `xmp:Thumbnails` kann mehrere Einträge enthalten. Das Beispiel extrahiert nur den ersten; iterieren Sie das Array, wenn Sie alle Thumbnails benötigen.  
- **Namespace‑Bewusstsein:** XMP‑Schlüssel verwenden Namespaces (z. B. `xmp:`, `dc:`). Stellen Sie sicher, dass Sie den genauen Schlüsselnamen referenzieren; andernfalls gibt `containsKey` false zurück.  

## Häufig gestellte Fragen
### Kann ich Aspose.Page für Java mit anderen Programmiersprachen verwenden?
Ja, Aspose.Page unterstützt Java, .NET und mehrere andere Sprachen. Siehe die vollständige Liste in der [documentation](https://reference.aspose.com/page/java/).

### Ist ein kostenloser Testzeitraum für Aspose.Page für Java verfügbar?
Ja, Sie können den kostenlosen Testzeitraum [here](https://releases.aspose.com/) nutzen.

### Wo finde ich Support für Aspose.Page für Java?
Besuchen Sie das [Aspose.Page forum](https://forum.aspose.com/c/page/39) für Community‑Hilfe und offiziellen Support.

### Wie erhalte ich eine temporäre Lizenz für Aspose.Page für Java?
Sie können eine temporäre Lizenz [here](https://purchase.aspose.com/temporary-license/) erhalten.

### Gibt es zusätzliche Ressourcen für Aspose.Page für Java?
Entdecken Sie die vollständige [documentation](https://reference.aspose.com/page/java/) und laden Sie die Bibliothek [here](https://releases.aspose.com/page/java/) herunter.

## Zusätzliche FAQ
**F: Funktioniert dieser Ansatz mit PDF‑Dateien, die XMP enthalten?**  
A: Ja, Aspose.Page kann XMP aus PDF, EPS und mehreren Bildformaten lesen.

**F: Kann ich XMP‑Metadaten nach dem Lesen ändern?**  
A: Absolut. Das `XmpMetadata`‑Objekt ist veränderlich; Sie können Schlüssel hinzufügen, aktualisieren oder entfernen und anschließend das Dokument speichern.

**F: Gibt es eine Möglichkeit, alle Thumbnail‑Bilder zu extrahieren, nicht nur die Abmessungen?**  
A: Sie können die Binärdaten aus der Eigenschaft `xmpGImg:data` jedes Thumbnail‑Eintrags abrufen und in eine Datei schreiben.

## Fazit
Sie haben nun gelernt, **wie man XMP**‑Metadaten mit Java und Aspose.Page liest. Durch das Befolgen dieser Schritte können Sie Erstellertools, Zeitstempel, Thumbnails, Formatinformationen und Dokument‑IDs extrahieren – und erhalten vollständige Einblicke in die eingebetteten Metadaten Ihrer EPS‑Dateien. Experimentieren Sie gern mit zusätzlichen XMP‑Namespaces, um noch reichhaltigere Daten für Ihre Anwendungen zu erhalten.

---

**Last Updated:** 2026-05-25  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose

## Verwandte Tutorials

- [Aspose Page Java Tutorial – XMP‑Metadaten zu EPS‑Dateien hinzufügen](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page xmp tutorial – Namespace in XMP mit Java hinzufügen](/page/java/xmp-metadata-manipulation/add-namespace/)
- [aspose page xmp tutorial – Benannten Wert in XMP mit Java ändern](/page/java/xmp-metadata-manipulation/change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}