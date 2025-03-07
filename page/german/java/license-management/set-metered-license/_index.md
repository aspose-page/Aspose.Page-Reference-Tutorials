---
title: Mühelose Integration gemessener Lizenzen mit Aspose.Page Java
linktitle: Legen Sie eine gemessene Lizenz in Java fest
second_title: Aspose.Page Java-API
description: Entdecken Sie die nahtlose Integration von Aspose.Page mit Java. Richten Sie mühelos bemessene Lizenzen ein und verbessern Sie Ihre Möglichkeiten zur Dokumentenverarbeitung.
weight: 10
url: /de/java/license-management/set-metered-license/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mühelose Integration gemessener Lizenzen mit Aspose.Page Java

## Einführung
Willkommen zu unserem umfassenden Leitfaden zum Einrichten einer gemessenen Lizenz in Java mit Aspose.Page. Wenn Sie Ihre Möglichkeiten zur Dokumentenverarbeitung verbessern und eine nahtlose Integration mit Aspose.Page sicherstellen möchten, sind Sie hier richtig. In diesem Tutorial führen wir Sie durch den Prozess und unterteilen jeden Schritt in leicht verdauliche Abschnitte.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundkenntnisse der Java-Programmierung.
-  Aspose.Page-Bibliothek installiert. Sie können es herunterladen unter[Hier](https://releases.aspose.com/page/java/).
- Gemessene öffentliche und private Schlüssel, die Sie über Ihr Aspose-Konto erhalten können.
## Pakete importieren
Beginnen wir mit dem Import der notwendigen Pakete für unser Java-Programm. Stellen Sie sicher, dass die Aspose.Page-Bibliothek in Ihr Projekt integriert ist.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;

```
## Schritt 1: Dokument- und Bildformat initialisieren
Der erste Schritt besteht darin, das Dokument einzurichten und das gewünschte Bildformat zu definieren.
```java
// Legen Sie gemessene öffentliche und private Schlüssel fest
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Greifen Sie auf die Eigenschaft setMeteredKey zu und übergeben Sie öffentliche und private Schlüssel als Parameter
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```
## Schritt 2: PostScript-Eingabestream initialisieren
In diesem Schritt initialisieren wir den PostScript-Eingabestream für die Verarbeitung.
```java
// Initialisieren Sie den PostScript-Eingabestream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```
## Schritt 3: Überprüfen Sie die Dokumentlizenz
Bevor Sie fortfahren, müssen Sie unbedingt überprüfen, ob das Dokument ordnungsgemäß lizenziert ist.
```java
// Überprüfen Sie, ob das Dokument lizenziert ist
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```
## Schritt 4: Optionen und Bildgerät initialisieren
Lassen Sie uns nun die Optionen und das Bildgerät mit Standardparametern initialisieren.
```java
// Optionsobjekt mit Standardparametern initialisieren.
ImageSaveOptions options = new ImageSaveOptions();
// Initialisieren Sie das ImageDevice-Objekt mit Standardparametern.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```
## Schritt 5: EPS-Datei als Bild speichern
Speichern Sie die EPS-Datei als Bild mit den definierten Optionen und dem definierten Gerät.
```java
// EPS-Datei als Bild speichern
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```
## Schritt 6: Bildbytes abrufen und speichern
Bildbytes abrufen und in einer Datei speichern.
```java
// Holen Sie sich Bildbytes. Ein Byte-Array für eine Seite. In unserem Fall haben wir eine Seite.
byte[][] imagesBytes = device.getImagesBytes();
// Bildbytes in Datei speichern
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```
## Abschluss
Glückwunsch! Sie haben mit Aspose.Page erfolgreich eine getaktete Lizenz in Java eingerichtet. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung, um einen reibungslosen Integrationsprozess zu gewährleisten.
## FAQs
### F: Wie erhalte ich gemessene öffentliche und private Schlüssel?
Sie können diese Schlüssel über Ihr Aspose-Konto erhalten.
### F: Ist die Aspose.Page-Bibliothek kostenlos?
 Aspose.Page bietet sowohl kostenlose Testversionen als auch kostenpflichtige Versionen an. Besuchen[Hier](https://releases.aspose.com/) für eine kostenlose Testversion.
### F: Kann ich Aspose.Page für kommerzielle Projekte verwenden?
 Ja, Aspose.Page bietet kommerzielle Lizenzen an. Sie können sie kaufen[Hier](https://purchase.aspose.com/buy).
### F: Wo finde ich zusätzliche Dokumentation?
 Weitere Informationen finden Sie in der Dokumentation[Hier](https://reference.aspose.com/page/java/).
### F: Wie kann ich temporäre Lizenzen erhalten?
 Es können befristete Lizenzen erworben werden[Hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
