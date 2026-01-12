---
date: 2026-01-12
description: Erfahren Sie, wie Sie XPS‑Dokumente mit Aspose.Page für .NET bearbeiten,
  und entdecken Sie, wie Sie Text zu XPS‑Dateien mit einfachen Codebeispielen hinzufügen.
linktitle: Modify XPS Document
second_title: Aspose.Page .NET API
title: XPS-Dokument mit Aspose.Page für .NET bearbeiten
url: /de/net/document-creation/modify-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS-Dokument mit Aspose.Page für .NET ändern

## Einführung

Willkommen zu unserer Schritt‑für‑Schritt‑Anleitung, **wie man XPS‑Dokumente** mit Aspose.Page für .NET ändert. Ob Sie eine Signatur einfügen, ein Wasserzeichen hinzufügen oder einfach benutzerdefinierten Text auf einer Seite platzieren möchten – dieses Tutorial zeigt Ihnen genau **wie man Text** zu einem XPS‑Dokument in wenigen Minuten hinzufügt. Wir gehen jede Codezeile durch, erklären, warum jeder Schritt wichtig ist, und geben Ihnen Tipps, um häufige Fallstricke zu vermeiden.

### Schnelle Antworten
- **Worum geht es in diesem Tutorial?** Eine Signatur‑Text („Confirmed“) zu ausgewählten Seiten einer XPS‑Datei hinzufügen.  
- **Welche Bibliothek wird benötigt?** Aspose.Page für .NET (neueste Version).  
- **Benötige ich eine Lizenz?** Eine temporäre Lizenz reicht für Tests; für die Produktion ist eine Voll‑Lizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Wie lange dauert die Implementierung?** Etwa 10 Minuten für das Einfügen einer einfachen Signatur.

## Was bedeutet das Ändern eines XPS‑Dokuments?

XPS (XML Paper Specification) ist Microsofts festes Layout‑Dokumentformat, ähnlich wie PDF. Ein XPS‑Dokument zu ändern bedeutet, den visuellen Inhalt programmgesteuert zu verändern – Text, Bilder oder Formen hinzuzufügen – ohne die Datei in ein anderes Format zu konvertieren. Aspose.Page bietet ein umfangreiches Objektmodell, mit dem Sie XPS‑Dateien direkt aus Ihrem .NET‑Code heraus bearbeiten können.

## Warum Aspose.Page zum Ändern von XPS‑Dokumenten verwenden?

* **Vollständige Kontrolle** – Arbeiten Sie mit Seiten, Glyphen, Brushes und Transformations‑Operationen auf niedriger Ebene.  
* **Keine externen Abhängigkeiten** – Reine .NET‑Bibliothek, kein Bedarf an Office‑ oder Adobe‑Komponenten.  
* **Plattformübergreifend** – Läuft unter Windows, Linux und macOS via .NET Core.  
* **Robuste Performance** – Handhabt große Dokumente effizient und unterstützt erweiterte Typografie.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- **Aspose.Page für .NET** – Installieren Sie das NuGet‑Paket oder laden Sie die Bibliothek aus der offiziellen Dokumentation **[hier](https://reference.aspose.com/page/net/)** herunter.  
- **Eingabe‑XPS‑Datei** – Beschaffen Sie ein Beispiel‑XPS‑Dokument (z. B. `input1.xps`) von der **[Aspose‑Releases‑Seite](https://releases.aspose.com/page/net/)**.  
- **Arbeitsverzeichnis** – Erstellen Sie einen Ordner auf Ihrem Rechner, um die Eingabe‑ und Ausgabedateien zu speichern, und notieren Sie dessen vollständigen Pfad; Sie werden diesen Pfad der Variable `dir` im Code zuweisen.  
- **Entwicklungsumgebung** – Visual Studio 2019/2022, .NET Framework 4.7.2 oder höher, oder ein beliebiges .NET Core/5/6‑Projekt.

Jetzt, wo alles bereit ist, tauchen wir in den Code ein.

## Namespaces importieren

Importieren Sie in Ihrem .NET‑Projekt die erforderlichen Namespaces für Aspose.Page:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
using System.IO;
```

## Schritt 1: XPS‑Dokument‑Stream öffnen

Wir öffnen die Quell‑XPS‑Datei als Stream und erstellen ein `XpsDocument`‑Objekt, das das gesamte Dokument repräsentiert.

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

*Pro‑Tipp:* Packen Sie den Stream in einen `using`‑Block, damit die Dateihandhabung automatisch freigegeben wird.

## Schritt 2: Signatur‑Text erstellen

Als Nächstes erzeugen wir einen einfarbigen Brush, der zum Zeichnen der Signatur‑Glyphen verwendet wird.

```csharp
// ExStart:4
// Create fill of the signature text
XpsSolidColorBrush textFill = document.CreateSolidColorBrush(Color.BlueViolet);
// Continue to the next step...
// ExEnd:4
```

Sie können `Color.BlueViolet` durch jede beliebige `System.Drawing.Color` ersetzen, die zu Ihrem Branding passt.

## Schritt 3: Seiten definieren und Signatur hinzufügen

Wir geben an, welche Seiten die Signatur erhalten sollen, und fügen dann die Glyphen jeder Seite hinzu.

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

*Warum diese Koordinaten?* Die X‑ und Y‑Werte werden in Punkten (1/72 Zoll) gemessen. Passen Sie sie an, um den Text exakt dort zu positionieren, wo Sie ihn im Layout benötigen.

## Schritt 4: Änderungen im XPS‑Dokument speichern

Schließlich schreiben wir das geänderte Dokument zurück auf die Festplatte.

```csharp
// ExStart:6
// Save changed XPS document
document.Save(dir + "input1_out.xps");
// ExEnd:6
```

Die neue Datei `input1_out.xps` enthält nun die Signatur „Confirmed“ auf den Seiten 1‑3.

## Häufige Probleme und Lösungen

| Problem | Ursache | Lösung |
|-------|-------|----------|
| **Signatur nicht sichtbar** | Falsche Koordinaten oder Seite nicht ausgewählt | Prüfen Sie, ob `SelectActivePage` für jede Seite aufgerufen wird, und passen Sie die X/Y‑Werte an. |
| **Ausnahme bei `AddGlyphs`** | Schriftart nicht auf dem Server installiert | Stellen Sie sicher, dass die angegebene Schriftart (z. B. Arial) verfügbar ist, oder betten Sie eine benutzerdefinierte Schriftart mit `document.AddFont` ein. |
| **Ausgabedatei ist beschädigt** | Stream nicht korrekt geschlossen | Verwenden Sie `using`‑Anweisungen für alle Streams und rufen Sie bei Bedarf `document.Dispose()` auf. |
| **Leistungseinbruch bei großen Dateien** | Gesamtes Dokument wird in den Speicher geladen | Verarbeiten Sie Seiten stapelweise oder nutzen Sie `XpsLoadOptions` mit Streaming‑Optionen (falls in neueren Versionen verfügbar). |

## Häufig gestellte Fragen

**F: Ist Aspose.Page mit den neuesten .NET‑Frameworks kompatibel?**  
A: Ja, Aspose.Page wird regelmäßig aktualisiert und unterstützt .NET Framework 4.5+, .NET Core 3.1+, .NET 5 und .NET 6.

**F: Kann ich Schriftart und Stil des hinzugefügten Textes anpassen?**  
A: Absolut. Ändern Sie die Parameter von `AddGlyphs` (Schriftname, Größe, `FontStyle`), um Ihr Design zu erfüllen.

**F: Gibt es Größenbeschränkungen für XPS‑Dateien?**  
A: Aspose.Page kann große Dokumente verarbeiten, jedoch steigt der Speicherverbrauch mit der Dateigröße. Bei sehr großen Dateien sollten Sie die Seiten einzeln verarbeiten.

**F: Wie erhalte ich eine temporäre Lizenz für Aspose.Page?**  
A: Sie können eine temporäre Lizenz **[hier](https://purchase.aspose.com/temporary-license/)** erhalten.

**F: Wo finde ich Hilfe oder die Aspose‑Community?**  
A: Besuchen Sie das **[Aspose.Page‑Forum](https://forum.aspose.com/c/page/39)**, um Fragen zu stellen und Erfahrungen zu teilen.

## Fazit

In diesem Tutorial haben wir gezeigt, wie man **XPS‑Dokumente** ändert, indem man benutzerdefinierten Signatur‑Text mit Aspose.Page für .NET hinzufügt. Sie verfügen nun über eine solide Grundlage, um beliebigen Text, Wasserzeichen oder Anmerkungen auf bestimmten Seiten einer XPS‑Datei zu platzieren. Experimentieren Sie mit verschiedenen Schriftarten, Farben und Positionen, um die Markenanforderungen Ihrer Anwendung zu erfüllen, und erkunden Sie die umfangreichere Aspose.Page‑API für fortgeschrittene Grafik‑ und Layout‑Funktionen.

---

**Zuletzt aktualisiert:** 2026-01-12  
**Getestet mit:** Aspose.Page 24.11 für .NET (zum Zeitpunkt der Erstellung)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}