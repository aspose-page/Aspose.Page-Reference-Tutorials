---
title: Fügen Sie einfache Eigenschaften mit Aspose.Page für .NET hinzu
linktitle: Fügen Sie einfache Eigenschaften hinzu
second_title: Aspose.Page .NET-API
description: Verbessern Sie EPS-Dateien mit Aspose.Page für .NET. Fügen Sie mühelos einfache Eigenschaften für benutzerdefinierte Dokumentmetadaten hinzu.
weight: 14
url: /de/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fügen Sie einfache Eigenschaften mit Aspose.Page für .NET hinzu

## Einführung

Im Bereich der Dokumentbearbeitung und -verbesserung erweist sich Aspose.Page für .NET als leistungsstarkes Tool, das Entwicklern die Möglichkeit bietet, XMP-Metadaten nahtlos in EPS-Dateien einzufügen und zu ändern. Dieses Tutorial führt Sie durch den Prozess des Hinzufügens einfacher Eigenschaften zu einer EPS-Datei mit Aspose.Page für .NET.

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1.  Aspose.Page für .NET: Stellen Sie sicher, dass Aspose.Page für .NET in Ihrer Entwicklungsumgebung installiert ist. Wenn nicht, können Sie es herunterladen[Hier](https://releases.aspose.com/page/net/).

2.  Dokumentenverzeichnis: Richten Sie ein Verzeichnis zum Speichern Ihrer EPS-Dateien ein. Aktualisieren Sie die`dataDir` Variable im bereitgestellten Code-Snippet mit dem Pfad zu Ihrem Dokumentverzeichnis.

## Namespaces importieren

Importieren Sie zunächst die erforderlichen Namespaces, um die Kommunikation mit Aspose.Page für .NET zu ermöglichen. Fügen Sie am Anfang Ihrer Codedatei die folgenden Zeilen hinzu:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Schritt 1: EPS-Datei-Eingabestream initialisieren

```csharp
// ExStart:1
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "Your Document Directory";
// Initialisieren Sie den EPS-Datei-Eingabestream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//Erstellen Sie eine PsDocument-Instanz aus dem Stream
PsDocument document = new PsDocument(psStream);
```

## Schritt 2: XMP-Metadaten abrufen

```csharp
// Holen Sie sich XMP-Metadaten. Wenn die EPS-Datei keine XMP-Metadaten enthält, erhalten wir eine neue, gefüllt mit Werten aus PS-Metadatenkommentaren (%%Creator, %%CreateDate, %%Title usw.).
XmpMetadata xmp = document.GetXmpMetadata();
```

## Schritt 3: XMP-Metadatenwerte ändern

```csharp
// XMP-Metadatenwerte ändern
DateTime now = DateTime.UtcNow;

// Fügen Sie die Eigenschaft „Integer“ hinzu
xmp.Add("xmp:Intg1", new XmpValue(111));

// Fügen Sie die DateTime-Eigenschaft hinzu
xmp.Add("xmp:Date1", new XmpValue(now));

// Double-Eigenschaft hinzufügen
xmp.Add("xmp:Double1", new XmpValue(111.11D));

//String-Eigenschaft hinzufügen
xmp.Add("xmp:String1", new XmpValue("ABC"));
```

## Schritt 4: EPS-Datei mit geänderten XMP-Metadaten speichern

```csharp
// EPS-Datei mit geänderten XMP-Metadaten speichern

// Ausgabestream erstellen
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_simple_props_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // EPS-Datei speichern
    document.Save(outPsStream);
}
```

## Schritt 5: FileStream schließen

```csharp
finally
{
    psStream.Close();
}
```

Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Page für .NET mühelos einfache Eigenschaften in Ihre EPS-Dateien integrieren.

## Abschluss

Zusammenfassend erweist sich Aspose.Page für .NET als unschätzbar wertvoller Vorteil für Entwickler, die EPS-Dateien mit benutzerdefinierten XMP-Metadaten erweitern möchten. Durch das Hinzufügen einfacher Eigenschaften können Sie Ihre Dokumente an spezifische Anforderungen anpassen und bereichern und so eine Welt voller Möglichkeiten für die Dokumentbearbeitung eröffnen.

## FAQs

### F1: Ist Aspose.Page für .NET mit allen EPS-Dateien kompatibel?

A1: Aspose.Page für .NET unterstützt eine Vielzahl von EPS-Dateien. Die Kompatibilität kann jedoch je nach Komplexität und Struktur einzelner Dateien variieren.

### F2: Kann ich vorhandene XMP-Metadaten mit Aspose.Page für .NET ändern?

A2: Auf jeden Fall! Wie in diesem Tutorial gezeigt, können Sie vorhandene XMP-Metadatenwerte ganz einfach ändern oder neue hinzufügen, um sie Ihren Anforderungen anzupassen.

### F3: Gibt es Einschränkungen hinsichtlich der Arten von Eigenschaften, die ich hinzufügen kann?

A3: Aspose.Page für .NET unterstützt verschiedene Datentypen für Eigenschaften, einschließlich Ganzzahlen, Datumsangaben, Doppelzahlen und Zeichenfolgen. Sie haben die Flexibilität, den geeigneten Typ für Ihre Metadaten auszuwählen.

### F4: Wie kann ich technischen Support für Aspose.Page für .NET erhalten?

 A4: Für technische Unterstützung besuchen Sie die[Aspose.Page-Forum](https://forum.aspose.com/c/page/39) oder erkunden Sie die[Dokumentation](https://reference.aspose.com/page/net/) für eine umfassende Beratung.

### F5: Gibt es eine kostenlose Testversion für Aspose.Page für .NET?

 A5: Ja, Sie können auf eine kostenlose Testversion zugreifen[Hier](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
