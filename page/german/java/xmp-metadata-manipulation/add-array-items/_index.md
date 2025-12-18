---
date: 2025-12-18
description: Erfahren Sie, wie Sie Metadaten hinzufügen, indem Sie Array‑Elemente
  in die XMP‑Metadaten von EPS‑Dateien mit Aspose.Page für Java einfügen. Folgen Sie
  unserer Schritt‑für‑Schritt‑Anleitung.
linktitle: Add Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Wie man Metadaten hinzufügt – Array‑Elemente in XMP (Java)
url: /de/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Array-Elemente in XMP-Metadaten mit Java hinzufügen

## So fügen Sie Metadaten hinzu
Willkommen zu unserem Schritt‑für‑Schritt‑Leitfaden, wie man **Metadaten** zu EPS‑Dateien mit Aspose.Page für Java hinzufügt. In diesem Tutorial führen wir Sie durch das Hinzufügen von Array‑Elementen zu XMP‑Metadaten – ein häufiges Bedürfnis, wenn Sie Dokumentinformationen wie Titel oder Ersteller anreichern müssen. Am Ende verstehen Sie, warum XMP wertvoll ist, wie man es programmgesteuert manipuliert und wie man die aktualisierte EPS‑Datei speichert.

## Schnelle Antworten
- **Welche Bibliothek wird verwendet?** Aspose.Page for Java  
- **Welches Dateiformat wird angesprochen?** EPS (Encapsulated PostScript)  
- **Kann ich mehrere Titel hinzufügen?** Ja, verwenden Sie `xmp.addArrayItem("dc:title", ...)` wiederholt  
- **Benötige ich eine Lizenz für die Produktion?** Ja, eine gültige Aspose.Page‑Lizenz ist erforderlich  
- **Ist der Code mit Java 8+ kompatibel?** Absolut, er funktioniert mit allen modernen Java‑Versionen  

## Voraussetzungen
Bevor wir ins Tutorial einsteigen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Aspose.Page for Java Bibliothek installiert.
- Grundlegendes Verständnis der Java‑Programmierung.
- Eine gültige EPS‑Datei mit vorhandenen XMP‑Metadaten oder PS‑Metadaten‑Kommentaren.

## Pakete importieren
Um zu beginnen, müssen Sie die notwendigen Pakete für die Arbeit mit Aspose.Page importieren. Fügen Sie die folgenden Zeilen am Anfang Ihrer Java‑Datei ein:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Schritt 1: XMP‑Metadaten abrufen
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
In diesem Schritt rufen wir die vorhandenen XMP‑Metadaten aus der EPS‑Datei ab. Wenn die EPS‑Datei noch keine XMP‑Metadaten enthält, erzeugt Aspose.Page neue und füllt sie mit Werten aus den PS‑Metadaten‑Kommentaren.

## Schritt 2: Array‑Element "dc:title" hinzufügen
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Jetzt fügen wir ein neues Array‑Element zur **dc:title**‑Eigenschaft in den XMP‑Metadaten hinzu. Ersetzen Sie `"NewTitle"` durch den gewünschten Titel.

## Schritt 3: Array‑Element "dc:creator" hinzufügen
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
Analog fügen wir ein neues Array‑Element zur **dc:creator**‑Eigenschaft in den XMP‑Metadaten hinzu. Ersetzen Sie `"NewCreator"` durch die gewünschten Ersteller‑Informationen.

## Schritt 4: Ausgabestream für EPS‑Datei initialisieren
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Bereiten Sie den Ausgabestream für die EPS‑Datei vor, in dem das modifizierte Dokument mit aktualisierten XMP‑Metadaten gespeichert wird.

## Schritt 5: Dokument mit geänderten XMP‑Metadaten speichern
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Speichern Sie das Dokument mit den aktualisierten XMP‑Metadaten in die Ausgabedatei EPS.

## Fazit
Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, **wie man Metadaten** durch Einfügen von Array‑Elementen in XMP‑Metadaten mit Aspose.Page für Java hinzufügt. Diese leistungsstarke Bibliothek vereinfacht das Manipulieren von EPS‑Dateien und bietet umfangreiche Funktionen für die Dokumentenverarbeitung.

## Häufig gestellte Fragen

### Kann ich Aspose.Page für Java mit anderen Dokumentformaten verwenden?
Ja, Aspose.Page unterstützt verschiedene Dokumentformate, einschließlich EPS, PDF und XPS.

### Gibt es eine kostenlose Testversion für Aspose.Page für Java?
Ja, Sie können die kostenlose Testversion [hier](https://releases.aspose.com/) nutzen.

### Wo finde ich die Dokumentation für Aspose.Page für Java?
Die Dokumentation ist [hier](https://reference.aspose.com/page/java/) verfügbar.

### Wie kann ich Aspose.Page für Java erwerben?
Sie können das Produkt [hier](https://purchase.aspose.com/buy) kaufen.

### Sind temporäre Lizenzen für Aspose.Page für Java verfügbar?
Ja, Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erhalten.

## Weitere häufig gestellte Fragen

**F: Kann ich mehr als ein Array‑Element zur selben Eigenschaft hinzufügen?**  
**A: Absolut. Rufen Sie `xmp.addArrayItem` mehrmals für dieselbe Eigenschaft auf, um eine Liste von Werten zu erstellen.**

**F: Funktioniert dieser Ansatz mit bestehenden XMP‑Schemas außer Dublin Core?**  
**A: Ja, Sie können Array‑Elemente zu jeder XMP‑Eigenschaft hinzufügen, solange der Namensraum korrekt referenziert wird.**

**F: Wie kann ich überprüfen, ob die Metadaten korrekt hinzugefügt wurden?**  
**A: Öffnen Sie die resultierende EPS‑Datei in einem Viewer, der XMP unterstützt (z. B. Adobe Bridge), oder extrahieren Sie die Metadaten programmgesteuert mit den `XmpMetadata`‑Methoden.**

---

**Last Updated:** 2025-12-18  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}