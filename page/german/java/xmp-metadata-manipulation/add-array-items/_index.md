---
title: Fügen Sie Array-Elemente in XMP-Metadaten mit Java hinzu
linktitle: Fügen Sie Array-Elemente in XMP-Metadaten mit Java hinzu
second_title: Aspose.Page Java-API
description: Verbessern Sie EPS-Dateien mit Aspose.Page für Java. Erfahren Sie, wie Sie Array-Elemente mühelos zu XMP-Metadaten hinzufügen. Folgen Sie jetzt unserer Schritt-für-Schritt-Anleitung!
weight: 10
url: /de/java/xmp-metadata-manipulation/add-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fügen Sie Array-Elemente in XMP-Metadaten mit Java hinzu

## Einführung
Willkommen zu unserer Schritt-für-Schritt-Anleitung zur Verwendung von Aspose.Page für Java zum Hinzufügen von Array-Elementen in XMP-Metadaten. Aspose.Page ist eine leistungsstarke Java-Bibliothek, mit der Sie verschiedene Dokumentformate, einschließlich EPS-Dateien, bearbeiten und damit arbeiten können. In diesem Tutorial konzentrieren wir uns auf die spezifische Aufgabe des Hinzufügens von Array-Elementen in XMP-Metadaten mithilfe von Java.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Aspose.Page für Java-Bibliothek installiert.
- Grundlegendes Verständnis der Java-Programmierung.
- Eine gültige EPS-Datei mit vorhandenen XMP-Metadaten oder PS-Metadatenkommentaren.
## Pakete importieren
Um zu beginnen, müssen Sie die notwendigen Pakete für die Arbeit mit Aspose.Page importieren. Fügen Sie die folgenden Zeilen am Anfang Ihrer Java-Datei ein:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## Schritt 1: XMP-Metadaten abrufen
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Initialisieren Sie den EPS-Eingabedateistream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Holen Sie sich XMP-Metadaten. Wenn die EPS-Datei keine XMP-Metadaten enthält, erhalten wir eine neue, gefüllt mit Werten aus PS-Metadatenkommentaren (%%Creator, %%CreateDate, %%Title usw.).
XmpMetadata xmp = document.getXmpMetadata();
```
In diesem Schritt rufen wir die vorhandenen XMP-Metadaten aus der EPS-Datei ab. Wenn die EPS-Datei noch keine XMP-Metadaten enthält, generiert Aspose.Page eine neue und füllt sie mit Werten aus PS-Metadatenkommentaren.
## Schritt 2: Array-Element „dc:title“ hinzufügen
```java
// Fügen Sie ein weiteres Array-Element „dc:title“ hinzu
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Jetzt fügen wir der Eigenschaft „dc:title“ in den XMP-Metadaten ein neues Array-Element hinzu. Ersetzen Sie „NewTitle“ durch den gewünschten Titel.
## Schritt 3: Array-Element „dc:creator“ hinzufügen
```java
// Fügen Sie ein weiteres Array-Element „dc:creator“ hinzu
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
Ebenso fügen wir der Eigenschaft „dc:creator“ in den XMP-Metadaten ein neues Array-Element hinzu. Ersetzen Sie „NewCreator“ durch die gewünschten Erstellerinformationen.
## Schritt 4: Initialisieren Sie den Ausgabe-EPS-Dateistream
```java
// Ausgabe-EPS-Dateistream initialisieren
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Bereiten Sie den Ausgabe-EPS-Dateistream vor, in dem das geänderte Dokument mit aktualisierten XMP-Metadaten gespeichert wird.
## Schritt 5: Dokument mit geänderten XMP-Metadaten speichern
```java
//Dokument mit geänderten XMP-Metadaten speichern
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Speichern Sie das Dokument mit den aktualisierten XMP-Metadaten in der EPS-Ausgabedatei.
## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Page für Java Array-Elemente in XMP-Metadaten hinzufügen. Diese leistungsstarke Bibliothek vereinfacht die Bearbeitung von EPS-Dateien und bietet umfangreiche Funktionen für die Dokumentenverarbeitung.
## Häufig gestellte Fragen

### Kann ich Aspose.Page für Java mit anderen Dokumentformaten verwenden?
Ja, Aspose.Page unterstützt verschiedene Dokumentformate, darunter EPS, PDF und XPS.
### Gibt es eine kostenlose Testversion für Aspose.Page für Java?
 Ja, Sie können auf die kostenlose Testversion zugreifen[Hier](https://releases.aspose.com/).
### Wo finde ich die Dokumentation für Aspose.Page für Java?
 Die Dokumentation ist verfügbar[Hier](https://reference.aspose.com/page/java/).
### Wie kann ich Aspose.Page für Java kaufen?
 Sie können das Produkt kaufen[Hier](https://purchase.aspose.com/buy).
### Sind temporäre Lizenzen für Aspose.Page für Java verfügbar?
 Ja, Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
