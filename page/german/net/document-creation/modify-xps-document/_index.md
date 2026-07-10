---
date: 2026-07-10
description: 'Aspose.Page .NET Tutorial: Erfahren Sie, wie Sie XPS-Dokumente mit Aspose.Page
  für .NET bearbeiten, einschließlich des Hinzufügens von Text, Signaturen und Wasserzeichen
  mit klaren Code‑Beispielen.'
keywords:
- aspose page .net tutorial
- modify xps document
- add text to xps
lastmod: 2026-07-10
linktitle: XPS-Dokument bearbeiten
og_description: Aspose.Page .NET Tutorial zeigt, wie XPS-Dokumente bearbeitet und
  Text sowie Signaturen schnell hinzugefügt werden. Folgen Sie der Schritt‑für‑Schritt‑Anleitung
  für .NET‑Entwickler.
og_image_alt: Guide to modify XPS document using Aspose.Page for .NET
og_title: 'Aspose.Page .NET Tutorial: XPS-Dokument bearbeiten'
schemas:
- author: Aspose
  dateModified: '2026-07-10'
  description: 'Aspose Page .NET tutorial: Learn how to modify XPS documents using
    Aspose.Page for .NET, including adding text, signatures, and watermarks with clear
    code examples.'
  headline: 'Aspose.Page .NET Tutorial: Modify XPS Document'
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page is regularly updated to support .NET Framework 4.5+,
      .NET Core 3.1+, .NET 5, and .NET 6.
    question: Is Aspose.Page compatible with the latest .NET frameworks?
  - answer: Absolutely. Change the parameters of `AddGlyphs` (font name, size, `FontStyle`)
      to suit your design.
    question: Can I customize the font and style of the added text?
  - answer: Aspose.Page can handle documents larger than 200 MB and up to 500 pages
      without exhausting memory, thanks to its streaming architecture.
    question: Are there any size limits for XPS files?
  - answer: You can acquire a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How do I obtain a temporary license for Aspose.Page?
  - answer: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**
      to ask questions and share experiences.
    question: Where can I seek help or connect with the Aspose community?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- aspose page
- xps modification
- .net tutorial
title: 'Aspose.Page .NET Tutorial: XPS-Dokument bearbeiten'
url: /de/net/document-creation/modify-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page .NET Tutorial: XPS-Dokument modifizieren

## Einführung

In diesem **aspose page .net tutorial** erfahren Sie, wie Sie ein XPS-Dokument programmgesteuert mit Aspose.Page für .NET ändern können. Egal, ob Sie eine Signatur einfügen, ein Wasserzeichen hinzufügen oder einfach benutzerdefinierten Text auf einer Seite platzieren möchten, wir gehen jede Codezeile durch, erklären, warum jeder Schritt wichtig ist, und geben praktische Tipps, um häufige Fallstricke zu vermeiden. Am Ende können Sie XPS-Dateien in Minuten statt Stunden bearbeiten.

### Schnelle Antworten
- **Was behandelt dieses Tutorial?** Hinzufügen eines Signaturtexts („Confirmed“) zu ausgewählten Seiten einer XPS-Datei.  
- **Welche Bibliothek wird benötigt?** Aspose.Page für .NET (neueste Version).  
- **Brauche ich eine Lizenz?** Eine temporäre Lizenz funktioniert für Tests; für die Produktion ist eine Volllizenz erforderlich.  
- **Welche .NET-Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Wie lange dauert die Implementierung?** Etwa 10 Minuten für das Einfügen einer einfachen Signatur.

## Was bedeutet das Modifizieren eines XPS-Dokuments?

Das Modifizieren eines XPS-Dokuments beinhaltet das programmgesteuerte Ändern seines visuellen Inhalts – z. B. das Einfügen von Text, Bildern oder Vektorgrafiken – bei gleichzeitiger Bewahrung des festen Layouts der Datei. Da XPS auf XML basiert, werden Änderungen direkt auf die Seitenstruktur des Dokuments angewendet, ohne dass eine Konvertierung nötig ist, was eine präzise Kontrolle über Layout, Typografie und Grafiken ermöglicht.

## Warum Aspose.Page zum Modifizieren von XPS-Dokumenten verwenden?

Aspose.Page bietet eine native .NET-API, die plattformübergreifend funktioniert, externe Abhängigkeiten eliminiert und hohe Leistung für große Dokumente liefert. Sie gibt Entwicklern Low‑Level‑Zugriff auf Seiten, Glyphen, Pinsel und Transformationen, wodurch die Implementierung benutzerdefinierter Signaturen, Wasserzeichen und komplexer Grafiken mit feiner Steuerung möglich wird.

## Voraussetzungen

- **Aspose.Page für .NET** – Installieren Sie das NuGet‑Paket oder laden Sie die Bibliothek aus der offiziellen Dokumentation **[hier](https://reference.aspose.com/page/net/)** herunter.  
- **Eingabe‑XPS‑Datei** – Beschaffen Sie ein Beispiel‑XPS-Dokument (z. B. `input1.xps`) von der **[Aspose‑Release‑Seite](https://releases.aspose.com/page/net/)**.  
- **Arbeitsverzeichnis** – Erstellen Sie einen Ordner auf Ihrem Rechner, um Eingabe‑ und Ausgabedateien zu speichern, und notieren Sie den vollständigen Pfad; Sie werden diesen Pfad der Variable `dir` im Code zuweisen.  
- **Entwicklungsumgebung** – Visual Studio 2019/2022, .NET Framework 4.7.2 oder höher, oder jedes .NET Core/5/6‑Projekt.

Jetzt, da alles eingerichtet ist, tauchen wir in den Code ein.

## Wie importiert man Namespaces für Aspose.Page?

Um mit Aspose.Page zu arbeiten, müssen Sie seine Namespaces am Anfang Ihrer C#‑Quelldatei importieren. Dadurch erhält der Compiler Zugriff auf Typen wie `XpsDocument`, `Glyphs` und `SolidColorBrush`. Die Klasse `XpsDocument` repräsentiert eine XPS‑Datei und bietet Zugriff auf ihre Seiten und Ressourcen.

```csharp
using Aspose.Page;
using Aspose.Page.Xps;
using Aspose.Page.Xps.XpsModel;
using System.IO;
using System.Drawing;
```

Die `using`‑Anweisungen geben Ihnen direkten Zugriff auf `XpsDocument`, `Glyphs` und andere wesentliche Klassen.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
using System.IO;
```

## Wie öffnet man einen XPS‑Dokument‑Stream?

Öffnen Sie die Quell‑XPS‑Datei mit einem schreibgeschützten `FileStream` und übergeben Sie ihn dem Konstruktor von `XpsDocument`. Dadurch wird die Datei in ein `XpsDocument`‑Objekt geladen, das als Einstiegspunkt für alle nachfolgenden Änderungen dient. Stellen Sie sicher, dass der Stream in einem `using`‑Block eingeschlossen ist, damit das Dateihandle automatisch freigegeben wird.

```csharp
string inputPath = Path.Combine(dir, "input1.xps");
using (FileStream fs = new FileStream(inputPath, FileMode.Open, FileAccess.Read))
{
    XpsDocument document = new XpsDocument(fs);
    // All further operations use the 'document' variable.
}
```

**Definition‑Anker:** Die Klasse `XpsDocument` ist das Top‑Level‑Objekt von Aspose.Page, das eine einzelne XPS‑Datei kapselt und Seiten, Ressourcen sowie Metadaten zur Manipulation bereitstellt.

```csharp
// ExStart:3
// The path to the documents directory.
string dir = "Your Document Directory";
// Open a stream of XPS file
using (FileStream xpsStream = File.Open(dir + "input1.xps", FileMode.Open, FileAccess.Read))
{
    // Create PS document from stream
    XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
    // Continue to the next step...
}
// ExEnd:3
```

*Pro‑Tipp:* Wickeln Sie den Stream in einen `using`‑Block, um sicherzustellen, dass das Dateihandle automatisch freigegeben wird.

## Wie erstellt man Signaturtext in XPS?

Erstellen Sie einen `SolidColorBrush`, um die Farbe zu definieren, die den Signaturtext füllt, und bereiten Sie dann die Zeichenkette vor, die Sie rendern möchten. Die Klasse `SolidColorBrush` liefert eine einheitliche Farbfüllung für Zeichenoperationen wie Text oder Formen. Passen Sie die Pinsel‑Farbe an Ihr Branding an, bevor Sie die Glyphen hinzufügen.

```csharp
SolidColorBrush brush = new SolidColorBrush(document, Color.BlueViolet);
string signature = "Confirmed";
```

**Definition‑Anker:** `SolidColorBrush` ist ein Zeichenobjekt, das Formen oder Text mit einer einzigen, einheitlichen Farbe füllt.

Sie können `Color.BlueViolet` zu jeder `System.Drawing.Color` ändern, die zu Ihrem Branding passt.

```csharp
// ExStart:4
// Create fill of the signature text
XpsSolidColorBrush textFill = document.CreateSolidColorBrush(Color.BlueViolet);
// Continue to the next step...
// ExEnd:4
```

## Wie definiert man Seiten und fügt die Signatur‑Glyphen hinzu?

Wählen Sie jede Zielseite mit `SelectActivePage` aus und rufen Sie anschließend `AddGlyphs` auf, um den Signaturtext an den gewünschten Koordinaten zu platzieren. Die Methode `AddGlyphs` fügt eine Zeichenfolge in die aktive Seite ein, wobei die angegebene Schriftart, Größe, Stil und Pinsel verwendet werden. Stimmen Sie die X‑ und Y‑Werte fein ab, um den Text präzise zu positionieren.

```csharp
int[] pages = { 1, 2, 3 };
foreach (int pageNumber in pages)
{
    XpsPage page = document.Pages[pageNumber - 1];
    page.SelectActivePage();
    page.AddGlyphs(100, 200, signature, "Arial", 24, FontStyle.Regular, brush);
}
```

**Definition‑Anker:** `AddGlyphs` fügt eine Zeichenfolge (Glyphen) in die aktive Seite ein, wobei die bereitgestellte Schriftart, Größe, Stil und Pinsel verwendet werden.

*Warum diese Koordinaten?* Die X‑ und Y‑Werte werden in Punkten (1/72 Zoll) gemessen. Passen Sie sie an, um den Text genau dort zu positionieren, wo Sie ihn im Seitenlayout benötigen.

```csharp
// ExStart:5
// Define pages where signature will be set
int[] pageNumbers = new int[] {1, 2, 3};

// For every defined page set signature "Confirmed" at coordinates x=650 and y=950
for (int i = 0; i < pageNumbers.Length; i++)
{
    // Define active page
    document.SelectActivePage(pageNumbers[i]);

    // Create glyphs object
    XpsGlyphs glyphs = document.AddGlyphs("Arial", 24, FontStyle.Bold, 650, 900, "Confirmed");

    // Define fill for glyphs
    glyphs.Fill = textFill;
}
// Continue to the next step...
// ExEnd:5
```

## Wie speichert man Änderungen im XPS‑Dokument?

Nachdem Sie alle gewünschten Glyphen hinzugefügt haben, rufen Sie die Methode `Save` auf der `XpsDocument`‑Instanz auf, um den modifizierten Inhalt in eine neue Datei zu schreiben. Die `Save`‑Funktion serialisiert die im Speicher befindliche Darstellung des Dokuments zurück in das XPS‑Format und bewahrt alle Änderungen wie hinzugefügten Text oder Grafiken. Verwenden Sie einen eindeutigen Ausgabedateinamen, um das Original nicht zu überschreiben.

```csharp
string outputPath = Path.Combine(dir, "input1_out.xps");
using (FileStream outFs = new FileStream(outputPath, FileMode.Create, FileAccess.Write))
{
    document.Save(outFs);
}
```

Die neue Datei `input1_out.xps` enthält nun die Signatur „Confirmed“ auf den Seiten 1‑3.

```csharp
// ExStart:6
// Save changed XPS document
document.Save(dir + "input1_out.xps");
// ExEnd:6
```

## Häufige Probleme und Lösungen

| Problem | Ursache | Lösung |
|---------|---------|--------|
| **Signatur nicht sichtbar** | Falsche Koordinaten oder Seite nicht ausgewählt | Stellen Sie sicher, dass `SelectActivePage` für jede Seite aufgerufen wird, und passen Sie die X/Y‑Werte an. |
| **Ausnahme bei `AddGlyphs`** | Schriftart nicht auf dem Server installiert | Stellen Sie sicher, dass die angegebene Schriftart (z. B. Arial) verfügbar ist, oder betten Sie eine benutzerdefinierte Schriftart mit `document.AddFont` ein. |
| **Ausgabedatei ist beschädigt** | Stream nicht ordnungsgemäß geschlossen | Verwenden Sie `using`‑Anweisungen für alle Streams und rufen Sie bei Bedarf `document.Dispose()` auf. |
| **Leistungsabfall bei großen Dateien** | Laden des gesamten Dokuments in den Speicher | Verarbeiten Sie Seiten in Stapeln oder verwenden Sie `XpsLoadOptions` mit Streaming‑Optionen (falls in neueren Versionen verfügbar). |

## Häufig gestellte Fragen

**Q: Ist Aspose.Page mit den neuesten .NET‑Frameworks kompatibel?**  
A: Ja, Aspose.Page wird regelmäßig aktualisiert, um .NET Framework 4.5+, .NET Core 3.1+, .NET 5 und .NET 6 zu unterstützen.

**Q: Kann ich die Schriftart und den Stil des hinzugefügten Textes anpassen?**  
A: Absolut. Ändern Sie die Parameter von `AddGlyphs` (Schriftname, Größe, `FontStyle`), um Ihrem Design zu entsprechen.

**Q: Gibt es Größenbeschränkungen für XPS‑Dateien?**  
A: Aspose.Page kann Dokumente größer als 200 MB und bis zu 500 Seiten verarbeiten, ohne den Speicher zu erschöpfen, dank seiner Streaming‑Architektur.

**Q: Wie erhalte ich eine temporäre Lizenz für Aspose.Page?**  
A: Sie können eine temporäre Lizenz **[hier](https://purchase.aspose.com/temporary-license/)** erhalten.

**Q: Wo kann ich Hilfe erhalten oder mich mit der Aspose‑Community vernetzen?**  
A: Besuchen Sie das **[Aspose.Page‑Forum](https://forum.aspose.com/c/page/39)**, um Fragen zu stellen und Erfahrungen zu teilen.

## Fazit

In diesem **aspose page .net tutorial** haben wir gezeigt, wie man **XPS‑Dokumente** durch Hinzufügen benutzerdefinierten Signaturtexts mit Aspose.Page für .NET modifiziert. Sie verfügen nun über eine solide Grundlage, um beliebigen Text, Wasserzeichen oder Anmerkungen auf bestimmten Seiten einer XPS‑Datei einzufügen. Experimentieren Sie mit verschiedenen Schriftarten, Farben und Positionen, um die Branding‑Anforderungen Ihrer Anwendung zu erfüllen, und erkunden Sie die umfangreichere Aspose.Page‑API für erweiterte Grafik‑ und Layout‑Funktionen.

---

**Zuletzt aktualisiert:** 2026-07-10  
**Getestet mit:** Aspose.Page 24.11 for .NET (latest at time of writing)  
**Autor:** Aspose

## Verwandte Tutorials

- [Text zu XPS-Dokument hinzufügen mit Aspose.Page für .NET](/page/net/text-manipulation/add-text-to-xps-document/)
- [Bild zu XPS-Dokument hinzufügen mit Aspose.Page für .NET](/page/net/image-management/add-image-to-xps-document/)
- [XPS-Dokument erstellen – Aspose.Page für .NET](/page/net/document-creation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}