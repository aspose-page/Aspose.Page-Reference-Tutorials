---
title: Fügen Sie Array-Elemente mit Aspose.Page hinzu
linktitle: Array-Elemente hinzufügen
second_title: Aspose.Page .NET-API
description: Erfahren Sie, wie Sie mit Aspose.Page für .NET Array-Elemente in EPS-Dateien hinzufügen. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für eine reibungslose Dokumentenbearbeitung.
weight: 11
url: /de/net/eps-metadata-management/modify-eps-metadata-add-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fügen Sie Array-Elemente mit Aspose.Page hinzu

## Einführung

Im Bereich der Dokumentbearbeitung und -verarbeitung in .NET sticht Aspose.Page als leistungsstarkes Tool hervor. Unter den vielen Funktionen ist die Handhabung von Array-Elementen innerhalb einer EPS-Datei eine häufige Anforderung. In diesem Tutorial erkunden wir Schritt für Schritt den Prozess des Hinzufügens von Array-Elementen mithilfe von Aspose.Page in einer .NET-Umgebung. Egal, ob Sie ein erfahrener Entwickler oder ein Neuling sind, dieser Leitfaden führt Sie klar und präzise durch den Prozess.

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Ein grundlegendes Verständnis der .NET-Programmierung.
-  Aspose.Page für .NET installiert. Wenn nicht, können Sie es hier herunterladen[Hier](https://releases.aspose.com/page/net/).
- Ein Code-Editor wie Visual Studio, der den Beispielen folgt.

## Namespaces importieren

Stellen Sie in Ihrem .NET-Projekt sicher, dass Sie die erforderlichen Namespaces importieren, um die Aspose.Page-Funktionen nutzen zu können. Fügen Sie am Anfang Ihres Codes die folgenden Zeilen hinzu:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Diese Namespaces bieten Zugriff auf die wesentlichen Klassen und Methoden, die für die Bearbeitung von EPS-Dateien erforderlich sind.

## Schritt 1: Initialisieren Sie den EPS-Datei-Eingabestream

```csharp
// ExStart:3
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "Your Document Directory";
// Initialisieren Sie den EPS-Datei-Eingabestream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//Erstellen Sie eine PsDocument-Instanz aus dem Stream
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

 Hier richten wir den ersten Eingabestream für die EPS-Datei ein und erstellen einen`PsDocument` Beispiel.

## Schritt 2: XMP-Metadaten abrufen

```csharp
// ExStart:4
// Holen Sie sich XMP-Metadaten. Wenn die EPS-Datei keine XMP-Metadaten enthält, erhalten wir eine neue Datei, die mit Werten aus PS-Metadatenkommentaren gefüllt ist (%%Creator, %%CreateDate, %%Title usw.).
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

Rufen Sie die XMP-Metadaten aus der EPS-Datei ab. Wenn in der EPS-Datei XMP-Metadaten fehlen, wird eine neue mit Werten aus PS-Metadatenkommentaren erstellt.

## Schritt 3: XMP-Metadatenwerte ändern

```csharp
// ExStart:5
// XMP-Metadatenwerte ändern

// Fügen Sie einen weiteren Titel hinzu. Es wird standardmäßig am Ende des Arrays hinzugefügt.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Fügen Sie einen weiteren Ersteller hinzu. Es wird im Array durch einen Index (0) hinzugefügt.
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

Ändern Sie die XMP-Metadaten, indem Sie dem Array neue Titel und Ersteller hinzufügen.

## Schritt 4: EPS-Datei mit geänderten XMP-Metadaten speichern

```csharp
// ExStart:6
// EPS-Datei mit geänderten XMP-Metadaten speichern

// Ausgabestream erstellen
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // EPS-Datei speichern
    document.Save(outPsStream);
}
// ExEnd:6
```

Speichern Sie abschließend die EPS-Datei mit den aktualisierten XMP-Metadaten. Die an den Array-Elementen vorgenommenen Änderungen werden in der Ausgabedatei widergespiegelt.

## Abschluss

Das Hinzufügen von Array-Elementen mit Aspose.Page in .NET ist ein unkomplizierter Vorgang, wie in diesem Tutorial gezeigt. Mit den richtigen Voraussetzungen und einer Schritt-für-Schritt-Anleitung können Entwickler EPS-Dateien nahtlos bearbeiten und sicherstellen, dass ihre Dokumente bestimmte Metadatenanforderungen erfüllen.

## FAQs

### F1: Ist Aspose.Page mit allen .NET-Umgebungen kompatibel?

A1: Ja, Aspose.Page ist so konzipiert, dass es nahtlos mit allen .NET-Umgebungen zusammenarbeitet und konsistente Funktionalität auf allen Plattformen bietet.

### F2: Kann ich Aspose.Page kostenlos nutzen?

 A2: Aspose.Page bietet eine kostenlose Testversion an, mit der Benutzer seine Funktionen erkunden können. Für die weitere Nutzung muss eine Lizenz erworben werden[Hier](https://purchase.aspose.com/buy).

### F3: Sind temporäre Lizenzen für Aspose.Page verfügbar?

 A3: Ja, temporäre Lizenzen sind erhältlich bei[Hier](https://purchase.aspose.com/temporary-license/) für kurzfristige Projektbedürfnisse.

### F4: Wo finde ich Community-Unterstützung für Aspose.Page?

A4: Für Community-Diskussionen und Unterstützung besuchen Sie die[Aspose.Page-Forum](https://forum.aspose.com/c/page/39).

### F5: Was ist die neueste Version von Aspose.Page für .NET?

 A5: Informationen zum Zugriff auf die neueste Version von Aspose.Page für .NET finden Sie im[Dokumentation](https://reference.aspose.com/page/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
