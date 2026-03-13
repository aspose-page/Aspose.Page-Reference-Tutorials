---
date: 2026-03-13
description: Erfahren Sie, wie Sie in Java mit Aspose.Page Verläufe zu XPS-Dokumenten
  hinzufügen und wie Sie Farbverlaufspunkte für beeindruckende horizontale Effekte
  anpassen.
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: Wie man einen Farbverlauf – Horizontalen Farbverlauf – in Java XPS hinzufügt
url: /de/java/xps-gradient-addition/horizontal/
weight: 11
---

 shortcodes exactly.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man einen Farbverlauf hinzufügt – Horizontaler Farbverlauf in Java XPS

## Einführung
Willkommen zu dieser Schritt‑für‑Schritt‑Anleitung, wie man **einen Farbverlauf** zu einem XPS‑Dokument mit Java hinzufügt. In diesem Tutorial lernen Sie, wie man einen horizontalen Farbverlauf hinzufügt, warum er für die visuelle Verfeinerung wichtig ist und wie man **Farbverlaufsstopps** für präzise Farbkontrolle **anpasst**. Aspose.Page für Java macht die Arbeit mit XPS (XML Paper Specification)-Dokumenten unkompliziert, sodass Sie sich auf das Design statt auf die Low‑Level‑Dateiverarbeitung konzentrieren können.

## Schnelle Antworten
- **Welche Bibliothek wird benötigt?** Aspose.Page for Java  
- **Welche Java‑Version funktioniert?** Jede Java 8+ Runtime  
- **Brauche ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich  
- **Kann ich die Richtung des Farbverlaufs ändern?** Ja – ändern Sie einfach die Start‑/Endpunkte des linearen Pinsels  
- **Ist es möglich, mehrere Farbverläufe hinzuzufügen?** Absolut – wiederholen Sie die Pfaderstellungs‑Schritte mit verschiedenen Pinseln  

## Was ist ein horizontaler Farbverlauf in XPS?
Ein horizontaler Farbverlauf ist ein sanfter Übergang von Farben von links nach rechts über eine Form. In XPS wird er durch einen linearen Farbverlaufs‑Pinsel dargestellt, der zwischen definierten **gradient stops** interpoliert. Dieser visuelle Effekt wird häufig für Banner, Schaltflächen und Hintergrundfüllungen verwendet.

## Warum Aspose.Page für Java verwenden?
- **Vollständige XPS‑Unterstützung** – erstellen, bearbeiten und rendern ohne Drittanbieter‑Tools.  
- **Einfache API** – High‑Level‑Objekte wie `XpsDocument`, `XpsPath` und `XpsGradientBrush` verbergen die XML‑Komplexität.  
- **Performance** – optimiert für große Dokumente und Batch‑Verarbeitung.  

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java‑Entwicklungsumgebung** – Installieren Sie das neueste JDK von [java.com](https://www.java.com).  
2. **Aspose.Page für Java Bibliothek** – Laden Sie das JAR von der [Aspose.Page für Java Dokumentation](https://reference.aspose.com/page/java/) herunter.  

## Pakete importieren
Beginnen Sie mit dem Import der erforderlichen Klassen. Diese Importe geben Ihnen Zugriff auf Dokumenterstellung, Farbverlaufs‑Verarbeitung und grundlegende Geometrie.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## Schritt 1: XPS‑Dokument initialisieren
Erstellen Sie eine neue `XpsDocument`‑Instanz und geben Sie den Ordner an, in dem Sie das Ergebnis speichern möchten.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## Schritt 2: Horizontalen Farbverlauf erstellen
Definieren Sie eine Liste von **gradient stops**, die Farbe und Position jedes Übergabepunkts steuern. Das untenstehende Beispiel erstellt einen lebendigen regenbogenähnlichen Farbverlauf.

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

### Wie man Farbverlaufsstopps anpasst
- **Farbe** – Verwenden Sie `doc.createColor(alpha, red, green, blue)`, um einen beliebigen ARGB‑Wert festzulegen.  
- **Position** – Das zweite Argument (`float` zwischen `0` und `1`) definiert, wo der Stopp entlang der Farbverlaufs‑Linie erscheint. Passen Sie diese Werte an, um Farben nach links oder rechts zu verschieben.

## Schritt 3: Pfad mit Farbverlauf hinzufügen
Erstellen Sie einen rechteckigen Pfad, wenden Sie bei Bedarf eine Transformation an und füllen Sie ihn mit dem linearen Farbverlaufs‑Pinsel. Der Pinsel verwendet zwei Punkte (`(10,0)` bis `(228,0)`), um einen horizontalen Effekt zu erzeugen. Da die Y‑Koordinaten identisch sind, wirkt dieser Pinsel als **horizontaler Farbverlaufs‑Pinsel**.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**Pro‑Tipp:** Das Wiederverwenden derselben `stops`‑Liste für mehrere Pfade kann die Leistung verbessern, aber denken Sie daran, sie vor dem Hinzufügen neuer Stopps mit `clear()` zu leeren.

## Schritt 4: Dokument speichern
Speichern Sie die XPS‑Datei auf dem Datenträger. Sie können sie nun mit jedem XPS‑Betrachter öffnen, um den horizontalen Farbverlauf in Aktion zu sehen.

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## Wie man mehrere Farbverläufe anwendet
Wenn Sie **mehrere Farbverläufe** im selben XPS‑Dokument **anwenden** möchten, wiederholen Sie einfach die Schritte „Horizontalen Farbverlauf erstellen“ und „Pfad mit Farbverlauf hinzufügen“ für jede neue Form. Verwenden Sie eine neue Liste von `XpsGradientStop`‑Objekten (oder leeren Sie die vorhandene Liste) und weisen Sie einen neuen `LinearGradientBrush` mit eigenen Start‑/Endpunkten zu. Dieser Ansatz ermöglicht es Ihnen, Farbverläufe zu schichten, komplexe Hintergründe zu erstellen oder verschiedene UI‑Elemente auf einer einzigen Seite hervorzuheben.

## Warum das wichtig ist – Vorteile des horizontalen Farbverlaufs‑Pinsels
- **Visuelle Tiefe:** Ein horizontaler Farbverlaufs‑Pinsel verleiht ein subtiles dreidimensionales Gefühl ohne zusätzliche Bilder.  
- **Dateigrößen‑Effizienz:** Farbverläufe werden als Vektor‑Definitionen gespeichert, wodurch die XPS‑Datei leicht bleibt.  
- **Skalierbarkeit:** Da der Farbverlauf vektor‑basiert ist, skaliert er sauber auf hochauflösenden Displays.  

## Häufige Probleme & Lösungen
| Problem | Ursache | Lösung |
|---------|---------|--------|
| Farbverlauf erscheint einfarbig | Keine Farbverlaufsstopps hinzugefügt oder Pinsel nicht gesetzt | Stellen Sie sicher, dass `path.setFill(...)` einen `LinearGradientBrush` verwendet und dass Stopps über `getGradientStops().addAll(stops)` hinzugefügt werden. |
| Farben wirken gedämpft | Falscher Alpha‑Wert (erster Parameter) | Verwenden Sie `255` für vollständig undurchsichtige Farben, sofern keine Transparenz gewünscht ist. |
| Pfadgröße ist falsch | Transformationsmatrix‑Werte sind falsch | Passen Sie die Matrix‑Parameter (`scaleX, skewY, skewX, scaleY, translateX, translateY`) an. |

## Häufig gestellte Fragen

**Q: Kann ich mehrere Farbverläufe in einem einzigen XPS‑Dokument anwenden?**  
A: Ja, Sie können mehrere Pfade hinzufügen, jeder mit seinem eigenen Farbverlaufs‑Pinsel, um komplexe, geschichtete Designs zu erstellen.

**Q: Ist Aspose.Page mit den neuesten Java‑Versionen kompatibel?**  
A: Aspose.Page für Java wird regelmäßig aktualisiert und funktioniert mit Java 8 und neueren Versionen.

**Q: Gibt es weitere Farbverlaufstypen in Aspose.Page?**  
A: Neben linearen Farbverläufen unterstützt Aspose.Page auch radiale Farbverläufe für kreisförmige Farbübergänge.

**Q: Kann ich die Farben und Positionen der Farbverlaufsstopps anpassen?**  
A: Absolut! Sie haben die volle Kontrolle über die ARGB‑Farbe jedes Stopps und seine relative Position (Bereich 0‑1).

**Q: Gibt es ein Community‑Forum für Aspose.Page, wo ich Hilfe finden kann?**  
A: Ja, Sie können das [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39) besuchen, um mit der Community in Kontakt zu treten und Unterstützung zu erhalten.

---

**Zuletzt aktualisiert:** 2026-03-13  
**Getestet mit:** Aspose.Page für Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}