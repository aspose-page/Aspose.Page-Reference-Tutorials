---
title: Holen Sie sich Metadaten von XMP mit Java
linktitle: Holen Sie sich Metadaten von XMP mit Java
second_title: Aspose.Page Java-API
description: Nutzen Sie die Leistungsfähigkeit von Aspose.Page für Java, um XMP-Metadaten mühelos zu extrahieren. Verbessern Sie die Dokumentenanalyse mit unserer Schritt-für-Schritt-Anleitung!
type: docs
weight: 18
url: /de/java/xmp-metadata-manipulation/get-metadata/
---
## Einführung
Willkommen zu unserer Schritt-für-Schritt-Anleitung zur Verwendung von Aspose.Page für Java zum Extrahieren von Metadaten aus XMP-Dateien. XMP (Extensible Metadata Platform) bietet eine standardisierte Möglichkeit, Metadaten in Dateien zu speichern. Dieses Tutorial konzentriert sich auf das Abrufen wichtiger Informationen aus XMP mithilfe von Java und bietet Einblicke in Dokumentdetails.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Java Development Kit (JDK): Stellen Sie sicher, dass Java auf Ihrem Computer installiert ist.
-  Aspose.Page für Java: Laden Sie die Aspose.Page-Bibliothek herunter und installieren Sie sie[Hier](https://releases.aspose.com/page/java/).
## Pakete importieren
Importieren Sie in Ihrem Java-Projekt die erforderlichen Pakete:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## Schritt 1: Initialisieren Sie den Eingabe-EPS-Dateistream
Beginnen Sie damit, den Pfad zu Ihrem Dokumentverzeichnis festzulegen und den Eingabe-EPS-Dateistream zu initialisieren.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```
## Schritt 2: XMP-Metadaten abrufen
Rufen Sie XMP-Metadaten aus der EPS-Datei ab. Wenn der Datei XMP-Metadaten fehlen, wird eine neue mit Werten aus PS-Metadatenkommentaren generiert.
```java
XmpMetadata xmp = document.getXmpMetadata();
```
## Schritt 3: CreatorTool-Informationen extrahieren
Überprüfen und drucken Sie den „CreatorTool“-Wert aus den XMP-Metadaten.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## Schritt 4: Extrahieren Sie die CreateDate-Informationen
Überprüfen und drucken Sie den Wert „CreateDate“ aus den XMP-Metadaten.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Schritt 5: Miniaturbildbreite abrufen
Wenn Miniaturansichten vorhanden sind, extrahieren Sie die Breite der ersten Miniaturansicht und drucken Sie sie aus.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```
## Schritt 6: Formatinformationen extrahieren
Überprüfen Sie den „Format“-Wert aus den XMP-Metadaten und drucken Sie ihn aus.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## Schritt 7: DocumentID abrufen
Überprüfen und drucken Sie den Wert „DocumentID“ aus den XMP-Metadaten.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```
## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie XMP-Metadaten mit Aspose.Page für Java extrahieren. Dieser Leitfaden bietet einen umfassenden Überblick über den Prozess und stellt sicher, dass Sie wichtige Informationen effektiv aus Ihren Dokumenten abrufen können.
## Häufig gestellte Fragen
### Kann ich Aspose.Page für Java mit anderen Programmiersprachen verwenden?
 Ja, Aspose.Page unterstützt mehrere Sprachen, darunter Java, .NET und mehr. Überprüf den[Dokumentation](https://reference.aspose.com/page/java/) für Details.
### Ist eine kostenlose Testversion für Aspose.Page für Java verfügbar?
 Ja, Sie können auf die kostenlose Testversion zugreifen[Hier](https://releases.aspose.com/).
### Wo finde ich Unterstützung für Aspose.Page für Java?
 Besuche den[Aspose.Page-Forum](https://forum.aspose.com/c/page/39) für die Unterstützung der Gemeinschaft.
### Wie erhalte ich eine temporäre Lizenz für Aspose.Page für Java?
 Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).
### Gibt es zusätzliche Ressourcen für Aspose.Page für Java?
 Entdecken Sie das Ganze[Dokumentation](https://reference.aspose.com/page/java/) und laden Sie die Bibliothek herunter[Hier](https://releases.aspose.com/page/java/).