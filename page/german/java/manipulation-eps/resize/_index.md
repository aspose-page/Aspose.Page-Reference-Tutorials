---
title: Ändern Sie die Größe von EPS-Dateien in Java mit Aspose.Page
linktitle: Ändern Sie die Größe der EPS-Datei in Java
second_title: Aspose.Page Java-API
description: Erfahren Sie, wie Sie mit Aspose.Page für Java mühelos die Größe von EPS-Dateien in Java ändern. Befolgen Sie unsere umfassende Anleitung für Schritt-für-Schritt-Anleitungen.
type: docs
weight: 11
url: /de/java/manipulation-eps/resize/
---
## Einführung
Willkommen zu unserer Schritt-für-Schritt-Anleitung zur Größenänderung von EPS-Dateien in Java mithilfe der leistungsstarken Aspose.Page-Bibliothek. Wenn Sie jemals die Abmessungen Ihrer EPS-Bilder programmgesteuert anpassen mussten, sind Sie hier richtig. In diesem Tutorial erkunden wir verschiedene Größenänderungsoptionen, darunter Punkte, Zoll, Millimeter und Prozentsätze, die Ihnen die Flexibilität bieten, die Sie für Ihre spezifischen Anforderungen benötigen.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- Java Development Kit (JDK) ist auf Ihrem Computer installiert.
-  Aspose.Page für Java-Bibliothek. Sie können es herunterladen[Hier](https://releases.aspose.com/page/java/).
- Ein grundlegendes Verständnis der Java-Programmierung.
## Pakete importieren
Stellen Sie in Ihrem Java-Projekt sicher, dass Sie über die erforderlichen Importe verfügen, um die Funktionen von Aspose.Page zu nutzen. Hier ist ein Beispiel:
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;

```
Lassen Sie uns das Tutorial nun für jede Größenänderungsoption in mehrere Schritte unterteilen:
## Ändern Sie die EPS-Größe mithilfe von Punkten
### Schritt 1: Richten Sie den Eingabestream ein
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
### Schritt 2: PsDocument-Objekt initialisieren
```java
PsDocument doc = new PsDocument(inputEpsStream);
```
### Schritt 3: Extrahieren Sie die aktuelle Größe des EPS-Bildes
```java
Dimension oldSize = doc.extractEpsSize();
```
### Schritt 4: Erstellen Sie einen Ausgabestream
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```
### Schritt 5: Größe ändern und in Punkten speichern
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```
## Ändern Sie die EPS-Größe in Zoll
Befolgen Sie ähnliche Schritte wie in Beispiel 1, ersetzen Sie „Punkte“ durch „Zoll“ und passen Sie die neue Größe entsprechend an.
## Ändern Sie die EPS-Größe mithilfe von Millimetern
Befolgen Sie ähnliche Schritte wie in Beispiel 1, ersetzen Sie „Punkte“ durch „Millimeter“ und passen Sie die neue Größe entsprechend an.
## Ändern Sie die EPS-Größe mithilfe von Prozentsätzen
Befolgen Sie ähnliche Schritte wie in Beispiel 1, ersetzen Sie „Punkte“ durch „Prozentsätze“ und passen Sie die neue Größe entsprechend an.
## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Page die Größe von EPS-Dateien in Java ändern. Dieser Leitfaden bietet Ihnen vielseitige Optionen und stellt sicher, dass Sie den Größenänderungsprozess an Ihre spezifischen Bedürfnisse anpassen können.

## FAQs
### Kann ich diese Bibliothek für andere Bildformate verwenden?
Nein, Aspose.Page ist speziell für die Verarbeitung von PostScript- und EPS-Dateien konzipiert.
### Gibt es eine kostenlose Testversion für Aspose.Page für Java?
Ja, Sie können die kostenlose Testversion erkunden[Hier](https://releases.aspose.com/).
### Wo finde ich zusätzliche Hilfe und Diskussionen?
 Besuche den[Aspose.Page-Forum](https://forum.aspose.com/c/page/39) für die Unterstützung der Gemeinschaft.
### Wie kann ich eine temporäre Lizenz erhalten?
 Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).
### Gibt es Beispielprojekte?
 Ja, überprüfen Sie die Dokumentation[Hier](https://reference.aspose.com/page/java/).