---
date: 2026-02-15
description: Lernen Sie, wie Sie PostScript‑Java‑Dokumente erstellen und PostScript‑Dokumentdateien
  mit Bildverschiebung und -rotation mithilfe von Aspose.Page für Java generieren.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: PostScript in Java erstellen – Bild in Java‑PostScript einfügen
url: /de/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PostScript in Java erstellen – Bild in Java PostScript hinzufügen

## Einleitung
In diesem Tutorial lernen Sie, wie Sie **create postscript java**-Dokumente erstellen und Bilder mit der Aspose.Page for Java-Bibliothek einbetten. Wir gehen Schritt für Schritt vor, von der Initialisierung einer neuen PostScript-Datei bis zur Anwendung von **translate and rotate image**-Transformationen. Am Ende können Sie PostScript-Dateien programmgesteuert erzeugen und die Bildplatzierung pixelgenau steuern – ideal für automatisierte Berichte, Druck‑Workflows oder jede Situation, in der Sie **generate postscript document**-Ausgaben aus Java benötigen.

## Schnelle Antworten
- **Welche Bibliothek wird benötigt?** Aspose.Page for Java  
- **Kann ich mehrere Bilder hinzufügen?** Ja – wiederholen Sie die Transformations- und Zeichen‑Schritte  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion funktioniert für Tests; für die Produktion ist eine Lizenz erforderlich  
- **Welche Java-Version wird unterstützt?** Java 8 und neuer  
- **Wird Bildrotation unterstützt?** Absolut – verwenden Sie `AffineTransform.rotate()`

## Was ist create postscript java?
Ein **create postscript java**-Vorgang erzeugt eine PostScript-Seitenbeschreibungsdatei, die Text, Vektorgrafiken und Rasterbilder kodiert. Mit Aspose.Page können Sie diese Dateien direkt aus Java-Code erstellen, wodurch Sie die vollständige programmgesteuerte Kontrolle über Layout, Skalierung und Rotation erhalten, ohne einen separaten PostScript-Interpreter zu benötigen.

## Warum Aspose.Page für die Bildbearbeitung verwenden?
- **High‑level API:** Abstractiert Low‑Level‑PostScript‑Befehle in einfache Java‑Methoden.  
- **Cross‑platform:** Läuft auf jedem Betriebssystem, das Java unterstützt.  
- **Full graphics‑state control:** Speichern, wiederherstellen, übersetzen, skalieren und rotieren von Grafiken nach Belieben.  
- **No external dependencies:** Handhabt das Laden von Bildern, die Formatkonvertierung und das Einbetten intern.

## Voraussetzungen
Bevor wir in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

- Java Development Kit (JDK) auf Ihrem System installiert.  
- Aspose.Page for Java Bibliothek. Sie können sie [hier](https://releases.aspose.com/page/java/) herunterladen.  
- Grundlegendes Verständnis der Java-Programmierung.  

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

## Schritt 1: Grafik‑Speichern schreiben
Der erste Schritt besteht darin, das Grafik‑Speichern in das Dokument zu schreiben. Dadurch wird sichergestellt, dass alle danach vorgenommenen Transformationen oder Änderungen bei Bedarf zurückgesetzt werden können.

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

## Schritt 2: Übersetzen und Transformieren (translate and rotate image)
Als Nächstes verschieben Sie das Dokument und erstellen ein `BufferedImage`‑Objekt aus der Bilddatei. Wenden Sie eine Reihe von Transformationen wie Skalierung und Rotation mit `AffineTransform` an. Hier findet die **translate and rotate image**‑Operation statt.

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

## Schritt 3: Bild zum Dokument hinzufügen
Fügen Sie nun das transformierte Bild dem Dokument hinzu.

```java
document.drawImage(image, transform, null);
```

## Schritt 4: Grafik‑Wiederherstellung schreiben
Nachdem das Bild hinzugefügt wurde, schreiben Sie die Grafik‑Wiederherstellung, um die vorgenommenen Änderungen abzuschließen.

```java
document.writeGraphicsRestore();
```

## Schritt 5: Aktuelle Seite schließen und speichern
Schließen Sie die aktuelle Seite und speichern Sie das Dokument.

```java
document.closePage();
document.save();
```

Sie können diese Schritte wiederholen, um mehrere Bilder hinzuzufügen oder die Transformationen nach Ihren Anforderungen anzupassen.

## Häufige Probleme und Lösungen
- **FileNotFoundException:** Stellen Sie sicher, dass der `dataDir`-Pfad mit einem Dateiseparator (`/` oder `\\`) endet und dass der Bilddateiname exakt übereinstimmt.  
- **ImageIO.read returns null:** Überprüfen Sie, ob das Bildformat unterstützt wird (z. B. JPEG, PNG).  
- **Incorrect rotation angle:** `AffineTransform.rotate` erwartet Radianten. Konvertieren Sie bei Bedarf Grad in Radianten (`Math.toRadians(degrees)`).

## Häufig gestellte Fragen

**Q: Kann ich Aspose.Page für Java mit anderen Programmiersprachen verwenden?**  
A: Aspose.Page unterstützt hauptsächlich Java, es gibt jedoch auch Versionen für andere Programmiersprachen.

**Q: Gibt es eine kostenlose Testversion für Aspose.Page für Java?**  
A: Ja, Sie können die kostenlose Testversion [hier](https://releases.aspose.com/) nutzen.

**Q: Wie kann ich eine temporäre Lizenz für Aspose.Page für Java erhalten?**  
A: Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erhalten.

**Q: Wo finde ich Community‑Support und Diskussionen zu Aspose.Page für Java?**  
A: Besuchen Sie das [Aspose.Page Forum](https://forum.aspose.com/c/page/39) für Community‑Support.

**Q: Gibt es weitere Ressourcen zum Kauf von Aspose.Page für Java?**  
A: Sie können die Bibliothek [hier](https://purchase.aspose.com/buy) erwerben.

## Fazit
Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie man **create postscript java**-Dokumente erstellt und Bilder mit Aspose.Page for Java einbettet. Erkunden Sie die [Dokumentation](https://reference.aspose.com/page/java/) für weiterführende Funktionen und Features, wie Vektorgrafiken, Textdarstellung und benutzerdefinierte Seitengrößen.

---

**Zuletzt aktualisiert:** 2026-02-15  
**Getestet mit:** Aspose.Page for Java 23.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}