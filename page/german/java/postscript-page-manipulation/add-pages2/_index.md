---
date: 2026-10-25
description: Erfahren Sie, wie Sie mit Aspose.Page benutzerdefinierte Seitengröße
  festlegen und Seiten zu Java‑PostScript‑Dokumenten hinzufügen. Folgen Sie unserer
  step‑by‑step‑Anleitung für nahtlose document manipulation.
keywords:
- set custom page size
- Aspose.Page Java
- PostScript page manipulation
- add pages PostScript
lastmod: 2026-10-25
linktitle: Adding Pages in PostScript
og_description: Erfahren Sie, wie Sie mit Aspose.Page für Java benutzerdefinierte
  Seitengröße in PostScript festlegen. Folgen Sie step‑by‑step‑Anweisungen, um Seiten
  hinzuzufügen, dimensions festzulegen und save the document effizient.
og_image_alt: Aspose.Page Java tutorial showing how to set custom page size in a PostScript
  document
og_title: Benutzerdefinierte Seitengröße in PostScript mit Aspose.Page Java festlegen
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to set custom page size and add pages to Java PostScript
    documents using Aspose.Page. Follow our step‑by‑step guide for seamless document
    manipulation.
  headline: Aspose.Page Java Tutorial – set custom page size while Adding Pages in
    PostScript
  type: TechArticle
- questions:
  - answer: Yes—you can open pages with custom dimensions using `document.openPage(width,
      height)`.
    question: Can I set different page sizes for each page?
  - answer: A valid Aspose.Page license is required for non‑evaluation deployments.
    question: Do I need a license for production use?
  - answer: The library works with Java 8 and newer.
    question: Which Java versions are supported?
  - answer: Document instances are not thread‑safe; create a separate `PsDocument`
      per thread.
    question: Is the API thread‑safe?
  - answer: Aspose.Page handles multi‑megabyte files efficiently; memory usage scales
      with content, not page count.
    question: How large can a PostScript file be?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java PostScript
- custom page size
- add pages
- document generation
title: Aspose.Page Java Tutorial – benutzerdefinierte Seitengröße festlegen beim Adding
  Pages in PostScript
url: /de/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java‑Tutorial – benutzerdefinierte Seitengröße festlegen beim Hinzufügen von Seiten in PostScript

## Einführung
In modernen Java‑Anwendungen ist das **Festlegen einer benutzerdefinierten Seitengröße** für PostScript‑Ausgaben häufig erforderlich – sei es beim Erzeugen von Rechnungen, Tickets oder individuellen Grafiken. Dieses Tutorial zeigt Ihnen, wie Sie für jede Seite eine benutzerdefinierte Seitengröße festlegen, mehrere Seiten hinzufügen und eine PostScript‑Datei erzeugen, die exakt Ihren Layout‑Anforderungen entspricht. Sie erhalten ein vollständiges, ausführbares Beispiel, das Sie in jedes Java 8+‑Projekt einbinden können.

## Schnelle Antworten
- **Kann ich für jede Seite unterschiedliche Seitengrößen festlegen?** Ja – Sie können Seiten mit benutzerdefinierten Abmessungen öffnen, indem Sie `document.openPage(width, height)` verwenden.  
- **Benötige ich eine Lizenz für den Produktionseinsatz?** Für den Einsatz außerhalb der Evaluierung ist eine gültige Aspose.Page‑Lizenz erforderlich.  
- **Welche Java‑Versionen werden unterstützt?** Die Bibliothek funktioniert mit Java 8 und neueren Versionen.  
- **Ist die API thread‑sicher?** Dokumentinstanzen sind nicht thread‑sicher; erstellen Sie pro Thread ein separates `PsDocument`.  
- **Wie groß kann eine PostScript‑Datei sein?** Aspose.Page verarbeitet mehrmegabytegroße Dateien effizient; der Speicherverbrauch skaliert mit dem Inhalt, nicht mit der Seitenzahl.  
- **Kann ich die Überladung für Breite/Höhe beim Öffnen einer Seite verwenden?** Absolut – `openPage(double width, double height)` ermöglicht die Angabe beliebiger Abmessungen in Punkten.  

## Voraussetzungen
Bevor wir starten, stellen Sie sicher, dass Sie Folgendes haben:

- Grundlegende Kenntnisse in der Java‑Programmierung.  
- Aspose.Page für Java in Ihrem Projekt eingebunden (Maven/Gradle oder manuell als JAR).  
- Eine Java‑Entwicklungsumgebung (IDE, JDK 8+).  

## Pakete importieren
Die folgenden Klassen werden benötigt: `FileOutputStream` zum Schreiben von Dateien, `PsDocument` zum Erstellen von PostScript‑Dokumenten und `PsSaveOptions` zur Konfiguration der Ausgabeoptionen.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Schritt 1: ein mehrseitiges PostScript‑Dokument erstellen
`PsDocument` ist die Kernklasse, die ein PostScript‑Dokument repräsentiert, das mehrere Seiten enthalten kann.

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
Nachdem das Dokument bereit ist, können Sie beliebigen Inhalt zur ersten Seite hinzufügen. Wenn Sie fertig sind, schließen Sie die Seite, um deren Inhalt zu sperren.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## Wie man benutzerdefinierte Seitengröße festlegt
Sie legen eine benutzerdefinierte Seitengröße fest, indem Sie vor dem Zeichnen von Inhalten `document.openPage(width, height)` mit den gewünschten Abmessungen in Punkten aufrufen. `openPage(width, height)` öffnet eine neue Seite mit der angegebenen Breite und Höhe und gibt Ihnen die volle Kontrolle über die Zeichenfläche. Wenn die Standardseitengröße nicht Ihren Anforderungen entspricht, können Sie **eine benutzerdefinierte Seitengröße** beim Öffnen einer neuen Seite festlegen. Das ist nützlich für Quittungen, Etiketten oder jedes nicht‑standardmäßige Layout.

## Schritt 3: eine zweite Seite mit anderer Größe hinzufügen
Im Folgenden öffnen wir eine zweite Seite und geben explizit eine benutzerdefinierte Breite und Höhe (in Punkten) an. Dies demonstriert, wie Sie für einzelne Seiten **verschiedene Seitengrößen** festlegen können, sodass Sie innerhalb desselben Dokuments mit unterschiedlichen Formaten arbeiten können.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Schritt 4: das Dokument speichern
Abschließend speichern Sie das Dokument, um die Änderungen zu übernehmen. Alle Seiten – einschließlich der mit benutzerdefinierten Größen – werden in die Ausgabedatei geschrieben.

```java
// Save the document
document.save();
```

Durch Befolgen dieser Schritte können Sie nahtlos Seiten hinzufügen und **benutzerdefinierte Seitengrößen** in einem Java‑PostScript‑Dokument mit Aspose.Page festlegen, wodurch Sie die volle Kontrolle über das Layout jeder Seite erhalten.

## Warum Aspose.Page zum Festlegen benutzerdefinierter Seitengrößen verwenden?
Aspose.Page bietet präzise Kontrolle über Seitenabmessungen, sodass Sie jede Breite und Höhe in Punkten definieren, mehrere Seitengrößen in einer einzigen Datei mischen und Inhalte effizient streamen können – ideal für Rechnungen, Tickets und groß angelegte Batch‑Verarbeitungen, bei denen der Speicherverbrauch niedrig bleiben muss.

Aspose.Page ermöglicht das Definieren exakter Seitenabmessungen in Punkten, das Mischen mehrerer Größen in einer Datei und das effiziente Streamen von Inhalten, was Ihnen präzise Kontrolle und hohe Leistung bei der Generierung von PostScript gibt.  
- **Präzision:** Abmessungen werden in Punkten definiert, sodass Sie die Seitenbreite und -höhe exakt steuern können.  
- **Flexibilität:** Mischen Sie **verschiedene Seitengrößen** in einer einzigen PostScript‑Datei.  
- **Leistung:** Die Bibliothek streamt Inhalte direkt in die Ausgabedatei und verarbeitet Dateien bis zu 500 MB, während der Heap‑Verbrauch unter 100 MB bleibt – ideal für groß angelegte **PostScript‑Datei‑Generierung**‑Szenarien.  
- **Umfangreiche API:** Unterstützt über 30 Grafik‑Primitive, 10 Bildformate und unbegrenzte Textobjekte pro Seite – alles unter Berücksichtigung der von Ihnen festgelegten benutzerdefinierten Abmessungen.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| **Seitenabmessungen erscheinen vertauscht** | Denken Sie daran, dass `openPage(width, height)` zuerst die Breite und dann die Höhe erwartet (beide in Punkten). |
| **Inhalt überschreitet die Seite** | Verwenden Sie das Koordinatensystem von `PsGraphics`, um Elemente innerhalb der benutzerdefinierten Grenzen zu positionieren, oder skalieren Sie Ihre Zeichnung. |
| **Out‑of‑Memory‑Fehler bei riesigen Dokumenten** | Aktivieren Sie das Streaming, indem Sie wie gezeigt direkt in einen `FileOutputStream` schreiben, und vermeiden Sie das gleichzeitige Laden großer Bilder in den Speicher. |

## Häufig gestellte Fragen
### Kann ich Seiten unterschiedlicher Größe in einem einzigen PostScript‑Dokument hinzufügen?
Ja, wie in diesem Tutorial demonstriert, können Sie Seiten mit variierenden Größen in einem mehrseitigen PostScript‑Dokument hinzufügen.  

### Gibt es Beschränkungen für die Anzahl der Seiten, die ich hinzufügen kann?
Aspose.Page unterstützt das Hinzufügen praktisch unbegrenzter Seiten zu einem Dokument.  

### Kann ich benutzerdefinierten Inhalt, wie Bilder oder Grafiken, zu den Seiten hinzufügen?
Absolut! Aspose.Page ermöglicht das Hinzufügen einer breiten Palette von Inhalten, einschließlich Text, Bildern und anderen grafischen Elementen.  

### Ist Aspose.Page für die Verarbeitung großer Dokumente geeignet?
Ja, Aspose.Page ist darauf ausgelegt, sowohl kleine als auch große Dokumente effizient zu handhaben.  

### Wo finde ich zusätzliche Ressourcen und Unterstützung für Aspose.Page?
Entdecken Sie die [Aspose.Page‑Dokumentation](https://reference.aspose.com/page/java/) oder besuchen Sie das [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39) für Community‑Support.  

**Zusätzliche Fragen & Antworten**

**F:** *Welche Bildformate werden unterstützt, wenn man auf einer PostScript‑Seite zeichnet?*  
**A:** Sie können PNG-, JPEG-, BMP‑ und GIF‑Bilder direkt über die Zeichen‑API einbetten.  

**F:** *Wie ändere ich die Standard‑DPI für das Dokument?*  
**A:** Setzen Sie `PsSaveOptions.setResolution(int dpi)` bevor Sie das `PsDocument` erstellen.  

**F:** *Kann ich eine PostScript‑Datei mit einem Passwort verschlüsseln?*  
**A:** PostScript selbst unterstützt keine Verschlüsselung, aber Sie können die Ausgabe in ein PDF einbetten und bei Bedarf Sicherheitseinstellungen anwenden.  

---

**Zuletzt aktualisiert:** 2026-10-25  
**Getestet mit:** Aspose.Page für Java 24.10  
**Autor:** Aspose  

## Verwandte Tutorials

- [Wie man die A4‑Seitengröße festlegt und PostScript in Java mit Aspose.Page erstellt](/page/java/document-creation/postscript/)
- [Wie man PostScript mit der Aspose.Page Java API in PDF konvertiert](/page/java/postscript-conversion/to-pdf/)
- [Wie man ein Rechteck in Java‑PostScript mit Aspose.Page zeichnet](/page/java/postscript-shapes/add-rectangle/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}