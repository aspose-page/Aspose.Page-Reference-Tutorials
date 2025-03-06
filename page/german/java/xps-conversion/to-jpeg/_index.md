---
title: Konvertieren Sie XPS in JPEG in Java
linktitle: Konvertieren Sie XPS in JPEG in Java
second_title: Aspose.Page Java-API
description: Erfahren Sie, wie Sie XPS mit Aspose.Page in Java in JPEG konvertieren. Eine umfassende Anleitung mit Schritt-für-Schritt-Anleitungen für eine nahtlose Integration.
weight: 11
url: /de/java/xps-conversion/to-jpeg/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konvertieren Sie XPS in JPEG in Java

## Einführung
In diesem Tutorial erfahren Sie, wie Sie XPS-Dateien (XML Paper Specification) mit Aspose.Page für Java in JPEG-Bilder konvertieren. Aspose.Page ist eine leistungsstarke Java-Bibliothek, die Entwicklern die nahtlose Arbeit mit XPS und anderen Dokumentformaten ermöglicht. Diese Schritt-für-Schritt-Anleitung hilft Ihnen, den Prozess zu verstehen und ihn in Ihren Java-Anwendungen zu implementieren.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Java-Entwicklungsumgebung: Stellen Sie sicher, dass auf Ihrem Computer eine Java-Entwicklungsumgebung eingerichtet ist.
-  Aspose.Page für Java-Bibliothek: Laden Sie die Aspose.Page für Java-Bibliothek herunter und installieren Sie sie. Sie finden die Bibliothek[Hier](https://releases.aspose.com/page/java/).
- Beispiel-XPS-Dokument: Sie verfügen über ein Beispiel-XPS-Dokument, das Sie in JPEG konvertieren möchten.
## Pakete importieren
Beginnen Sie mit dem Importieren der erforderlichen Pakete in Ihre Java-Klasse:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Schritt 1: Pfade und XPS-Dokument initialisieren
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Initialisieren Sie den XPS-Eingabestream
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Schritt 2: JpegSaveOptions festlegen
```java
// Initialisieren Sie das Optionsobjekt mit den erforderlichen Parametern.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## Schritt 3: Rendering-Gerät erstellen
```java
// Erstellen Sie ein Rendering-Gerät für das PDF-Format
ImageDevice device = new ImageDevice();
```
## Schritt 4: XPS als JPEG speichern
```java
document.save(device, options);
```
## Schritt 5: JPEG-Seiten iterieren und speichern
```java
//Dokumentpartitionen durchlaufen (feste Dokumente, in XPS-Begriffen)
for (int i = 0; i < device.getResult().length; i++) {
    // Durchlaufen Sie Partitionsseiten
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Bildausgabestream initialisieren
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // Bild schreiben
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //Schließen Sie den Stream
        imageStream.close();
    }
}
```
Mit dieser Reihe von Schritten wird Ihr XPS-Dokument effektiv in JPEG-Bilder konvertiert, die jeweils separat gespeichert werden.
## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie XPS mit Aspose.Page in Java in JPEG konvertieren. Dieser Prozess ist für Entwickler, die mit der Dokumentkonvertierung in Java-Anwendungen arbeiten, von unschätzbarem Wert.
## Häufig gestellte Fragen

### F: Ist Aspose.Page für kommerzielle Projekte geeignet?
 A: Ja, Aspose.Page ist ein kommerzielles Produkt mit verfügbaren Lizenzoptionen. Überprüfen[Hier](https://purchase.aspose.com/buy) für Details.
### F: Kann ich Aspose.Page vor dem Kauf testen?
 A: Ja, Sie können eine kostenlose Testversion erhalten[Hier](https://releases.aspose.com/).
### F: Wo finde ich die Aspose.Page-Dokumentation?
 A: Die Dokumentation ist verfügbar[Hier](https://reference.aspose.com/page/java/).
### F: Wie kann ich Unterstützung für Aspose.Page erhalten?
 A: Besuchen Sie die[Aspose.Page-Forum](https://forum.aspose.com/c/page/39) für gemeinschaftsbasierte Unterstützung.
### F: Benötige ich zum Testen eine temporäre Lizenz?
 A: Ja, Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
