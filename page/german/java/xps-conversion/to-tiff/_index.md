---
title: Konvertieren Sie XSP in TIFF in Java
linktitle: Konvertieren Sie XSP in TIFF in Java
second_title: Aspose.Page Java-API
description: Konvertieren Sie XPS mühelos in TIFF mit Aspose.Page für Java. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für eine nahtlose Integration. Jetzt downloaden!
weight: 14
url: /de/java/xps-conversion/to-tiff/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konvertieren Sie XSP in TIFF in Java

Im heutigen digitalen Zeitalter spielt die Dokumentenkonvertierung in verschiedenen Anwendungen eine entscheidende Rolle. Wenn Sie als Java-Entwickler eine robuste Lösung zum Konvertieren von XPS-Dokumenten (XML Paper Specification) in TIFF (Tagged Image File Format) suchen, ist Aspose.Page für Java die Bibliothek Ihrer Wahl. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch den Prozess und sorgen mit detaillierten Erklärungen und Codeausschnitten für ein reibungsloses Erlebnis.
## Voraussetzungen
Bevor Sie mit dem Konvertierungsprozess beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Java Development Kit (JDK) ist auf Ihrem Computer installiert.
-  Aspose.Page für Java-Bibliothek. Sie können es herunterladen[Hier](https://releases.aspose.com/page/java/).
-  Eine gültige Lizenz für Aspose.Page für Java. Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/) , oder erwerben Sie eine Volllizenz[Hier](https://purchase.aspose.com/buy).
## Pakete importieren
Beginnen Sie mit dem Importieren der erforderlichen Pakete in Ihr Java-Projekt. Stellen Sie sicher, dass Sie die Aspose.Page for Java-Bibliothek zu Ihrem Projekt hinzugefügt haben.
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Schritt 1: Dokumentenverzeichnis einrichten
Definieren Sie den Pfad zu Ihrem Dokumentverzeichnis, in dem sich die Eingabe-XPS-Datei befindet.
```java
String dataDir = "Your Document Directory";
```
## Schritt 2: XPS-Dokument laden
Laden Sie das XPS-Dokument mit der Aspose.Page-Bibliothek.
```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Schritt 3: TiffSaveOptions initialisieren
Initialisieren Sie das TiffSaveOptions-Objekt mit den erforderlichen Parametern, z. B. Glättungsmodus, Auflösung und bestimmten Seitenzahlen.
```java
TiffSaveOptions options = new TiffSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## Schritt 4: Erstellen Sie ein Rendering-Gerät
Erstellen Sie mithilfe der ImageDevice-Klasse ein Renderinggerät für das TIFF-Format.
```java
ImageDevice device = new ImageDevice();
```
## Schritt 5: Dokument im TIFF speichern
Speichern Sie das XPS-Dokument mit den angegebenen Optionen und dem angegebenen Rendering-Gerät im TIFF-Format.
```java
document.save(device, options);
```
## Schritt 6: TIFF-Bilder iterieren und speichern
Durchlaufen Sie die Dokumentpartitionen und -seiten, initialisieren Sie Bildausgabeströme und speichern Sie die TIFF-Bilder.
```java
for (int i = 0; i < device.getResult().length; i++) {
    for (int j = 0; j < device.getResult()[i].length; j++) {
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoTIFF" + "_" + (i + 1) + "_" + (j + 1) + ".tif");
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```
 Glückwunsch! Sie haben XPS mit Aspose.Page erfolgreich in Java in TIFF konvertiert. Entdecken Sie weitere Features und Funktionalitäten der Bibliothek im[Dokumentation](https://reference.aspose.com/page/java/).
## Abschluss
In diesem Tutorial haben wir die wesentlichen Schritte zum Konvertieren von XPS in TIFF in Java mit Aspose.Page behandelt. Die Konvertierung von Dokumenten steht Ihnen jetzt zur Verfügung und Sie können Ihre Anwendungen mit vielseitiger Dateiformatunterstützung erweitern.
## Häufig gestellte Fragen
### Kann ich Aspose.Page für Java ohne Lizenz verwenden?
 Während Sie für die Evaluierung eine temporäre Lizenz erhalten können, ist für die Produktionsnutzung eine gültige Lizenz erforderlich. Holen Sie sich Ihre Lizenz[Hier](https://purchase.aspose.com/buy).
### Gibt es Beschränkungen hinsichtlich der Größe der zu konvertierenden XPS-Dateien?
Aspose.Page für Java verarbeitet Dokumente unterschiedlicher Größe, es ist jedoch ratsam, es mit größeren Dateien in Ihrer spezifischen Umgebung zu testen.
### Wie kann ich Unterstützung erhalten oder Fragen zu Aspose.Page für Java stellen?
 Besuche den[Aspose.Page-Forum](https://forum.aspose.com/c/page/39) für Community-Unterstützung und Diskussionen.
### Gibt es eine kostenlose Testversion für Aspose.Page für Java?
 Ja, Sie können die Bibliothek mit einer kostenlosen Testversion erkunden. Lade es herunter[Hier](https://releases.aspose.com/).
### Welche Auflösung wird für TIFF-Bilder bei dieser Konvertierung empfohlen?
Das bereitgestellte Beispiel verwendet eine Auflösung von 300 DPI, Sie können diese jedoch an Ihre spezifischen Anforderungen anpassen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
