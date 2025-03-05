---
title: Fügen Sie einfache Eigenschaften in XMP mit Java hinzu
linktitle: Fügen Sie einfache Eigenschaften in XMP mit Java hinzu
second_title: Aspose.Page Java-API
description: Nutzen Sie das Potenzial von Aspose.Page für Java mit unserem Leitfaden zum Hinzufügen von Eigenschaften zu XMP-Metadaten in EPS-Dateien. Verbessern Sie die Dokumentenverarbeitung mühelos!
type: docs
weight: 14
url: /de/java/xmp-metadata-manipulation/add-simple-properties/
---
## Einführung
In der sich ständig weiterentwickelnden Landschaft der Dokumentenverarbeitung ist die effiziente Verwaltung von Metadaten von entscheidender Bedeutung. Aspose.Page für Java ermöglicht Entwicklern die nahtlose Bearbeitung von XMP-Daten (Extensible Metadata Platform). In diesem Tutorial untersuchen wir den Prozess des Hinzufügens einfacher Eigenschaften zu XMP mithilfe von Java und stellen Ihnen eine umfassende Schritt-für-Schritt-Anleitung zur Verfügung.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundkenntnisse der Java-Programmierung.
-  Aspose.Page für Java-Bibliothek installiert. Sie können es herunterladen[Hier](https://releases.aspose.com/page/java/).
- Eine Beispiel-EPS-Datei mit Metadaten. Wenn Sie noch keine haben, können Sie gerne die bereitgestellte Datei „xmp3.eps“ verwenden.
## Pakete importieren
Stellen Sie sicher, dass Sie die erforderlichen Pakete importieren, um Ihr Projekt zu starten:
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
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Initialisieren Sie den EPS-Eingabedateistream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Holen Sie sich XMP-Metadaten. Wenn die EPS-Datei keine XMP-Metadaten enthält, erhalten wir eine neue, gefüllt mit Werten aus PS-Metadatenkommentaren (%%Creator, %%CreateDate, %%Title usw.).
XmpMetadata xmp = document.getXmpMetadata();
```
## Schritt 2: Datumseigenschaft hinzufügen
```java
// Datumseigenschaftswert „xmp:Date1“ hinzufügen
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```
## Schritt 3: Integer-Eigenschaft hinzufügen
```java
// Fügen Sie den ganzzahligen Eigenschaftswert „xmp:Intg1“ hinzu
xmp.put("xmp:Intg1", new XmpValue(111));
```
## Schritt 4: Doppelte Eigenschaft hinzufügen
```java
// Fügen Sie den Double-Eigenschaftswert „xmp:Double1“ hinzu
xmp.put("xmp:Double1", new XmpValue(111.11D));
```
## Schritt 5: String-Eigenschaft hinzufügen
```java
// Fügen Sie den Wert der String-Eigenschaft „xmp:String1“ hinzu
xmp.put("xmp:String1", new XmpValue("ABC"));
```
## Schritt 6: Dokument speichern
```java
// Ausgabe-EPS-Dateistream initialisieren
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
//Dokument mit geänderten XMP-Metadaten speichern
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Schritt 7: Streams schließen
```java
// Schließen Sie den Eingabe-EPS-Stream
psStream.close();
```
## Abschluss
Aspose.Page für Java vereinfacht die Bearbeitung von XMP-Metadaten in EPS-Dateien. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie mühelos einfache Eigenschaften hinzufügen, um die Metadaten Ihres Dokuments zu verbessern.
## Häufig gestellte Fragen
### Kann ich Aspose.Page für Java mit anderen Programmiersprachen verwenden?
Aspose.Page unterstützt hauptsächlich Java, es sind jedoch Versionen für andere Sprachen wie .NET verfügbar.
### Ist eine kostenlose Testversion für Aspose.Page für Java verfügbar?
 Ja, Sie können die Funktionen von Aspose.Page erkunden, indem Sie eine kostenlose Testversion erhalten[Hier](https://releases.aspose.com/).
### Wo finde ich eine ausführliche Dokumentation für Aspose.Page für Java?
 Die Dokumentation ist verfügbar[Hier](https://reference.aspose.com/page/java/).
### Wie kann ich eine temporäre Lizenz für Aspose.Page für Java erhalten?
 Eine temporäre Lizenz kann erworben werden[Hier](https://purchase.aspose.com/temporary-license/).
### Wo kann ich Aspose.Page für Java kaufen?
 Sie können das Produkt kaufen[Hier](https://purchase.aspose.com/buy).