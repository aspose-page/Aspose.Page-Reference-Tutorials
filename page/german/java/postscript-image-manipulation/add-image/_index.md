---
date: 2025-12-09
description: Erfahren Sie, wie Sie ein PostScript‑Dokument in Java erstellen und ein
  Bild mit Aspose.Page verschieben und drehen, um eine na nahtlose Bildbearbeitung
  zu ermöglichen.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: PostScript-Dokument in Java erstellen – Bild in Java-PostScript hinzufügen
url: /de/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen eines PostScript-Dokuments in Java – Bild hinzufügen in Java PostScript

## Einführung
In diesem Tutorial lernen Sie, wie Sie ein **PostScript-Dokument in Java** erstellen und Bilder mit der Aspose.Page für Java‑Bibliothek einbetten. Wir führen Sie Schritt für Schritt durch den gesamten Prozess, von der Einrichtung des Dokuments bis hin zu Transformationen wie **Übersetzen und Drehen von Bildern**. Am Ende können Sie programmgesteuert reichhaltige PostScript‑Dateien erzeugen und die Bildplatzierung exakt an Ihre Layout‑Anforderungen anpassen.

## Schnelle Antworten
- **Welche Bibliothek wird benötigt?** Aspose.Page für Java  
- **Kann ich mehrere Bilder hinzufügen?** Ja – wiederholen Sie einfach die Transformations‑ und Zeichen‑Schritte  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion reicht für Tests; für die Produktion ist eine Lizenz erforderlich  
- **Welche Java‑Version wird unterstützt?** Java 8 und höher  
- **Wird Bildrotation unterstützt?** Absolut – verwenden Sie `AffineTransform.rotate()`  

## Was bedeutet das Erstellen eines PostScript-Dokuments in Java?
Ein PostScript‑Dokument ist eine Page‑Description‑Language‑Datei, die Text, Grafiken und Bilder beschreibt. Mit Aspose.Page können Sie diese Dateien programmgesteuert in Java erzeugen und haben volle Kontrolle über Layout, Grafik‑Zustand und Bildverarbeitung, ohne dass ein PostScript‑Interpreter nötig ist.

## Warum Aspose.Page für die Bildbearbeitung verwenden?
- **High‑Level‑API:** Vereinfacht komplexe PostScript‑Befehle.  
- **Plattformübergreifend:** Funktioniert auf jedem Betriebssystem, das Java unterstützt.  
- **Vollständige Kontrolle des Grafik‑Zustands:** Grafik‑Speichern, Wiederherstellen, Übersetzen, Skalieren und Drehen lassen sich leicht durchführen.  
- **Keine externen Abhängigkeiten:** Bildladen und -konvertierung werden intern gehandhabt.

## Voraussetzungen
Bevor wir in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

- Java Development Kit (JDK) auf Ihrem System installiert.  
- Aspose.Page für Java‑Bibliothek. Sie können sie [hier](https://releases.aspose.com/page/java/) herunterladen.  
- Grundlegende Kenntnisse in der Java‑Programmierung.  

## Pakete importieren
Um loszulegen, importieren Sie die notwendigen Pakete in Ihrem Java‑Projekt. Verwenden Sie das folgende Code‑Snippet als Referenz:

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Schritt 1: Grafik speichern schreiben
Der erste Schritt besteht darin, das Grafik‑Speichern in das Dokument zu schreiben. Dadurch wird sichergestellt, dass alle nachfolgenden Transformationen oder Änderungen bei Bedarf zurückgesetzt werden können.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

## Schritt 2: Übersetzen und Transformieren (Bild übersetzen und drehen)
Als Nächstes übersetzen Sie das Dokument und erstellen ein `BufferedImage`‑Objekt aus der Bilddatei. Wenden Sie eine Reihe von Transformationen wie Skalieren und Drehen mit `AffineTransform` an. Hier findet die **Übersetzen‑ und Drehen‑Operation** statt.

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

## Schritt 3: Bild zum Dokument hinzufügen
Jetzt fügen Sie das transformierte Bild dem Dokument hinzu.

```java
document.drawImage(image, transform, null);
```

## Schritt 4: Grafik wiederherstellen schreiben
Nachdem das Bild hinzugefügt wurde, schreiben Sie das Grafik‑Wiederherstellen, um die vorgenommenen Änderungen abzuschließen.

```java
document.writeGraphicsRestore();
```

## Schritt 5: Aktuelle Seite schließen und speichern
Schließen Sie die aktuelle Seite und speichern Sie das Dokument.

```java
document.closePage();
document.save();
```

Sie können diese Schritte wiederholen, um mehrere Bilder hinzuzufügen oder die Transformationen nach Ihren Anforderungen anzupassen.

## Häufige Probleme und Lösungen
- **FileNotFoundException:** Stellen Sie sicher, dass der `dataDir`‑Pfad mit einem Dateiseparator (`/` oder `\\`) endet und der Bilddateiname exakt übereinstimmt.  
- **ImageIO.read gibt null zurück:** Prüfen Sie, ob das Bildformat unterstützt wird (z. B. JPEG, PNG).  
- **Falscher Rotationswinkel:** `AffineTransform.rotate` erwartet Radianten. Konvertieren Sie bei Bedarf Grad in Radianten (`Math.toRadians(degrees)`).

## Häufig gestellte Fragen

**F: Kann ich Aspose.Page für Java mit anderen Programmiersprachen verwenden?**  
A: Aspose.Page unterstützt hauptsächlich Java, es gibt jedoch Versionen für andere Programmiersprachen.

**F: Gibt es eine kostenlose Testversion von Aspose.Page für Java?**  
A: Ja, Sie können die kostenlose Testversion [hier](https://releases.aspose.com/) erhalten.

**F: Wie kann ich eine temporäre Lizenz für Aspose.Page für Java erhalten?**  
A: Eine temporäre Lizenz erhalten Sie [hier](https://purchase.aspose.com/temporary-license/).

**F: Wo finde ich Community‑Support und Diskussionen zu Aspose.Page für Java?**  
A: Besuchen Sie das [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39) für Community‑Support.

**F: Gibt es zusätzliche Ressourcen zum Kauf von Aspose.Page für Java?**  
A: Die Bibliothek können Sie [hier](https://purchase.aspose.com/buy) erwerben.

## Fazit
Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie ein **PostScript‑Dokument in Java** erstellen und Bilder mit Aspose.Page für Java einbetten. Erkunden Sie die [Dokumentation](https://reference.aspose.com/page/java/) für weiterführende Funktionen wie Vektorgrafiken, Textdarstellung und benutzerdefinierte Seitengrößen.

---

**Zuletzt aktualisiert:** 2025-12-09  
**Getestet mit:** Aspose.Page für Java 23.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}