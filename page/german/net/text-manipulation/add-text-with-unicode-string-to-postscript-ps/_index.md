---
title: Fügen Sie mit Aspose.Page Text mit Unicode-Zeichenfolge zu PostScript (PS) hinzu
linktitle: Text mit Unicode-String zu PostScript (PS) hinzufügen
second_title: Aspose.Page .NET-API
description: Erfahren Sie, wie Sie mit Aspose.Page für .NET Unicode-Text zu PostScript-Dateien hinzufügen. Verbessern Sie die Dokumentenbearbeitung ganz einfach.
weight: 11
url: /de/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fügen Sie mit Aspose.Page Text mit Unicode-Zeichenfolge zu PostScript (PS) hinzu

## Einführung

Im Bereich der Dokumentbearbeitung sticht Aspose.Page für .NET als robuste Bibliothek hervor, die Entwicklern das Erstellen, Bearbeiten und Konvertieren verschiedener Dokumentformate ermöglicht. Eine seiner leistungsstarken Funktionen ist die Möglichkeit, Text mithilfe von Unicode-Zeichenfolgen zu PostScript-Dateien (PS) hinzuzufügen. In diesem Tutorial erkunden wir eine Schritt-für-Schritt-Anleitung zur Bewältigung dieser Aufgabe und bieten Entwicklern, die mit Aspose.Page arbeiten, ein nahtloses Erlebnis.

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Grundkenntnisse der Programmiersprache C#.
-  Aspose.Page für .NET-Bibliothek installiert. Sie können es hier herunterladen[Aspose.Page für .NET-Dokumentation](https://reference.aspose.com/page/net/).
- Eine mit den erforderlichen Konfigurationen eingerichtete Entwicklungsumgebung.

## Namespaces importieren

Importieren Sie in Ihrem C#-Code die erforderlichen Namespaces für die Verwendung von Aspose.Page für .NET-Funktionen:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Schritt 1: Dokumentverzeichnis und Schriftartenordner einrichten

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## Schritt 2: Ausgabestream für PostScript-Dokument erstellen

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    // Erstellen Sie Speicheroptionen im A4-Format
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    // ... (Weitere Optionen können hier eingestellt werden)
    
    // Erstellen Sie ein neues einseitiges PS-Dokument
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (Weitere Schritte werden weiter unten erläutert)
    
    // Speichern Sie das Dokument
    document.Save();
}
```

## Schritt 3: Unicode-Text mit benutzerdefinierter Schriftart hinzufügen

```csharp
string str = "試してみます.";  // Unicode-Text
int fontSize = 48;

// Verwenden einer benutzerdefinierten Schriftart zum Füllen von Text
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## Schritt 4: Schließen Sie die aktuelle Seite

```csharp
document.ClosePage();
```

## Schritt 5: Finalisieren und speichern Sie das Dokument

```csharp
document.Save();
```

## Abschluss

In diesem Tutorial haben wir den Prozess des Hinzufügens von Unicode-Text zu einem PostScript-Dokument mithilfe von Aspose.Page für .NET durchlaufen. Durch die Nutzung seiner leistungsstarken Funktionen können Entwickler ihre Arbeitsabläufe zur Dokumentbearbeitung verbessern und so Flexibilität und Präzision gewährleisten.

## FAQs

### F1: Kann ich Aspose.Page für .NET mit anderen Programmiersprachen verwenden?

A1: Aspose.Page ist hauptsächlich für .NET konzipiert, es sind jedoch auch andere Versionen für Java verfügbar.

### F2: Wie erhalte ich eine temporäre Lizenz für Aspose.Page für .NET?

 A2: Besuchen[Temporäre Lizenz](https://purchase.aspose.com/temporary-license/) für den Erhalt einer vorläufigen Lizenz.

### F3: Gibt es ein Community-Forum für Aspose.Page-Diskussionen?

 A3: Ja, besuchen Sie die[Aspose.Page-Forum](https://forum.aspose.com/c/page/39) für die Unterstützung der Gemeinschaft.

### F4: Mit welchen Formaten kann Aspose.Page für .NET arbeiten?

A4: Aspose.Page unterstützt verschiedene Formate, darunter XPS, PS, EPS, PDF und mehr.

### F5: Kann ich das Erscheinungsbild des hinzugefügten Textes anpassen?

A5: Ja, Sie können Schriftart, Größe, Farbe und andere Eigenschaften des Texts in Aspose.Page anpassen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
