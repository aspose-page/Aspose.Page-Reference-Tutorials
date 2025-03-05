---
title: Konvertieren Sie XPS in PNG in Java
linktitle: Konvertieren Sie XPS in PNG in Java
second_title: Aspose.Page Java-API
description: Konvertieren Sie XPS mit Aspose.Page mühelos in Java in PNG. Optimieren Sie Dokumentaufgaben mit dieser zuverlässigen und entwicklerfreundlichen Lösung.
type: docs
weight: 13
url: /de/java/xps-conversion/to-png/
---
## Einführung
In der dynamischen Welt der Softwareentwicklung besteht häufig die Notwendigkeit, XPS-Dokumente (XML Paper Specification) in PNG-Bilder (Portable Network Graphics) zu konvertieren. Um diese Aufgabe nahtlos in Java zu erledigen, bietet Aspose.Page eine leistungsstarke Lösung. In diesem Tutorial werden wir den Prozess der Konvertierung von XPS in PNG mit Aspose.Page für Java durchgehen.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1. Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem System installiert ist.
2.  Aspose.Page für Java: Laden Sie die Aspose.Page-Bibliothek herunter und installieren Sie sie. Den Download-Link finden Sie hier[Hier](https://releases.aspose.com/page/java/).
3. Integrierte Entwicklungsumgebung (IDE): Wählen Sie eine Java-kompatible IDE wie IntelliJ IDEA oder Eclipse.
## Pakete importieren
Importieren Sie in Ihrem Java-Projekt die erforderlichen Pakete, um die Aspose.Page-Funktionen zu nutzen. Fügen Sie am Anfang Ihrer Java-Datei die folgenden Importanweisungen hinzu:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Schritt 1: Dokumentverzeichnis festlegen
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
```
## Schritt 2: XPS-Dokument laden
```java
// XPS-Dokument laden
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Schritt 3: Optionen initialisieren
```java
// Initialisieren Sie das Optionsobjekt mit den erforderlichen Parametern.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## Schritt 4: Erstellen Sie ein Rendering-Gerät
```java
// Erstellen Sie ein Rendering-Gerät für das PDF-Format
ImageDevice device = new ImageDevice();
```
## Schritt 5: Speichern und iterieren
```java
// Speichern Sie das XPS-Dokument mithilfe von Optionen und Gerät im PNG-Format
document.save(device, options);
//Dokumentpartitionen durchlaufen (feste Dokumente, in XPS-Begriffen)
for (int i = 0; i < device.getResult().length; i++) {
    // Durchlaufen Sie Partitionsseiten
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Bildausgabestream initialisieren
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Bild schreiben
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Schließen Sie den Stream
        imageStream.close();
    }
}
```
Wenn Sie diese Schritte befolgen, können Sie XPS-Dokumente mit Aspose.Page für Java mühelos in PNG-Bilder konvertieren.
## Abschluss
Zusammenfassend lässt sich sagen, dass Aspose.Page für Java den XPS-zu-PNG-Konvertierungsprozess vereinfacht und Entwicklern ein zuverlässiges und effizientes Tool zur Verfügung stellt. Integrieren Sie diese Bibliothek in Ihre Java-Projekte, um Dokumentmanipulationsaufgaben zu optimieren.
## FAQs
### Kann ich Aspose.Page für Java in kommerziellen Projekten verwenden?
 Ja, Aspose.Page ist ein kommerzielles Produkt. Lizenzinformationen finden Sie hier[Hier](https://purchase.aspose.com/buy).
### Gibt es eine kostenlose Testversion?
 Ja, Sie können eine kostenlose Testversion ausprobieren[Hier](https://releases.aspose.com/).
### Wo finde ich die Dokumentation für Aspose.Page für Java?
 Die umfassende Dokumentation liegt vor[Hier](https://reference.aspose.com/page/java/).
### Wie erhalte ich eine temporäre Lizenz zu Testzwecken?
 Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).
### Gibt es Community-Foren für Aspose.Page-Diskussionen?
 Ja, besuchen Sie die Community-Foren[Hier](https://forum.aspose.com/c/page/39).