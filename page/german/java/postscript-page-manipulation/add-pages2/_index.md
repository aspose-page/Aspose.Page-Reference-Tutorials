---
date: 2025-12-11
description: Erfahren Sie, wie Sie benutzerdefinierte Seitengrößen festlegen und Seiten
  zu Java‑PostScript‑Dokumenten mit Aspose.Page hinzufügen. Folgen Sie unserer Schritt‑für‑Schritt‑Anleitung
  für eine nahtlose Dokumentenbearbeitung.
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: Aspose.Page Java Tutorial – benutzerdefinierte Seitengröße festlegen beim Hinzufügen
  von Seiten in PostScript
url: /de/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java Tutorial – benutzerdefinierte Seitengröße festlegen beim Hinzufügen von Seiten in PostScript

## Introduction
In modernen Java‑Anwendungen ist das **Festlegen einer benutzerdefinierten Seitengröße** für PostScript‑Ausgaben häufig erforderlich – sei es beim Erzeugen von Rechnungen, Tickets oder benutzerdefinierten Grafiken. Aspose.Page für Java macht diese Aufgabe unkompliziert. In diesem Tutorial lernen Sie, wie man Seiten hinzufügt und benutzerdefinierte Seitengrößen in einem PostScript‑Dokument festlegt, Schritt für Schritt, sodass Sie jedes Mal das exakt richtige Layout erzeugen können.

## Quick Answers
- **Kann ich für jede Seite unterschiedliche Seitengrößen festlegen?** Ja, Sie können Seiten mit benutzerdefinierten Abmessungen öffnen, indem Sie `document.openPage(width, height)` verwenden.  
- **Benötige ich eine Lizenz für den Produktionseinsatz?** Eine gültige Aspose.Page‑Lizenz ist für den Einsatz außerhalb der Evaluierung erforderlich.  
- **Welche Java‑Versionen werden unterstützt?** Die Bibliothek funktioniert mit Java 8 und neuer.  
- **Ist die API thread‑sicher?** Dokumentinstanzen sind nicht thread‑sicher; erstellen Sie pro Thread ein separates `PsDocument`.  
- **Wie groß kann eine PostScript‑Datei sein?** Aspose.Page verarbeitet Multi‑Megabyte‑Dateien effizient; der Speicherverbrauch skaliert mit dem Inhalt, nicht mit der Seitenzahl.

## Prerequisites
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Grundkenntnisse in der Java‑Programmierung.  
- Aspose.Page für Java zu Ihrem Projekt hinzugefügt (Maven/Gradle oder manuelles JAR).  
- Eine Java‑Entwicklungsumgebung (IDE, JDK 8+).  

## Import Packages
Um zu beginnen, importieren Sie die erforderlichen Klassen aus der Aspose.Page‑Bibliothek.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Create a Multipaged PostScript Document
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

## Step 2: Add Content to the First Page
Wenn das Dokument bereit ist, können Sie beliebige Inhalte zur ersten Seite hinzufügen. Sobald Sie fertig sind, schließen Sie die Seite, um deren Inhalt zu sperren.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## How to set custom page size
Wenn die Standard‑Seitengröße nicht Ihren Anforderungen entspricht, können Sie beim Öffnen einer neuen Seite **eine benutzerdefinierte Seitengröße festlegen**. Das ist nützlich für Quittungen, Etiketten oder jedes nicht‑standardmäßige Layout.

## Step 3: Add a Second Page with Different Size
Im Folgenden öffnen wir eine zweite Seite und geben explizit eine benutzerdefinierte Breite und Höhe (in Punkten) an. Dies demonstriert, wie man für einzelne Seiten eine benutzerdefinierte Seitengröße festlegt.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Step 4: Save the Document
Abschließend speichern Sie das Dokument, um die Änderungen zu übernehmen. Alle Seiten – einschließlich derjenigen mit benutzerdefinierten Größen – werden in die Ausgabedatei geschrieben.

```java
// Save the document
document.save();
```

Durch das Befolgen dieser Schritte können Sie nahtlos Seiten hinzufügen und **benutzerdefinierte Seitengrößen** in einem Java‑PostScript‑Dokument mit Aspose.Page festlegen, wodurch Sie die volle Kontrolle über das Layout jeder Seite erhalten.

## Conclusion
Aspose.Page für Java bietet eine robuste, entwicklerfreundliche API zur Verarbeitung von PostScript‑Dokumenten. Sie wissen jetzt, wie Sie mehrere Seiten hinzufügen, benutzerdefinierte Abmessungen anwenden und das Ergebnis speichern – sodass Sie für jede Java‑basierte Lösung präzise formatierte Ausgaben erzeugen können.

## Frequently Asked Questions
### Can I add pages of different sizes in a single PostScript document?
Ja, wie in diesem Tutorial gezeigt, können Sie in einem mehrseitigen PostScript‑Dokument Seiten mit unterschiedlichen Größen hinzufügen.  
### Are there any limitations on the number of pages I can add?
Aspose.Page unterstützt das Hinzufügen einer praktisch unbegrenzten Anzahl von Seiten zu einem Dokument.  
### Can I add custom content, such as images or graphics, to the pages?
Absolut! Aspose.Page ermöglicht das Hinzufügen einer breiten Palette von Inhalten, einschließlich Text, Bildern und anderen grafischen Elementen.  
### Is Aspose.Page suitable for handling large documents?
Ja, Aspose.Page ist darauf ausgelegt, sowohl kleine als auch große Dokumente effizient zu verarbeiten.  
### Where can I find additional resources and support for Aspose.Page?
Entdecken Sie die [Aspose.Page documentation](https://reference.aspose.com/page/java/), oder besuchen Sie das [Aspose.Page forum](https://forum.aspose.com/c/page/39) für Community‑Support.  

**Additional Q&A**

**Q:** *Welche Bildformate werden beim Zeichnen auf einer PostScript‑Seite unterstützt?*  
**A:** Sie können PNG-, JPEG-, BMP- und GIF‑Bilder direkt über die Zeichen‑API einbetten.  

**Q:** *Wie ändere ich die Standard‑DPI für das Dokument?*  
**A:** Setzen Sie `PsSaveOptions.setResolution(int dpi)` bevor Sie das `PsDocument` erstellen.  

**Q:** *Kann ich eine PostScript‑Datei mit einem Passwort verschlüsseln?*  
**A:** PostScript selbst unterstützt keine Verschlüsselung, aber Sie können die Ausgabe in ein PDF einbetten und bei Bedarf Sicherheitseinstellungen anwenden.

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.Page for Java 24.10  
**Author:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
