---
title: Rechteck in Java XPS hinzufügen
linktitle: Rechteck in Java XPS hinzufügen
second_title: Aspose.Page Java-API
description: Erfahren Sie, wie Sie mit Aspose.Page Rechtecke in Java XPS hinzufügen. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für eine reibungslose Dokumentenbearbeitung. #JavaXPS #AsposePage
weight: 11
url: /de/java/xps-shapes/add-rectangle/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rechteck in Java XPS hinzufügen

## Einführung
Willkommen zu dieser umfassenden Anleitung zum Hinzufügen von Rechtecken in Java XPS mit Aspose.Page! Egal, ob Sie ein erfahrener Entwickler sind oder gerade erst mit Java XPS beginnen, dieses Tutorial führt Sie mit Schritt-für-Schritt-Anleitungen durch den Prozess und stellt sicher, dass Sie ein tiefes Verständnis des Themas erlangen.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundkenntnisse der Programmiersprache Java.
-  Aspose.Page-Bibliothek installiert. Wenn nicht, können Sie es hier herunterladen[Aspose.Page Java-Dokumentation](https://reference.aspose.com/page/java/).
- Eine funktionierende Java-Entwicklungsumgebung.
## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete in Ihr Java-Projekt. Stellen Sie sicher, dass die Aspose.Page-Bibliothek korrekt zu Ihrem Klassenpfad hinzugefügt wurde. Hier ist ein einfaches Beispiel:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```
Lassen Sie uns nun das bereitgestellte Beispiel in mehrere Schritte aufteilen, um ein Rechteck in Java XPS hinzuzufügen.
## Schritt 1: Legen Sie das Dokumentverzeichnis fest
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
```
Ersetzen Sie „Ihr Dokumentverzeichnis“ durch den Pfad zu Ihrem gewünschten Verzeichnis.
## Schritt 2: Erstellen Sie ein neues XPS-Dokument
```java
// Erstellen Sie ein neues XPS-Dokument
XpsDocument doc = new XpsDocument();
```
Dadurch wird ein neues XPS-Dokument initialisiert.
## Schritt 3: Fügen Sie ein CMYK-Vollfarb-Strichrechteck hinzu
```java
// CMYK (blau) einfarbiges, gestricheltes Rechteck unten links
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
Dieser Schritt fügt ein gestricheltes Rechteck mit einer CMYK-Volltonfarbe hinzu.
## Schritt 4: Speichern Sie das resultierende XPS-Dokument
```java
// Speichern Sie das resultierende XPS-Dokument
doc.save(dataDir + "AddRectangle_out.xps");
```
Speichern Sie abschließend das geänderte XPS-Dokument mit dem hinzugefügten Rechteck.
Wiederholen Sie diese Schritte und passen Sie die Parameter nach Bedarf an, um Ihre Rechtecke weiter anzupassen.
## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Page Rechtecke in Java XPS hinzufügen. Dieses Tutorial bietet eine solide Grundlage für Ihre Bemühungen zur Manipulation von XPS-Dokumenten.
## FAQs
### Kann ich in einem einzelnen XPS-Dokument mehrere Rechtecke hinzufügen?
Ja, Sie können beliebig viele Rechtecke hinzufügen, indem Sie die im Tutorial beschriebenen Schritte wiederholen.
### Wie kann ich die Farbe des Rechtecks ändern?
 Ändern Sie die Farbwerte im`createColor` Methode, um die gewünschte Farbe zu erzielen.
### Ist Aspose.Page für die Handhabung komplexer XPS-Dokumentmanipulationen geeignet?
Absolut! Aspose.Page bietet eine Reihe robuster Funktionen für die Bearbeitung verschiedener XPS-Dokumentaufgaben.
### Wo finde ich weitere Beispiele und Unterstützung?
 Entdecke die[Aspose.Page-Forum](https://forum.aspose.com/c/page/39)Weitere Beispiele finden Sie hier und bitten Sie die Community um Hilfe.
### Kann ich Aspose.Page vor dem Kauf testen?
 Ja, Sie können a erkunden[Kostenlose Testphase](https://releases.aspose.com/) um die Möglichkeiten von Aspose.Page kennenzulernen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
