---
date: 2025-12-25
description: Erfahren Sie, wie Sie in Java mit Aspose.Page Verläufe zu XPS-Dokumenten
  hinzufügen und wie Sie Farbverlaufspunkte für beeindruckende horizontale Effekte
  anpassen.
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: Wie man einen Farbverlauf hinzufügt – Horizontaler Farbverlauf in Java XPS
url: /de/java/xps-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man einen Verlauf hinzufügt – Horizontaler Verlauf in Java XPS

## Einleitung
Willkommen zu dieser Schritt‑für‑Schritt‑Anleitung, **wie man einen Verlauf** zu einem XPS‑Dokument mit Java hinzufügt. In diesem Tutorial lernen Sie, wie Sie einen horizontalen Verlauf hinzufügen, warum er für die visuelle Politur wichtig ist und wie Sie **Verlaufspunkte anpassen** können, um eine präzise Farbkontrolle zu erreichen. Aspose.Page für Java macht die Arbeit mit XPS‑Dokumenten (XML Paper Specification) unkompliziert, sodass Sie sich auf das Design statt auf die Dateiverarbeitung im Low‑Level konzentrieren können.

## Schnelle Antworten
- **Welche Bibliothek wird benötigt?** Aspose.Page für Java  
- **Welche Java‑Version funktioniert?** Jede Java 8+ Runtime  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich  
- **Kann ich die Verlaufsrichtung ändern?** Ja – ändern Sie einfach die Start‑/Endpunkte des linearen Brushes  
- **Ist es möglich, mehrere Verläufe hinzuzufügen?** Absolut – wiederholen Sie die Pfaderstellungs‑Schritte mit unterschiedlichen Brushes  

## Was ist ein horizontaler Verlauf in XPS?
Ein horizontaler Verlauf ist ein sanfter Farbübergang von links nach rechts über eine Form hinweg. In XPS wird er durch einen linearen Verlaufs‑Brush dargestellt, der zwischen definierten **Verlaufspunkten** interpoliert. Dieser visuelle Effekt wird häufig für Banner, Schaltflächen und Hintergrundfüllungen verwendet.

## Warum Aspose.Page für Java verwenden?
- **Vollständige XPS‑Unterstützung** – erstellen, bearbeiten und rendern ohne Drittanbieter‑Tools.  
- **Einfache API** – High‑Level‑Objekte wie `XpsDocument`, `XpsPath` und `XpsGradientBrush` verbergen die XML‑Komplexität.  
- **Performance** – optimiert für große Dokumente und Batch‑Verarbeitung.  

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java‑Entwicklungsumgebung** – Installieren Sie das neueste JDK von [java.com](https://www.java.com).  
2. **Aspose.Page für Java Bibliothek** – Laden Sie das JAR von der [Aspose.Page für Java Dokumentation](https://reference.aspose.com/page/java/) herunter.  

## Pakete importieren
Beginnen Sie mit dem Import der notwendigen Klassen. Diese Importe geben Ihnen Zugriff auf Dokumentenerstellung, Verlaufshandhabung und grundlegende Geometrie.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## Schritt 1: Initialisieren des XPS‑Dokuments
Erstellen Sie eine neue `XpsDocument`‑Instanz und geben Sie den Ordner an, in dem Sie das Ergebnis speichern möchten.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## Schritt 2: Horizontalen Verlauf erstellen
Definieren Sie eine Liste von **Verlaufspunkten**, die die Farbe und Position jedes Übergangspunkts steuern. Das Beispiel unten erzeugt einen lebhaften regenbogenähnlichen Verlauf.

```java
// Horizontal gradient
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```

### Wie man Verlaufspunkte anpasst
- **Farbe** – Verwenden Sie `doc.createColor(alpha, red, green, blue)`, um einen beliebigen ARGB‑Wert festzulegen.  
- **Position** – Das zweite Argument (`float` zwischen `0` und `1`) definiert, wo der Punkt entlang der Verlaufs‑Linie erscheint. Passen Sie diese Werte an, um Farben nach links oder rechts zu verschieben.

## Schritt 3: Pfad mit Verlauf hinzufügen
Erstellen Sie einen rechteckigen Pfad, wenden Sie bei Bedarf eine Transformation an und füllen Sie ihn mit dem linearen Verlaufs‑Brush. Der Brush verwendet zwei Punkte (`(10,0)` bis `(228,0)`), um einen horizontalen Effekt zu erzeugen.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**Profi‑Tipp:** Das Wiederverwenden derselben `stops`‑Liste für mehrere Pfade kann die Performance verbessern, denken Sie jedoch daran, sie vor dem Hinzufügen neuer Punkte mit `clear()` zu leeren.

## Schritt 4: Dokument speichern
Speichern Sie die XPS‑Datei auf dem Datenträger. Sie können sie nun mit jedem XPS‑Viewer öffnen, um den horizontalen Verlauf in Aktion zu sehen.

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## Häufige Probleme & Lösungen
| Problem | Ursache | Lösung |
|---------|---------|--------|
| Verlauf erscheint einfarbig | Keine Verlaufspunkte hinzugefügt oder Brush nicht gesetzt | Stellen Sie sicher, dass `path.setFill(...)` einen `LinearGradientBrush` verwendet und dass die Punkte über `getGradientStops().addAll(stops)` hinzugefügt werden. |
| Farben wirken gedämpft | Falscher Alpha‑Wert (erster Parameter) | Verwenden Sie `255` für vollständig undurchsichtige Farben, sofern keine Transparenz gewünscht ist. |
| Pfadgröße ist falsch | Transformationsmatrix‑Werte sind inkorrekt | Passen Sie die Matrix‑Parameter (`scaleX, skewY, skewX, scaleY, translateX, translateY`) an. |

## Häufig gestellte Fragen

**F: Kann ich mehrere Verläufe in einem einzigen XPS‑Dokument anwenden?**  
A: Ja, Sie können mehrere Pfade hinzufügen, jeder mit seinem eigenen Verlaufs‑Brush, um komplexe, geschichtete Designs zu erstellen.

**F: Ist Aspose.Page mit den neuesten Java‑Versionen kompatibel?**  
A: Aspose.Page für Java wird regelmäßig aktualisiert und funktioniert mit Java 8 und neueren Versionen.

**F: Gibt es weitere Verlaufsarten in Aspose.Page?**  
A: Neben linearen Verläufen unterstützt Aspose.Page auch radiale Verläufe für kreisförmige Farbübergänge.

**F: Kann ich die Farben und Positionen der Verlaufspunkte anpassen?**  
A: Absolut! Sie haben die volle Kontrolle über jede ARGB‑Farbe und deren relative Position (Bereich 0‑1).

**F: Gibt es ein Community‑Forum für Aspose.Page, wo ich Hilfe finden kann?**  
A: Ja, besuchen Sie das [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39), um sich mit der Community zu vernetzen und Unterstützung zu erhalten.

---

**Zuletzt aktualisiert:** 2025-12-25  
**Getestet mit:** Aspose.Page für Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}