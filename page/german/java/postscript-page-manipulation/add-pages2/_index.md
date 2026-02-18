---
date: 2026-02-18
description: Erfahren Sie, wie Sie benutzerdefinierte Seitengrößen festlegen und Seiten
  zu Java‑PostScript‑Dokumenten mit Aspose.Page hinzufügen. Folgen Sie unserer Schritt‑für‑Schritt‑Anleitung
  für eine nahtlose Dokumentenbearbeitung.
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: Aspose.Page Java‑Tutorial – benutzerdefinierte Seitengröße beim Hinzufügen
  von Seiten in PostScript festlegen
url: /de/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java‑Tutorial – benutzerdefinierte Seitengröße festlegen beim Hinzufügen von Seiten in PostScript

## Einführung
In modernen Java‑Anwendungen ist das **Festlegen einer benutzerdefinierten Seitengröße** für die PostScript‑Ausgabe häufig erforderlich – sei es beim Erzeugen von Rechnungen, Tickets oder individuellen Grafiken. In diesem Tutorial lernen Sie, wie Sie **für jede Seite eine benutzerdefinierte Seitengröße setzen**, mehrere Seiten hinzufügen und schließlich **eine PostScript‑Datei erzeugen**, die exakt Ihren Layout‑Anforderungen entspricht. Wir gehen den Code Schritt für Schritt durch, sodass Sie die Technik schnell in Ihren eigenen Projekten anwenden können.

## Schnelle Antworten
- **Kann ich für jede Seite unterschiedliche Seitengrößen festlegen?** Ja, Sie können Seiten mit benutzerdefinierten Abmessungen über `document.openPage(width, height)` öffnen.  
- **Benötige ich eine Lizenz für den Produktionseinsatz?** Eine gültige Aspose.Page‑Lizenz ist für den Einsatz außerhalb der Evaluation erforderlich.  
- **Welche Java‑Versionen werden unterstützt?** Die Bibliothek funktioniert mit Java 8 und neueren Versionen.  
- **Ist die API thread‑sicher?** Dokumentinstanzen sind nicht thread‑sicher; erstellen Sie pro Thread ein separates `PsDocument`.  
- **Wie groß kann eine PostScript‑Datei werden?** Aspose.Page verarbeitet Multi‑Megabyte‑Dateien effizient; der Speicherverbrauch skaliert mit dem Inhalt, nicht mit der Seitenzahl.  
- **Kann ich die Überladung openPage(width, height) verwenden?** Absolut – `openPage(double width, double height)` ermöglicht die Angabe beliebiger Abmessungen in Punkten.  

## Voraussetzungen
Bevor wir starten, stellen Sie sicher, dass Sie Folgendes haben:

- Grundlegende Kenntnisse in der Java‑Programmierung.  
- Aspose.Page für Java in Ihrem Projekt eingebunden (Maven/Gradle oder manuell als JAR).  
- Eine Java‑Entwicklungsumgebung (IDE, JDK 8+).  

## Pakete importieren
Um zu beginnen, importieren Sie die erforderlichen Klassen aus der Aspose.Page‑Bibliothek.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Schritt 1: Ein mehrseitiges PostScript‑Dokument erstellen
Zuerst erstellen Sie ein neues `PsDocument`, das für mehrere Seiten konfiguriert ist. Dadurch wird der Ausgabestream eingerichtet und der Bibliothek mitgeteilt, dass wir mit einer mehrseitigen Datei arbeiten.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddPages2_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Set variable that indicates if resulting PostScript document will be multipaged
boolean multiPaged = true;
// Create new multipaged PS Document with one page opened
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Schritt 2: Inhalt zur ersten Seite hinzufügen
Nachdem das Dokument bereit ist, können Sie beliebige Inhalte zur ersten Seite hinzufügen. Sobald Sie fertig sind, schließen Sie die Seite, um deren Inhalt zu fixieren.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## Wie man eine benutzerdefinierte Seitengröße festlegt
Falls die Standardseitengröße nicht Ihren Anforderungen entspricht, können Sie **eine benutzerdefinierte Seitengröße** beim Öffnen einer neuen Seite festlegen. Das ist nützlich für Quittungen, Etiketten oder jedes nicht‑standardmäßige Layout.

## Schritt 3: Eine zweite Seite mit anderer Größe hinzufügen
Im Folgenden öffnen wir eine zweite Seite und geben explizit eine benutzerdefinierte Breite und Höhe (in Punkten) an. Dies demonstriert, wie Sie für einzelne Seiten eine **benutzerdefinierte Seitengröße** festlegen und somit **unterschiedliche Seitengrößen** innerhalb desselben Dokuments verwenden können.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Schritt 4: Das Dokument speichern
Abschließend speichern Sie das Dokument, um die Änderungen zu persistieren. Alle Seiten – einschließlich der mit benutzerdefinierten Größen – werden in die Ausgabedatei geschrieben.

```java
// Save the document
document.save();
```

Durch Befolgen dieser Schritte können Sie nahtlos Seiten hinzufügen und **eine benutzerdefinierte Seitengröße** in einem Java‑PostScript‑Dokument mit Aspose.Page festlegen, wodurch Sie die volle Kontrolle über das Layout jeder Seite erhalten.

## Warum Aspose.Page zum Festlegen benutzerdefinierter Seitengrößen verwenden?
- **Präzision:** Abmessungen werden in Punkten definiert, sodass Sie die Seitenbreite und -höhe exakt steuern können.  
- **Flexibilität:** Kombinieren Sie **verschiedene Seitengrößen** in einer einzigen PostScript‑Datei.  
- **Performance:** Die Bibliothek streamt Inhalte direkt in die Ausgabedatei, was sie für groß angelegte **PostScript‑Datei‑Generierung**‑Szenarien geeignet macht.  
- **Umfangreiche API:** Unterstützt das Zeichnen von Grafiken, das Einbetten von Bildern und das Hinzufügen von Text – alles unter Beachtung der von Ihnen festgelegten benutzerdefinierten Abmessungen.  

## Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| **Seitenabmessungen erscheinen vertauscht** | Denken Sie daran, dass `openPage(width, height)` zuerst die Breite und dann die Höhe (beide in Punkten) erwartet. |
| **Inhalt überläuft die Seite** | Verwenden Sie das Koordinatensystem von `PsGraphics`, um Elemente innerhalb der benutzerdefinierten Grenzen zu positionieren, oder skalieren Sie Ihre Zeichnung. |
| **Out‑of‑Memory‑Fehler bei riesigen Dokumenten** | Aktivieren Sie das Streaming, indem Sie direkt in einen `FileOutputStream` schreiben, wie gezeigt, und vermeiden Sie das Laden großer Bilder vollständig in den Speicher. |

## Häufig gestellte Fragen
### Kann ich Seiten mit unterschiedlichen Größen in einem einzigen PostScript‑Dokument hinzufügen?
Ja, wie in diesem Tutorial demonstriert, können Sie Seiten mit variierenden Größen in einem mehrseitigen PostScript‑Dokument hinzufügen.  

### Gibt es Beschränkungen für die Anzahl der hinzuzufügenden Seiten?
Aspose.Page unterstützt das Hinzufügen einer praktisch unbegrenzten Anzahl von Seiten zu einem Dokument.  

### Kann ich benutzerdefinierte Inhalte wie Bilder oder Grafiken zu den Seiten hinzufügen?
Absolut! Aspose.Page ermöglicht das Einfügen einer breiten Palette von Inhalten, einschließlich Text, Bildern und anderen grafischen Elementen.  

### Ist Aspose.Page für die Verarbeitung großer Dokumente geeignet?
Ja, Aspose.Page ist darauf ausgelegt, sowohl kleine als auch große Dokumente effizient zu handhaben.  

### Wo finde ich zusätzliche Ressourcen und Support für Aspose.Page?
Entdecken Sie die [Aspose.Page‑Dokumentation](https://reference.aspose.com/page/java/), oder besuchen Sie das [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39) für Community‑Support.  

**Zusätzliche Fragen & Antworten**

**F:** *Welche Bildformate werden beim Zeichnen auf einer PostScript‑Seite unterstützt?*  
**A:** Sie können PNG-, JPEG-, BMP- und GIF‑Bilder direkt über die Zeichen‑API einbetten.  

**F:** *Wie ändere ich die Standard‑DPI für das Dokument?*  
**A:** Setzen Sie `PsSaveOptions.setResolution(int dpi)` bevor Sie das `PsDocument` erstellen.  

**F:** *Kann ich eine PostScript‑Datei mit einem Passwort verschlüsseln?*  
**A:** PostScript selbst unterstützt keine Verschlüsselung, aber Sie können die Ausgabe in ein PDF einbetten und dort Sicherheitseinstellungen anwenden, falls nötig.

---

**Zuletzt aktualisiert:** 2026-02-18  
**Getestet mit:** Aspose.Page für Java 24.10  
**Autor:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}