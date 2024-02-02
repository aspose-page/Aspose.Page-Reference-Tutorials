---
title: Fügen Sie mit Aspose.Page Text mit Unicode-Zeichenfolge zum XPS-Dokument hinzu
linktitle: Fügen Sie Text mit Unicode-Zeichenfolge zum XPS-Dokument hinzu
second_title: Aspose.Page .NET-API
description: Entdecken Sie die Leistungsfähigkeit von Aspose.Page für .NET mit unserer Schritt-für-Schritt-Anleitung zum Hinzufügen von Unicode-Text zu XPS-Dokumenten.
type: docs
weight: 12
url: /de/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
---
## Einführung

In der sich ständig weiterentwickelnden Landschaft der .NET-Entwicklung sticht Aspose.Page als leistungsstarkes Tool für den Umgang mit XPS-Dokumenten hervor. Unter den vielen Funktionen ist die Möglichkeit, Text mit Unicode-Strings zu einem XPS-Dokument hinzuzufügen, eine wertvolle Funktionalität. Diese Schritt-für-Schritt-Anleitung führt Sie durch den Prozess und stellt sicher, dass Sie diese Funktion effektiv nutzen.

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Ein grundlegendes Verständnis der .NET-Entwicklung.
- Visual Studio ist auf Ihrem Computer installiert.
-  Aspose.Page für .NET-Bibliothek. Sie können es herunterladen unter[Hier](https://releases.aspose.com/page/net/).

## Namespaces importieren

Stellen Sie zunächst sicher, dass Sie die erforderlichen Namespaces in Ihr Projekt importieren. Dadurch werden die erforderlichen Klassen und Funktionalitäten für die Arbeit mit Aspose.Page bereitgestellt. Hier sind die wesentlichen Namensräume:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Schritt 1: Richten Sie das Dokument ein

Erstellen Sie zunächst ein neues XPS-Dokument, in dem Sie den Unicode-Text hinzufügen. Folgen Sie dem folgenden Codeausschnitt:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "Your Document Directory";
// Erstellen Sie ein neues XPS-Dokument
XpsDocument doc = new XpsDocument();
```

## Schritt 2: Unicode-Text hinzufügen

Fügen wir nun Unicode-Text zum XPS-Dokument hinzu. In diesem Beispiel wird die Schriftart Arial verwendet, die Schriftgröße auf 20 festgelegt und der Text an den Koordinaten (400f, 200f) positioniert. Die Unicode-Zeichenfolge lautet in diesem Fall „TEN. rof SPX.esopsA“. Schauen Sie sich den folgenden Codeausschnitt an:

```csharp
// Text hinzufügen
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Schritt 3: Speichern Sie das Dokument

Sobald der Unicode-Text hinzugefügt wurde, speichern Sie das resultierende XPS-Dokument. Hier ist der letzte Schritt:

```csharp
// Speichern Sie das resultierende XPS-Dokument
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Glückwunsch! Sie haben mit Aspose.Page für .NET erfolgreich Unicode-Text zu einem XPS-Dokument hinzugefügt.

## Abschluss

In diesem Tutorial haben wir den Prozess des Hinzufügens von Unicode-Text zu XPS-Dokumenten mithilfe von Aspose.Page für .NET untersucht. Diese Funktionalität öffnet Türen für eine vielfältige und dynamische Dokumentenerstellung innerhalb der .NET-Umgebung.

## FAQs

### F1: Ist Aspose.Page mit den neuesten .NET-Frameworks kompatibel?

A1: Ja, Aspose.Page wird regelmäßig aktualisiert, um die Kompatibilität mit den neuesten .NET-Frameworks sicherzustellen.

### F2: Kann ich beim Hinzufügen von Text den Schriftstil und die Schriftgröße anpassen?

A2: Auf jeden Fall! Mit dem bereitgestellten Beispielcode können Sie Schriftart, Größe und andere Attribute einfach anpassen.

### F3: Wo finde ich zusätzliche Dokumentation für Aspose.Page?

 A3: Sie können sich auf die Dokumentation beziehen[Hier](https://reference.aspose.com/page/net/) Ausführliche Informationen und Beispiele finden Sie hier.

### F4: Gibt es kostenlose Ressourcen für den Einstieg in Aspose.Page?

 A4: Ja, Sie können das erkunden[Aspose.Page-Forum](https://forum.aspose.com/c/page/39) für Community-Unterstützung und Diskussionen.

### F5: Gibt es vor dem Kauf eine Testversion?

 A5: Auf jeden Fall! Sie können auf die kostenlose Testversion zugreifen[Hier](https://releases.aspose.com/) bevor Sie einen Kauf tätigen.