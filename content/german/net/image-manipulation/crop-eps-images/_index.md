---
title: Beschneiden Sie EPS-Bilder mit Aspose.Page für .NET
linktitle: EPS-Bilder zuschneiden
second_title: Aspose.Page .NET-API
description: Entdecken Sie die nahtlose Welt der EPS-Bildbearbeitung in .NET mit Aspose.Page. Schneiden Sie Bilder mühelos zu und ändern Sie ihre Größe, um atemberaubende Ergebnisse zu erzielen.
type: docs
weight: 10
url: /de/net/image-manipulation/crop-eps-images/
---
## Einführung

Haben Sie Probleme mit der Manipulation von EPS-Bildern in Ihren .NET-Anwendungen? Suchen Sie nicht weiter! In diesem Tutorial führen wir Sie durch den Prozess des Zuschneidens von EPS-Bildern mithilfe der leistungsstarken Bibliothek Aspose.Page für .NET. Unabhängig davon, ob Sie ein erfahrener Entwickler sind oder gerade erst anfangen, hilft Ihnen diese Schritt-für-Schritt-Anleitung dabei, mühelos einen präzisen Bildzuschnitt zu erzielen.

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Grundkenntnisse in der .NET-Entwicklung.
-  Aspose.Page für .NET-Bibliothek installiert. Wenn nicht, können Sie es herunterladen[Hier](https://releases.aspose.com/page/net/).
- Ein Beispiel-EPS-Bild (ersetzen Sie „input.eps“ im Code durch Ihre tatsächliche Datei).

## Namespaces importieren

Beginnen wir mit dem Importieren der erforderlichen Namespaces, damit unser Code reibungslos funktioniert. 

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

Lassen Sie uns nun das Tutorial in mehrere Schritte unterteilen.

## Schritt 1: PsDocument initialisieren

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

 Initialisieren Sie a`PsDocument` Objekt mit dem Eingabe-EPS-Stream.

## Schritt 2: Begrenzungsrahmen extrahieren

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

Rufen Sie den anfänglichen Begrenzungsrahmen des EPS-Bilds ab.

## Schritt 3: Ausgabestream erstellen

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

Erstellen Sie einen Ausgabestream für das zugeschnittene EPS-Bild.

## Schritt 4: Definieren Sie einen neuen Begrenzungsrahmen

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

Definieren Sie einen neuen Begrenzungsrahmen für das Zuschneiden. Stellen Sie sicher, dass die neuen Werte innerhalb des ursprünglichen Begrenzungsrahmens liegen.

## Schritt 5: Zuschneiden und speichern

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

Schneiden Sie das EPS-Bild mithilfe des neuen Begrenzungsrahmens zu und speichern Sie es im Ausgabestream.

Wiederholen Sie diese Schritte für verschiedene Größenänderungsszenarien.

## Größenänderung von EPS-Bildern

### Größe in Zoll ändern

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

Ändern Sie die Größe des EPS-Bilds und speichern Sie es mit den angegebenen Abmessungen in Zoll.

### Größe in Millimeter ändern

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

Ändern Sie die Größe des EPS-Bildes und speichern Sie es mit den angegebenen Abmessungen in Millimetern.

### Größe in Prozent ändern

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

Ändern Sie die Größe des EPS-Bildes und speichern Sie es mit den angegebenen Abmessungen in Prozent.

## Abschluss

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie EPS-Bilder mit Aspose.Page für .NET zuschneiden und in der Größe ändern. Erweitern Sie jetzt Ihre Bildbearbeitungsfunktionen und bringen Sie Ihre .NET-Anwendungen auf die nächste Stufe.

## FAQs

### F1: Kann ich Aspose.Page für .NET mit anderen Bildformaten verwenden?

A1: Aspose.Page konzentriert sich hauptsächlich auf EPS-Bilder, Aspose bietet jedoch verschiedene Bibliotheken für verschiedene Formate. Überprüfen Sie die Dokumentation auf bestimmte Formate.

### F2: Wie kann ich eine temporäre Lizenz für Aspose.Page für .NET erhalten?

 A2: Besuchen[dieser Link](https://purchase.aspose.com/temporary-license/) um eine temporäre Lizenz zum Testen zu erhalten.

### F3: Gibt es Einschränkungen hinsichtlich der Bildgröße, die ich mit Aspose.Page für .NET verarbeiten kann?

A3: Aspose.Page ist für die Verarbeitung von Bildern unterschiedlicher Größe konzipiert. Die Leistung kann jedoch je nach Komplexität des Bildes variieren.

### F4: Gibt es ein Community-Forum für Aspose.Page-Diskussionen?

 A4: Ja, Sie können mit der Aspose.Page-Community interagieren[Hier](https://forum.aspose.com/c/page/39).

### F5: Wo finde ich eine ausführliche Dokumentation für Aspose.Page für .NET?

 A5: Sehen Sie sich die Dokumentation an[Hier](https://reference.aspose.com/page/net/).