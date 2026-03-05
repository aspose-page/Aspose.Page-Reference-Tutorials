---
date: 2026-03-05
description: Erfahren Sie, wie Sie dc:title‑Array‑Elemente in den XMP‑Metadaten von
  EPS‑Dateien mit Aspose.Page für Java hinzufügen. Folgen Sie dieser Schritt‑für‑Schritt‑Anleitung
  für schnelle Ergebnisse.
linktitle: How to Add dc:title Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Wie man dc:title‑Array‑Elemente in XMP‑Metadaten mit Java hinzufügt
url: /de/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Array-Elemente in XMP-Metadaten mit Java hinzufügen

## Einleitung
In diesem Tutorial erfahren Sie **wie man dc:title** (und andere Array-Elemente) zu XMP-Metadaten in einer EPS-Datei mit Aspose.Page für Java hinzufügt. Das Aktualisieren von XMP-Metadaten ist nützlich, wenn Sie durchsuchbare Informationen – wie Titel, Ersteller oder Schlüsselwörter – direkt in Ihre Grafikdateien einbetten müssen. Wir gehen jeden Schritt durch, erklären, warum jede Zeile wichtig ist, und zeigen Ihnen, wie Sie die Änderungen überprüfen können.

## Schnelle Antworten
- **Was stellt “dc:title” dar?** Es ist die Dublin‑Core‑Titel‑Eigenschaft, die als XMP‑Array gespeichert wird.  
- **Warum XMP-Metadaten ändern?** Es ermöglicht ein besseres Asset‑Management, bessere Durchsuchbarkeit und die Einhaltung von Standards.  
- **Benötige ich einen bestehenden XMP‑Block?** Nein – Aspose.Page erzeugt bei Bedarf einen aus PS‑Kommentaren.  
- **Welche Bibliotheksversion wird benötigt?** Jede aktuelle Aspose.Page‑Version für Java (getestet mit dem neuesten Build 2026).  
- **Kann ich andere Array‑Eigenschaften hinzufügen?** Ja – verwenden Sie die gleiche `addArrayItem`‑Methode für Eigenschaften wie `dc:creator`.

## Voraussetzungen
- Aspose.Page für Java Bibliothek installiert (JAR zum Klassenpfad Ihres Projekts hinzufügen).  
- Grundlegende Java‑Entwicklungserfahrung (JDK 8+ empfohlen).  
- Eine EPS‑Datei, die bereits XMP‑Metadaten enthält oder zumindest PS‑Metadaten‑Kommentare (z. B. `%%Title`, `%%Creator`).  

## Pakete importieren
Um zu beginnen, importieren Sie die Klassen, die zum Lesen, Manipulieren und Speichern von EPS‑Dateien erforderlich sind:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Schritt 1: EPS‑Dokument laden und XMP‑Metadaten abrufen
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

Hier öffnen wir die EPS‑Datei und fragen Aspose.Page nach ihrem XMP‑Block. Fehlt das XMP, erzeugt die Bibliothek automatisch einen aus vorhandenen PS‑Kommentaren, sodass Sie stets einen Metadaten‑Container zur Verfügung haben.

## Schritt 2: Neues **dc:title**‑Array‑Element hinzufügen  
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```

Diese Zeile zeigt **wie man dc:title hinzufügt**. Ersetzen Sie `"NewTitle"` durch den tatsächlichen Titel, den Sie einbetten möchten. Die Methode fügt den Wert dem bestehenden Titel‑Array hinzu und bewahrt bereits vorhandene Titel.

## Schritt 3: Neues **dc:creator**‑Array‑Element hinzufügen  
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```

Analog können Sie die `dc:creator`‑Eigenschaft erweitern. Mehrere Ersteller können gespeichert werden; jeder Aufruf fügt einen weiteren Eintrag hinzu.

## Schritt 4: Ausgabestream vorbereiten  
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

Wir erstellen einen Stream für die modifizierte EPS‑Datei. Durch die Verwendung eines anderen Dateinamens (`xmp3_changed.eps`) bleibt die Originaldatei unverändert.

## Schritt 5: Dokument mit aktualisierten XMP‑Metadaten speichern  
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

Der Aufruf `save` schreibt die EPS‑Daten zusammen mit dem aktualisierten XMP‑Block. Der `finally`‑Block stellt sicher, dass das Dateihandle freigegeben wird, selbst wenn eine Ausnahme auftritt.

## Warum das wichtig ist
Das Einbetten genauer `dc:title`‑ und `dc:creator`‑Werte verbessert:

- **Durchsuchbarkeit** in Digital‑Asset‑Management‑Systemen (DAM).  
- **Konformität** mit Veröffentlichungsstandards, die Metadaten verlangen.  
- **Zusammenarbeit**, da Teammitglieder den Dateinhalt schnell erkennen können, ohne die EPS zu öffnen.

## Häufige Fallstricke & Tipps
- **Fallstrick:** Unabsichtliches Überschreiben vorhandener Array‑Elemente.  
  **Tipp:** Verwenden Sie `xmp.getArrayItems("dc:title")`, um aktuelle Werte zu prüfen, bevor Sie neue hinzufügen.  
- **Fallstrick:** Vergessen, Streams zu schließen, was zu Dateisperren führt.  
  **Tipp:** Wickeln Sie I/O immer in try‑with‑resources oder einen `finally`‑Block, wie gezeigt.  
- **Tipp:** Sie können mehrere `addArrayItem`‑Aufrufe verketten, um mehrere Titel oder Ersteller in einem Durchlauf hinzuzufügen.

## Häufig gestellte Fragen

### Kann ich Aspose.Page für Java mit anderen Dokumentformaten verwenden?
Ja, Aspose.Page unterstützt verschiedene Dokumentformate, darunter EPS, PDF und XPS.

### Gibt es eine kostenlose Testversion für Aspose.Page für Java?
Ja, Sie können die kostenlose Testversion [hier](https://releases.aspose.com/) nutzen.

### Wo finde ich die Dokumentation für Aspose.Page für Java?
Die Dokumentation ist [hier](https://reference.aspose.com/page/java/) verfügbar.

### Wie kann ich Aspose.Page für Java kaufen?
Sie können das Produkt [hier](https://purchase.aspose.com/buy) erwerben.

### Sind temporäre Lizenzen für Aspose.Page für Java verfügbar?
Ja, Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erhalten.

**Zuletzt aktualisiert:** 2026-03-05  
**Getestet mit:** Aspose.Page für Java (neueste 2026‑Version)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}