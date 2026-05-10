---
date: 2026-03-21
description: Erfahren Sie, wie Sie ein XPS‑Dokument in .NET erstellen und mit Aspose.Page
  Text hinzufügen, indem Sie Aspose.Page für .NET verwenden. Schritt‑für‑Schritt‑Anleitung
  für .NET‑Entwickler.
linktitle: Add Text to XPS Document
second_title: Aspose.Page .NET API
title: XPS‑Dokument in .NET erstellen und Text mit Aspose.Page hinzufügen
url: /de/net/text-manipulation/add-text-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen Sie XPS-Dokument .NET und fügen Sie Text mit Aspose.Page hinzu

In der modernen .NET-Entwicklung ist die Fähigkeit, **XPS-Dokumente .NET** programmgesteuert zu erstellen, eine wertvolle Fähigkeit, besonders wenn Sie druckbare Berichte, Rechnungen oder benutzerdefinierte Grafiken erzeugen müssen. Dieses Tutorial führt Sie durch die Verwendung von Aspose.Page, um **aspose.page add text** zu einem XPS-Dokument hinzuzufügen, und gibt Ihnen die volle Kontrolle über Layout und Stil – alles innerhalb Ihrer .NET-Anwendung.

## Quick Answers
- **Was behandelt dieses Tutorial?** Hinzufügen von Text zu einem neu erstellten XPS-Dokument mit Aspose.Page für .NET.  
- **Wie lange dauert es?** Etwa 5‑10 Minuten für eine Grundimplementierung.  
- **Was sind die Voraussetzungen?** .NET-Entwicklungsumgebung und Aspose.Page-Bibliothek.  
- **Ist eine Lizenz erforderlich?** Ja, für den Produktionseinsatz wird eine gültige Aspose.Page-Lizenz benötigt.  
- **Läuft es auf .NET Core / .NET 6+?** Absolut – Aspose.Page unterstützt alle aktuellen .NET-Versionen.

## Was bedeutet XPS-Dokument .NET erstellen?

Ein XPS-Dokument in .NET zu erstellen bedeutet, eine Fixed‑Layout‑Datei zu erzeugen, die das genaue Aussehen Ihres Inhalts auf verschiedenen Geräten und Druckern beibehält. XPS (XML Paper Specification) ist Microsofts offener Standard für Seitenbeschreibung, ähnlich wie PDF, jedoch vollständig XML‑basiert.

## Warum Aspose.Page zum Hinzufügen von Text verwenden?

Aspose.Page bietet eine hochrangige, objektorientierte API, die das Low‑Level‑XPS-Markup abstrahiert. Sie können Text, Grafiken und Formen hinzufügen, ohne sich mit rohem XML befassen zu müssen, was den Entwicklungsprozess schneller und weniger fehleranfällig macht.

## Prerequisites

- Aspose.Page für .NET: Stellen Sie sicher, dass die Aspose.Page-Bibliothek installiert ist. Sie können sie von der [Aspose.Page für .NET Dokumentation](https://reference.aspose.com/page/net/) herunterladen.
- Entwicklungsumgebung: Richten Sie Ihre .NET-Entwicklungsumgebung ein. Falls Sie das noch nicht getan haben, folgen Sie den Installationsanweisungen in der [Dokumentation](https://reference.aspose.com/page/net/).
- Dokumentverzeichnis: Erstellen Sie ein Verzeichnis, in dem Sie Ihre Dokumente speichern. Ersetzen Sie „Your Document Directory“ im bereitgestellten Code‑Snippet durch den tatsächlichen Pfad.

Nachdem wir die Grundlagen behandelt haben, tauchen wir in den Code ein.

## Import Namespaces

Zunächst importieren Sie die erforderlichen Namespaces, um das Projekt zu starten:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Step 1: Create XPS document .NET

Erstellen Sie ein neues XPS-Dokument, das als Zeichenfläche für unseren Text dient.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

## Step 2: Create a brush for text

Definieren Sie einen einfarbigen Pinsel, der die Textfarbe bestimmt. Hier verwenden wir Schwarz.

```csharp
// ExStart:4
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
// ExEnd:4
```

## Step 3: Add glyphs (aspose.page add text)

Glyphs sind die Low‑Level‑Darstellung von Zeichen in einem XPS-Dokument. Dieser Aufruf fügt den Text „Hello World!“ an den angegebenen Koordinaten hinzu.

```csharp
// ExStart:5
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.Fill = textFill;
// ExEnd:5
```

## Step 4: Save the resultant XPS document

Speichern Sie das Dokument auf dem Datenträger, damit Sie es später ansehen oder drucken können.

```csharp
// ExStart:6
doc.Save(dataDir + "AddText_out.xps");
// ExEnd:6
```

Durch das Befolgen dieser Schritte haben Sie erfolgreich **XPS-Dokument .NET erstellen** und benutzerdefinierten Text mit Aspose.Page hinzugefügt.

## Common Issues and Solutions

| Problem | Grund | Lösung |
|-------|--------|-----|
| **Datei nicht gefunden** beim Speichern | `dataDir` verweist auf einen nicht existierenden Ordner | Stellen Sie sicher, dass das Verzeichnis existiert, oder verwenden Sie `Directory.CreateDirectory(dataDir)` vor dem Speichern. |
| **Text nicht sichtbar** | Pinsel‑Farbe entspricht dem Hintergrund | Ändern Sie `Color.Black` zu einer anderen kontrastreichen Farbe. |
| **Nicht unterstützte Schriftart** | Schriftart ist nicht auf dem System installiert | Verwenden Sie eine Schriftart, die garantiert vorhanden ist, oder betten Sie die Schriftart mit den Font‑Embedding‑Funktionen von Aspose.Page ein. |

## Frequently Asked Questions

### Q1: Kann ich die Schriftart und Größe des hinzugefügten Textes anpassen?

A1: Ja, Sie haben die vollständige Kontrolle über Schriftart und Größe. Passen Sie die Parameter in der `AddGlyphs`‑Methode entsprechend an.

### Q2: Ist Aspose.Page mit .NET Core kompatibel?

A2: Absolut! Aspose.Page unterstützt .NET Core und gewährleistet die Kompatibilität mit den neuesten .NET‑Technologien.

### Q3: Gibt es Lizenzanforderungen für die Verwendung von Aspose.Page?

A3: Ja, Sie benötigen eine gültige Lizenz. Erkunden Sie Lizenzoptionen [hier](https://purchase.aspose.com/buy).

### Q4: Wie kann ich Support erhalten oder Hilfe suchen?

A4: Besuchen Sie das [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39), um mit der Community in Kontakt zu treten und Unterstützung zu erhalten.

### Q5: Gibt es eine kostenlose Testversion?

A5: Natürlich! Sie können eine kostenlose Testversion [hier](https://releases.aspose.com/) erhalten.

**Additional Q&A**

**Q: Kann ich mehrere Textblöcke auf derselben Seite hinzufügen?**  
A: Ja, rufen Sie einfach `doc.AddGlyphs` mehrmals mit unterschiedlichen Koordinaten auf.

**Q: Unterstützt Aspose.Page Textrotation?**  
A: Sie können eine Transformationsmatrix auf das `XpsGlyphs`‑Objekt anwenden, um den Text zu drehen oder zu kippen.

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

---