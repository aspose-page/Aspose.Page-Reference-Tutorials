---
title: Ändern Sie Werte mit Aspose.Page für .NET
linktitle: Werte ändern
second_title: Aspose.Page .NET-API
description: Meistern Sie die Bearbeitung von EPS-Dateien mit Aspose.Page für .NET. Ändern Sie XMP-Metadatenwerte mühelos.
weight: 17
url: /de/net/eps-metadata-management/modify-eps-metadata-change-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ändern Sie Werte mit Aspose.Page für .NET

## Einführung

In der dynamischen Welt der Dokumentenverarbeitung sticht Aspose.Page für .NET als leistungsstarkes Tool hervor, das Entwicklern die Möglichkeit bietet, EPS-Dateien mühelos zu bearbeiten. In diesem Tutorial befassen wir uns mit dem Prozess der Werteänderung in EPS-Dateien mithilfe von Aspose.Page für .NET. Egal, ob Sie ein erfahrener Entwickler oder ein neugieriger Anfänger sind, diese Schritt-für-Schritt-Anleitung vermittelt Ihnen die erforderlichen Fähigkeiten, um XMP-Metadaten in Ihren EPS-Dateien effizient zu ändern.

## Voraussetzungen

Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

### 1. Aspose.Page für .NET-Bibliothek

Stellen Sie sicher, dass die Aspose.Page for .NET-Bibliothek in Ihrer Entwicklungsumgebung installiert ist. Wenn nicht, können Sie es herunterladen[Hier](https://releases.aspose.com/page/net/).

### 2. Dokumentenverzeichnis

Richten Sie ein Verzeichnis für Ihre Dokumente ein. Dies ist der Ort, an dem Ihre EPS-Dateien gespeichert werden.

Nachdem wir nun unsere Voraussetzungen geklärt haben, gehen wir zu den nächsten entscheidenden Schritten über.

## Namespaces importieren

In jedem .NET-Projekt ist es wichtig, die erforderlichen Namespaces zu importieren, um die Funktionen von Aspose.Page nutzen zu können. So können Sie es machen:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Schritt 1: Initialisieren Sie den EPS-Datei-Eingabestream

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "Your Document Directory";
// Initialisieren Sie den EPS-Datei-Eingabestream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

## Schritt 2: Erstellen Sie eine PsDocument-Instanz aus dem Stream

```csharp
//Erstellen Sie eine PsDocument-Instanz aus dem Stream
PsDocument document = new PsDocument(psStream);
```

Nachdem wir nun die Voraussetzungen geschaffen haben, gehen wir zum Kern unseres Tutorials über – dem Ändern der XMP-Metadatenwerte in der EPS-Datei.

## Schritt 3: XMP-Metadaten abrufen

```csharp
// Holen Sie sich XMP-Metadaten. Wenn die EPS-Datei keine XMP-Metadaten enthält, erhalten wir eine neue, gefüllt mit Werten aus PS-Metadatenkommentaren (%%Creator, %%CreateDate, %%Title usw.).
XmpMetadata xmp = document.GetXmpMetadata();
```

## Schritt 4: XMP-Metadatenwerte ändern

Lassen Sie uns nun einige Schlüsselwerte in den XMP-Metadaten ändern:

### Schritt 4.1: ModifyDate-Wert ändern

```csharp
// Ändern Sie den ModifyDate-Wert
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

### Schritt 4.2: Erstellerwert ändern

```csharp
// Erstellerwert ändern
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### Schritt 4.3: Titelwert ändern

```csharp
// Titelwert ändern
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

Nachdem wir diese Änderungen vorgenommen haben, fahren wir mit dem letzten Schritt fort – dem Speichern der geänderten EPS-Datei.

## Schritt 5: EPS-Datei mit geänderten XMP-Metadaten speichern

### Schritt 5.1: Ausgabestream erstellen

```csharp
// Ausgabestream erstellen
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

### Schritt 5.2: EPS-Datei speichern

```csharp
// EPS-Datei speichern
document.Save(outPsStream);
```

Schließen Sie abschließend den Eingabestream:

```csharp
finally
{
    psStream.Close();
}
```

Glückwunsch! Sie haben mit Aspose.Page für .NET erfolgreich XMP-Metadatenwerte in einer EPS-Datei geändert.

## Abschluss

In diesem Tutorial haben wir den nahtlosen Prozess der Änderung von Werten in EPS-Dateien mit Aspose.Page für .NET untersucht. Als Entwickler steht Ihnen nun ein leistungsstarkes Werkzeug zur effizienten Dokumentenbearbeitung zur Verfügung.

## FAQs

### F1: Kann ich Aspose.Page für .NET mit anderen Dateiformaten verwenden?

A1: Aspose.Page konzentriert sich hauptsächlich auf die Manipulation von EPS-Dateien. Für andere Formate erkunden Sie die vielfältige Produktpalette von Aspose.

### F2: Gibt es eine Testversion?

 A2: Ja, Sie können Aspose.Page für .NET mit der verfügbaren kostenlosen Testversion ausprobieren[Hier](https://releases.aspose.com/).

### F3: Wo finde ich eine ausführliche Dokumentation?

 A3: Die umfassende Dokumentation finden Sie hier[Hier](https://reference.aspose.com/page/net/).

### F4: Wie erhalte ich eine temporäre Lizenz?

 A4: Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).

### F5: Kann ich Aspose.Page für .NET kaufen?

 A5: Auf jeden Fall! Besuchen Sie die Kaufseite[Hier](https://purchase.aspose.com/buy) für Lizenzoptionen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
