---
date: 2026-05-25
description: Erfahren Sie, wie Sie Gradient zu XPS-Dokumenten in Java mit Aspose.Page
  hinzufügen. Diese Schritt‑für‑Schritt‑Anleitung zeigt, wie Sie einen Diagonal Gradient
  hinzufügen, linear gradient brushes anwenden und professionelle XPS files erzeugen.
keywords:
- how to add gradient
- Aspose.Page Java
- diagonal gradient XPS
linktitle: Diagonal Gradient in Java XPS hinzufügen
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to add gradient to XPS documents in Java using Aspose.Page.
    This step‑by‑step guide shows how to add a diagonal gradient, apply linear gradient
    brushes, and produce professional XPS files.
  headline: 'How to Add Gradient: Diagonal Gradient in Java XPS'
  type: TechArticle
- questions:
  - answer: Create a `XpsLinearGradientBrush`, define gradient stops, and assign it
      to the shape’s `Fill` property as shown in Step 6.
    question: How do I **how to add gradient** to an existing XPS shape?
  - answer: It generates a brush definition in the XPS package that references the
      start/end points and a collection of gradient stops, which the viewer renders
      as a smooth color transition.
    question: What does **apply linear gradient** actually do behind the scenes?
  - answer: Yes, the Aspose.Page API includes methods for adding images, text, and
      custom shapes—simply explore the `XpsDocument` class for additional helpers.
    question: Is there a quick way to **how to use aspose** for other XPS features?
  - answer: Absolutely. Define any geometry using `createPathGeometry` and then set
      its `Fill` to a gradient brush.
    question: Can I **add gradient path** to non‑rectangular shapes?
  - answer: Only marginally; gradient definitions are lightweight XML entries within
      the XPS package.
    question: Does the gradient affect file size significantly?
  type: FAQPage
second_title: Aspose.Page Java API
title: 'Wie man Gradient hinzufügt: Diagonal Gradient in Java XPS'
url: /de/java/xps-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man einen Farbverlauf hinzufügt: Diagonalverlauf in Java XPS

## Einführung
In der modernen Java-Entwicklung gibt das Beherrschen **wie man einen Farbverlauf hinzufügt** zu XPS-Dokumenten Ihren Berichten ein poliertes, auffälliges Aussehen, das heraussticht. Dieses Tutorial führt Sie durch das Erstellen einer XPS-Datei von Grund auf, das Hinzufügen eines diagonalen Farbverlaufs und das Speichern des Ergebnisses – alles mit Aspose.Page für Java. Sie verstehen, warum Farbverläufe wichtig sind, sehen die genauen API-Aufrufe und erhalten praktische Tipps, um häufige Fallstricke zu vermeiden.

## Schnelle Antworten
- **Was ist die primäre Bibliothek?** Aspose.Page for Java  
- **Welche Methode fügt den Farbverlauf hinzu?** `createLinearGradientBrush` with gradient stops  
- **Benötige ich eine Lizenz?** A trial works for development; a commercial license is required for production  
- **Wie lange dauert die Implementierung?** About 10‑15 minutes for a basic diagonal gradient  
- **Kann ich das mit anderen Java-Frameworks verwenden?** Yes, the API is framework‑agnostic  

## Was ist ein diagonaler Farbverlauf in einem XPS-Dokument?
Ein diagonaler Farbverlauf ist ein sanfter Farbwechsel, der von einer Ecke einer Form zur gegenüberliegenden Ecke verläuft und einen schrägen visuellen Effekt erzeugt. In XPS wird dieser Effekt durch einen linearen Farbverlaufs‑Pinsel definiert, der geordnete Farbverlaufsstopps enthält, die Farben und relative Positionen entlang der Diagonalen festlegen.

## Warum einen diagonalen Farbverlauf mit Aspose.Page hinzufügen?
Aspose.Page liefert **100 % Rendering‑Treue** für Farbverläufe in über 20 XPS‑Betrachtern und unterstützt **30+ XPS‑Funktionen** wie Text, Bilder und Vektorgrafiken. Die API abstrahiert das komplexe XPS‑Markup, sodass Sie sich auf das Design konzentrieren können, während garantiert wird, dass dieselbe Datei auf Windows-, macOS‑ und Linux‑Plattformen identisch aussieht.

## Voraussetzungen
- Grundlegende Java-Programmierkenntnisse.  
- JDK auf Ihrem Rechner installiert.  
- Aspose.Page für Java Bibliothek – laden Sie sie **[hier](https://releases.aspose.com/page/java/)** herunter.  
- Eine IDE wie IntelliJ IDEA oder Eclipse.

## Pakete importieren
Beginnen Sie damit, die Klassen zu importieren, die Sie benötigen. Diese Importe geben Ihnen Zugriff auf Geometrie, Farbverlauf‑Verarbeitung und die Erstellung von XPS‑Dokumenten.

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```

## Schritt 1: Projekt einrichten
Erstellen Sie ein neues Java‑Projekt in Ihrer bevorzugten IDE und fügen Sie die Aspose.Page‑JAR‑Dateien dem Build‑Pfad des Projekts hinzu.

## Schritt 2: Dokumentverzeichnis festlegen
Geben Sie an, wo die erzeugte XPS‑Datei gespeichert werden soll.

```java
String dataDir = "Your Document Directory";
```

## Schritt 3: XPS‑Dokument erstellen
`XpsDocument` ist das Kernobjekt, das eine XPS‑Datei im Speicher repräsentiert. Durch die Instanziierung erhalten Sie eine Zeichenfläche, um Seiten, Formen und Pinsel hinzuzufügen.

```java
XpsDocument doc = new XpsDocument();
```

## Schritt 4: Diagonalen Farbverlaufspfad hinzufügen
Erstellen Sie einen rechteckigen Pfad, der den Farbverlauf erhalten soll. Die Pfadgeometrie verwendet einen einfachen move‑line‑close‑Befehl.  
XpsPath definiert eine Vektorform im XPS‑Dokument, wie ein Rechteck oder eine benutzerdefinierte Geometrie.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```

## Schritt 5: Lineare Farbverlaufs‑Stopps definieren
Richten Sie die Farben und deren Positionen ein. Jeder Stopp definiert einen Punkt im Farbverlauf, an dem eine bestimmte Farbe erscheint.  
XpsGradientStop repräsentiert einen einzelnen Farbstopp in einem Farbverlauf und gibt eine Farbe sowie deren Offset an.

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... repeat for other colors and positions
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```

## Schritt 6: Linearen Farbverlauf auf den Pfad anwenden
`XpsLinearGradientBrush` ist Aspose.Page’s Pinseltyp für lineare Farbübergänge. Er nimmt zwei Punkte, die die Verlaufsrichtung definieren, und eine Sammlung von Farbverlaufs‑Stopps, die die Farben entlang dieser Linie festlegen.

```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## Schritt 7: Dokument speichern
Speichern Sie die XPS‑Datei auf dem Datenträger. Die Datei enthält das Rechteck, das mit dem von Ihnen definierten diagonalen Farbverlauf gefüllt ist.

```java
doc.save(dataDir + "LinearGradient.xps");
```

## Wie man einen Farbverlauf in Java XPS hinzufügt?
Laden Sie das XpsDocument, erstellen Sie einen `XpsLinearGradientBrush` mit dem Startpunkt `(0,0)` und dem Endpunkt `(width,height)`, fügen Sie Farbverlaufs‑Stopps hinzu, weisen Sie den Pinsel der `Fill`‑Eigenschaft einer Form zu und rufen Sie schließlich `save` auf. Dieser kompakte Ablauf ermöglicht es Ihnen, einen diagonalen Farbverlauf mit nur wenigen API‑Aufrufen einzubetten, wodurch Ihr Code sauber und wartbar bleibt.

## Häufige Fallstricke & Tipps
- **Gradientrichtung** – Stellen Sie sicher, dass die Start‑ und Endpunkte des Pinsels die gewünschte Diagonale widerspiegeln; ein Vertauschen kehrt den Farbverlauf um.  
- **Farbpräzision** – Aspose verwendet ARGB; schließen Sie den Alpha‑Kanal ein, wenn Sie Transparenz benötigen.  
- **Dateipfad** – Verwenden Sie immer einen absoluten Pfad oder prüfen Sie, dass der relative Pfad auf ein existierendes, beschreibbares Verzeichnis zeigt.

## Zusätzliche FAQ

**Q: Wie füge ich **wie man einen Farbverlauf hinzufügt** zu einer bestehenden XPS‑Form hinzu?**  
A: Erstellen Sie einen `XpsLinearGradientBrush`, definieren Sie Farbverlaufs‑Stopps und weisen Sie ihn der `Fill`‑Eigenschaft der Form zu, wie in Schritt 6 gezeigt.

**Q: Was bewirkt **linearen Farbverlauf anwenden** tatsächlich im Hintergrund?**  
A: Es erzeugt eine Pinseldefinition im XPS‑Paket, die die Start‑/Endpunkte und eine Sammlung von Farbverlaufs‑Stopps referenziert, die der Betrachter als sanften Farbübergang rendert.

**Q: Gibt es einen schnellen Weg, **wie man Aspose verwendet** für andere XPS‑Funktionen?**  
A: Ja, die Aspose.Page‑API enthält Methoden zum Hinzufügen von Bildern, Text und benutzerdefinierten Formen – durchsuchen Sie einfach die Klasse `XpsDocument` für weitere Hilfsmittel.

**Q: Kann ich **Farbverlaufspfad hinzufügen** zu nicht‑rechtwinkligen Formen?**  
A: Absolut. Definieren Sie jede Geometrie mit `createPathGeometry` und setzen Sie anschließend deren `Fill` auf einen Farbverlaufs‑Pinsel.

**Q: Beeinflusst der Farbverlauf die Dateigröße signifikant?**  
A: Nur marginal; Farbverlaufsdefinitionen sind leichte XML‑Einträge im XPS‑Paket.

---

**Zuletzt aktualisiert:** 2026-05-25  
**Getestet mit:** Aspose.Page for Java 24.11  
**Autor:** Aspose

## Verwandte Tutorials

- [Aspose Page XPS Farbverlauf hinzufügen](/page/java/xps-gradient-addition/)
- [Java XPS Text hinzufügen – Aspose.Page Tutorial](/page/java/xps-text-manipulation/add-text/)
- [Wie man ein Bild zu Java XPS-Dokumenten hinzufügt – Eine einfache Anleitung mit Aspose.Page](/page/java/xps-image-manipulation/add-image/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}