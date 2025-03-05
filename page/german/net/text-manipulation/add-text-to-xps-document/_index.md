---
title: Fügen Sie mit Aspose.Page für .NET Text zu einem XPS-Dokument hinzu
linktitle: Text zum XPS-Dokument hinzufügen
second_title: Aspose.Page .NET-API
description: Entdecken Sie eine Schritt-für-Schritt-Anleitung zum Hinzufügen von Text zu XPS-Dokumenten mit Aspose.Page für .NET. Verbessern Sie Ihre .NET-Projekte mühelos.
type: docs
weight: 13
url: /de/net/text-manipulation/add-text-to-xps-document/
---
## Einführung

In der dynamischen Welt der .NET-Entwicklung sticht Aspose.Page als leistungsstarkes Tool für die Arbeit mit XPS-Dokumenten hervor. Das Hinzufügen von Text zu XPS-Dokumenten ist eine häufige Anforderung, und Aspose.Page vereinfacht diesen Prozess. In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Page für .NET nahtlos Text zu XPS-Dokumenten hinzufügen.

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Aspose.Page für .NET: Stellen Sie sicher, dass Sie die Aspose.Page-Bibliothek installiert haben. Sie können es hier herunterladen[Aspose.Page für .NET-Dokumentation](https://reference.aspose.com/page/net/).

-  Entwicklungsumgebung: Richten Sie Ihre .NET-Entwicklungsumgebung ein. Wenn Sie dies noch nicht getan haben, befolgen Sie die Installationsanweisungen im[Dokumentation](https://reference.aspose.com/page/net/).

- Dokumentenverzeichnis: Erstellen Sie ein Verzeichnis, in dem Sie Ihre Dokumente speichern. Ersetzen Sie „Ihr Dokumentverzeichnis“ im bereitgestellten Code-Snippet durch den tatsächlichen Pfad.

Kommen wir nun zur Schritt-für-Schritt-Anleitung.

## Namespaces importieren

Importieren wir zunächst die notwendigen Namespaces, um unser Projekt anzukurbeln:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Schritt 1: Erstellen Sie ein neues XPS-Dokument

Um mit Aspose.Page zu arbeiten, erstellen Sie ein neues XPS-Dokument. Dies ist die Leinwand, auf der wir unseren Text hinzufügen.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

## Schritt 2: Erstellen Sie einen Pinsel für Text

Erstellen wir nun einen Pinsel, um die Textfarbe zu definieren. In diesem Beispiel verwenden wir einen schwarzen Farbpinsel.

```csharp
// ExStart:4
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
// ExEnd:4
```

## Schritt 3: Fügen Sie dem Dokument Glyphen hinzu

Glyphen repräsentieren den Text in XPS-Dokumenten. Fügen Sie dem Dokument Glyphen mit der gewünschten Schriftart, Größe, Stil und Position hinzu.

```csharp
// ExStart:5
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.Fill = textFill;
// ExEnd:5
```

## Schritt 4: Speichern Sie das resultierende XPS-Dokument

Speichern Sie abschließend das XPS-Dokument mit dem hinzugefügten Text in Ihrem angegebenen Verzeichnis.

```csharp
// ExStart:6
doc.Save(dataDir + "AddText_out.xps");
// ExEnd:6
```

Indem Sie diese einfachen Schritte befolgen, haben Sie mit Aspose.Page für .NET erfolgreich Text zu einem XPS-Dokument hinzugefügt.

## Abschluss

Zusammenfassend bietet Aspose.Page für .NET eine unkomplizierte Lösung zum Hinzufügen von Text zu XPS-Dokumenten in Ihren .NET-Projekten. Die Einfachheit der Bibliothek in Kombination mit ihren robusten Funktionen macht sie zu einem unschätzbar wertvollen Werkzeug für die Dokumentenbearbeitung.

## Häufig gestellte Fragen

### F1: Kann ich die Schriftart und -größe des hinzugefügten Texts anpassen?

 A1: Ja, Sie haben die volle Kontrolle über Schriftart und -größe. Passen Sie die Parameter im an`AddGlyphs` Methode entsprechend anpassen.

### F2: Ist Aspose.Page mit .NET Core kompatibel?

A2: Auf jeden Fall! Aspose.Page unterstützt .NET Core und gewährleistet so die Kompatibilität mit den neuesten .NET-Technologien.

### F3: Gibt es Lizenzanforderungen für die Verwendung von Aspose.Page?

 A3: Ja, Sie benötigen eine gültige Lizenz. Entdecken Sie Lizenzoptionen[Hier](https://purchase.aspose.com/buy).

### F4: Wie kann ich Unterstützung erhalten oder Hilfe suchen?

 A4: Besuchen Sie die[Aspose.Page-Forum](https://forum.aspose.com/c/page/39) um mit der Community in Kontakt zu treten und Hilfe zu erhalten.

### F5: Gibt es eine kostenlose Testversion?

 A5: Auf jeden Fall! Sie können eine kostenlose Testversion erhalten[Hier](https://releases.aspose.com/).