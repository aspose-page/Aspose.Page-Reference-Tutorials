---
title: Benannten Wert mit Aspose.Page hinzufügen
linktitle: Benannten Wert hinzufügen
second_title: Aspose.Page .NET-API
description: Erfahren Sie, wie Sie mit Aspose.Page benannte Werte zu EPS-Dateien in .NET hinzufügen. Dieses umfassende Tutorial führt Sie Schritt für Schritt durch den Prozess.
weight: 12
url: /de/net/eps-metadata-management/modify-eps-metadata-add-named-value/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Benannten Wert mit Aspose.Page hinzufügen

## Einführung

Im Bereich der Dokumentenverarbeitung mit .NET zeichnet sich Aspose.Page als leistungsstarkes Tool zur Verarbeitung von EPS-Dateien aus. Aspose.Page ermöglicht Entwicklern die Bearbeitung von XMP-Metadaten und erleichtert so Aufgaben wie das Hinzufügen benannter Werte. Dieses Tutorial führt Sie Schritt für Schritt durch den Prozess des Hinzufügens benannter Werte zu einer EPS-Datei mit Aspose.Page.

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Grundkenntnisse der Programmiersprache C#.
- Eine integrierte Entwicklungsumgebung (IDE) wie Visual Studio installiert.
-  Aspose.Page für .NET-Bibliothek. Wenn es nicht installiert ist, können Sie es hier herunterladen[Hier](https://releases.aspose.com/page/net/).

## Namespaces importieren

Importieren wir zunächst die erforderlichen Namespaces in Ihren C#-Code. Diese Namespaces sind für den Zugriff auf die von Aspose.Page bereitgestellten Funktionen von entscheidender Bedeutung:

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

 Der erste Schritt besteht darin, den Eingabestream für die EPS-Datei zu initialisieren. Ersetzen`"Your Document Directory"` mit dem Pfad zu Ihrem Dokumentenverzeichnis:

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Schritt 2: XMP-Metadaten abrufen

Rufen Sie XMP-Metadaten aus der EPS-Datei ab. Wenn in der EPS-Datei XMP-Metadaten fehlen, wird eine neue erstellt, gefüllt mit Werten aus PS-Metadatenkommentaren:

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## Schritt 3: XMP-Metadatenwerte ändern

Nehmen wir nun Änderungen an den XMP-Metadaten vor. In diesem Beispiel fügen wir der Struktur „xmpTPg:MaxPageSize“ einen benannten Wert hinzu:

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## Schritt 4: EPS-Datei mit geänderten XMP-Metadaten speichern

Speichern Sie die EPS-Datei mit den aktualisierten XMP-Metadaten. Erstellen Sie einen Ausgabestream und speichern Sie die geänderte EPS-Datei:

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## Abschluss

Glückwunsch! Sie haben mit Aspose.Page in .NET erfolgreich einen benannten Wert zu einer EPS-Datei hinzugefügt. Dieses Tutorial hat Sie durch die wesentlichen Schritte geführt und die Einfachheit und Effektivität von Aspose.Page bei der Dokumentenbearbeitung demonstriert.

## FAQs

### F1: Ist Aspose.Page mit verschiedenen EPS-Dateiversionen kompatibel?

A1: Aspose.Page unterstützt verschiedene EPS-Dateiversionen und gewährleistet so die Kompatibilität mit einer Vielzahl von Dokumenten.

### F2: Kann ich Aspose.Page für kommerzielle Projekte verwenden?

 A2: Ja, Aspose.Page wird mit einer kommerziellen Lizenz geliefert und Sie können diese erwerben[Hier](https://purchase.aspose.com/buy).

### F3: Gibt es eine kostenlose Testversion für Aspose.Page?

 A3: Ja, Sie können Aspose.Page mit einer kostenlosen Testversion erkunden[Hier](https://releases.aspose.com/).

### F4: Wie kann ich Unterstützung erhalten oder mich mit der Aspose-Community verbinden?

 A4: Besuchen Sie die[Aspose.Page-Forum](https://forum.aspose.com/c/page/39) um Unterstützung zu erhalten und mit der Community in Kontakt zu treten.

### F5: Was ist eine temporäre Lizenz und wie kann ich eine erhalten?

 A5: Wenn Sie zu Test- oder Evaluierungszwecken eine temporäre Lizenz benötigen, können Sie eine erwerben[Hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
