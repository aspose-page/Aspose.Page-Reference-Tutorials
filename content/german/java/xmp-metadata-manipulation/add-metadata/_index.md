---
title: Fügen Sie Metadaten in XMP mit Java hinzu
linktitle: Fügen Sie Metadaten in XMP mit Java hinzu
second_title: Aspose.Page Java-API
description: Entdecken Sie die nahtlose Integration von Aspose.Page für Java und erfahren Sie, wie Sie mühelos XMP-Metadaten zu Ihren EPS-Dateien hinzufügen. Verbessern Sie noch heute Ihr Dokumentenmanagement!
type: docs
weight: 11
url: /de/java/xmp-metadata-manipulation/add-metadata/
---
## Einführung
Möchten Sie die Metadaten Ihres Dokuments durch das Hinzufügen von XMP-Informationen mithilfe von Java verbessern? Suchen Sie nicht weiter! Diese Schritt-für-Schritt-Anleitung führt Sie durch den Prozess des Hinzufügens von Metadaten zu einer EPS-Datei mithilfe der Aspose.Page für Java-Bibliothek. Aspose.Page ist ein leistungsstarkes Tool, das Dokumentmanipulationsaufgaben in Java-Anwendungen vereinfacht.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Grundkenntnisse der Java-Programmierung.
-  Aspose.Page für Java-Bibliothek installiert. Sie können es herunterladen[Hier](https://releases.aspose.com/page/java/).
- Eine EPS-Datei, die Sie ändern möchten.
## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete in Ihr Java-Programm:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```
## Schritt 1: XMP-Metadaten abrufen
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Initialisieren Sie den EPS-Eingabedateistream
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Holen Sie sich XMP-Metadaten. Wenn die EPS-Datei keine XMP-Metadaten enthält, wird eine neue mit Werten aus PS-Metadatenkommentaren (%%Creator, %%CreateDate, %%Title usw.) erstellt.
XmpMetadata xmp = document.getXmpMetadata();
```
Stellen Sie sicher, dass Sie „Ihr Dokumentenverzeichnis“ durch den tatsächlichen Pfad ersetzen, in dem Ihre Dokumente gespeichert sind.

## Schritt 2: CreatorTool-Wert abrufen
```java
// Rufen Sie den Wert „CreatorTool“ ab
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## Schritt 3: Rufen Sie den CreateDate-Wert ab
```java
// Rufen Sie den Wert „CreateDate“ ab
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Schritt 4: Titelwert abrufen
```java
// Rufen Sie den Wert „Titel“ ab
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```
## Schritt 5: Formatwert abrufen
```java
//Wert „Format“ abrufen
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## Schritt 6: Erstellerwert abrufen
```java
// Holen Sie sich den „Ersteller“-Wert
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```
## Schritt 7: MetadataDate-Wert abrufen
```java
// Rufen Sie den Wert „MetadataDate“ ab
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```
## Schritt 8: Dokument mit neuen XMP-Metadaten speichern
```java
// Ausgabe-EPS-Dateistream initialisieren
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Dokument mit neuen XMP-Metadaten speichern
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Vergessen Sie abschließend nicht, den Eingabe-EPS-Stream zu schließen:
```java
// Schließen Sie den Eingabe-EPS-Stream
psStream.close();
```
Jetzt haben Sie mit Aspose.Page für Java erfolgreich Metadaten zu Ihrer EPS-Datei hinzugefügt!
## Abschluss
In diesem Tutorial haben wir den Prozess des Hinzufügens von XMP-Metadaten zu einer EPS-Datei mithilfe der Aspose.Page for Java-Bibliothek untersucht. Mit diesem leistungsstarken Tool können Sie Dokumente nahtlos bearbeiten und so Ihre gesamte Dokumentenverwaltung verbessern.
## FAQs
### F: Ist die Nutzung von Aspose.Page für Java kostenlos?
 A: Aspose.Page für Java ist ein kommerzielles Produkt. Sie können die Funktionen im Rahmen einer kostenlosen Testversion erkunden[Hier](https://releases.aspose.com/).
### F: Wo finde ich die Dokumentation für Aspose.Page für Java?
 A: Die Dokumentation ist verfügbar[Hier](https://reference.aspose.com/page/java/).
### F: Wie kann ich eine temporäre Lizenz für Aspose.Page für Java erhalten?
 A: Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).
### F: Welche Dateiformate unterstützt Aspose.Page für Java?
A: Aspose.Page für Java unterstützt verschiedene Formate, darunter EPS, PDF und XPS.
### F: Kann ich Aspose.Page für Java kaufen?
 A: Ja, Sie können Aspose.Page für Java erwerben[Hier](https://purchase.aspose.com/buy).