---
date: 2026-03-21
description: Lernen Sie, wie Sie mit C# ein PostScript‑Dokument mit Unicode‑Text unter
  Verwendung von Aspose.Page für .NET erstellen – ein schneller Weg, die Dokumentenbearbeitung
  zu verbessern.
linktitle: Add Text with Unicode String to PostScript (PS)
second_title: Aspose.Page .NET API
title: PostScript-Dokument in C# mit Unicode-Text erstellen – Aspose.Page
url: /de/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Text mit Unicode‑Zeichenfolge zu PostScript (PS) mit Aspose.Page hinzufügen

## Einführung

Wenn Sie **ein PostScript‑Dokument C#** erstellen und Unicode‑Zeichen einbetten müssen, macht Aspose.Page für .NET den Prozess unkompliziert. In diesem Tutorial führen wir Sie durch ein vollständiges, praxisnahes Beispiel, das zeigt, wie Sie japanischen Text (oder jede Unicode‑Zeichenfolge) zu einer PS‑Datei hinzufügen, eine benutzerdefinierte Schriftart auswählen und das Ergebnis speichern. Am Ende haben Sie einen wiederverwendbaren Code‑Snippet, den Sie in jedes C#‑Projekt einbinden können.

## Schnelle Antworten
- **Worum geht es in diesem Tutorial?** Unicode‑Text zu einer PostScript‑Datei mit Aspose.Page in C# hinzufügen.
- **Welche Bibliothek wird benötigt?** Aspose.Page für .NET (neueste Version).
- **Benötige ich eine spezielle Schriftart?** Jede TrueType/OpenType‑Schrift, die den gewünschten Unicode‑Bereich unterstützt, z. B. *Arial Unicode MS*.
- **Wie viele Codezeilen?** Etwa 30 Zeilen, aufgeteilt in klare Schritte.
- **Ist eine Lizenz erforderlich?** Eine temporäre Lizenz reicht für die Evaluierung; für die Produktion ist eine Voll‑Lizenz nötig.

## Was bedeutet „create postscript document c#“?
Ein PostScript‑Dokument in C# zu erstellen bedeutet, programmgesteuert eine .ps‑Datei zu erzeugen, die den Spezifikationen der PostScript‑Sprache entspricht. Aspose.Page abstrahiert die Low‑Level‑Details, sodass Sie sich auf Inhalte wie Text, Grafiken und Schriftarten konzentrieren können.

## Warum Aspose.Page für Unicode‑Text verwenden?
- **Vollständige Unicode‑Unterstützung** – Zeichen aus jeder Sprache rendern, ohne manuelle Kodierung.
- **Geräteunabhängig** – derselbe Code funktioniert für PS-, EPS- und PDF‑Ausgaben.
- **Keine externen Abhängigkeiten** – die Bibliothek übernimmt das Laden von Schriftarten und die Glyphen‑Zuordnung intern.

## Voraussetzungen

- Grundlegende Kenntnisse in C# und .NET‑Entwicklung.
- Aspose.Page für .NET Bibliothek installiert. Sie können sie von der [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/) herunterladen.
- Ein Ordner, der die Schriftarten enthält, die Sie verwenden möchten (z. B. *Arial Unicode MS*).

## Namespaces importieren

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Schritt 1: Dokumentverzeichnis und Schriftarten‑Ordner einrichten

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## Schritt 2: Ausgabestream für das PostScript‑Dokument erstellen

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    // ... (Additional options can be set here)
    
    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (Further steps will be explained below)
    
    // Save the document
    document.Save();
}
```

## Schritt 3: Unicode‑Text mit benutzerdefinierter Schriftart hinzufügen

```csharp
string str = "試してみます.";  // Unicode text
int fontSize = 48;

// Using custom font for filling text
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## Schritt 4: Aktuelle Seite schließen

```csharp
document.ClosePage();
```

## Schritt 5: Dokument finalisieren und speichern

```csharp
document.Save();
```

## Häufige Probleme und Lösungen

- **Schriftart nicht gefunden** – Stellen Sie sicher, dass der Pfad `AdditionalFontsFolders` auf den Ordner mit den .ttf/.otf‑Dateien zeigt und dass der Schriftartname exakt übereinstimmt.
- **Fehlerhafte Zeichen** – Überprüfen Sie, dass die Quellzeichenfolge in Ihrer C#‑Quelldatei als UTF‑8 kodiert ist (verwenden Sie bei Bedarf `#pragma warning disable 1591`).
- **Datei wurde nicht erstellt** – Prüfen Sie Schreibrechte für `dataDir` und dass der Stream korrekt freigegeben wird (der `using`‑Block übernimmt dies).

## Häufig gestellte Fragen

**F: Kann ich Aspose.Page für .NET mit anderen Programmiersprachen verwenden?**  
A: Aspose.Page ist hauptsächlich für .NET konzipiert, es gibt jedoch Java‑Entsprechungen.

**F: Wie erhalte ich eine temporäre Lizenz für Aspose.Page für .NET?**  
A: Besuchen Sie [Temporary License](https://purchase.aspose.com/temporary-license/) um eine temporäre Lizenz zu erhalten.

**F: Gibt es ein Community‑Forum für Aspose.Page‑Diskussionen?**  
A: Ja, besuchen Sie das [Aspose.Page forum](https://forum.aspose.com/c/page/39) für Community‑Support.

**F: Welche Formate unterstützt Aspose.Page für .NET?**  
A: Aspose.Page unterstützt verschiedene Formate, darunter XPS, PS, EPS, PDF und weitere.

**F: Kann ich das Aussehen des hinzugefügten Textes anpassen?**  
A: Ja, Sie können Schriftart, Größe, Farbe und weitere Eigenschaften des Textes in Aspose.Page anpassen.

## Fazit

In diesem Tutorial haben wir gezeigt, wie man **ein PostScript‑Dokument C#** erstellt und Unicode‑Text mit Aspose.Page einbettet. Durch Befolgen der obigen Schritte können Sie die mehrsprachige Textdarstellung schnell in jede .NET‑Anwendung integrieren und erhalten volle Kontrolle über die Dokumentenerstellung und das Layout.

---

**Letzte Aktualisierung:** 2026-03-21  
**Getestet mit:** Aspose.Page 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}