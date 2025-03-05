---
title: Werte in XMP mit Java ändern
linktitle: Werte in XMP mit Java ändern
second_title: Aspose.Page Java-API
description: Erweitern Sie EPS-Dokumente mit Aspose.Page für Java. Ändern Sie mühelos XMP-Metadaten für maßgeschneiderte und professionelle Inhalte. #JavaEntwicklung
type: docs
weight: 17
url: /de/java/xmp-metadata-manipulation/change-values/
---
## Einführung
Im Bereich der Dokumentenverarbeitung und -manipulation sticht Aspose.Page für Java als leistungsstarkes Tool hervor. Dieses Tutorial befasst sich mit dem Prozess der Änderung von XMP-Werten (Extensible Metadata Platform) in EPS-Dokumenten (Encapsulated PostScript) mithilfe von Java mit der Aspose.Page-Bibliothek. Indem Sie der bereitgestellten Schritt-für-Schritt-Anleitung folgen, erfahren Sie, wie Sie Metadaten mühelos ändern und so sicherstellen, dass Ihre Dokumente auf Ihre spezifischen Anforderungen zugeschnitten sind.
## Voraussetzungen
Bevor wir mit diesem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1. Java-Entwicklungsumgebung: Stellen Sie sicher, dass auf Ihrem Computer eine funktionierende Java-Entwicklungsumgebung vorhanden ist.
2.  Aspose.Page für Java-Bibliothek: Laden Sie die Aspose.Page für Java-Bibliothek herunter und installieren Sie sie. Sie können das erforderliche Paket finden[Hier](https://releases.aspose.com/page/java/).
## Pakete importieren
Beginnen Sie mit dem Importieren der erforderlichen Pakete in Ihr Java-Projekt. Diese Pakete sind für die Interaktion mit und die Bearbeitung von EPS-Dokumenten von entscheidender Bedeutung.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```
## Schritt 1: XMP-Metadaten abrufen
Rufen Sie XMP-Metadaten aus dem EPS-Dokument ab. Wenn die EPS-Datei keine XMP-Metadaten enthält, wird eine neue mit Werten aus PS-Metadatenkommentaren wie %%Creator, %%CreateDate und %%Title erstellt.
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Initialisieren Sie den EPS-Eingabedateistream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Holen Sie sich XMP-Metadaten. Wenn die EPS-Datei keine XMP-Metadaten enthält, wird eine neue mit Werten aus PS-Metadatenkommentaren erstellt
XmpMetadata xmp = document.getXmpMetadata();
```
## Schritt 2: Ändern Sie den Wert „ModifyDate“.
Ändern Sie den Wert „ModifyDate“ in den XMP-Metadaten, um das gewünschte Datum wiederzugeben.
```java
// Ändern Sie den Wert „ModifyDate“.
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```
## Schritt 3: Ändern Sie den Wert „Ersteller“.
Aktualisieren Sie den Wert „Creator“ in den XMP-Metadaten, um den Ersteller des Dokuments anzugeben.
```java
// Ändern Sie den Wert „Ersteller“.
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```
## Schritt 4: Ändern Sie den Wert „Titel“.
Ändern Sie den Wert „Titel“ in den XMP-Metadaten, um einen geeigneten Titel für das Dokument festzulegen.
```java
//Ändern Sie den Wert „Titel“.
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```
## Schritt 5: Dokument mit geänderten XMP-Metadaten speichern
Speichern Sie das Dokument mit den aktualisierten XMP-Metadaten in einer neuen EPS-Datei.
```java
// Ausgabe-EPS-Dateistream initialisieren
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
//Dokument mit geänderten XMP-Metadaten speichern
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Abschluss
Glückwunsch! Sie haben den Prozess der Änderung von XMP-Werten in EPS-Dokumenten mit Aspose.Page für Java erfolgreich gemeistert. Dieses Tutorial vermittelt Ihnen das Wissen, Metadaten zu ändern und sicherzustellen, dass Ihre Dokumente nahtlos an Ihre spezifischen Anforderungen angepasst werden.
## FAQs
### F: Wie kann ich beim Ändern von XMP-Werten Zeitzonen berücksichtigen?
 Nutzen`TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` um die Konsistenz der Zeitzoneneinstellungen sicherzustellen.
### F: Kann ich mehrere XMP-Werte in einem einzigen Vorgang ändern?
 Ja, indem Sie die verwenden`put` Mit der Methode für jeden gewünschten Wert können Sie mehrere XMP-Werte gleichzeitig ändern.
### F: Wo finde ich zusätzliche Dokumentation für Aspose.Page für Java?
 Entdecken Sie die umfassende Dokumentation[Hier](https://reference.aspose.com/page/java/).
### F: Gibt es eine kostenlose Testversion für Aspose.Page für Java?
 Ja, Sie können auf die kostenlose Testversion zugreifen[Hier](https://releases.aspose.com/).
### F: Wie kann ich eine temporäre Lizenz für Aspose.Page für Java erhalten?
 Besorgen Sie sich eine temporäre Lizenz[Hier](https://purchase.aspose.com/temporary-license/).