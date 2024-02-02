---
title: Fügen Sie mit Aspose.Page eine Kreisellipse zu PostScript (PS) hinzu
linktitle: Kreisellipse zu PostScript hinzufügen (PS)
second_title: Aspose.Page .NET-API
description: Erfahren Sie, wie Sie mit Aspose.Page für .NET mühelos Kreisellipsen zu PostScript-Dokumenten (PS) hinzufügen. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für eine nahtlose Integration.
type: docs
weight: 10
url: /de/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
---
## Einführung

Willkommen zu diesem umfassenden Tutorial zum Hinzufügen von Kreisellipsen zu PostScript-Dokumenten (PS) mit Aspose.Page für .NET. Aspose.Page ist eine leistungsstarke Bibliothek, die Entwicklern die nahtlose Arbeit mit PostScript und anderen Dokumentformaten ermöglicht. In diesem Leitfaden führen wir Sie durch den Prozess der einfachen Integration von Kreisellipsen in Ihre PS-Dokumente.

## Voraussetzungen

Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1.  Aspose.Page für .NET-Bibliothek: Laden Sie die Aspose.Page für .NET-Bibliothek von herunter und installieren Sie sie[Hier](https://releases.aspose.com/page/net/).

2. Entwicklungsumgebung: Stellen Sie sicher, dass auf Ihrem Computer eine funktionierende .NET-Entwicklungsumgebung eingerichtet ist.

Beginnen wir nun mit der Schritt-für-Schritt-Anleitung.

## Namespaces importieren

Im ersten Schritt müssen Sie die notwendigen Namespaces importieren, um die Aspose.Page-Funktionalität in Ihrem Code verfügbar zu machen.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Lassen Sie uns nun das bereitgestellte Beispiel in mehrere Schritte unterteilen, um Sie durch den Prozess des Hinzufügens von Kreisellipsen zu einem PostScript-Dokument zu führen.

## Schritt 1: Legen Sie das Dokumentverzeichnis fest

```csharp
// ExStart:1
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "Your Document Directory";
```

Stellen Sie sicher, dass Sie „Ihr Dokumentenverzeichnis“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis ersetzen.

## Schritt 2: Ausgabestream für PostScript-Dokument erstellen

```csharp
//Erstellen Sie einen Ausgabestream für ein PostScript-Dokument
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

Hier wird ein FileStream erstellt, um das PostScript-Dokument zu schreiben, und der Dateimodus wird so eingestellt, dass eine neue Datei erstellt wird.

## Schritt 3: Speicheroptionen und PS-Dokument erstellen

```csharp
//Erstellen Sie Speicheroptionen im A4-Format
PsSaveOptions options = new PsSaveOptions();

// Erstellen Sie ein neues einseitiges PS-Dokument
PsDocument document = new PsDocument(outPsStream, options, false);
```

Dieser Schritt umfasst das Erstellen von Speicheroptionen im A4-Format und das Initialisieren eines neuen einseitigen PS-Dokuments.

## Schritt 4: Erstellen Sie einen Grafikpfad für die erste Ellipse

```csharp
//Erstellen Sie einen Grafikpfad aus der ersten Ellipse
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

Für die erste Ellipse wird ein Grafikpfad erstellt, der ihre Position und Abmessungen angibt.

## Schritt 5: Legen Sie die Farbe fest und füllen Sie die Ellipse

```csharp
//Farbe einstellen
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//Füllen Sie die Ellipse
document.Fill(path);
```

Hier wird die Farbe eingestellt und die erste Ellipse mit der angegebenen Farbe gefüllt.

## Schritt 6: Erstellen Sie einen Grafikpfad für die zweite Ellipse

```csharp
//Erstellen Sie einen Grafikpfad aus der zweiten Ellipse
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

Auf ähnliche Weise wird ein Grafikpfad für die zweite Ellipse erstellt, der deren Position und Abmessungen definiert.

## Schritt 7: Legen Sie den Strich fest und zeichnen Sie die Ellipse

```csharp
//Hub einstellen
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//Zeichnen Sie einen Umriss der Ellipse
document.Draw(path);
```

In diesem Schritt wird der Strich festgelegt und die zweite Ellipse mit der angegebenen Farbe und Linienstärke umrandet.

## Schritt 8: Schließen Sie die aktuelle Seite und speichern Sie das Dokument

```csharp
//Aktuelle Seite schließen
document.ClosePage();

//Speichern Sie das Dokument
document.Save();
```

Abschließend wird die aktuelle Seite geschlossen und das gesamte Dokument gespeichert, wodurch der Vorgang abgeschlossen ist.

## Abschluss

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Page für .NET Kreisellipsen zu PostScript-Dokumenten hinzufügen. Dieses Tutorial bietet eine detaillierte Schritt-für-Schritt-Anleitung, die Ihnen hilft, diese Funktionalität nahtlos in Ihre Projekte zu integrieren.

## FAQs

### F1: Kann ich Aspose.Page für .NET mit anderen Dokumentformaten verwenden?

 A1: Aspose.Page konzentriert sich hauptsächlich auf PostScript, Aspose bietet jedoch auch andere Bibliotheken für verschiedene Dokumentformate. Überprüf den[Dokumentation bereitstellen](https://reference.aspose.com/page/net/) für mehr Details.

### F2: Wo finde ich zusätzlichen Support und Community-Diskussionen?

 A2: Besuchen Sie die[Aspose.Page-Forum](https://forum.aspose.com/c/page/39) für Community-Diskussionen und Unterstützung.

### F3: Gibt es eine kostenlose Testversion für Aspose.Page für .NET?

 A3: Ja, Sie können darauf zugreifen[Kostenlose Testphase](https://releases.aspose.com/)um die Funktionen von Aspose.Page für .NET zu erkunden.

### F4: Wie kann ich eine temporäre Lizenz für Aspose.Page erhalten?

 A4: Besorgen Sie sich eine temporäre Lizenz[Hier](https://purchase.aspose.com/temporary-license/) zu Test- und Evaluierungszwecken.

### F5: Wo kann ich Aspose.Page für .NET kaufen?

 A5: Kaufen Sie Aspose.Page für .NET bei[Kaufseite](https://purchase.aspose.com/buy).