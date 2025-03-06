---
title: Ändern Sie die Größe von EPS-Bildern mit Aspose.Page für .NET
linktitle: Ändern Sie die Größe von EPS-Bildern
second_title: Aspose.Page .NET-API
description: Entdecken Sie den nahtlosen Prozess der Größenänderung von EPS-Bildern in .NET mit Aspose.Page. Erzielen Sie mühelos Präzision in Punkten, Zoll, Millimetern und Prozentsätzen.
weight: 11
url: /de/net/image-manipulation/resize-eps-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ändern Sie die Größe von EPS-Bildern mit Aspose.Page für .NET

## Einführung

Möchten Sie die Größe von EPS-Bildern nahtlos mit Aspose.Page für .NET ändern? Dieses Tutorial ist Ihr umfassender Leitfaden zum mühelosen Bearbeiten der Größe von EPS-Bildern in verschiedenen Einheiten wie Punkt, Zoll, Millimeter und Prozent. Aspose.Page für .NET bietet eine Reihe leistungsstarker Tools. In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess.

## Voraussetzungen

Bevor Sie in die Magie der Größenänderung eintauchen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Aspose.Page für .NET-Bibliothek: Stellen Sie sicher, dass die Aspose.Page für .NET-Bibliothek installiert ist. Sie können es herunterladen unter[Hier](https://releases.aspose.com/page/net/).

- Dokumentverzeichnis: Erstellen Sie ein Verzeichnis, in dem Sie Ihre Eingabe-EPS-Datei und die Ausgabedateien mit geänderter Größe speichern.

Nachdem Sie nun alles eingerichtet haben, beginnen wir mit dem Import der erforderlichen Namespaces und vertiefen uns in die Schritt-für-Schritt-Anleitung.

## Namespaces importieren

Beginnen Sie in Ihrem .NET-Projekt mit dem Importieren der erforderlichen Namespaces für die Arbeit mit Aspose.Page. Fügen Sie den folgenden Code am Anfang Ihrer Datei hinzu:

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

## Schritt 1: Größenänderung in Punkten

Beginnen wir mit der Größenänderung eines EPS-Bildes in Punkten. Punkte sind eine Standardmaßeinheit in der Druckindustrie.

```csharp
public static void ResizeInPoints()
{
    // Ihr Dokumentenverzeichnis
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_points.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(oldSize.Width * 2, oldSize.Height * 2), Units.Points);
        }
    }
}
```

## Schritt 2: Größenänderung in Zoll

Lassen Sie uns nun die Größe eines EPS-Bildes in Zoll ändern, einer im Grafikdesign üblichen Einheit.

```csharp
public static void ResizeInInches()
{
    // Ihr Dokumentenverzeichnis
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_inches.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
        }
    }
}
```

## Schritt 3: Größenänderung in Millimetern

Lassen Sie uns nun die Größe eines EPS-Bildes in Millimetern ändern, einer weiteren häufig verwendeten Einheit in Design und Druck.

```csharp
public static void ResizeInMillimeters()
{
    // Ihr Dokumentenverzeichnis
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_mms.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
        }
    }
}
```

## Schritt 4: Größenänderung in Prozent

Abschließend ändern wir die Größe eines EPS-Bilds mithilfe von Prozentsätzen und bieten so einen flexiblen Ansatz zum Anpassen der Bildgröße.

```csharp
public static void ResizeInPercents()
{
    // Ihr Dokumentenverzeichnis
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_percents.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
        }
    }
}
```

Integrieren Sie diese Methoden gerne in Ihr Projekt und Sie können die Größe von EPS-Bildern mühelos ändern. Experimentieren Sie mit verschiedenen Einheiten, um die gewünschten Abmessungen zu erreichen.

## Abschluss

Glückwunsch! Sie beherrschen die Kunst der Größenänderung von EPS-Bildern mit Aspose.Page für .NET. Diese leistungsstarke Bibliothek eröffnet eine Welt voller Möglichkeiten zur Bearbeitung von Vektorgrafiken. Egal, ob Sie für Print- oder digitale Medien entwerfen, mit Aspose.Page können Sie präzise und individuelle Ergebnisse erzielen.

## FAQs

### F1: Kann ich die Größe mehrerer EPS-Bilder gleichzeitig ändern?

A1: Ja, Sie können eine Sammlung von EPS-Dateien durchlaufen und die Größenänderungsmethoden entsprechend anwenden.

### F2: Ist Aspose.Page mit anderen Bildformaten kompatibel?

A2: Aspose.Page konzentriert sich hauptsächlich auf PostScript- und EPS-Formate. Erwägen Sie für andere Bildformate die Verwendung von Aspose.Imaging.

### F3: Gibt es Lizenzierungsaspekte für kommerzielle Projekte?

 A3: Ja, stellen Sie sicher, dass Sie über eine gültige Lizenz verfügen. Besuchen[Hier](https://purchase.aspose.com/buy) für Lizenzdetails.

### F4: Kann ich Aspose.Page vor dem Kauf testen?

 A4: Auf jeden Fall! Sie können eine kostenlose Testversion erhalten[Hier](https://releases.aspose.com/).

### F5: Wo kann ich zusätzliche Hilfe suchen oder Probleme besprechen?

 A5: Besuchen Sie die[Aspose.Page-Forum](https://forum.aspose.com/c/page/39) um mit der Community in Kontakt zu treten und Hilfe zu erhalten.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
