---
title: Legen Sie die Deckkraftmaske in Java XPS fest
linktitle: Legen Sie die Deckkraftmaske in Java XPS fest
second_title: Aspose.Page Java-API
description: Entdecken Sie mit Aspose.Page die Möglichkeiten des Festlegens von Deckkraftmasken in Java XPS. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für ein visuell verbessertes Dokumentenerlebnis.
weight: 11
url: /de/java/xps-transparency/set-opacity-mask/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Legen Sie die Deckkraftmaske in Java XPS fest

## Einführung
Willkommen zu unserem umfassenden Leitfaden zum Festlegen von Deckkraftmasken in Java XPS mit Aspose.Page. In diesem Tutorial führen wir Sie durch den Prozess der Erstellung eines XPS-Dokuments, des Hinzufügens einer Leinwand und des Anwendens einer Deckkraftmaske auf ein Rechteck mithilfe der leistungsstarken Funktionen von Aspose.Page für Java.
## Voraussetzungen
Bevor Sie mit diesem Tutorial beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- Ein grundlegendes Verständnis der Java-Programmierung.
-  Aspose.Page für Java-Bibliothek installiert. Sie können es herunterladen[Hier](https://releases.aspose.com/page/java/).
-  Eine gültige Lizenz für Aspose.Page. Wenn Sie noch keine haben, können Sie eine temporäre Lizenz erwerben[Hier](https://purchase.aspose.com/temporary-license/).
- Eine Entwicklungsumgebung, die zum Ausführen von Java-Anwendungen eingerichtet ist.
## Pakete importieren
Beginnen Sie mit dem Importieren der erforderlichen Pakete in Ihr Java-Projekt. Stellen Sie sicher, dass die Aspose.Page-Bibliothek ordnungsgemäß integriert ist. Nachfolgend finden Sie einen Ausschnitt zur Orientierung:
```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
Lassen Sie uns nun den Beispielcode in mehrere Schritte unterteilen:
## Schritt 1: Erstellen Sie ein neues XPS-Dokument
```java
// Erstellen Sie ein neues XPS-Dokument
XpsDocument doc = new XpsDocument();
```
## Schritt 2: Fügen Sie eine Leinwand hinzu
```java
// Neue Leinwand
XpsCanvas canvas = doc.addCanvas();
```
## Schritt 3: Fügen Sie ein Rechteck mit einer Deckkraftmaske hinzu
```java
// Rechteck in der Mitte links mit durch ImageBrush maskierter Deckkraft
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```
## Schritt 4: Legen Sie die Deckkraftmaske mit ImageBrush fest
```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```
## Schritt 5: Speichern Sie das resultierende XPS-Dokument
```java
// Speichern Sie das resultierende XPS-Dokument
doc.save(dataDir + "OpacityMask_out.xps"); 
```
Befolgen Sie diese Schritte sorgfältig, um mithilfe von Aspose.Page Deckkraftmasken in Ihr Java XPS-Dokument zu integrieren.
## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Page Deckkraftmasken in Java XPS festlegen. Diese Funktion verleiht Ihren Dokumenten eine visuelle Fülle und macht sie ansprechender und dynamischer.
## FAQs
### Ist Aspose.Page mit allen Java-Entwicklungsumgebungen kompatibel?
Ja, Aspose.Page ist so konzipiert, dass es nahtlos mit verschiedenen Java-Entwicklungsumgebungen zusammenarbeitet.
### Kann ich Aspose.Page ohne Lizenz nutzen?
Sie können Aspose.Page zwar ohne Lizenz nutzen, es wird jedoch empfohlen, eine zu erwerben, um den gesamten Funktionsumfang und Support nutzen zu können.
### Gibt es Einschränkungen bei der Testversion?
Die Testversion kann einige Funktionseinschränkungen aufweisen. Es empfiehlt sich, die Dokumentation auf Einzelheiten zu prüfen.
### Wie kann ich Unterstützung für Aspose.Page erhalten?
 Sie können die besuchen[Aspose.Page-Forum](https://forum.aspose.com/c/page/39) für Community-Support oder erwerben Sie eine Lizenz für Premium-Unterstützung.
### Gibt es eine Geld-zurück-Garantie für Aspose.Page?
 Siehe die[Kaufseite](https://purchase.aspose.com/buy) für Informationen zu Rückerstattungsrichtlinien.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
