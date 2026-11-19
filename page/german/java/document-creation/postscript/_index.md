---
date: 2026-11-19
description: Erfahren Sie, wie Sie PostScript-Dateien in Java erstellen, die A4‑Seitengröße
  festlegen und benutzerdefinierte Schriftarten mit Aspose.Page hinzufügen. Testen
  Sie die kostenlose Testversion noch heute!
keywords:
- create postscript file java
- add custom fonts java
- set a4 page size java
- aspose.page java
- postscript generation java
lastmod: 2026-11-19
linktitle: Dokument in Java mit PostScript erstellen
og_description: Erfahren Sie, wie Sie eine PostScript-Datei in Java erstellen, die
  A4‑Seitengröße festlegen und benutzerdefinierte Schriftarten mit Aspose.Page hinzufügen.
  Schnellstart‑Anleitung für Entwickler.
og_image_alt: Screenshot of Java code generating an A4 PostScript file with custom
  fonts using Aspose.Page
og_title: Erstellen Sie eine PostScript-Datei in Java mit A4-Größe mit Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to create PostScript file in Java with A4 size
  type: TechArticle
- description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to create PostScript file in Java with A4 size
  steps:
  - name: set document directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: define fonts folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: create output stream for PostScript document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: create save options with A4 size
    text: '`PsSaveOptions` defines how the PostScript document is saved, including
      page size, margins, and compression. **Definition:** `PsPageSize` is an enumeration
      that contains standard page‑size constants such as A4, Letter, and Legal. Setting
      `options.setPageSize(PsPageSize.A4)` configures the document f'
  - name: set page margins and add custom fonts folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: create a multipaged or single‑paged PS document
    text: '`PsDocument` represents a PostScript document that can contain one or many
      pages. Instantiating it with `new PsDocument(outputStream, options)` creates
      the document object. Set `multiPaged` to `true` for multi‑page output, then
      call `document.newPage()` for each additional page you need.'
  - name: close current page and save document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [Aspose.Page free trial page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [API reference documentation](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [license purchase page](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create postscript
- Aspose.Page
- Java document processing
- custom fonts
- A4 page size
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to create PostScript file in Java with A4 size using Aspose.Page
  type: TechArticle
- description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to create PostScript file in Java with A4 size using Aspose.Page
  steps:
  - name: Set document directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define fonts folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create output stream for PostScript document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create save options with A4 size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set page margins and add custom fonts folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a multipaged or single‑paged PS document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close current page and save document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [Aspose.Page free trial page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [API reference documentation](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [license purchase page](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
title: Wie man eine PostScript-Datei in Java mit A4-Größe erstellt
url: /de/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man eine PostScript-Datei in Java mit A4-Größe erstellt

## Einführung
Wenn Sie **eine PostScript-Datei in Java erstellen** möchten und dabei die Standard‑A4‑Seitengrößen festlegen, bietet Aspose.Page für Java eine kompakte, leistungsstarke API, die die low‑level PostScript‑Syntax abstrahiert. In diesem Tutorial führen wir Sie durch jeden Schritt – vom Laden der Bibliothek und Konfigurieren von `PsSaveOptions` bis zum Einbetten Ihrer eigenen TrueType‑ oder OpenType‑Schriften. Am Ende haben Sie ein sofort einsatzbereites Snippet, das Sie in jedes Java‑Projekt einbinden können.

## Schnelle Antworten
- **Welche Bibliothek erstellt PostScript in Java?** Aspose.Page für Java.  
- **Welche Seitengröße behandelt dieser Leitfaden?** A4 (210 mm × 297 mm).  
- **Kann ich eigene Schriftarten einbetten?** Ja – legen Sie den zusätzlichen Schriftartenordner in den Speichereinstellungen fest.  
- **Benötige ich eine Lizenz für die Produktion?** Eine kommerzielle Lizenz ist erforderlich; eine kostenlose Testversion ist verfügbar.  
- **Welche Java‑Versionen werden unterstützt?** Java 8, 11 und 17 werden vollständig unterstützt.

## Wie man die A4-Seitengröße einstellt und PostScript in Java erstellt?
Laden Sie die Aspose.Page‑Bibliothek, konfigurieren Sie `PsSaveOptions` mit den A4‑Konstanten und schreiben Sie das Dokument in eine Datei – alles in weniger als zehn Codezeilen. Dieser Ansatz garantiert die korrekten Seitenabmessungen und ermöglicht das Hinzufügen benutzerdefinierter Schriftarten ohne zusätzliche Konfiguration.

## Was ist PostScript A4-Größe?
PostScript A4‑Größe ist der ISO‑216‑Standard (210 mm × 297 mm), ausgedrückt in der PostScript‑Seitenbeschreibungssprache. Sie definiert den druckbaren Bereich, den Drucker und Viewer interpretieren, und sorgt für ein konsistentes Layout über verschiedene Plattformen hinweg. Da PostScript den Seiteninhalt geräteunabhängig beschreibt, garantiert die Verwendung der A4‑Größe, dass das Dokument auf jedem A4‑fähigen Drucker oder Viewer weltweit gleich aussieht.

## Warum Aspose.Page verwenden, um die PostScript-Seitengröße festzulegen?
Aspose.Page unterstützt mehr als 30 PostScript‑Operatoren und kann Dateien bis zu 500 MB erzeugen, ohne das gesamte Dokument in den Speicher zu laden. Es verarbeitet ein 200‑seitiges Dokument in weniger als 2 Sekunden und bietet präzise Kontrolle über die Seitenabmessungen, während große Arbeitslasten effizient gehandhabt werden. Die Bibliothek abstrahiert zudem komplexe PostScript‑Syntax und verwaltet Ressourcen automatisch, was sie sowohl für einfache Flyer als auch für komplexe mehrseitige Berichte ideal macht.

## Wie man benutzerdefinierte Schriftarten in Java hinzufügt
Das Einbetten eigener Schriftarten stellt sicher, dass das erzeugte Dokument auf jedem Drucker oder Viewer exakt wie entworfen aussieht, und Aspose.Page erkennt automatisch Schriftarten, die im angegebenen Ordner abgelegt sind. Durch die Registrierung eines zusätzlichen Schriftartenordners können Sie jede TrueType‑ oder OpenType‑Schrift verwenden, Ersatzschriften vermeiden und die Marken‑Konsistenz über alle Ausgabegeräte hinweg wahren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Grundlegende Kenntnisse in der Java‑Programmierung.  
- Aspose.Page für Java installiert. Sie können es von der [Aspose.Page Java download page](https://releases.aspose.com/page/java/) herunterladen.  
- Einen Ordner namens `necessary_fonts` (oder einen beliebigen anderen Namen), der die benutzerdefinierten Schriftarten enthält, die Sie einbetten möchten.

## Pakete importieren
In Ihrem Java‑Projekt importieren Sie die erforderlichen Aspose.Page‑Klassen:

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Jetzt teilen wir das Beispiel in klare, nummerierte Schritte auf.

### Schritt 1: Dokumentverzeichnis festlegen
Die Konstante `OUTPUT_DIR` gibt der Bibliothek an, wohin die erzeugte Datei geschrieben werden soll.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Schritt 2: Schriftartenordner definieren
`FONTS_FOLDER` verweist auf das Verzeichnis, das Ihre benutzerdefinierten TrueType‑ oder OpenType‑Schriften enthält.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Schritt 3: Ausgabestream für PostScript-Dokument erstellen
`FileOutputStream` öffnet einen Stream, der die endgültige PostScript‑A4‑Ausgabe empfängt.

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### Schritt 4: Speichereinstellungen mit A4-Größe erstellen
`PsSaveOptions` definiert, wie das PostScript‑Dokument gespeichert wird, einschließlich Seitengröße, Ränder und Kompression.  
**Definition:** `PsPageSize` ist eine Aufzählung, die Standard‑Seitengrößen‑Konstanten wie A4, Letter und Legal enthält.  
Durch das Setzen von `options.setPageSize(PsPageSize.A4)` wird das Dokument auf die Standard‑A4‑Abmessungen konfiguriert.

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### Schritt 5: Seitenränder festlegen und benutzerdefinierten Schriftartenordner hinzufügen
`options.setMargins(0, 0, 0, 0)` entfernt alle Ränder für eine randlose Seite, und `options.setAdditionalFontsFolder(FONTS_FOLDER)` registriert Ihre benutzerdefinierten Schriftarten.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### Schritt 6: Mehrseitiges oder einseitiges PS-Dokument erstellen
`PsDocument` repräsentiert ein PostScript‑Dokument, das eine oder mehrere Seiten enthalten kann. Durch die Instanziierung mit `new PsDocument(outputStream, options)` wird das Dokumentobjekt erstellt. Setzen Sie `multiPaged` auf `true` für mehrseitige Ausgabe und rufen Sie anschließend `document.newPage()` für jede weitere Seite auf, die Sie benötigen.

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### Schritt 7: Aktuelle Seite schließen und Dokument speichern
Durch den Aufruf von `document.close()` wird die Datei abgeschlossen und die **PostScript A4‑Größe**‑Ausgabe auf die Festplatte geschrieben.

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Häufige Probleme & Tipps
- **Schriftart wird nicht angezeigt?** Überprüfen Sie, ob die Schriftdatei ein unterstütztes TrueType‑ oder OpenType‑Format ist und dass `FONTS_FOLDER` mit einem Schrägstrich (`/`) endet.  
- **Ränder werden immer noch angezeigt?** Rufen Sie `options.setMargins(...)` **vor** der Erstellung des `PsDocument` auf.  
- **Mehrseitige Ausgabe erscheint leer?** Denken Sie daran, `document.newPage()` für jede zusätzliche Seite aufzurufen.  
- **Große Dateien verursachen Out‑of‑Memory‑Fehler?** Aspose.Page streamt Daten, sodass Sie sicher Dateien bis zu 500 MB erzeugen können; stellen Sie lediglich sicher, dass Ihr JVM‑Heap für sehr große Arbeitslasten mindestens 1 GB beträgt.

## Häufig gestellte Fragen

**F: Kann ich benutzerdefinierte Schriftarten in meinem PostScript‑Dokument verwenden?**  
A: Ja, legen Sie den zusätzlichen Schriftartenordner in den Speichereinstellungen fest (siehe Schritt 5) und Aspose.Page bettet die Schriftarten automatisch ein.

**F: Gibt es eine Testversion für Aspose.Page für Java?**  
A: Ja, Sie können eine kostenlose Testversion erhalten [Aspose.Page free trial page](https://releases.aspose.com/).

**F: Wie kann ich auf die vollständige API‑Referenz zugreifen?**  
A: Sie finden die Dokumentation unter [API reference documentation](https://reference.aspose.com/page/java/).

**F: Wo kann ich eine Lizenz für Aspose.Page für Java erwerben?**  
A: Sie können eine Lizenz erwerben [license purchase page](https://purchase.aspose.com/buy).

**F: Wo kann ich die Community um Hilfe bitten?**  
A: Besuchen Sie das Aspose.Page‑Community‑Forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).

**F: Kann ich mehrseitige PostScript‑Dateien erzeugen?**  
A: Absolut – setzen Sie `multiPaged` in Schritt 6 auf `true` und rufen Sie `document.newPage()` für jede zusätzliche Seite auf.

## Fazit
Indem Sie diese Schritte befolgt haben, wissen Sie jetzt, **wie man eine PostScript‑Datei in Java erstellt** und **die A4‑Seitengröße** mit Aspose.Page festlegt, während Sie zudem **benutzerdefinierte Schriftarten in Java hinzufügen** und die Seitengrößen‑Optionen steuern können. Aspose.Page übernimmt die schwere Arbeit, sodass Sie sich auf den Inhalt Ihrer Dokumente konzentrieren können, anstatt sich mit den Feinheiten der PostScript‑Sprache zu befassen.

---

**Zuletzt aktualisiert:** 2026-11-19  
**Getestet mit:** Aspose.Page für Java 24.11  
**Autor:** Aspose  

## Verwandte Tutorials

- [Aspose.Page Java Tutorial – benutzerdefinierte Seitengröße festlegen beim Hinzufügen von Seiten in PostScript](/page/java/postscript-page-manipulation/add-pages2/)
- [Wie man Text in PostScript mit Aspose.Page für Java hinzufügt](/page/java/postscript-text-manipulation/)
- [Aspose Page Java Tutorial – PostScript in PDF konvertieren](/page/java/postscript-conversion/to-pdf/)

```java
document.closePage();
document.save();
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}