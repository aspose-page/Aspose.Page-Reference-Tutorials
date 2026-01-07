---
date: 2026-01-07
description: Erfahren Sie, wie Sie ein XPS‑Dokument erstellen, Glyphenklone hinzufügen,
  einen Pinsel mit Vollfarbe verwenden und die XPS‑Datei mit Aspose.Page für .NET
  speichern.
linktitle: Add Glyph Clone and Change Color
second_title: Aspose.Page .NET API
title: XPS-Dokument erstellen – Glyph‑Klon hinzufügen und Farbe ändern mit Aspose.Page
  für .NET
url: /de/net/cross-document-editing/add-glyph-clone-and-change-color/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS-Dokument erstellen – Glyph‑Klon hinzufügen & Farbe ändern mit Aspose.Page für .NET

## Einführung

Willkommen zu dieser Schritt‑für‑Schritt‑Anleitung, die Ihnen zeigt, **wie Sie XPS‑Dokumentdateien** erstellen, Glyphs klonen und deren Farben ändern können, und das mit Aspose.Page für .NET. Egal, ob Sie dynamische Berichte, Rechnungen oder benutzerdefinierte Grafiken erstellen – mit diesen Techniken erzeugen Sie visuell ansprechende XPS‑Ausgaben, ohne das .NET‑Ökosystem zu verlassen.

## Schnellantworten
- **Was ist das Hauptziel?** Ein XPS‑Dokument erstellen, Glyph‑Klone hinzufügen und deren Farben ändern.  
- **Welche Bibliothek wird verwendet?** Aspose.Page für .NET.  
- **Benötige ich eine Lizenz?** Eine temporäre Lizenz steht für Evaluierungszwecke zur Verfügung; für den Produktionseinsatz ist eine Voll‑Lizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Wie speichere ich das Ergebnis?** Verwenden Sie die `Save`‑Methode, um die XPS‑Datei auf die Festplatte zu schreiben.

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Grundkenntnisse der Programmiersprache C#.  
- Visual Studio oder eine andere bevorzugte C#‑Entwicklungsumgebung installiert.  
- Aspose.Page für .NET‑Bibliothek. Sie können sie [hier](https://releases.aspose.com/page/net/) herunterladen.  
- Vertrautheit mit dem XPS‑Dokumentenformat.

## Namespaces importieren

Um loszulegen, fügen Sie die erforderlichen Namespaces in Ihr C#‑Projekt ein:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Wie man ein XPS‑Dokument erstellt und Glyph‑Klone hinzufügt

### Schritt 1: Dokumentverzeichnis einrichten

Richten Sie das Verzeichnis ein, in dem Ihre Dokumente gespeichert werden sollen:

```csharp
string dataDir = "Your Document Directory";
```

### Schritt 2: Das erste XPS‑Dokument erstellen

Erstellen wir nun das erste XPS‑Dokument:

```csharp
XpsDocument doc1 = new XpsDocument();
```

### Schritt 3: Glyphs zum ersten Dokument hinzufügen

Fügen Sie dem ersten Dokument Glyphs mit den angegebenen Parametern hinzu:

```csharp
XpsGlyphs glyphs = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Schritt 4: Glyphs mit einem einfarbigen Pinsel füllen

Füllen Sie die Glyphs im ersten Dokument mit einem **einfarbigen Pinsel**, zum Beispiel Grün:

```csharp
glyphs.Fill = doc1.CreateSolidColorBrush(Color.Green);
```

### Schritt 5: Das zweite XPS‑Dokument erstellen

Erstellen Sie nun das zweite XPS‑Dokument:

```csharp
XpsDocument doc2 = new XpsDocument();
```

### Schritt 6: Glyph‑Klon zu einem anderen Dokument hinzufügen

Klonen Sie Glyphs aus dem ersten Dokument und fügen Sie sie dem zweiten Dokument hinzu:

```csharp
glyphs = doc2.Add(glyphs.Clone());
```

### Schritt 7: Farbe des geklonten Glyphs ändern

Ändern Sie die Farbe der geklonten Glyphs im zweiten Dokument, zum Beispiel zu Rot. Dies demonstriert, **wie man die Farbe** eines Glyphs nach dem Klonen ändert:

```csharp
((XpsSolidColorBrush)glyphs.Fill).Color = doc2.CreateColor(Color.Red);
```

### Schritt 8: XPS‑Datei speichern – Erstes Dokument

Speichern Sie das erste XPS‑Dokument im zuvor definierten Ordner:

```csharp
doc1.Save(dataDir + "out1.xps");
```

### Schritt 9: XPS‑Datei speichern – Zweites Dokument

Speichern Sie das zweite XPS‑Dokument:

```csharp
doc2.Save(dataDir + "out2.xps");
```

Herzlichen Glückwunsch! Sie haben erfolgreich **XPS‑Dokumente** erstellt, Glyph‑Klone hinzugefügt und deren Farben mit Aspose.Page für .NET geändert.

## Warum Glyph‑Klonen und Farbänderungen verwenden?

- **Wiederverwendbarkeit:** Klonen Sie vorhandene Glyphs, um komplexe Vektorformen wiederzuverwenden, ohne sie neu definieren zu müssen.  
- **Performance:** Reduziert die Verarbeitungszeit im Vergleich zum Neuerstellen von Glyphs von Grund auf.  
- **Design‑Flexibilität:** Wenden Sie verschiedene `SolidColorBrush`‑Instanzen auf denselben Glyph an, um unterschiedliche visuelle Themen zu erzielen.  
- **Cross‑Document‑Bearbeitung:** Klonen Sie Glyphs über mehrere XPS‑Dateien hinweg, um ein konsistentes Branding in Berichten zu gewährleisten.

## Häufige Probleme & Fehlersuche

| Problem | Lösung |
|-------|----------|
| **Clone gibt null zurück** | Stellen Sie sicher, dass das Quell‑Glyph (`glyphs`) dem ersten Dokument hinzugefügt wurde, bevor Sie klonen. |
| **Farbe ändert sich nicht** | Casten Sie `glyphs.Fill` zu `XpsSolidColorBrush`, bevor Sie die `Color`‑Eigenschaft setzen (wie in Schritt 7 gezeigt). |
| **Datei wird nicht gespeichert** | Prüfen Sie, ob `dataDir` auf einen gültigen, beschreibbaren Ordner zeigt und ob Sie die entsprechenden Dateisystem‑Berechtigungen besitzen. |
| **Unerwartete Glyph‑Größe** | Passen Sie den Schriftgrößen‑Parameter (zweites Argument in `AddGlyphs`) an, um das Glyph entsprechend zu skalieren. |

## Häufig gestellte Fragen

**F1: Kann ich Aspose.Page für .NET mit anderen Dokumentformaten verwenden?**  
A1: Aspose.Page für .NET ist speziell für die Arbeit mit XPS‑Dokumenten konzipiert. Wenn Sie andere Formate manipulieren müssen, können Sie andere Aspose‑Bibliotheken prüfen, die für diese Formate vorgesehen sind.

**F2: Gibt es eine temporäre Lizenz für Aspose.Page für .NET?**  
A2: Ja, Sie können eine temporäre Lizenz für Testzwecke erhalten. Besuchen Sie [hier](https://purchase.aspose.com/temporary-license/) für weitere Informationen.

**F3: Wie kann ich Support erhalten oder bei Problemen Hilfe suchen?**  
A3: Besuchen Sie das [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39), um mit der Community in Kontakt zu treten und Unterstützung zu erhalten.

**F4: Gibt es Einschränkungen in der kostenlosen Testversion?**  
A4: Die kostenlose Testversion hat einige Einschränkungen; es wird empfohlen, die Dokumentation für Details vor der Nutzung zu prüfen.

**F5: Wo finde ich umfassende Dokumentation für Aspose.Page für .NET?**  
A5: Die Dokumentation finden Sie [hier](https://reference.aspose.com/page/net/) mit detaillierten Informationen und Beispielen.

**F6: Wie ändere ich die Konturfarbe eines Glyphs anstelle der Füllfarbe?**  
A6: Verwenden Sie `glyphs.Stroke = doc.CreateSolidColorBrush(Color.Blue);`, um einen Konturpinsel zu setzen.

**F7: Kann ich mehrere Glyph‑Klone zum selben Dokument hinzufügen?**  
A7: Ja, rufen Sie wiederholt `doc2.Add(glyphs.Clone());` auf und passen Sie die Positionen nach Bedarf an.

---

**Zuletzt aktualisiert:** 2026-01-07  
**Getestet mit:** Aspose.Page 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}