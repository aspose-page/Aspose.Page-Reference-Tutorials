---
date: 2026-04-30
description: Erfahren Sie, wie Sie ein XPS‑Dokument in Java erstellen und eine Opazitätsmaske
  mit Aspose.Page Java hinzufügen. Schritt‑für‑Schritt‑Anleitung mit Codebeispielen.
keywords:
- create xps document java
- opacity mask java
- aspose.page java
linktitle: Opacity‑Maske in Java XPS setzen
second_title: Aspose.Page Java API
title: XPS-Dokument in Java erstellen – Opazitätsmaske mit Aspose.Page festlegen
url: /de/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Deckkraftmaske in Java XPS mit Aspose.Page Java

## Einführung
In diesem Tutorial erstellen Sie **XPS-Dokumente in Java** und lernen, wie Sie eine Deckkraftmaske anwenden, die Ihren Grafiken ein poliertes, halbtransparentes Aussehen verleiht. Wir gehen den gesamten Prozess durch – vom Initialisieren eines XPS-Dokuments, Hinzufügen einer Leinwand, Zeichnen eines Rechtecks bis zum Anbringen einer bildbasierten Deckkraftmaske – mithilfe der intuitiven Aspose.Page Java API. Am Ende können Sie professionelle XPS-Dateien programmgesteuert erzeugen und die Maske für jede gewünschte Form wiederverwenden.

## Schnelle Antworten
- **Was macht eine Deckkraftmaske?** Sie definiert unterschiedliche Transparenzstufen für eine Form, sodass darunterliegender Inhalt sichtbar wird.  
- **Welche Bibliothek wird benötigt?** Aspose.Page für Java (aspose page java).  
- **Benötige ich eine Lizenz?** Eine temporäre Lizenz funktioniert für Tests; für die Produktion ist eine Voll‑Lizenz erforderlich.  
- **Wie viele Codezeilen?** Etwa 20 Java‑Zeilen plus ein paar Setup‑Anweisungen.  
- **Kann ich die Maske für mehrere Formen wiederverwenden?** Ja, Sie können denselben `ImageBrush` mehreren Pfaden zuweisen.

## Was ist eine Deckkraftmaske in XPS?
Eine Deckkraftmaske ist ein Bitmap oder Vektor, der den Alpha‑Wert (Transparenz) jedes Pixels einer Form steuert. Wird sie auf ein Rechteck angewendet, werden Teile des Rechtecks vollständig undurchsichtig, teilweise transparent oder vollständig transparent, wodurch anspruchsvolle visuelle Effekte ohne zusätzliche Zeichenebenen entstehen.

## Warum Aspose.Page Java zum **Erstellen von XPS-Dokumenten in Java** verwenden?
- **Pure Java API** – Keine nativen Abhängigkeiten, sodass derselbe Code unter Windows, Linux oder macOS läuft.  
- **Vollständige XPS‑Spezifikationskonformität** – Masken werden exakt gemäß dem XPS‑Standard gerendert.  
- **Objektorientiertes Design** – Ähnlich zu .NET, sodass es leicht zu erlernen ist, wenn Sie Aspose bereits in anderen Sprachen verwendet haben.  
- **Hohe Leistung** – Optimiert für große Dokumente und Batch‑Verarbeitung.

## Häufige Anwendungsfälle
- **Wasserzeichen** – Ein halbtransparentes Logo über alle Seiten legen.  
- **Dynamisches Theming** – Den visuellen Stil von UI‑Elementen in generierten Berichten ändern.  
- **Druckfertige Vorschauen** – Zeigen, wie ein Design mit unterschiedlicher Deckkraft aussieht, bevor es an den Drucker gesendet wird.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:
- Grundlegende Kenntnisse in Java-Programmierung.  
- Aspose.Page für Java Bibliothek installiert. Sie können sie **[hier](https://releases.aspose.com/page/java/)** herunterladen.  
- Eine gültige Lizenz für Aspose.Page. Wenn Sie keine haben, erhalten Sie eine temporäre Lizenz **[hier](https://purchase.aspose.com/temporary-license/)**.  
- Eine Entwicklungsumgebung, die Java‑Anwendungen kompilieren und ausführen kann (z. B. IntelliJ IDEA, Eclipse oder VS Code).

## Pakete importieren
Beginnen Sie damit, die erforderlichen Klassen aus der Aspose.Page‑Bibliothek zu importieren. Dadurch steht die API Ihrem Projekt zur Verfügung.

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Neues XPS‑Dokument erstellen
Zuerst erstellen Sie ein neues XPS‑Dokument, das all unsere Grafiken enthält.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### Schritt 2: Leinwand hinzufügen
Eine Leinwand dient als Zeichenfläche innerhalb der XPS‑Seite.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### Schritt 3: Rechteck hinzufügen und solide Füllung anwenden
Hier erstellen wir einen Rechteck‑Pfad und geben ihm eine solide rote Füllung. Dieses Rechteck erhält später die Deckkraftmaske.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### Schritt 4: Deckkraftmaske mit einem ImageBrush hinzufügen
Wir laden ein TIFF‑Bild, definieren Quell‑ und Ziel‑Rechtecke und setzen den Brush auf Kachelmodus, damit die Maske bei Bedarf wiederholt wird.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### Schritt 5: Ergebnis‑XPS‑Dokument speichern
Abschließend speichern wir das Dokument auf dem Datenträger. Die Ausgabedatei enthält das Rechteck mit der angewendeten Deckkraftmaske.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

Befolgen Sie diese Schritte sorgfältig, um die **add opacity mask**‑Funktionalität in Ihr Java‑XPS‑Dokument mit Aspose.Page zu integrieren.

## Häufige Probleme & Fehlersuche
- **Bild nicht gefunden** – Stellen Sie sicher, dass `dataDir` auf den richtigen Ordner zeigt und dass `R08SY_NN.tif` existiert.  
- **Maske erscheint solide** – Vergewissern Sie sich, dass das Quellbild tatsächlich unterschiedliche Alpha‑Werte enthält; ein vollständig undurchsichtiges Bild zeigt keine Transparenz.  
- **Kachelmodus wird nicht beachtet** – Das Ziel‑Rechteck muss kleiner sein als das Quell‑Rechteck, damit das Kacheln erkennbar ist.

## Häufig gestellte Fragen

**F: Ist Aspose.Page mit allen Java‑Entwicklungsumgebungen kompatibel?**  
A: Ja, Aspose.Page ist so konzipiert, dass es nahtlos mit verschiedenen Java‑IDEs und Build‑Tools funktioniert.

**F: Kann ich Aspose.Page ohne Lizenz verwenden?**  
A: Sie können die Bibliothek zwar mit einer temporären Lizenz testen, für den Produktionseinsatz ist jedoch eine Voll‑Lizenz erforderlich.

**F: Gibt es Einschränkungen in der Testversion?**  
A: Die Testversion kann Größen‑ oder Funktionsbeschränkungen haben; konsultieren Sie die offizielle Dokumentation für Details.

**F: Wie kann ich Support für Aspose.Page erhalten?**  
A: Besuchen Sie das **[Aspose.Page‑Forum](https://forum.aspose.com/c/page/39)** für Community‑Hilfe oder erwerben Sie eine Lizenz für Premium‑Unterstützung.

**F: Gibt es eine Geld‑zurück‑Garantie für Aspose.Page?**  
A: Siehe die **[Kaufseite](https://purchase.aspose.com/buy)** für Informationen zu Rückerstattungsrichtlinien.

---

**Zuletzt aktualisiert:** 2026-04-30  
**Getestet mit:** Aspose.Page Java 24.11 (zum Zeitpunkt des Schreibens aktuell)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}