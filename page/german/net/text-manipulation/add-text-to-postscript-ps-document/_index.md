---
date: 2026-03-21
description: Erfahren Sie, wie Sie Text in PS‑Dokumente einfügen und hinzufügen können,
  indem Sie Aspose.Page für .NET verwenden. Schritt‑für‑Schritt‑Anleitung mit Codebeispielen.
linktitle: Add Text to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Wie man Text in PostScript (PS)-Dokumenten mit Aspose.Page ausfüllt
url: /de/net/text-manipulation/add-text-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Text in PostScript (PS)-Dokumenten mit Aspose.Page füllt

## Einführung

Wenn Sie **Text füllen** in einer PostScript (PS)-Datei benötigen, macht Aspose.Page für .NET das unkompliziert. Egal, ob Sie Berichte, Rechnungen oder benutzerdefinierte Grafiken erzeugen, das Hinzufügen und Gestalten von Text ist eine Kernanforderung. In diesem Tutorial führen wir Sie durch den gesamten Prozess – von der Einrichtung der Umgebung bis zum Speichern des finalen PS-Dokuments – damit Sie Text sicher zu PS-Dateien in Ihren .NET-Anwendungen hinzufügen können.

## Schnelle Antworten
- **Was bedeutet „fill text“?** Es rendert Zeichen mit einem Vollpinsel und malt die Glyphen direkt auf die Seite.  
- **Kann ich benutzerdefinierte Schriften verwenden?** Ja – Aspose.Page unterstützt benutzerdefinierte Schriften über die `add custom font ps`-Funktion.  
- **Wie speichere ich das PS-Dokument?** Rufen Sie `document.Save()` nach dem Schließen der Seite auf; dies schreibt die Datei auf die Festplatte (`save ps document`).  
- **Wird „fill and stroke text“ unterstützt?** Absolut; verwenden Sie `FillAndStrokeText`, um sowohl Füllung als auch Kontur anzuwenden.  
- **Welche .NET-Versionen werden benötigt?** Jedes .NET Framework 4.5+ oder .NET Core/5/6+ Runtime.

## Was bedeutet „how to fill text“ in einem PS-Dokument?

Text füllen bedeutet, die Zeichen mit einer einfarbigen Farbe (oder Pinsel) ohne Kontur zu malen. In PostScript entspricht dies dem `fill`‑Operator. Aspose.Page abstrahiert dies in einfach zu verwendende Methoden wie `FillText` und `FillAndStrokeText`.

## Warum Aspose.Page für das Hinzufügen von benutzerdefinierten Schriftarten in PS verwenden?

- **Vollständige Schriftunterstützung** – Systemschriften und externe TrueType/OpenType‑Schriften funktionieren sofort.  
- **Präzise Positionierung** – Sie steuern X/Y‑Koordinaten, Größe und Stil.  
- **Umfangreiche Gestaltung** – kombinieren Sie Füllungen, Konturen und Stifte für Effekte wie „fill and stroke text“.  
- **Plattformübergreifend** – funktioniert unter Windows, Linux und macOS mit derselben API.

## Voraussetzungen

Stellen Sie vor dem Start sicher, dass Sie Folgendes haben:

- **Aspose.Page for .NET** – Laden Sie die Bibliothek von der [Aspose.Page .NET documentation](https://reference.aspose.com/page/net/) herunter.  
- **Document Directory** – ein Ordner auf Ihrem Rechner, in dem die Quell‑ und Ausgabedateien für PS gespeichert werden (im Code als *Your Document Directory* bezeichnet).  
- **Fonts Folder** – ein Unterordner, der alle benutzerdefinierten Schriften enthält, die Sie verwenden möchten.

## Namespaces importieren

Importieren Sie zunächst die erforderlichen Namespaces, damit der Compiler weiß, wo die Klassen zu finden sind, die wir verwenden werden:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Ausgabestream für PS‑Dokument erstellen  

Wir öffnen einen `FileStream`, der die erzeugte PS‑Datei enthält, konfigurieren `PsSaveOptions`, um auf unseren benutzerdefinierten Schriftordner zu verweisen, und instanziieren ein `PsDocument`.

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

> **Pro‑Tipp:** Behalten Sie den `using`‑Block bei, um sicherzustellen, dass der Stream automatisch geschlossen wird, was gleichzeitig die PS‑Datei finalisiert (`save ps document`).

### Schritt 2: Text mit einer Systemschrift füllen  

Hier demonstrieren wir die grundlegende **Text füllen**‑Operation mit der integrierten *Times New Roman*-Schrift.

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

### Schritt 3: Text mit einer benutzerdefinierten Schrift füllen  

Wenn Sie ein bestimmtes Aussehen benötigen, laden Sie eine benutzerdefinierte Schrift aus dem Schriftordner mit `ExternalFontCache.FetchDrFont`. Damit wird die Anforderung **add custom font ps** erfüllt.

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

### Schritt 4: Text mit einer Systemschrift umranden (Stroke)  

Das Umranden zeichnet die Kontur der Glyphen. Kombinieren Sie es mit einer Füllung für einen „fill and stroke“-Effekt.

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

> **Warum das wichtig ist:** Der Aufruf `FillAndStrokeText` zeigt, wie man **fill and stroke text** in einem einzigen Schritt ausführt und Ihnen damit mehr typografische Kontrolle gibt.

### Schritt 5: Text mit einer benutzerdefinierten Schrift umranden  

Die gleiche Umrandungstechnik funktioniert mit jeder benutzerdefinierten Schrift, die Sie geladen haben.

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

### Schritt 6: Seite schließen und Dokument speichern  

Der Abschluss ist einfach: Schließen Sie die aktuelle Seite und rufen Sie `Save()` auf, um die PS‑Datei auf die Festplatte zu schreiben.

```csharp
document.ClosePage();
document.Save();
}
```

> **Ergebnis:** Sie finden `AddText_outPS.ps` in *Your Document Directory*, das sowohl gefüllten als auch umrandeten Text enthält, der mit System- und benutzerdefinierten Schriften gerendert wurde.

## Häufige Probleme und Lösungen

| Problem | Lösung |
|-------|----------|
| **Custom font not found** | Überprüfen Sie, ob die Schriftdatei (.ttf/.otf) im Ordner existiert, der in `AdditionalFontsFolders` angegeben ist. |
| **Text appears at wrong position** | Passen Sie die an `FillText`/`OutlineText` übergebenen X/Y‑Koordinaten an. Denken Sie daran, dass PostScript Punkte (1/72 Zoll) verwendet. |
| **Colors look different** | Stellen Sie sicher, dass Sie `SolidBrush` oder `Pen` mit den korrekten `Color`‑Werten verwenden. |
| **Document not saving** | Vergewissern Sie sich, dass der `using`‑Block ohne Ausnahmen abgeschlossen wird und die Anwendung Schreibrechte für den Zielordner hat. |

## Häufig gestellte Fragen

**Q: Kann ich Aspose.Page mit anderen .NET-Bibliotheken verwenden?**  
A: Ja, Aspose.Page lässt sich nahtlos in andere .NET‑Komponenten integrieren, sodass Sie PDF-, Bild- oder Diagrammbibliotheken in derselben Lösung kombinieren können.

**Q: Sind benutzerdefinierte Schriften für diesen Vorgang zwingend erforderlich?**  
A: Während Systemschriften gut funktionieren, bieten benutzerdefinierte Schriften Ihnen volle Gestaltungsfreiheit und sind nützlich, wenn markenspezifische Typografie benötigt wird.

**Q: Ist Aspose.Page für die Verarbeitung von Dokumenten in großem Maßstab geeignet?**  
A: Absolut. Die Bibliothek ist für Hochdurchsatz‑Szenarien optimiert und kann Tausende von PS‑Dateien effizient verarbeiten.

**Q: Kann ich die Position des Textes im PS‑Dokument ändern?**  
A: Sicherlich – ändern Sie einfach die numerischen X/Y‑Werte in den Aufrufen von `FillText` oder `OutlineText`.

**Q: Wo kann ich Unterstützung für Aspose.Page‑bezogene Fragen erhalten?**  
A: Besuchen Sie das [Aspose.Page Forum](https://forum.aspose.com/c/page/39), um mit der Community in Kontakt zu treten und fachkundige Hilfe zu erhalten.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2026-03-21  
**Getestet mit:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose