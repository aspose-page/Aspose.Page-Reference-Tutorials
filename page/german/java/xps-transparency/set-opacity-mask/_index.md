---
date: 2026-01-02
description: Erfahren Sie, wie Sie XPS‑Dokumenten mit Aspose.Page Java eine Opazitätsmaske
  hinzufügen. Schritt‑für‑Schritt‑Anleitung zum Erstellen eines Opazitätsmasken‑Rechtecks
  und zur Verbesserung der visuellen Qualität.
linktitle: Set Opacity Mask in Java XPS
second_title: Aspose.Page Java API
title: Opacity‑Maske in Java XPS mit Aspose.Page Java festlegen
url: /de/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Opacity-Maske in Java XPS mit Aspose.Page Java festlegen

## Einleitung
Willkommen zu unserem umfassenden Leitfaden zu **aspose page java** Opacity-Masken. In diesem Tutorial lernen Sie, wie man ein XPS-Dokument erstellt, eine Leinwand hinzufügt und eine Opacity-Maske auf ein Rechteck anwendet – alles mit der leistungsstarken Aspose.Page Java API. Am Ende können Sie Opacity-Masken‑Rechtecke hinzufügen, die Ihren XPS-Dateien ein poliertes, halbtransparentes Aussehen verleihen.

## Schnelle Antworten
- **Was macht eine Opacity-Maske?** Sie definiert unterschiedliche Transparenzstufen für eine Form, sodass darunterliegender Inhalt durchscheint.
- **Welche Bibliothek wird benötigt?** Aspose.Page für Java (aspose page java).
- **Benötige ich eine Lizenz?** Eine temporäre Lizenz funktioniert für Tests; für die Produktion ist eine Voll‑Lizenz erforderlich.
- **Wie viele Codezeilen?** Etwa 20 Zeilen Java plus einige Setup‑Anweisungen.
- **Kann ich die Maske für mehrere Formen wiederverwenden?** Ja, Sie können denselben ImageBrush mehreren Pfaden zuweisen.

## Was ist eine Opacity-Maske in XPS?
Eine Opacity-Maske ist ein Bitmap oder Vektor, der den Alpha‑Wert (Transparenz) jedes Pixels in einer Form steuert. Wird sie auf ein Rechteck angewendet, werden Teile des Rechtecks vollständig undurchsichtig, teilweise transparent oder vollständig transparent, wodurch anspruchsvolle visuelle Effekte entstehen.

## Warum Aspose.Page Java für Opacity-Masken verwenden?
- **Vollständige .NET‑ähnliche API in Java** – intuitives Objektmodell.
- **Keine externen Abhängigkeiten** – funktioniert mit reinem Java.
- **Hochpräzises Rendering** – Masken werden exakt gemäß der XPS‑Spezifikation gerendert.
- **Plattformübergreifend** – läuft auf Windows, Linux oder macOS ohne Änderungen.

## Voraussetzungen
- Grundlegendes Verständnis der Java‑Programmierung.  
- Aspose.Page für Java Bibliothek installiert. Sie können sie **[hier](https://releases.aspose.com/page/java/)** herunterladen.  
- Eine gültige Lizenz für Aspose.Page. Wenn Sie keine haben, erhalten Sie eine temporäre Lizenz **[hier](https://purchase.aspose.com/temporary-license/)**.  
- Eine Entwicklungsumgebung, die Java‑Anwendungen kompilieren und ausführen kann (z. B. IntelliJ IDEA, Eclipse oder VS Code).

## Pakete importieren
Beginnen Sie damit, die erforderlichen Klassen aus der Aspose.Page‑Bibliothek zu importieren. Dadurch ist die API in Ihrem Projekt verfügbar.

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Erstellen Sie ein neues XPS-Dokument
Zuerst instanziieren Sie ein frisches XPS-Dokument, das all unsere Grafiken enthält.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### Schritt 2: Fügen Sie eine Leinwand hinzu
Eine Leinwand dient als Zeichenfläche innerhalb der XPS‑Seite.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### Schritt 3: Fügen Sie ein Rechteck hinzu und wenden Sie eine einfarbige Füllung an
Hier erstellen wir einen Rechteck‑Pfad und geben ihm eine einfarbige rote Füllung. Dieses Rechteck erhält später die Opacity-Maske.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### Schritt 4: Opacity-Maske mit einem ImageBrush hinzufügen
Wir laden ein TIFF‑Bild, definieren Quell‑ und Ziel‑Rechtecke und setzen den Brush auf Tile‑Modus, sodass die Maske bei Bedarf wiederholt wird.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### Schritt 5: Speichern Sie das resultierende XPS-Dokument
Abschließend speichern Sie das Dokument auf dem Datenträger. Die Ausgabedatei enthält das Rechteck mit der angewendeten Opacity-Maske.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

Befolgen Sie diese Schritte sorgfältig, um die **add opacity mask**‑Funktionalität in Ihr Java XPS‑Dokument mit Aspose.Page zu integrieren.

## Häufige Probleme & Fehlersuche
- **Bild nicht gefunden** – Überprüfen Sie, ob `dataDir` auf den richtigen Ordner zeigt und ob `R08SY_NN.tif` existiert.
- **Maske erscheint solide** – Stellen Sie sicher, dass das Quellbild tatsächlich unterschiedliche Alpha‑Werte enthält; ein vollständig undurchsichtiges Bild zeigt keine Transparenz.
- **Tile‑Modus wird nicht beachtet** – Das Ziel‑Rechteck muss kleiner sein als das Quell‑Rechteck, damit das Kacheln sichtbar wird.

## Häufig gestellte Fragen

**Q: Ist Aspose.Page mit allen Java‑Entwicklungsumgebungen kompatibel?**  
A: Ja, Aspose.Page ist so konzipiert, dass es nahtlos mit verschiedenen Java‑IDEs und Build‑Tools funktioniert.

**Q: Kann ich Aspose.Page ohne Lizenz verwenden?**  
A: Obwohl Sie die Bibliothek mit einer temporären Lizenz evaluieren können, ist für den Produktionseinsatz eine Voll‑Lizenz erforderlich.

**Q: Gibt es Einschränkungen in der Testversion?**  
A: Die Testversion kann Größen‑ oder Funktionsbeschränkungen haben; konsultieren Sie die offizielle Dokumentation für Details.

**Q: Wie kann ich Support für Aspose.Page erhalten?**  
A: Besuchen Sie das **[Aspose.Page‑Forum](https://forum.aspose.com/c/page/39)** für Community‑Hilfe oder erwerben Sie eine Lizenz für Premium‑Unterstützung.

**Q: Gibt es eine Geld‑zurück‑Garantie für Aspose.Page?**  
A: Siehe die **[Kaufseite](https://purchase.aspose.com/buy)** für Informationen zu Rückerstattungsrichtlinien.

---

**Zuletzt aktualisiert:** 2026-01-02  
**Getestet mit:** Aspose.Page Java 24.11 (latest at time of writing)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}