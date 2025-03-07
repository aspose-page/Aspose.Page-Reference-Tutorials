---
title: Wenden Sie eine gemessene Lizenz mit Aspose.Page für .NET an
linktitle: Wenden Sie eine Metered-Lizenz an
second_title: Aspose.Page .NET-API
description: Entdecken Sie die nahtlose Integration von Aspose.Page für .NET mit dieser Schritt-für-Schritt-Anleitung zum Anwenden einer getakteten Lizenz. Optimieren Sie die Dokumentenverarbeitung mühelos.
weight: 10
url: /de/net/getting-started/apply-metered-license/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wenden Sie eine gemessene Lizenz mit Aspose.Page für .NET an

## Einführung

Schöpfen Sie das volle Potenzial von Aspose.Page für .NET aus, indem Sie eine getaktete Lizenz anwenden. Dieses Tutorial führt Sie durch den Prozess der Einrichtung und Anwendung der gemessenen Lizenz und sorgt so für eine reibungslose und optimierte Nutzung dieser leistungsstarken .NET-Bibliothek.

## Voraussetzungen

Bevor Sie sich an die einzelnen Schritte machen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Eine gültige Aspose.Page für .NET-Lizenz: Sie können sie erhalten von[Purchase.aspose.com](https://purchase.aspose.com/buy).
-  Aspose.Page-Bibliothek installiert: Siehe[Dokumentation](https://reference.aspose.com/page/net/) für Installationsanweisungen.
- .NET-Entwicklungsumgebung: Stellen Sie sicher, dass auf Ihrem Computer eine funktionierende .NET-Umgebung eingerichtet ist.

## Namespaces importieren

Importieren Sie in Ihrem .NET-Projekt die erforderlichen Namespaces, um auf die Aspose.Page-Funktionen zuzugreifen:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

## Schritt 1: Legen Sie gemessene öffentliche und private Schlüssel fest

 Initialisieren Sie die`Aspose.Page.Metered` Klasse und legen Sie die gemessenen öffentlichen und privaten Schlüssel fest. Ersetzen`<type public key here>` Und`<type private key here>` mit Ihren tatsächlichen Schlüsseln.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

## Schritt 2: EPS-Datei laden und Dokument erstellen

 Geben Sie den Pfad zu Ihrer EPS-Datei an und erstellen Sie einen Stream, um deren Inhalt zu lesen. Erstellen Sie dann eine Instanz von`PsDocument` Klasse aus dem Stream.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Schritt 3: EPS in PNG-Bild konvertieren

 Erstelle ein`ImageDevice` zum Konvertieren der EPS-Datei in ein PNG-Bild. Speichern Sie die EPS-Datei als Bild mit`ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

## Schritt 4: Bildbytes abrufen

Rufen Sie die Bildbytes ab, wobei jedes Byte-Array eine Seite darstellt. In diesem Fall haben wir eine Seite.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

## Schritt 5: Bildbytes in Datei speichern

Speichern Sie die Bildbytes in einer Datei, um eine erfolgreiche Konvertierung von EPS in PNG sicherzustellen.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

## Schritt 6: Überprüfen Sie die gemessene Lizenz

Überprüfen Sie visuell, ob die gemessene Lizenz erfolgreich angewendet wurde. Wenn das resultierende Bild die rote Bewertungsmeldung nicht enthält, bedeutet dies, dass die gemessene Lizenz ohne Probleme angewendet wird.

Jetzt sind Sie bereit, die vollen Funktionen von Aspose.Page für .NET mit einer getakteten Lizenz zu nutzen!

## Abschluss

Diese Schritt-für-Schritt-Anleitung vermittelt Ihnen das Wissen, mit dem Sie Aspose.Page für .NET nahtlos anwenden können. Erweitern Sie Ihre Möglichkeiten zur Dokumentenverarbeitung und erkunden Sie die umfangreichen Funktionen dieser leistungsstarken Bibliothek.

## FAQs

### F1: Wie erhalte ich eine getaktete Lizenz für Aspose.Page für .NET?

 A1: Besuchen[Purchase.aspose.com](https://purchase.aspose.com/buy) eine gültige Lizenz zu erwerben.

### F2: Wo finde ich die Dokumentation für Aspose.Page für .NET?

 A2: Siehe[Aspose.Page .NET](https://reference.aspose.com/page/net/) für eine umfassende Dokumentation.

### F3: Gibt es ein Forum für Aspose.Page-Diskussionen und Support?

 A3: Ja, besuchen Sie uns[Forum](https://forum.aspose.com/c/page/39) sich mit der Gemeinschaft auseinanderzusetzen und Hilfe zu suchen.

### F4: Kann ich Aspose.Page für .NET vor dem Kauf testen?

 A4: Auf jeden Fall! Greifen Sie auf die kostenlose Testversion zu unter[Hier](https://releases.aspose.com/).

### F5: Wie kann ich eine temporäre Lizenz für Aspose.Page für .NET erhalten?

 A5: Besuchen[temporäre Lizenz/](https://purchase.aspose.com/temporary-license/) eine befristete Lizenz zu erhalten.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
