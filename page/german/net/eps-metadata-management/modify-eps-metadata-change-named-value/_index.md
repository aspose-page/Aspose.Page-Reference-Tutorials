---
title: Ändern Sie den benannten Wert mit Aspose.Page für .NET
linktitle: Benannten Wert ändern
second_title: Aspose.Page .NET-API
description: Erfahren Sie, wie Sie benannte Werte in EPS-Dateien mit Aspose.Page für .NET ändern. Passen Sie XMP-Metadaten mühelos für eine maßgeschneiderte Dokumentenverarbeitung an.
weight: 16
url: /de/net/eps-metadata-management/modify-eps-metadata-change-named-value/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ändern Sie den benannten Wert mit Aspose.Page für .NET

## Einführung

In der Welt der Dokumentenverarbeitung sticht Aspose.Page für .NET als leistungsstarkes Tool zur Bearbeitung von EPS-Dateien hervor. Eine der wichtigsten Funktionen ist die Möglichkeit, benannte Werte in XMP-Metadaten zu ändern. Dieses Tutorial führt Sie durch den Prozess der Änderung eines benannten Werts mit Aspose.Page für .NET und ermöglicht Ihnen die Anpassung Ihrer EPS-Dateien an Ihre spezifischen Anforderungen.

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Aspose.Page für .NET: Stellen Sie sicher, dass die Aspose.Page für .NET-Bibliothek installiert ist. Wenn nicht, können Sie es herunterladen[Hier](https://releases.aspose.com/page/net/).

- Dokumentenverzeichnis: Legen Sie ein bestimmtes Verzeichnis für Ihre EPS-Dateien fest, in dem Sie die benannten Wertänderungen durchführen können.

## Namespaces importieren

In Ihrem .NET-Projekt müssen Sie die erforderlichen Namespaces importieren, um auf die von Aspose.Page bereitgestellten Funktionen zuzugreifen. Fügen Sie Ihrem Code die folgenden Namespaces hinzu:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Lassen Sie uns nun den Code für ein umfassendes Verständnis in mehrere Schritte aufteilen:

## Schritt 1: EPS-Datei-Eingabestream initialisieren

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// ExEnd:1
```

In diesem Schritt richten wir den Eingabestream für die EPS-Datei ein, die Sie ändern möchten. Stellen Sie sicher, dass Sie „Ihr Dokumentverzeichnis“ durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis ersetzen.

## Schritt 2: XMP-Metadaten abrufen

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

Rufen Sie die vorhandenen XMP-Metadaten aus der EPS-Datei ab. Wenn die EPS-Datei keine XMP-Metadaten enthält, wird eine neue mit Werten aus PS-Metadatenkommentaren generiert.

## Schritt 3: XMP-Metadatenwerte ändern

```csharp
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

Hier demonstrieren wir die Änderung zweier benannter Werte innerhalb der Struktur „xmpTPg:MaxPageSize“. Sie können dies entsprechend Ihren spezifischen Anforderungen anpassen.

## Schritt 4: EPS-Datei mit geänderten XMP-Metadaten speichern

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

Speichern Sie die geänderte EPS-Datei im Ausgabestream. Die Datei spiegelt nun die an den XMP-Metadaten vorgenommenen Änderungen wider.

## Abschluss

Mit diesem Tutorial haben Sie gelernt, wie Sie Aspose.Page für .NET nutzen können, um benannte Werte in XMP-Metadaten in EPS-Dateien zu ändern. Diese Funktionalität eröffnet eine Welt voller Möglichkeiten zum Anpassen und Anpassen Ihrer Dokumente an spezifische Anforderungen.

## FAQs

### F1: Kann ich Aspose.Page für .NET mit anderen Dokumentformaten verwenden?

A1: Ja, Aspose.Page unterstützt verschiedene Dokumentformate, einschließlich EPS, XPS und PDF.

### F2: Gibt es eine Testversion für Aspose.Page für .NET?

 A2: Ja, Sie können auf eine kostenlose Testversion zugreifen[Hier](https://releases.aspose.com/).

### F3: Wo finde ich weitere Dokumentation zu Aspose.Page für .NET?

 A3: Sehen Sie sich die Dokumentation an[Hier](https://reference.aspose.com/page/net/).

### F4: Wie kann ich eine temporäre Lizenz für Aspose.Page für .NET erhalten?

 A4: Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).

### F5: Welche Supportoptionen stehen für Aspose.Page für .NET-Benutzer zur Verfügung?

 A5: Besuchen Sie das Community-Forum[Hier](https://forum.aspose.com/c/page/39) für Unterstützung und Diskussionen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
