---
date: 2026-04-24
description: Lernen Sie, wie Sie XPS‑Text in Java mit Aspose.Page hinzufügen – ein
  Schritt‑für‑Schritt‑Leitfaden zum Erstellen von XPS‑Dokumenten, Hinzufügen von Text
  und mühelosen Speichern von XPS‑Dateien.
keywords:
- how to add xps
- create xps document
- aspose.page add text
linktitle: Text in Java XPS hinzufügen
second_title: Aspose.Page Java API
title: Wie man XPS‑Text in Java hinzufügt – Aspose.Page‑Tutorial
url: /de/java/xps-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# So fügen Sie XPS-Text in Java hinzu – Aspose.Page Tutorial

## Einführung
Wenn Sie **XPS-Text** programmgesteuert hinzufügen müssen, bietet Aspose.Page für Java eine saubere, leistungsstarke API zur Arbeit mit XPS (XML Paper Specification)-Dateien. In diesem Tutorial führen wir Sie durch das Erstellen eines XPS-Dokuments, das Einfügen von formatiertem Text und das Speichern des Ergebnisses – alles mit prägnantem, leicht nachvollziehbarem Code. Egal, ob Sie eine Reporting-Engine bauen, Rechnungen generieren oder einfach Text auf einer Seite überlagern möchten, diese Schritte bringen Sie schnell ans Ziel.

## Schnelle Antworten
- **Welche Bibliothek ist am besten für die XPS-Manipulation in Java?** Aspose.Page for Java.
- **Kann ich XPS-Dateien ohne Lizenz erstellen und speichern?** Eine kostenlose Testversion funktioniert für die Evaluierung; für die Produktion ist eine Lizenz erforderlich.
- **Welche IDEs werden unterstützt?** IntelliJ IDEA, Eclipse, NetBeans oder jede IDE, die Java unterstützt.
- **Wie viele Codezeilen werden benötigt, um einfachen Text hinzuzufügen?** Etwa 10 Zeilen plus Setup.
- **Ist Schriftstil möglich?** Ja – Sie können Schriftfamilie, Größe, Stil und Farbe festlegen.

## Was ist XPS und warum Text hinzufügen?
XPS (XML Paper Specification) ist Microsofts festes Layout‑Dokumentenformat, ähnlich wie PDF, jedoch auf XML basierend. Das Hinzufügen von Text zu einer XPS‑Datei ist üblich, wenn Sie eine präzise Platzierung benötigen, etwa für Etiketten, Wasserzeichen oder dynamische Daten in Berichten. Mit Aspose.Page können Sie XPS manipulieren, ohne sich mit Low‑Level‑XML‑Strukturen auseinandersetzen zu müssen.

## Warum Aspose.Page zum Hinzufügen von XPS-Text verwenden?
- **Vollständige Kontrolle** über Glyphenpositionierung, Schriftstile und Pinsel.  
- **Keine externen Abhängigkeiten** – reine Java‑API.  
- **Hohe Treue** bei der Darstellung, die das Layout über Plattformen hinweg bewahrt.  
- **Umfassende Dokumentation** und Beispielcode für einen schnellen Einstieg.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- **Java Development Kit (JDK)** – eine aktuelle Version (8 oder höher) installiert.
- **Aspose.Page für Java** – laden Sie die Bibliothek von der offiziellen Seite [here](https://releases.aspose.com/page/java/).
- **Eine Java‑IDE** – IntelliJ IDEA, Eclipse oder ein beliebiger Editor Ihrer Wahl.

## Pakete importieren
Beginnen Sie damit, die Klassen zu importieren, die Sie für die XPS‑Manipulation benötigen:

```java
import java.awt.Color;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
```

## Schritt 1: Dokumentverzeichnis festlegen (XPS-Datei erstellen)
Definieren Sie, wo die erzeugte XPS‑Datei gespeichert werden soll:

```java
String dataDir = "Your Document Directory";
```

## Schritt 2: XPS-Dokument erstellen (XPS-Dokument erstellen)
Instanziieren Sie ein neues, leeres XPS‑Dokument:

```java
XpsDocument doc = new XpsDocument();
```

## Schritt 3: Pinsel für Textstil erstellen
Ein einfarbiger Pinsel bestimmt die Textfarbe. Hier verwenden wir Schwarz:

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
```

## Schritt 4: Glyphen hinzufügen – der eigentliche Text (aspose.page add text)
Fügen Sie den Text ein, der im Dokument erscheinen soll. Die Methode `addGlyphs` ermöglicht die Angabe von Schriftart, Größe, Stil und genauen Koordinaten:

```java
XpsGlyphs glyphs = doc.addGlyphs("Arial", 12, XpsFontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.setFill(textFill);
```

## Schritt 5: Ergebnis‑XPS-Dokument speichern (XPS-Datei speichern)
Schreiben Sie schließlich das Dokument auf die Festplatte:

```java
doc.save(dataDir + "AddText_out.xps");
```

Wiederholen Sie den **Add Glyphs**‑Schritt nach Bedarf, um weitere Zeilen einzufügen, Schriftarten zu ändern oder Positionen anzupassen.

## Häufige Probleme & Pro‑Tipps
- **Falsche Koordinaten:** XPS verwendet ein Koordinatensystem, das in Punkten (1/72 Zoll) gemessen wird. Passen Sie die Werte `x` und `y` an, um den Text präzise zu positionieren.
- **Schriftart nicht gefunden:** Stellen Sie sicher, dass der Schriftname (z. B. „Arial“) auf dem Rechner, auf dem der Code ausgeführt wird, installiert ist.
- **Lizenzausnahme:** Ohne gültige Lizenz kann das erzeugte XPS ein Wasserzeichen enthalten. Wenden Sie Ihre Lizenz früh im Anwendungscode an, um dies zu vermeiden.

## Häufig gestellte Fragen

### Ist Aspose.Page mit allen Java-IDE kompatibel?
Ja, Aspose.Page funktioniert mit gängigen Java‑IDEs, einschließlich IntelliJ IDEA und Eclipse.

### Kann ich verschiedene Schriftstile auf den hinzugefügten Text anwenden?
Absolut! Verwenden Sie `XpsFontStyle.Bold`, `Italic` oder kombinieren Sie Stile, wenn Sie `addGlyphs` aufrufen.

### Wo finde ich zusätzliche Beispiele und Dokumentation für Aspose.Page?
Entdecken Sie die umfassende Dokumentation [here](https://reference.aspose.com/page/java/).

### Gibt es eine kostenlose Testversion für Aspose.Page?
Ja, Sie können die kostenlose Testversion [here](https://releases.aspose.com/) nutzen.

### Wie erhalte ich eine temporäre Lizenz für Aspose.Page?
Erhalten Sie eine temporäre Lizenz [here](https://purchase.aspose.com/temporary-license/).

**F: Kann ich Bilder zusammen mit dem Text einbetten?**  
**A: Ja – verwenden Sie `XpsImage`‑Objekte neben Glyphen, um reichhaltige Layouts zu erstellen.**

**F: Unterstützt Aspose.Page Unicode‑Zeichen?**  
**A: Es unterstützt Unicode vollständig, sodass Sie Text in jeder Sprache hinzufügen können.**

**F: Welche Version von Aspose.Page wurde für die Tests verwendet?**  
**A: Der Code wurde mit Aspose.Page 23.12 für Java getestet.**

---

**Zuletzt aktualisiert:** 2026-04-24  
**Getestet mit:** Aspose.Page 23.12 für Java  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}