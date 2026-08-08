---
date: 2026-06-20
description: Erfahren Sie, wie Sie die A4-Seitengröße festlegen, PostScript-Dateien
  in Java erstellen und benutzerdefinierte Schriftarten mit Aspose.Page hinzufügen.
  Testen Sie die kostenlose Testversion noch heute!
keywords:
- set a4 page size
- add custom fonts java
- java create postscript
linktitle: Dokument in Java mit PostScript erstellen
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to set A4 page size and create PostScript in Java with Aspose.Page
  type: TechArticle
- description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to set A4 page size and create PostScript in Java with Aspose.Page
  steps:
  - name: Set Document Directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define Fonts Folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create Output Stream for PostScript Document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create Save Options with A4 Size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set Page Margins and Add Custom Fonts Folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a Multipaged or Single‑Paged PS Document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close Current Page and Save Document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [here](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [here](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page forum [forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
title: Wie man die A4-Seitengröße festlegt und PostScript in Java mit Aspose.Page
  erstellt
url: /de/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man die A4-Seitengröße festlegt und PostScript in Java mit Aspose.Page erstellt

## Einleitung
Wenn Sie **set a4 page size** festlegen müssen, während Sie PostScript‑Dateien aus Java generieren, bietet Aspose.Page eine schnelle, zuverlässige API, die die Low‑Level‑Details verbirgt. In diesem Tutorial führen wir Sie durch den gesamten Arbeitsablauf – das Erstellen eines PostScript‑Dokuments, das Konfigurieren der A4‑Seitenabmessungen und **adding custom fonts**, falls erforderlich. Am Ende haben Sie ein einsatzbereites Code‑Snippet, das Sie in jedes Java‑Projekt einbinden können.

## Schnelle Antworten
- **Welche Bibliothek erstellt PostScript in Java?** Aspose.Page for Java.  
- **Welche Seitengröße behandelt diese Anleitung?** A4 (210 mm × 297 mm).  
- **Kann ich meine eigenen Schriften einbetten?** Yes – set the additional fonts folder in the save options.  
- **Benötige ich eine Lizenz für den produktiven Einsatz?** A commercial license is required; a free trial is available.  
- **Welche Java‑Versionen werden unterstützt?** Java 8 and later.

## Wie man a4 page size festlegt und postscript in Java erstellt
Laden Sie die Aspose.Page‑Bibliothek, konfigurieren Sie `PsSaveOptions` mit den A4‑Konstanten und schreiben Sie das Dokument in eine Datei – alles in weniger als zehn Codezeilen. Dieser direkte Ansatz garantiert die korrekten Seitenabmessungen und ermöglicht das Hinzufügen benutzerdefinierter Schriften ohne zusätzliche Konfiguration.

## Was ist postscript a4 size?
PostScript A4 size ist der ISO‑216‑Standard (210 mm × 297 mm), ausgedrückt in der PostScript‑Seitenbeschreibungssprache. Er definiert den druckbaren Bereich, den Drucker und Viewer interpretieren, und sorgt für ein konsistentes Layout über Plattformen hinweg. Da PostScript den Seiteninhalt geräteunabhängig beschreibt, garantiert die Verwendung der A4‑Größe, dass das Dokument auf jedem A4‑fähigen Drucker oder Viewer weltweit gleich aussieht.

## Warum Aspose.Page verwenden, um postscript page size festzulegen?
Aspose.Page unterstützt **30+ PostScript‑Operatoren** und kann Dateien bis zu **500 MB** erzeugen, ohne das gesamte Dokument in den Speicher zu laden. Das gibt Ihnen präzise Kontrolle über die Seitenabmessungen und ermöglicht gleichzeitig eine effiziente Verarbeitung großer Arbeitslasten. Die Bibliothek abstrahiert zudem komplexe PostScript‑Syntax, verwaltet Ressourcen automatisch und bietet hochperformantes Streaming, was sie sowohl für einfache einseitige Flyer als auch für komplexe mehrseitige Berichte ideal macht.

## Wie man benutzerdefinierte Schriften in Java hinzufügt
Das Einbetten eigener Schriftarten stellt sicher, dass das erzeugte Dokument auf jedem Drucker oder Viewer exakt wie entworfen aussieht, und Aspose.Page erkennt automatisch Schriften, die im angegebenen Ordner abgelegt wurden. Durch die Registrierung eines zusätzlichen Schriftordners können Sie jede TrueType‑ oder OpenType‑Schrift verwenden, Fallback‑Ersetzungen vermeiden und die Marken‑konsistenz über alle Ausgabegeräte hinweg wahren.

## Voraussetzungen
- Ein grundlegendes Wissen in Java‑Programmierung.  
- Aspose.Page für Java installiert. Sie können es [hier](https://releases.aspose.com/page/java/) herunterladen.  
- Ein Ordner namens `necessary_fonts` (oder ein beliebiger anderer Name), der alle benutzerdefinierten Schriften enthält, die Sie einbetten möchten.

## Pakete importieren
Importieren Sie in Ihrem Java‑Projekt die erforderlichen Aspose.Page‑Klassen:

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Jetzt teilen wir das Beispiel in klare, nummerierte Schritte auf.

### Schritt 1: Dokumentverzeichnis festlegen
Die Konstante `OUTPUT_DIR` gibt der Bibliothek an, wohin die erzeugte Datei geschrieben werden soll.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Schritt 2: Schriftordner definieren
`FONTS_FOLDER` verweist auf das Verzeichnis, das Ihre benutzerdefinierten TrueType‑ oder OpenType‑Schriften enthält.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Schritt 3: Ausgabestream für PostScript‑Dokument erstellen
`FileOutputStream` öffnet einen Stream, der die endgültige PostScript‑A4‑Ausgabe empfängt.

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### Schritt 4: Save‑Optionen mit A4‑Größe erstellen
`PsSaveOptions` ermöglicht das Festlegen der Zielseitengröße.  
**Definition:** `PsPageSize` ist eine Aufzählung, die Standard‑Seiten‑größen‑Konstanten wie A4, Letter und Legal enthält.  
Durch `options.setPageSize(PsPageSize.A4)` wird das Dokument auf die Standard‑A4‑Abmessungen konfiguriert.

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### Schritt 5: Seitenränder festlegen und benutzerdefinierten Schriftordner hinzufügen
`options.setMargins(0, 0, 0, 0)` entfernt alle Ränder für eine randlose Seite, und `options.setAdditionalFontsFolder(FONTS_FOLDER)` registriert Ihre benutzerdefinierten Schriften.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### Schritt 6: Mehrseitiges oder einseitiges PS‑Dokument erstellen
`PsDocument document = new PsDocument(outputStream, options)` erstellt das Dokument. `PsDocument` repräsentiert ein PostScript‑Dokument, das eine oder mehrere Seiten enthalten kann. Setzen Sie `multiPaged` auf `true` für mehrseitige Ausgabe.

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### Schritt 7: Aktuelle Seite schließen und Dokument speichern
Durch Aufruf von `document.close()` wird die Datei finalisiert und die **PostScript A4 size**‑Ausgabe auf die Festplatte geschrieben.

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Häufige Probleme & Tipps
- **Schrift wird nicht angezeigt?** Stellen Sie sicher, dass die Schriftdatei ein unterstütztes TrueType‑ oder OpenType‑Format ist und dass `FONTS_FOLDER` mit einem Schrägstrich (`/`) endet.  
- **Ränder werden immer noch angezeigt?** Rufen Sie `options.setMargins(...)` **vor** dem Erzeugen des `PsDocument` auf.  
- **Mehrseitige Ausgabe erscheint leer?** Denken Sie daran, `document.newPage()` für jede zusätzliche Seite, die Sie benötigen, aufzurufen.

## Häufig gestellte Fragen

**Q: Kann ich benutzerdefinierte Schriften in meinem PostScript‑Dokument verwenden?**  
A: Ja, setzen Sie den zusätzlichen Schriftordner in den Save‑Optionen (siehe Schritt 5) und Aspose.Page bettet die Schriften automatisch ein.

**Q: Gibt es eine Testversion für Aspose.Page für Java?**  
A: Ja, Sie können eine kostenlose Testversion [hier](https://releases.aspose.com/) erhalten.

**Q: Wie kann ich auf die vollständige API‑Referenz zugreifen?**  
A: Siehe die Dokumentation [hier](https://reference.aspose.com/page/java/).

**Q: Wo kann ich eine Lizenz für Aspose.Page für Java erwerben?**  
A: Sie können eine Lizenz [hier](https://purchase.aspose.com/buy) kaufen.

**Q: Wo kann ich die Community um Hilfe bitten?**  
A: Besuchen Sie das Aspose.Page‑Forum [forum](https://forum.aspose.com/c/page/39).

**Q: Kann ich mehrseitige PostScript‑Dateien erzeugen?**  
A: Natürlich – setzen Sie `multiPaged` in Schritt 6 auf `true` und rufen Sie `document.newPage()` für jede zusätzliche Seite auf.

## Fazit
Durch das Befolgen dieser Schritte wissen Sie jetzt **how to set a4 page size** und können **PostScript**‑Dateien in Java mit Aspose.Page erstellen, gleichzeitig **add custom fonts java** nutzen und die Seitengrößen‑Optionen steuern. Aspose.Page übernimmt die schwere Arbeit, sodass Sie sich auf den Inhalt Ihrer Dokumente konzentrieren können.

---

**Zuletzt aktualisiert:** 2026-06-20  
**Getestet mit:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Aspose.Page Java Tutorial – benutzerdefinierte Seitengröße festlegen beim Hinzufügen von Seiten in PostScript](/page/java/postscript-page-manipulation/add-pages2/)
- [Wie man Text in PostScript mit Aspose.Page für Java hinzufügt](/page/java/postscript-text-manipulation/)
- [Aspose Page Java Tutorial – PostScript nach PDF konvertieren](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
document.closePage();
document.save();
```