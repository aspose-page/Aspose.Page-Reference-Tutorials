---
date: 2026-03-21
description: Erfahren Sie, wie Sie Unicode‑Text zu einem XPS‑Dokument mit Aspose.Page
  für .NET hinzufügen. Dieser Leitfaden zeigt Ihnen, wie Sie ein XPS‑Dokument in C#
  erstellen und mit Aspose.Page Text mit Unicode‑Zeichenketten einfügen.
linktitle: Add Text with Unicode String to XPS Document
second_title: Aspose.Page .NET API
title: Wie man Unicode‑Text zu einem XPS‑Dokument mit Aspose.Page hinzufügt
url: /de/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Unicode-Text zu einem XPS-Dokument mit Aspose.Page hinzufügt

## Einführung

Wenn Sie **how to add unicode** Zeichen zu einer XPS-Datei hinzufügen müssen, sind Sie hier genau richtig. In diesem Tutorial gehen wir die genauen Schritte durch, die erforderlich sind, um **create XPS document C#**‑style mit Aspose.Page für .NET zu erstellen und die **aspose page add text**‑Funktion mit einem Unicode‑String zu demonstrieren. Am Ende haben Sie ein voll funktionsfähiges XPS-Dokument, das rechts‑nach‑links (RTL) Unicode‑Text korrekt anzeigt.

## Schnelle Antworten
- **Was behandelt das Tutorial?** Unicode‑Text zu einem XPS-Dokument mit Aspose.Page für .NET hinzufügen.  
- **Welche Sprache wird verwendet?** C# (kompatibel mit .NET Framework und .NET Core).  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich die Schriftart oder Größe ändern?** Ja – das Beispiel verwendet Arial 20 pt, aber jede installierte Schriftart funktioniert.  
- **Ist RTL‑Unterstützung enthalten?** Das Setzen von `BidiLevel = 1` aktiviert die rechts‑nach‑links‑Darstellung für Unicode‑Strings.

## Was bedeutet „how to add unicode“ in XPS?

Unicode‑Text hinzufügen bedeutet, Zeichen aus jeder Sprache—Arabisch, Hebräisch, Chinesisch usw.—in ein XPS-Dokument einzufügen. Aspose.Page’s `XpsGlyphs`‑Klasse übernimmt die niedrig‑stufige Glyphenplatzierung, während die `BidiLevel`‑Eigenschaft die Text‑richtung für RTL‑Skripte steuert.

## Warum Aspose.Page zum Hinzufügen von Text verwenden?

- **Vollständige .NET-Integration** – funktioniert mit .NET Framework, .NET Core, .NET 5/6+.  
- **Keine externen Abhängigkeiten** – reiner verwalteter Code, kein COM‑Interop.  
- **Umfangreiche Typografie‑Unterstützung** – Schriftarten, Stile, Farben und bidirektionaler Text.  
- **Hohe Leistung** – erstellt und speichert XPS‑Dateien schnell, ideal für serverseitige Generierung.

## Voraussetzungen

- Grundkenntnisse in C# und .NET-Entwicklung.  
- Visual Studio (beliebige aktuelle Version).  
- Aspose.Page für .NET Bibliothek – laden Sie sie von [here](https://releases.aspose.com/page/net/) herunter.

## Namespaces importieren

Zuerst importieren Sie die Namespaces, die Ihnen Zugriff auf das XPS‑Modell und die Zeichen‑Hilfsmittel geben.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Schritt 1: Dokument einrichten – XPS-Dokument in C# erstellen

Erstellen Sie ein neues XPS-Dokument, das den Unicode‑Text enthalten wird.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

## Schritt 2: Unicode‑Text hinzufügen – aspose page add text

Jetzt fügen wir den eigentlichen Unicode‑String hinzu. In diesem Beispiel verwenden wir die Schriftart Arial, Größe 20, und positionieren den Text bei (400 f, 200 f). Der `BidiLevel` von 1 weist den Renderer an, den String als rechts‑nach‑links zu behandeln.

```csharp
// Add Text
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Schritt 3: Dokument speichern

Abschließend speichern Sie die XPS‑Datei auf dem Datenträger.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Herzlichen Glückwunsch! Sie haben erfolgreich **how to add unicode** Text zu einem XPS-Dokument mit Aspose.Page für .NET hinzugefügt.

## Häufige Probleme und Lösungen

| Problem | Grund | Lösung |
|---------|-------|--------|
| Text erscheint verzerrt | Schriftart unterstützt den Unicode‑Bereich nicht | Verwenden Sie eine Schriftart, die die benötigten Glyphen enthält (z. B. Arial Unicode MS). |
| RTL‑Text bleibt immer noch links‑nach‑rechts | `BidiLevel` nicht gesetzt oder auf 0 gesetzt | Stellen Sie sicher, dass `glyphs.BidiLevel = 1;` für RTL‑Skripte gesetzt ist. |
| Datei wird nicht gespeichert | Ungültiger `dataDir`‑Pfad | Überprüfen Sie, ob das Verzeichnis existiert und die Anwendung Schreibrechte hat. |

## Häufig gestellte Fragen

**F: Ist Aspose.Page mit den neuesten .NET-Frameworks kompatibel?**  
A: Ja, Aspose.Page wird regelmäßig aktualisiert, um .NET Framework, .NET Core und .NET 5/6+ zu unterstützen.

**F: Kann ich den Schriftstil und die Größe beim Hinzufügen von Text anpassen?**  
A: Absolut! Die Methode `AddGlyphs` ermöglicht es Ihnen, jede gewünschte Schriftfamilie, Größe und `FontStyle` anzugeben.

**F: Wo finde ich zusätzliche Dokumentation für Aspose.Page?**  
A: Sie können die Dokumentation [here](https://reference.aspose.com/page/net/) für umfassende API‑Details einsehen.

**F: Gibt es kostenlose Ressourcen, um mit Aspose.Page zu beginnen?**  
A: Ja, besuchen Sie das Community‑Forum unter [Aspose.Page forum](https://forum.aspose.com/c/page/39) für Tipps, Beispiele und Unterstützung durch andere Nutzer.

**F: Gibt es eine Testversion, bevor man einen Kauf tätigt?**  
A: Natürlich! Laden Sie die kostenlose Testversion von [here](https://releases.aspose.com/) herunter, um die Bibliothek zu evaluieren.

---

**Zuletzt aktualisiert:** 2026-03-21  
**Getestet mit:** Aspose.Page 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}