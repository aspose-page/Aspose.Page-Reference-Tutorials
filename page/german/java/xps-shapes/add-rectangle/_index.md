---
date: 2026-04-24
description: Erfahren Sie, wie Sie die Farbe eines Rechtecks festlegen und ein Rechteck
  in Java XPS mit Aspose.Page hinzufügen. Dieser Leitfaden behandelt das Hinzufügen
  von Rechtecken in Java und das Ändern des Rechteckstrichs.
keywords:
- set rectangle color
- add rectangle java
- change rectangle stroke
linktitle: Rechteck in Java XPS hinzufügen
second_title: Aspose.Page Java API
title: Rechteckfarbe festlegen und Rechteck in Java XPS hinzufügen
url: /de/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rechteckfarbe festlegen und Rechteck in Java XPS hinzufügen

## Einleitung
In diesem Leitfaden lernen Sie, wie Sie **Rechteckfarbe festlegen** und **ein Rechteck hinzufügen** in Java XPS mithilfe der Aspose.Page‑Bibliothek. Egal, ob Sie einfache Formen für einen Bericht zeichnen oder komplexe Vektorgrafiken erstellen möchten – das Beherrschen der Rechteck‑Stilierung gibt Ihnen präzise Kontrolle über Ihre XPS‑Dokumente.  

## Schnelle Antworten
- **Welche Bibliothek wird benötigt?** Aspose.Page for Java  
- **Kann ich die Rechteck‑Kontur ändern?** Ja, mit `setStroke` und `setStrokeThickness`  
- **Wird ein CMYK‑Farbprofil unterstützt?** Absolut – Sie können ICC‑Profile wie gezeigt laden  
- **Benötige ich eine Lizenz für die Produktion?** Ja, für den nicht‑Evaluations‑Einsatz ist eine kommerzielle Lizenz erforderlich  
- **Wie lange dauert die Implementierung?** In der Regel unter 10 Minuten für ein einfaches Rechteck

## Was ist **set rectangle color**?
Das Festlegen der Rechteckfarbe bedeutet, die Füll‑ oder Konturfarbe zu definieren, mit der die Form im finalen XPS‑Dokument gerendert wird. Mit Aspose.Page können Sie RGB, CMYK oder sogar benutzerdefinierte ICC‑Farbprofile verwenden, um eine exakte Farbabstimmung zu erreichen.

## Warum Aspose.Page verwenden, um **add rectangle java** und **change rectangle stroke**?
- **Voll‑ausgestattete API** – unterstützt sowohl Volltonfarben als auch Verläufe.  
- **Plattformübergreifend** – funktioniert auf jeder Java‑Runtime ohne native Abhängigkeiten.  
- **Umfangreiche Geometrie‑Unterstützung** – erstellen Sie komplexe Pfade, wenden Sie Transformationen an und verwalten Sie die Strichstärke mühelos.  

## Voraussetzungen
Bevor wir in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

- Grundkenntnisse in der Java‑Programmierung.  
- Aspose.Page‑Bibliothek installiert. Falls nicht, laden Sie sie von der [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) herunter.  
- Eine funktionierende Java‑Entwicklungsumgebung (IDE, JDK usw.).  

## Pakete importieren
Um zu beginnen, importieren Sie die notwendigen Pakete in Ihr Java‑Projekt. Stellen Sie sicher, dass die Aspose.Page‑Bibliothek korrekt zu Ihrem Klassenpfad hinzugefügt wurde. Hier ein einfaches Beispiel:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Nun zerlegen wir das bereitgestellte Beispiel in mehrere Schritte, um **ein Rechteck hinzuzufügen** und **seine Farbe festzulegen** in Java XPS.

## Schritt 1: Dokumentverzeichnis festlegen
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
Ersetzen Sie `"Your Document Directory"` durch den absoluten Pfad, in dem Sie XPS‑Dateien lesen/schreiben möchten.

## Schritt 2: Neues XPS‑Dokument erstellen
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```
Diese Zeile initialisiert ein frisches XPS‑Dokument, das unsere Formen aufnehmen wird.

## Schritt 3: CMYK‑Solid‑Color‑Umrandetes Rechteck hinzufügen
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
Dieser Schritt fügt ein **umrandetes Rechteck** mit einer CMYK‑Volltonfarbe hinzu. Die Methode `setStroke` definiert die Konturfarbe des Rechtecks, während `setStrokeThickness` die Linienbreite steuert – perfekt, um **die Rechteck‑Kontur zu ändern**.

### Tipp:
Wenn Sie eine RGB‑Farbe bevorzugen, ersetzen Sie den Aufruf `createColor` durch `doc.createColor(0, 0, 255)` für eine durchgehend blaue Füllung.

## Schritt 4: Ergebnis‑XPS‑Dokument speichern
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```
Abschließend wird das XPS‑Dokument auf die Festplatte geschrieben. Die Datei `AddRectangle_out.xps` enthält nun ein Rechteck, dessen Farbe und Kontur Sie definiert haben.

## Häufige Probleme und Lösungen
| Problem | Ursache | Lösung |
|-------|-------|----------|
| **Rechteck nicht sichtbar** | Falsche Pfadgeometrie oder Strichstärke auf 0 gesetzt | Überprüfen Sie die Pfad‑Zeichenkette (`"M 20,10 L 220,10 220,100 20,100 Z"`) und stellen Sie sicher, dass `setStrokeThickness` größer als 0 ist. |
| **Falsche Farbe** | Verwendung eines ICC‑Profils, das nicht zum gewünschten Farbraum passt | Verwenden Sie `doc.createColor(r, g, b)` für RGB oder prüfen Sie den ICC‑Dateipfad erneut. |
| **Datei nicht gespeichert** | `dataDir` verweist auf einen nicht vorhandenen Ordner oder hat keine Schreibrechte | Erstellen Sie den Ordner vorher oder wählen Sie einen beschreibbaren Speicherort. |

## Häufig gestellte Fragen

**Q:** *Kann ich mehrere Rechtecke in einem einzigen XPS‑Dokument hinzufügen?*  
A: Ja. Einfach die Geometrieerstellung und Styling‑Schritte für jedes benötigte Rechteck wiederholen.

**Q:** *Wie kann ich die Füllfarbe des Rechtecks anstelle der Kontur ändern?*  
A: Verwenden Sie `path.setFill(...)` mit einem Vollton‑Farbpinsel, ähnlich wie bei `setStroke`.

**Q:** *Ist Aspose.Page für komplexe XPS‑Dokumentmanipulationen geeignet?*  
A: Absolut. Die Bibliothek unterstützt erweiterte Funktionen wie Verläufe, Transformationen und eingebettete Schriftarten.

**Q:** *Wo finde ich weitere Beispiele und Community‑Unterstützung?*  
A: Durchstöbern Sie das [Aspose.Page forum](https://forum.aspose.com/c/page/39) für weitere Code‑Beispiele und Hilfe von anderen Entwicklern.

**Q:** *Kann ich Aspose.Page vor dem Kauf testen?*  
A: Ja, Sie können eine [free trial](https://releases.aspose.com/) nutzen, um die Fähigkeiten der API zu evaluieren.

---

**Zuletzt aktualisiert:** 2026-04-24  
**Getestet mit:** Aspose.Page for Java 24.12  
**Autor:** Aspose

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}