---
date: 2026-03-03
description: Erfahren Sie, wie Sie EPS‑Bilder in .NET mit Aspose.Page skalieren –
  eine Schritt‑für‑Schritt‑Anleitung zum Ändern der Größe von EPS mit Punkten, Zoll,
  Millimetern oder Prozent.
linktitle: Resize EPS Images
second_title: Aspose.Page .NET API
title: Wie man EPS-Bilder mit Aspose.Page für .NET in der Größe ändert
url: /de/net/image-manipulation/resize-eps-images/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man EPS‑Bilder mit Aspose.Page für .NET skaliert

## Einführung

Suchen Sie **nach einer Möglichkeit, EPS‑Bilder** nahtlos mit Aspose.Page für .NET zu skalieren? Dieses Tutorial ist Ihr umfassender Leitfaden, um die Größe von EPS‑Bildern in verschiedenen Einheiten wie Punkten, Zoll, Millimetern und Prozentwerten mühelos zu ändern. Aspose.Page für .NET bietet ein leistungsstarkes Set‑von‑Tools, und in diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess.

## Schnellantworten
- **Welche Bibliothek übernimmt das Skalieren von EPS?** Aspose.Page für .NET  
- **Welche Einheiten werden unterstützt?** Punkte, Zoll, Millimeter und Prozent  
- **Benötige ich eine Lizenz für die Produktion?** Ja – eine kommerzielle Lizenz ist erforderlich  
- **Kann ich mehrere Dateien gleichzeitig skalieren?** Absolut – einfach über die Dateien iterieren  
- **Wird .NET Core unterstützt?** Ja, die API funktioniert mit .NET Framework und .NET Core  

## Was ist EPS‑Skalierung?
Encapsulated PostScript (EPS) ist ein vektorbasierter Grafikstandard, der häufig in Druck‑ und Design‑Workflows verwendet wird. Das Skalieren einer EPS‑Datei ändert ihre Begrenzungsbox, ohne die Grafik zu rasterisieren, und bewahrt so die Schärfe bei jeder Größe.

## Warum EPS‑Bilder skalieren?
- **Druckqualität erhalten:** Vektorskalierung hält Kanten scharf.  
- **Layout‑Anforderungen erfüllen:** Abmessungen an Seiten‑ oder Leinwandgrößen anpassen.  
- **Batch‑Jobs automatisieren:** Programmatisch Dutzende von Dateien in Sekunden skalieren.  

## Voraussetzungen

Bevor Sie mit der Skalier‑Magie beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Aspose.Page für .NET Bibliothek: Vergewissern Sie sich, dass die Aspose.Page für .NET Bibliothek installiert ist. Sie können sie von [hier](https://releases.aspose.com/page/net/) herunterladen.

- Dokumenten‑Verzeichnis: Erstellen Sie ein Verzeichnis, in dem Sie Ihre Eingabe‑EPS‑Datei und die ausgegebenen, skalierten Dateien speichern.

Jetzt, wo alles eingerichtet ist, fahren wir fort, die erforderlichen Namespaces zu importieren und gehen die Schritt‑für‑Schritt‑Anleitung durch.

## Namespaces importieren

Importieren Sie in Ihrem .NET‑Projekt die notwendigen Namespaces, um mit Aspose.Page zu arbeiten. Fügen Sie den folgenden Code am Anfang Ihrer Datei hinzu:

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

## EPS in Punkten skalieren

Punkte sind eine gängige Maßeinheit in der Druckindustrie. Das nachfolgende Beispiel verdoppelt die ursprüngliche Breite und Höhe.

```csharp
public static void ResizeInPoints()
{
    // Your Document Directory
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

## EPS in Zoll skalieren

Zoll werden von Grafikdesignern häufig verwendet, wenn sie Assets für den Druck vorbereiten.

```csharp
public static void ResizeInInches()
{
    // Your Document Directory
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

## EPS in Millimetern skalieren

Millimeter sind in Regionen üblich, die das metrische System verwenden.

```csharp
public static void ResizeInMillimeters()
{
    // Your Document Directory
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

## EPS mit Prozentwerten skalieren

Prozentbasierte Skalierung ermöglicht es, das Bild relativ zu seiner Originalgröße zu vergrößern oder zu verkleinern.

```csharp
public static void ResizeInPercents()
{
    // Your Document Directory
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

Integrieren Sie diese Methoden in Ihr Projekt, und Sie werden EPS‑Bilder mühelos skalieren. Experimentieren Sie mit verschiedenen Einheiten, um die gewünschten Abmessungen zu erreichen.

## Häufige Probleme und Lösungen
- **Datei nicht gefunden:** Prüfen Sie, ob `dataDir` auf den richtigen Ordner zeigt und `input.eps` existiert.  
- **Unerwartete Größe:** Denken Sie daran, dass `Units.Percents` Werte wie 150 für 150 % der Originalgröße erwartet.  
- **Lizenz‑Ausnahme:** Wenn ein Lizenzfehler angezeigt wird, stellen Sie sicher, dass eine gültige Aspose.Page‑Lizenzdatei geladen wird, bevor `PsDocument` erstellt wird.

## Fazit

Herzlichen Glückwunsch! Sie haben **gelernt, wie man EPS‑Bilder** mit Aspose.Page für .NET skaliert. Diese leistungsstarke Bibliothek eröffnet zahlreiche Möglichkeiten zur Manipulation von Vektorgrafiken. Egal, ob Sie für Druck oder digitale Medien designen, Aspose.Page ermöglicht Ihnen präzise und individuell angepasste Ergebnisse.

## FAQ's

### Q1: Kann ich mehrere EPS‑Bilder gleichzeitig skalieren?

A1: Ja, Sie können über eine Sammlung von EPS‑Dateien iterieren und die Skalierungsmethoden entsprechend anwenden.

### Q2: Ist Aspose.Page mit anderen Bildformaten kompatibel?

A2: Aspose.Page konzentriert sich hauptsächlich auf PostScript‑ und EPS‑Formate. Für andere Bildformate sollten Sie Aspose.Imaging in Betracht ziehen.

### Q3: Gibt es Lizenz‑Überlegungen für kommerzielle Projekte?

A3: Ja, stellen Sie sicher, dass Sie eine gültige Lizenz besitzen. Besuchen Sie [hier](https://purchase.aspose.com/buy) für Lizenzdetails.

### Q4: Kann ich Aspose.Page vor dem Kauf testen?

A4: Absolut! Sie können eine kostenlose Testversion [hier](https://releases.aspose.com/) erhalten.

### Q5: Wo finde ich zusätzliche Hilfe oder kann über Probleme diskutieren?

A5: Besuchen Sie das [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39), um mit der Community in Kontakt zu treten und Unterstützung zu erhalten.

## Häufig gestellte Fragen

**F: Funktioniert dieser Code mit .NET Core 6?**  
A: Ja. Die API ist kompatibel mit .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ und .NET 6+.

**F: Wie kann ich das ursprüngliche Farbprofil erhalten?**  
A: Die Methode `ResizeEps` ändert keine Farbdaten; sie ändert nur die Begrenzungsbox.

**F: Ist es möglich, ein EPS zu skalieren, ohne die gesamte Datei in den Speicher zu laden?**  
A: Die Verwendung eines Streams, wie gezeigt, hält den Speicherverbrauch niedrig; das Dokument wird on‑the‑fly verarbeitet.

**F: Kann ich mehrere Skalierungsoperationen hintereinander ausführen?**  
A: Absolut. Rufen Sie `ResizeEps` nacheinander auf derselben `PsDocument`‑Instanz auf.

**F: Was passiert mit eingebetteten Bildern im EPS?**  
A: Sie werden proportional zum Vektorinhalt skaliert und behalten ihre Qualität bei.

---

**Zuletzt aktualisiert:** 2026-03-03  
**Getestet mit:** Aspose.Page 24.12 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}