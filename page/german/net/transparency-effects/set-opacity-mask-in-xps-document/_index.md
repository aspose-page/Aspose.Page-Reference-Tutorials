---
title: Legen Sie die Deckkraftmaske im XPS-Dokument mit Aspose.Page für .NET fest
linktitle: Legen Sie die Deckkraftmaske im XPS-Dokument fest
second_title: Aspose.Page .NET-API
description: Erfahren Sie, wie Sie mit Aspose.Page für .NET Deckkraftmasken in XPS-Dokumenten festlegen. Verbessern Sie mühelos die Ästhetik von Dokumenten.
weight: 12
url: /de/net/transparency-effects/set-opacity-mask-in-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Legen Sie die Deckkraftmaske im XPS-Dokument mit Aspose.Page für .NET fest

## Einführung

Deckkraftmasken sind unerlässlich, wenn Sie optisch ansprechende Dokumente mit unterschiedlichen Transparenzgraden erstellen möchten. Aspose.Page für .NET vereinfacht diesen Prozess und bietet Entwicklern einen umfassenden Satz an Tools zur Verbesserung von XPS-Dokumenten. In diesem Tutorial erfahren Sie in einer Schritt-für-Schritt-Anleitung, wie Sie eine Deckkraftmaske festlegen.

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

-  Aspose.Page für .NET: Stellen Sie sicher, dass Sie die Bibliothek installiert haben. Wenn nicht, können Sie es hier herunterladen[Webseite](https://releases.aspose.com/page/net/).

- Dokumentenverzeichnis: Richten Sie ein Verzeichnis zum Speichern Ihrer XPS-Dokumente ein.

## Namespaces importieren

Beginnen Sie in Ihrem .NET-Projekt mit dem Importieren der erforderlichen Namespaces:

```csharp
using Aspose.Page.Xps;
using Aspose.Page.Xps.XpsModel;
using Aspose.Page.Xps.XpsModel.Shapes;
using Aspose.Page.Xps.XpsModel.Text;
using System.Drawing;
```

## Schritt 1: Erstellen Sie ein neues XPS-Dokument

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "Your Document Directory";
// Erstellen Sie ein neues XPS-Dokument
XpsDocument doc = new XpsDocument();
```

Beginnen Sie mit der Erstellung eines neuen XPS-Dokuments mit Aspose.Page für .NET.

## Schritt 2: Canvas zur XpsDocument-Instanz hinzufügen

```csharp
// Canvas zur XpsDocument-Instanz hinzufügen
XpsCanvas canvas = doc.AddCanvas();
```

Fügen Sie nun dem XPS-Dokument eine Leinwand hinzu. Die Leinwand dient als Container für verschiedene grafische Elemente.

## Schritt 3: Rechteck mit Deckkraftmaske hinzufügen

```csharp
// Rechteck mit durch ImageBrush maskierter Deckkraft
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.OpacityMask = doc.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)path.OpacityMask).TileMode = XpsTileMode.Tile;
```

 Fügen Sie der Leinwand ein Rechteck hinzu und legen Sie dessen Deckkraft mit fest`OpacityMask`Eigentum. In diesem Beispiel verwenden wir ein Bild als Deckkraftmaske.

## Schritt 4: Speichern Sie das resultierende XPS-Dokument

```csharp
// Speichern Sie das resultierende XPS-Dokument
doc.Save(dataDir + "OpacityMask_out.xps");
```

Speichern Sie abschließend das geänderte XPS-Dokument mit der angewendeten Deckkraftmaske.

## Abschluss

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Page für .NET Deckkraftmasken in XPS-Dokumenten festlegen. Diese Funktion eröffnet eine Fülle kreativer Möglichkeiten für die Gestaltung anspruchsvoller und optisch ansprechender Dokumente.

## FAQs

### F1: Kann ich Deckkraftmasken auch auf andere Formen als Rechtecke anwenden?

A1: Ja, mit Aspose.Page für .NET können Sie Deckkraftmasken auf verschiedene Formen anwenden, darunter Kreise, Polygone und benutzerdefinierte Pfade.

### F2: Ist die Deckkraftmaske auf Bilder beschränkt?

A2: Nein, während in diesem Tutorial ein Bild als Deckkraftmaske verwendet wurde, können Sie Volltonfarben, Verläufe oder sogar Muster verwenden.

### F3: Gibt es erweiterte Optionen zur Feinabstimmung der Deckkraft?

A3: Auf jeden Fall bietet Aspose.Page für .NET eine detaillierte Kontrolle über die Deckkrafteinstellungen, sodass Sie präzise Transparenzeffekte erzielen können.

### F4: Kann ich mehrere Deckkraftmasken auf ein einzelnes Element anwenden?

A4: Ja, Sie können mehrere Deckkraftmasken übereinander legen, um komplexe Transparenzeffekte zu erzeugen.

### F5: Ist Aspose.Page mit anderen Dokumentformaten kompatibel?

A5: Aspose.Page konzentriert sich hauptsächlich auf XPS-Dokumente, Aspose bietet jedoch eine Reihe von Produkten für die Verarbeitung verschiedener Formate.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
