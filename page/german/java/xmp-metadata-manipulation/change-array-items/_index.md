---
date: 2026-05-15
description: Entdecken Sie das aspose.page xmp Tutorial für Java – lernen Sie, wie
  Sie Array-Elemente in XMP-Metadaten ändern, EPS-Titel, Ersteller und mehr mit nur
  wenigen Codezeilen aktualisieren.
keywords:
- aspose.page xmp tutorial
- change array items java
- xmp metadata java
linktitle: Array-Elemente in XMP mit Java ändern
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Explore the aspose.page xmp tutorial for Java—learn how to change array
    items in XMP metadata, update EPS titles, creators, and more in just a few lines
    of code.
  headline: 'aspose.page xmp tutorial: Change Array Items in XMP using Java'
  type: TechArticle
- description: Explore the aspose.page xmp tutorial for Java—learn how to change array
    items in XMP metadata, update EPS titles, creators, and more in just a few lines
    of code.
  name: 'aspose.page xmp tutorial: Change Array Items in XMP using Java'
  steps:
  - name: Get XMP Metadata
    text: Call `document.getXmpMetadata()` to retrieve the XMP metadata object associated
      with the EPS file.
  - name: Set "dc:title" Array Item
    text: Use `xmpMetadata.setArrayItem("dc:title", 0, "New Title")` to replace the
      first title entry.
  - name: Set "dc:creator" Array Item
    text: Similarly, `xmpMetadata.setArrayItem("dc:creator", 0, "New Author")` updates
      the first creator entry.
  - name: Initialize Output EPS File Stream
    text: Create a `FileOutputStream` pointing to the destination EPS file to write
      the updated document.
  - name: Save Document with Changed XMP Metadata
    text: The `PsDocument` class represents an EPS document and provides the `save`
      method to write changes to a stream.
  type: HowTo
- questions:
  - answer: No. You must invoke `setArrayItem` for each index you wish to modify;
      the API does not provide a bulk‑update method.
    question: Can I update multiple array items in one call?
  - answer: Yes. Provide the full prefix (e.g., `myNS:customProp`) when calling `setArrayItem`
      or `removeArrayItem`.
    question: Does aspose.page xmp java support custom namespaces?
  - answer: Reload the EPS with `PsDocument`, call `getXmpMetadata()`, and inspect
      the returned values, or open the file in an XMP viewer.
    question: How do I verify that the metadata was updated correctly?
  - answer: Use `removeArrayItem(namespace, index)` to delete a specific entry from
      an XMP array.
    question: Is it possible to remove an array item entirely?
  - answer: No. XMP metadata is stored separately from the graphic content and does
      not alter how the EPS renders.
    question: Will the changes affect the visual appearance of the EPS?
  type: FAQPage
second_title: Aspose.Page Java API
title: 'aspose.page xmp Tutorial: Array-Elemente in XMP mit Java ändern'
url: /de/java/xmp-metadata-manipulation/change-array-items/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose.page xmp Tutorial: Array-Elemente in XMP mit Java ändern

## Einleitung
Willkommen zu unserem umfassenden **aspose.page xmp tutorial**. In diesem Leitfaden zeigen wir Ihnen Schritt für Schritt, wie Sie Array‑Einträge in XMP‑Metadaten innerhalb von EPS‑Dateien mit Aspose.Page für Java ändern können. Egal, ob Sie den Dokumenttitel, die Autorenliste oder ein anderes XMP‑Array aktualisieren müssen – der Vorgang ist unkompliziert, vollständig programmgesteuert und funktioniert mit Java 8 +.

## Schnellantworten
- **Was macht aspose.page xmp java?** Es liest und schreibt XMP‑Metadaten in EPS‑Dateien direkt aus Java.  
- **Benötige ich eine Lizenz für den Test?** Ja – ein kostenloser 30‑Tage‑Test ist verfügbar; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welche JDK‑Version wird unterstützt?** Java 8 oder höher (einschließlich Java 11, 17 und 21).  
- **Kann ich andere Metadatenfelder ändern?** Absolut – jede XMP‑Eigenschaft, einschließlich benutzerdefinierter Namespaces, kann gelesen oder aktualisiert werden.  
- **Ist die API thread‑sicher?** Die meisten Lese‑/Schreib‑Operationen sind sicher, wenn jeder Thread mit seiner eigenen `PsDocument`‑Instanz arbeitet.

## Was ist aspose.page xmp java?
`aspose.page xmp java` ist die Komponente von Aspose.Page für Java, die die Extensible Metadata Platform (XMP) in leicht zu nutzende Java‑Objekte abstrahiert. Sie ermöglicht das Manipulieren von Arrays, Bags und strukturierten Eigenschaften, ohne rohes XML zu bearbeiten. In der Praxis arbeiten Sie mit hoch‑level Methoden wie `setArrayItem` und `removeArrayItem`, um Metadaten sofort zu editieren.

## Warum aspose.page xmp java für EPS‑Metadaten verwenden?
Sie sollten diese Bibliothek einsetzen, wenn Sie präzise, automatisierte Kontrolle über EPS‑Metadaten in großem Umfang benötigen. Aspose.Page unterstützt **30+ XMP‑Schema‑Felder** und kann Dateien bis zu **500 MB** verarbeiten, ohne das gesamte Dokument in den Speicher zu laden, was sowohl Geschwindigkeit als auch geringen Speicherverbrauch gewährleistet. Die API garantiert zudem, dass Änderungen die ursprüngliche Grafik unverändert lassen, sodass das visuelle Rendering unberührt bleibt.

## Voraussetzungen
- Java Development Kit (JDK) 8 oder neuer installiert.  
- Aspose.Page für Java Bibliothek. Laden Sie die neueste JAR von [hier](https://releases.aspose.com/page/java/) herunter.  
- Eine gültige Aspose‑Lizenzdatei (oder Testlizenz), die im Klassenpfad liegt.

## So ändern Sie Array‑Einträge mit aspose.page xmp java
Dieser Abschnitt demonstriert den kompletten Workflow: Öffnen der EPS‑Datei, Abrufen des XMP‑Metadaten‑Objekts, Modifizieren bestimmter Array‑Einträge und schließlich Schreiben des aktualisierten Dokuments zurück auf die Festplatte. Jeder Schritt wird mit prägnantem Java‑Code illustriert, sodass er leicht in eigene Anwendungen integriert werden kann.

### Schritt 1: XMP‑Metadaten abrufen
Rufen Sie `document.getXmpMetadata()` auf, um das XMP‑Metadaten‑Objekt zu erhalten, das mit der EPS‑Datei verknüpft ist.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

### Schritt 2: „dc:title“ Array‑Eintrag setzen
Verwenden Sie `xmpMetadata.setArrayItem("dc:title", 0, "New Title")`, um den ersten Titel‑Eintrag zu ersetzen.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one will be filled with values from PS metadata comments.
XmpMetadata xmp = document.getXmpMetadata();
```

### Schritt 3: „dc:creator“ Array‑Eintrag setzen
Analog dazu aktualisiert `xmpMetadata.setArrayItem("dc:creator", 0, "New Author")` den ersten Ersteller‑Eintrag.

```java
// Set "dc:title" array item by index 0 
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```

### Schritt 4: Ausgabe‑EPS‑Dateistream initialisieren
Erzeugen Sie einen `FileOutputStream`, der auf die Ziel‑EPS‑Datei zeigt, um das aktualisierte Dokument zu schreiben.

```java
// Set "dc:creator" array item by index 0
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```

### Schritt 5: Dokument mit geänderten XMP‑Metadaten speichern
Die Klasse `PsDocument` repräsentiert ein EPS‑Dokument und stellt die Methode `save` bereit, um Änderungen in einen Stream zu schreiben.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

## Häufige Stolperfallen & Tipps
- **Index außerhalb des Bereichs:** Stellen Sie sicher, dass der Ziel‑Index existiert; andernfalls wirft Aspose eine `ArrayIndexOutOfBoundsException`.  
- **Stream‑Verwaltung:** Schließen Sie Streams immer in einem `finally`‑Block oder nutzen Sie try‑with‑resources, um Dateisperren zu vermeiden.  
- **Lizenzaktivierung:** Das Vergessen, eine gültige Lizenz anzuwenden, führt zu einem Wasserzeichen‑EPS im Testmodus.  
- **Große Dateien:** Für EPS‑Dateien größer als 200 MB sollten Sie die JVM‑Heap‑Größe (`-Xmx2g`) erhöhen, um Speicherengpässe zu vermeiden.

## Häufig gestellte Fragen

**F: Kann ich mehrere Array‑Einträge in einem Aufruf aktualisieren?**  
A: Nein. Sie müssen `setArrayItem` für jeden Index einzeln aufrufen; die API bietet keine Bulk‑Update‑Methode.

**F: Unterstützt aspose.page xmp java benutzerdefinierte Namespaces?**  
A: Ja. Geben Sie das vollständige Präfix (z. B. `myNS:customProp`) beim Aufruf von `setArrayItem` oder `removeArrayItem` an.

**F: Wie prüfe ich, ob die Metadaten korrekt aktualisiert wurden?**  
A: Laden Sie das EPS erneut mit `PsDocument`, rufen Sie `getXmpMetadata()` auf und inspizieren Sie die zurückgegebenen Werte, oder öffnen Sie die Datei in einem XMP‑Viewer.

**F: Ist es möglich, ein Array‑Element vollständig zu entfernen?**  
A: Verwenden Sie `removeArrayItem(namespace, index)`, um einen bestimmten Eintrag aus einem XMP‑Array zu löschen.

**F: Wirken sich die Änderungen auf das visuelle Erscheinungsbild des EPS aus?**  
A: Nein. XMP‑Metadaten werden separat vom Grafik‑Inhalt gespeichert und verändern nicht die Render‑Darstellung des EPS.

## Fazit
Sie haben nun das **aspose.page xmp tutorial** für Java gemeistert und können Array‑Einträge in EPS‑XMP‑Metadaten sicher ändern. Diese Fähigkeit ermöglicht automatisierte Dokument‑Pipelines, massenhafte Metadaten‑Updates und ein besseres Asset‑Management, ohne die visuellen Daten zu berühren.

---

**Zuletzt aktualisiert:** 2026-05-15  
**Getestet mit:** Aspose.Page für Java 24.11 (zum Zeitpunkt der Erstellung)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

```java
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Verwandte Tutorials

- [Array-Elemente in XMP‑Metadaten mit Java hinzufügen](/page/java/xmp-metadata-manipulation/add-array-items/)
- [aspose page xmp tutorial – Benannten Wert in XMP mit Java ändern](/page/java/xmp-metadata-manipulation/change-named-value/)
- [XMP‑Metadaten mit Java auslesen – Aspose.Page‑Leitfaden](/page/java/xmp-metadata-manipulation/get-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}