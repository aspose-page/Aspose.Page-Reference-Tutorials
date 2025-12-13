---
date: 2025-12-13
description: Erfahren Sie, wie Sie einer ASP‑Seite Text in Java hinzufügen, den Schriftstil
  in Java festlegen und Unicode‑Text mit Aspose.Page hinzufügen. Folgen Sie unserer
  Schritt‑für‑Schritt‑Anleitung.
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: ASP‑Seite Text hinzufügen – Unicode in Java‑PostScript
url: /de/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# asp page add text – Unicode in Java PostScript

## Einführung
Wenn Sie **asp page add text** in einem Java‑PostScript‑Workflow benötigen und dabei Unicode‑Zeichen erhalten wollen, sind Sie hier genau richtig. In diesem Tutorial führen wir Sie Schritt für Schritt durch das Hinzufügen von Unicode‑Text, das Festlegen des Schriftstils und das Speichern des Ergebnisses mit **Aspose.Page for Java**. Am Ende verstehen Sie, wie Sie *font style java* setzen und Unicode‑Text effizient in Ihren Projekten hinzufügen.

## Schnellantworten
- **Welche Bibliothek kann Unicode‑Text in Java PostScript hinzufügen?** Aspose.Page for Java.  
- **Welche primäre Methode fügt Text hinzu?** `doc.addGlyphs(...)` mit einem `XpsGlyphs`‑Objekt.  
- **Benötige ich eine spezielle Schriftart für Unicode?** Jede TrueType/OpenType‑Schrift, die die erforderlichen Code‑Punkte unterstützt (z. B. Arial).  
- **Kann ich den Schriftstil ändern?** Ja, mit `XpsFontStyle` (Regular, Bold, Italic usw.).  
- **Ist für die Produktion eine Lizenz erforderlich?** Ja, eine gültige Aspose.Page‑Lizenz ist für die Nutzung außerhalb der Testphase nötig.

## Was ist asp page add text?
`asp page add text` bezeichnet den Vorgang, Textzeichenketten in ein PostScript‑ oder XPS‑Dokument mithilfe der Aspose.Page‑API einzufügen. Die API abstrahiert low‑level PostScript‑Befehle und ermöglicht die Arbeit mit High‑Level‑Objekten wie `XpsGlyphs`.

## Warum Aspose.Page verwenden, um *font style java* zu setzen und Unicode‑Text hinzuzufügen?
- **Vollständige Unicode‑Unterstützung** – Handhabt Rechts‑zu‑Links‑Skripte und komplexe Glyphen.  
- **Einfache API** – Einzeilige Aufrufe zum Hinzufügen von Text und Anwenden von Stilen.  
- **Plattformübergreifend** – Funktioniert in jeder Java‑kompatiblen Umgebung.  
- **Keine externen Abhängigkeiten** – Keine zusätzlichen Rendering‑Engines nötig.

## Voraussetzungen
Bevor wir mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. **Java Development Kit (JDK)** – Vergewissern Sie sich, dass Java auf Ihrem Rechner installiert ist.  
2. **Aspose.Page for Java** – Laden Sie die Aspose.Page‑Bibliothek von dem [download link](https://releases.aspose.com/page/java/) herunter und installieren Sie sie.  
3. **Integrated Development Environment (IDE)** – Wählen Sie Ihre bevorzugte Java‑IDE, z. B. IntelliJ IDEA oder Eclipse.

## Pakete importieren
Importieren Sie in Ihrem Java‑Projekt die notwendigen Pakete für Aspose.Page. Fügen Sie die folgenden Zeilen zu Ihrem Code hinzu:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Schritt 1: Projekt einrichten
Erstellen Sie ein neues Java‑Projekt in Ihrer IDE und richten Sie die Projektstruktur ein. Stellen Sie sicher, dass die Aspose.Page‑Bibliothek in den Projekt‑Abhängigkeiten enthalten ist.

## Schritt 2: XPS‑Dokument initialisieren
Beginnen Sie damit, ein neues XPS‑Dokument in Ihrem Projekt zu initialisieren:

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Schritt 3: Unicode‑Text hinzufügen
Fügen Sie nun Unicode‑Text zu Ihrem XPS‑Dokument mithilfe der Aspose.Page‑Bibliothek hinzu. Verwenden Sie das folgende Code‑Snippet:

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

Dieses Code‑Segment fügt den Unicode‑Text **"AVAJ rof SPX.esopsA"** an den Koordinaten (400, 200) mit der angegebenen Schriftart und dem angegebenen Stil dem XPS‑Dokument hinzu. Beachten Sie, dass der Aufruf `setBidiLevel(1)` die Rechts‑zu‑Links‑Darstellung für eine korrekte Unicode‑Anzeige aktiviert.

## Schritt 4: Dokument speichern
Speichern Sie das resultierende XPS‑Dokument mit dem folgenden Code:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

## Fazit
Herzlichen Glückwunsch! Sie haben erfolgreich **asp page add text** durchgeführt und den Schriftstil in einem Java‑PostScript‑Szenario mithilfe von Aspose.Page gesetzt. Diese Methode bietet Ihnen eine feinkörnige Kontrolle über Unicode‑Rendering und Styling und eignet sich ideal für internationalisierte Berichte, Rechnungen und Grafiken.

Entdecken Sie weitere Funktionen und Möglichkeiten von Aspose.Page in der [documentation](https://reference.aspose.com/page/java/).

## Häufig gestellte Fragen

**F:** Kann ich Aspose.Page for Java mit anderen Programmiersprachen verwenden?  
**A:** Aspose.Page ist primär für Java konzipiert, aber Aspose bietet Bibliotheken für verschiedene Programmiersprachen an.

**F:** Gibt es eine kostenlose Testversion?  
**A:** Ja, Sie können eine kostenlose Testversion von Aspose.Page [hier](https://releases.aspose.com/) erhalten.

**F:** Wo finde ich Support und Diskussionen zu Aspose.Page?  
**A:** Besuchen Sie das [Aspose.Page forum](https://forum.aspose.com/c/page/39) für Support und Diskussionen.

**F:** Wie kann ich eine temporäre Lizenz für Aspose.Page erhalten?  
**A:** Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erwerben.

**F:** Welche Schriftstile stehen in Aspose.Page zur Verfügung?  
**A:** Aspose.Page unterstützt Schriftstile wie Regular, Bold, Italic und BoldItalic.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2025-12-13  
**Getestet mit:** Aspose.Page for Java (latest)  
**Autor:** Aspose  

---