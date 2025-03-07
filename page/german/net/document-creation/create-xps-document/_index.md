---
title: Erstellen Sie ein XPS-Dokument mit Aspose.Page für .NET
linktitle: Erstellen Sie ein XPS-Dokument
second_title: Aspose.Page .NET-API
description: Entdecken Sie die Welt der XPS-Dokumenterstellung mit Aspose.Page für .NET. Befolgen Sie unsere Schritt-für-Schritt-Anleitung, um mühelos elektronische Dokumente zu erstellen.
weight: 10
url: /de/net/document-creation/create-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen Sie ein XPS-Dokument mit Aspose.Page für .NET

## Einführung

Willkommen zu unserer Schritt-für-Schritt-Anleitung zum Erstellen von XPS-Dokumenten mit Aspose.Page für .NET. In diesem Tutorial untersuchen wir den Prozess der Generierung von XPS-Dateien, einem weit verbreiteten Format für elektronische Dokumente. Unabhängig davon, ob Sie ein erfahrener Entwickler sind oder gerade erst mit Aspose.Page beginnen, ist dieser Leitfaden darauf zugeschnitten, Ihnen bei der nahtlosen Erstellung von XPS-Dokumenten mit klaren Beispielen und detaillierten Erklärungen zu helfen.

## Voraussetzungen

Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1.  Aspose.Page für .NET-Bibliothek: Laden Sie die Aspose.Page-Bibliothek von herunter und installieren Sie sie[Download-Link](https://releases.aspose.com/page/net/).

2. Ihr Dokumentverzeichnis: Wählen oder erstellen Sie ein Verzeichnis auf Ihrem System, in dem Sie die ausgegebenen XPS-Dateien speichern möchten.

Kommen wir nun zum Tutorial!

## Namespaces importieren

Um Aspose.Page für .NET verwenden zu können, müssen Sie die erforderlichen Namespaces in Ihr Projekt importieren. Folge diesen Schritten:

### Schritt 1: Verweis auf Aspose.Page hinzufügen

Fügen Sie in Ihrem Projekt einen Verweis auf die Aspose.Page for .NET-Bibliothek hinzu. Die benötigte DLL finden Sie im heruntergeladenen Paket.

### Schritt 2: Namespaces importieren

Fügen Sie die folgenden Namespaces in Ihre Codedatei ein:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Nachdem wir nun die Voraussetzungen eingerichtet und die erforderlichen Namespaces importiert haben, unterteilen wir den Prozess der Erstellung eines XPS-Dokuments in mehrere Schritte.

## Schritt 1: Dokumentverzeichnis festlegen

```csharp
string dir = "Your Document Directory";
```

 Stellen Sie sicher, dass Sie es ersetzen`"Your Document Directory"` mit dem tatsächlichen Pfad, in dem Sie die XPS-Ausgabedatei speichern möchten.

## Schritt 2: XPS-Dokument erstellen

```csharp
XpsDocument xDocs = new XpsDocument();
```

 Initialisieren Sie ein neues XPS-Dokument mit`XpsDocument` Klasse.

## Schritt 3: Fügen Sie dem Dokument Glyphen hinzu

```csharp
var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
```

 Benutzen Sie die`AddGlyphs` Methode zum Hinzufügen von Glyphen (Text) zum Dokument. Passen Sie Schriftart, Größe, Stil und Position nach Bedarf an.

## Schritt 4: Legen Sie die Glyphenfüllfarbe fest

```csharp
glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);
```

Geben Sie die Füllfarbe für die hinzugefügten Glyphen an. In diesem Beispiel verwenden wir Schwarz, Sie können jedoch jede beliebige Farbe wählen.

## Schritt 5: Speichern Sie das Ergebnis

```csharp
xDocs.Save(dir + "output.xps");
```

Speichern Sie abschließend das XPS-Dokument mit dem gewünschten Dateinamen im angegebenen Verzeichnis. Die resultierende XPS-Datei enthält den Text „Hello World!“. Text.

Glückwunsch! Sie haben erfolgreich ein XPS-Dokument mit Aspose.Page für .NET erstellt.

## Abschluss

In diesem Tutorial haben wir den Prozess der Erstellung von XPS-Dokumenten mit Aspose.Page für .NET durchlaufen. Diese leistungsstarke Bibliothek bietet eine nahtlose Möglichkeit, problemlos elektronische Dokumente zu erstellen. Experimentieren Sie mit verschiedenen Schriftarten, Stilen und Inhalten, um Ihre XPS-Dateien an Ihre spezifischen Bedürfnisse anzupassen.

## FAQs

### F1: Kann ich in meinem XPS-Dokument benutzerdefinierte Schriftarten verwenden?

A1: Ja, Sie können die Schriftfamilie und -größe angeben, wenn Sie Glyphen zu Ihrem XPS-Dokument hinzufügen.

### F2: Ist Aspose.Page mit .NET Core kompatibel?

A2: Ja, Aspose.Page unterstützt .NET Core, sodass Sie es in plattformübergreifenden Anwendungen verwenden können.

### F3: Wie kann ich Bilder zu einem XPS-Dokument hinzufügen?

A3: Aspose.Page bietet Methoden zum Hinzufügen von Bildern zu Ihrem XPS-Dokument. Detaillierte Beispiele finden Sie in der Dokumentation.

### F4: Kann ich mehrseitige XPS-Dokumente erstellen?

A4: Auf jeden Fall! Mithilfe der Aspose.Page-Bibliothek können Sie Ihrem XPS-Dokument mehrere Seiten hinzufügen.

### F5: Gibt es eine Testversion?

 A5: Ja, Sie können die Funktionen von Aspose.Page erkunden, indem Sie das herunterladen[Kostenlose Testphase](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
