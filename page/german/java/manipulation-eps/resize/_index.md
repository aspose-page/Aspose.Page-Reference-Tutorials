---
date: 2025-12-02
description: Erfahren Sie, wie Sie EPS‑Dateien in Java mühelos mit Aspose.Page skalieren.
  Diese Schritt‑für‑Schritt‑Anleitung zeigt Ihnen, wie Sie EPS mithilfe von Punkten,
  Zoll, Millimetern oder Prozentwerten skalieren.
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: Wie man EPS-Dateien in Java mit Aspose.Page in der Größe ändert
url: /de/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man EPS-Dateien in Java mit Aspose.Page skaliert

## Einführung
Wenn Sie nach einer zuverlässigen Methode **wie man EPS**-Dateien programmgesteuert skalieren kann, sind Sie hier genau richtig. In diesem Tutorial führen wir Sie durch das Skalieren von EPS‑Bildern in Java mit der Aspose.Page‑Bibliothek. Egal, ob Sie die Größe verdoppeln, sie auf ein bestimmtes Maß verkleinern oder mit Prozentwerten arbeiten möchten, die nachfolgenden Schritte geben Ihnen die volle Kontrolle über die Ausgabedimensionen.

## Schnelle Antworten
- **Welche Bibliothek wird benötigt?** Aspose.Page for Java  
- **Kann ich mit Punkten, Zoll oder Millimetern skalieren?** Ja – die API unterstützt alle drei Einheiten sowie Prozentsätze.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion funktioniert für Tests; für die Produktion ist eine Lizenz erforderlich.  
- **Welche Java-Version wird benötigt?** Java 8 oder höher.  
- **Ist der Code thread‑sicher?** Jede `PsDocument`‑Instanz ist isoliert, sodass Sie Dateien parallel verarbeiten können.

## Voraussetzungen
Bevor wir in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

- Java Development Kit (JDK) auf Ihrem Rechner installiert.  
- Aspose.Page for Java Bibliothek. Sie können sie **[hier](https://releases.aspose.com/page/java/)** herunterladen.  
- Grundlegende Kenntnisse in Java-Programmierung.  

## Pakete importieren
Fügen Sie in Ihrem Java‑Projekt die erforderlichen Importe hinzu, damit Sie mit Aspose.Page‑Objekten und Standard‑I/O‑Streams arbeiten können.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## Wie man EPS mit Punkten skaliert

Unten finden Sie ein vollständiges, Schritt‑für‑Schritt‑Beispiel, das die Größe einer EPS‑Datei mithilfe von Punkten als Maßeinheit verdoppelt.

### Schritt 1: Eingabestream einrichten
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Schritt 2: `PsDocument`‑Objekt initialisieren
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Schritt 3: Aktuelle Größe des EPS‑Bildes ermitteln
```java
Dimension oldSize = doc.extractEpsSize();
```

### Schritt 4: Ausgabestream für die skalierte Datei erstellen
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Schritt 5: EPS mit Punkten skalieren und speichern
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## Wie man EPS mit Zoll skaliert
Das gleiche Fünf‑Schritte‑Muster gilt; ersetzen Sie einfach `Units.Points` durch `Units.Inches` und passen Sie den Skalierungsfaktor nach Bedarf an.

## Wie man EPS mit Millimetern skaliert
Wiederholen Sie die gleichen Schritte und tauschen Sie die Einheit zu `Units.Millimeters`. Das ist praktisch, wenn Sie metrische Abmessungen für Druck‑Workflows benötigen.

## Wie man EPS mit Prozentwerten skaliert
Für prozentbasierte Skalierung behalten Sie die Einheit `Units.Percent` bei. Multiplizieren Sie die ursprüngliche Breite und Höhe mit dem gewünschten Prozentsatz (z. B. `0.5` für eine Reduktion um 50 %).

## Häufige Fallstricke & Tipps
- **Streams immer schließen** – In Produktionscode sollten Sie Streams in try‑with‑resources einbetten, um Dateisperren zu vermeiden.  
- **Seitenverhältnis beibehalten** – Multiplizieren Sie Breite und Höhe mit demselben Faktor, es sei denn, Sie möchten bewusst Verzerrungen erzeugen.  
- **DPI prüfen** – Skalieren ändert die DPI nicht; wenn Sie eine andere DPI benötigen, passen Sie diese nach dem Skalieren separat an.

## Fazit
Sie wissen jetzt, **wie man EPS**‑Dateien in Java mit Aspose.Page skaliert, egal ob Sie Punkte, Zoll, Millimeter oder Prozentsätze bevorzugen. Diese Flexibilität ermöglicht es Ihnen, EPS‑Manipulation in automatisierte Pipelines, Desktop‑Utilities oder serverseitige Dienste zu integrieren.

## Häufig gestellte Fragen

**F: Kann ich diese Bibliothek für andere Bildformate verwenden?**  
A: Nein, Aspose.Page ist ausschließlich für PostScript‑ und EPS‑Dateien spezialisiert.

**F: Gibt es eine kostenlose Testversion für Aspose.Page für Java?**  
A: Ja, Sie können die kostenlose Testversion **[hier](https://releases.aspose.com/)** erkunden.

**F: Wo finde ich zusätzliche Hilfe und Diskussionen?**  
A: Besuchen Sie das **[Aspose.Page‑Forum](https://forum.aspose.com/c/page/39)** für Community‑Support.

**F: Wie kann ich eine temporäre Lizenz erhalten?**  
A: Sie können eine temporäre Lizenz **[hier](https://purchase.aspose.com/temporary-license/)** erhalten.

**F: Gibt es Beispielprojekte?**  
A: Ja, schauen Sie in die Dokumentation **[hier](https://reference.aspose.com/page/java/)**.

---

**Zuletzt aktualisiert:** 2025-12-02  
**Getestet mit:** Aspose.Page for Java 24.12 (zum Zeitpunkt des Schreibens die neueste Version)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}