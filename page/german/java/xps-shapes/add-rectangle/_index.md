---
date: 2025-12-30
description: Erfahren Sie, wie Sie ein XPS‑Dokument in Java erstellen, indem Sie Rechtecke
  mit Aspose.Page hinzufügen. Folgen Sie dieser Schritt‑für‑Schritt‑Anleitung für
  eine nahtlose XPS‑Dokumentenbearbeitung.
linktitle: Create XPS Document Java – Add Rectangle
second_title: Aspose.Page Java API
title: XPS-Dokument in Java erstellen – Rechteck mit Aspose.Page hinzufügen
url: /de/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS-Dokument in Java erstellen – Rechteck hinzufügen

## Einführung
In diesem umfassenden Tutorial erstellen Sie **XPS-Dokumente in Java** und lernen, wie Sie Rechtecke mit der Aspose.Page‑Bibliothek hinzufügen. Egal, ob Sie Berichte, Rechnungen oder benutzerdefinierte Grafiken erstellen – das Beherrschen der Rechteckerstellung gibt Ihnen präzise Kontrolle über das XPS‑Layout. Wir gehen Schritt für Schritt durch, erklären das „Warum“ hinter jeder Codezeile und zeigen, wie Sie Farben und Striche für professionelle Ergebnisse anpassen können.

## Schnellantworten
- **Welche Bibliothek wird empfohlen?** Aspose.Page für Java  
- **Wie lange dauert die Implementierung?** Ca. 10 Minuten für ein einfaches Rechteck  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich  
- **Welche Java‑Version wird unterstützt?** Java 8 und höher  
- **Kann ich mehrere Formen hinzufügen?** Ja – wiederholen Sie die Schritte für jede Form

## Voraussetzungen
Bevor wir starten, stellen Sie sicher, dass Sie Folgendes haben:

- Grundkenntnisse der Programmiersprache Java.  
- Die Aspose.Page‑Bibliothek installiert. Falls nicht, können Sie sie aus der [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) herunterladen.  
- Eine funktionierende Java‑Entwicklungsumgebung (IDE, JDK und Maven/Gradle, falls gewünscht).

## Pakete importieren
Um loszulegen, importieren Sie die notwendigen Pakete in Ihr Java‑Projekt. Stellen Sie sicher, dass die Aspose.Page‑Bibliothek korrekt im Klassenpfad eingebunden ist. Hier ein einfaches Beispiel:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Nun zerlegen wir das bereitgestellte Beispiel in mehrere Schritte, um ein Rechteck in Java XPS hinzuzufügen.

## Schritt 1: Dokumentverzeichnis festlegen
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

Ersetzen Sie `"Your Document Directory"` durch den Pfad zu dem Ordner, in dem Sie die XPS‑Dateien speichern möchten.

## Schritt 2: Neues XPS‑Dokument erstellen
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Diese Zeile **erstellt** ein frisches XPS‑Dokument, das Sie später mit Formen, Text oder Bildern füllen können.

## Schritt 3: CMYK‑Solid‑Color‑Stroked‑Rectangle hinzufügen
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```

Dieser Schritt fügt ein umrandetes Rechteck mit einer CMYK‑Farbe hinzu. Sie können den Geometriestring (`"M 20,10 L 220,10 220,100 20,100 Z"`) ändern, um Größe oder Position anzupassen, und die Farbwerte in `createColor` nach Ihren Designvorstellungen anpassen.

## Schritt 4: Ergebnis‑XPS‑Dokument speichern
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```

Abschließend speichern Sie das modifizierte XPS‑Dokument mit dem hinzugefügten Rechteck im zuvor angegebenen Verzeichnis.

## Häufige Anwendungsfälle
- **Berichtskopfzeilen** – Rechtecke als Hintergrundblöcke für Titel verwenden.  
- **Rechnungstabellen** – Zellen oder Abschnitte mit farbigen Rahmen hervorheben.  
- **Benutzerdefinierte Grafiken** – Mehrere Rechtecke kombinieren, um komplexe Formen zu erzeugen.

## Fehlersuche
- **Datei nicht gefunden:** Stellen Sie sicher, dass `dataDir` auf einen existierenden Ordner zeigt und das ICC‑Profil (`uswebuncoated.icc`) vorhanden ist.  
- **Falsche Farben:** Vergewissern Sie sich, dass das ICC‑Profil zum gewünschten Farbraum passt (CMYK vs. RGB).  
- **Unerwartete Abmessungen:** Passen Sie den Geometriestring an, um die korrekten Koordinaten zu erhalten.

## Fazit
Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, **XPS‑Dokumente in Java** zu erstellen und Rechtecke mit Aspose.Page hinzuzufügen. Dieses Fundament ermöglicht Ihnen, reichhaltigere XPS‑Dokumente zu bauen, Grafiken anzupassen und Formen in umfangreichere Workflows zu integrieren.

## FAQ
### Kann ich mehrere Rechtecke in einem einzigen XPS‑Dokument hinzufügen?
Ja, Sie können beliebig viele Rechtecke hinzufügen, indem Sie die im Tutorial beschriebenen Schritte wiederholen.

### Wie kann ich die Farbe des Rechtecks ändern?
Passen Sie die Farbwerte in der `createColor`‑Methode an, um die gewünschte Farbe zu erhalten.

### Ist Aspose.Page für die Verarbeitung komplexer XPS‑Dokumentmanipulationen geeignet?
Absolut! Aspose.Page bietet einen robusten Funktionsumfang für verschiedenste XPS‑Dokumentaufgaben.

### Wo finde ich weitere Beispiele und Support?
Besuchen Sie das [Aspose.Page forum](https://forum.aspose.com/c/page/39) für mehr Beispiele und holen Sie sich Unterstützung von der Community.

### Kann ich Aspose.Page vor dem Kauf testen?
Ja, Sie können eine [free trial](https://releases.aspose.com/) nutzen, um die Möglichkeiten von Aspose.Page kennenzulernen.

## Häufig gestellte Fragen

**F: Funktioniert dieser Ansatz mit Java 11 oder neuer?**  
A: Ja, die Aspose.Page‑Bibliothek ist kompatibel mit Java 8 und später, einschließlich Java 11, 17 und darüber hinaus.

**F: Kann ich Bilder innerhalb des Rechteckbereichs einbetten?**  
A: Sie können ein `XpsImage`‑Element hinzufügen und es über oder innerhalb des Rechtecks mit denselben Geometrie‑Koordinaten positionieren.

**F: Wie setze ich eine Füllfarbe statt nur einer Kontur?**  
A: Rufen Sie `path.setFill(...)` mit einem soliden Farb‑Brush auf, der über `doc.createSolidColorBrush(...)` erstellt wird.

**F: Ist es möglich, das Rechteck zu drehen?**  
A: Wenden Sie eine Transformationsmatrix auf den Pfad mit `path.setTransform(...)` an, um Drehungen oder Skalierungen zu erzielen.

**F: Welche Lizenz ist für den Produktionseinsatz erforderlich?**  
A: Für den Einsatz in der Produktion ist eine kommerzielle Aspose.Page‑Lizenz nötig; die kostenlose Testversion ist nur für Evaluierung und Entwicklung gedacht.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2025-12-30  
**Getestet mit:** Aspose.Page für Java 24.12 (neueste)  
**Autor:** Aspose  

---