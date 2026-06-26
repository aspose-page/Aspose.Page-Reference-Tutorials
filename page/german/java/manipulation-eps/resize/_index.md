---
date: 2026-02-07
description: Lernen Sie, wie Sie EPS‑Dateien in Java skalieren und EPS‑Abmessungen
  mit Aspose.Page ändern. Diese Schritt‑für‑Schritt‑Anleitung zeigt Ihnen, wie Sie
  EPS mit Punkten, Zoll, Millimetern oder Prozentwerten skalieren.
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
Wenn Sie nach einer zuverlässigen Methode **wie man EPS skaliert** suchen, sind Sie hier genau richtig. In diesem Tutorial zeigen wir, wie EPS‑Bilder in Java mit der Aspose.Page‑Bibliothek skaliert werden können. Egal, ob Sie die Größe verdoppeln, sie auf ein bestimmtes Maß verkleinern oder prozentual arbeiten möchten – die nachfolgenden Schritte geben Ihnen die volle Kontrolle über die Ausgabedimensionen. Das Verständnis von **wie man EPS skaliert** ist entscheidend, wenn Sie Grafiken für unterschiedliche Drucklayouts oder Bildschirmauflösungen anpassen müssen.

## Schnelle Antworten
- **Welche Bibliothek wird benötigt?** Aspose.Page für Java  
- **Kann ich mit Punkten, Zoll oder Millimetern skalieren?** Ja – die API unterstützt alle drei Einheiten sowie Prozente.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion reicht für Tests; für die Produktion ist eine Lizenz erforderlich.  
- **Welche Java‑Version wird benötigt?** Java 8 oder höher.  
- **Ist der Code thread‑sicher?** Jede `PsDocument`‑Instanz ist isoliert, sodass Sie Dateien parallel verarbeiten können.  

## Was ist EPS und warum es skalieren?
Encapsulated PostScript (EPS) ist ein verbreitetes Vektor‑Grafikformat, das in Verlag und Druck verwendet wird. Manchmal wird die ursprüngliche EPS‑Datei in einer Größe erstellt, die nicht zu Ihrem Zielausgabemedium passt – zum Beispiel ein Logo, das mit 72 pts entworfen wurde, muss für einen größeren Katalog 144 pts groß sein. Das Wissen **wie man EPS skaliert** ermöglicht es Ihnen, die Vektorqualität beizubehalten und die Abmessungen an jeden Workflow anzupassen.

## Warum Aspose.Page zum Skalieren von EPS verwenden?
- **Vollständige Kontrolle über Einheiten** – Punkte, Zoll, Millimeter oder Prozente.  
- **Keine externen Abhängigkeiten** – reine Java‑API, keine nativen Bibliotheken.  
- **Hohe Leistung** – geeignet für Batch‑Verarbeitung auf Servern.  
- **Erhält Vektor‑Treue** – die Ausgabe bleibt skalierbar, ohne Rasterisierung.

## Voraussetzungen
Bevor wir in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

- Java Development Kit (JDK) auf Ihrem Rechner installiert.  
- Aspose.Page für Java Bibliothek. Sie können sie **[hier](https://releases.aspose.com/page/java/)** herunterladen.  
- Grundlegende Kenntnisse in Java‑Programmierung.  

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

## Wie man EPS‑Dimensionen mit verschiedenen Einheiten ändert
Die Bibliothek ermöglicht es Ihnen, **eps‑Dimensionen zu ändern**, indem Sie einfach das passende `Units`‑Enum auswählen. Im Folgenden gehen wir das gleiche Fünf‑Schritte‑Muster für Punkte, Zoll, Millimeter und Prozente durch. Das Einzige, was sich ändert, ist die Einheit, die Sie an `resizeEps` übergeben.

## EPS mit Punkten skalieren
Im Folgenden finden Sie ein vollständiges, Schritt‑für‑Schritt‑Beispiel, das die Größe einer EPS‑Datei verdoppelt, wobei Punkte als Maßeinheit verwendet werden.

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

## EPS mit Zoll skalieren
Das gleiche Fünf‑Schritte‑Muster gilt; ersetzen Sie einfach `Units.Points` durch `Units.Inches` und passen Sie den Skalierungsfaktor auf den gewünschten Zollwert an.

## EPS mit Millimetern skalieren
Wiederholen Sie die Schritte und tauschen Sie die Einheit zu `Units.Millimeters`. Das ist praktisch, wenn Sie metrische Abmessungen für Druck‑Workflows benötigen.

## EPS mit Prozentsätzen skalieren
Für prozentbasierte Skalierung behalten Sie die Einheit `Units.Percent` bei. Multiplizieren Sie die ursprüngliche Breite und Höhe mit dem gewünschten Prozentsatz (z. B. `0.5` für eine Reduktion um 50 %).

## Häufige Stolperfallen & Tipps
- **Streams immer schließen** – In Produktionscode Streams mit try‑with‑resources umschließen, um Dateisperren zu vermeiden.  
- **Seitenverhältnis beibehalten** – Breite und Höhe mit demselben Faktor multiplizieren, es sei denn, Sie wollen bewusst Verzerrungen erzeugen.  
- **DPI prüfen** – Skalieren ändert die DPI nicht; benötigen Sie eine andere DPI, passen Sie diese nach dem Skalieren separat an.  
- **Thread‑Sicherheit** – Pro Thread ein neues `PsDocument` erzeugen; das Teilen derselben Instanz kann zu unerwarteten Ergebnissen führen.  

## Häufig gestellte Fragen

**F: Kann ich diese Bibliothek für andere Bildformate verwenden?**  
A: Nein, Aspose.Page ist ausschließlich für PostScript‑ und EPS‑Dateien spezialisiert.

**F: Gibt es eine kostenlose Testversion von Aspose.Page für Java?**  
A: Ja, Sie können die kostenlose Testversion **[hier](https://releases.aspose.com/)** ausprobieren.

**F: Wo finde ich zusätzliche Hilfe und Diskussionen?**  
A: Besuchen Sie das **[Aspose.Page‑Forum](https://forum.aspose.com/c/page/39)** für Community‑Support.

**F: Wie kann ich eine temporäre Lizenz erhalten?**  
A: Sie können eine temporäre Lizenz **[hier](https://purchase.aspose.com/temporary-license/)** erhalten.

**F: Gibt es Beispielprojekte?**  
A: Ja, die Dokumentation finden Sie **[hier](https://reference.aspose.com/page/java/)**.

---

**Zuletzt aktualisiert:** 2026-02-07  
**Getestet mit:** Aspose.Page für Java 24.12 (zum Zeitpunkt der Erstellung die neueste)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}