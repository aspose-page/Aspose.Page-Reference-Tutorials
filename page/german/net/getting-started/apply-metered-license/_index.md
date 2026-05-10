---
date: 2026-01-28
description: Erfahren Sie, wie Sie EPS mit Aspose.Page für .NET in PNG konvertieren
  und eine verbrauchsbasierte Lizenz für eine nahtlose Dokumentenverarbeitung anwenden.
linktitle: Apply Metered License
second_title: Aspose.Page .NET API
title: EPS in PNG konvertieren und Metered‑Lizenz mit Aspose.Page für .NET anwenden
url: /de/net/getting-started/apply-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# EPS in PNG konvertieren und Metered-Lizenz mit Aspose.Page für .NET anwenden

## Einleitung

Entfesseln Sie das volle Potenzial von Aspose.Page für .NET, indem Sie **EPS in PNG konvertieren** und eine Metered-Lizenz anwenden. Dieses Tutorial führt Sie durch jeden Schritt – vom Laden einer EPS‑Datei bis zum Speichern als PNG‑Bild – damit Sie Dokumente effizient und ohne Evaluations‑Wasserzeichen verarbeiten können.

## Schnelle Antworten
- **Was wird in diesem Tutorial behandelt?** Konvertieren von EPS‑Dateien zu PNG‑Bildern und Anwenden einer Metered‑Lizenz mit Aspose.Page für .NET.  
- **Benötige ich eine Lizenz?** Ja, für den Produktionseinsatz ist eine Metered‑Lizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Wie lange dauert die Implementierung?** Etwa 10–15 Minuten für eine Basis‑Konvertierung.  
- **Läuft das auf Linux/macOS?** Absolut – Aspose.Page ist plattformübergreifend.

## Was bedeutet „EPS in PNG konvertieren“?
Das Konvertieren von EPS zu PNG bedeutet, eine vektorbasierte Encapsulated PostScript (EPS)‑Datei in ein Bitmap‑PNG‑Bild zu rasterisieren. Das ist nützlich, wenn Sie Grafiken in Webseiten, Berichten oder UI‑Komponenten einbetten müssen, die kein EPS unterstützen.

## Warum eine Metered‑Lizenz für die EPS‑zu‑Bild‑Konvertierung verwenden?
Eine Metered‑Lizenz lässt Sie nur für die verarbeiteten Seiten zahlen, was ideal für Workloads mit variablem Volumen ist. Außerdem entfernt sie das rote Evaluations‑Banner, das bei Nutzung der kostenlosen Testversion erscheint, und sorgt für saubere Ausgaben für Ihre Endbenutzer.

## Voraussetzungen

Bevor Sie mit den Schritten beginnen, stellen Sie sicher, dass Sie folgende Voraussetzungen erfüllt haben:

- Eine gültige Aspose.Page für .NET‑Lizenz: Sie können sie unter [purchase.aspose.com](https://purchase.aspose.com/buy) erhalten.
- Aspose.Page‑Bibliothek installiert: Siehe die [Dokumentation](https://reference.aspose.com/page/net/) für Installationsanweisungen.
- .NET‑Entwicklungsumgebung: Stellen Sie sicher, dass eine funktionierende .NET‑Umgebung auf Ihrem Rechner eingerichtet ist.

## Namespaces importieren

Importieren Sie in Ihrem .NET‑Projekt die notwendigen Namespaces, um auf die Aspose.Page‑Funktionalitäten zuzugreifen:

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

## Wie konvertiere ich EPS zu PNG mit einer Metered‑Lizenz?

Im Folgenden finden Sie eine Schritt‑für‑Schritt‑Anleitung, die alles abdeckt, was Sie wissen müssen.

### Schritt 1: Öffentliche und private Metered‑Schlüssel festlegen

Initialisieren Sie die Klasse `Aspose.Page.Metered` und setzen Sie die öffentlichen und privaten Metered‑Schlüssel. Ersetzen Sie `<type public key here>` und `<type private key here>` durch Ihre tatsächlichen Schlüssel.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

### Schritt 2: EPS‑Datei laden und Dokument erstellen

Geben Sie den Pfad zu Ihrer EPS‑Datei an und erstellen Sie einen Stream, um deren Inhalt zu lesen. Anschließend erzeugen Sie eine Instanz der Klasse `PsDocument` aus dem Stream.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

### Schritt 3: EPS in PNG‑Bild konvertieren

Erstellen Sie ein `ImageDevice` zum Konvertieren der EPS‑Datei in ein PNG‑Bild. Speichern Sie die EPS‑Datei als Bild mithilfe der `ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

### Schritt 4: Bildbytes abrufen

Holen Sie die Bildbytes, wobei jedes Byte‑Array eine Seite repräsentiert. In diesem Fall haben wir nur eine Seite.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

### Schritt 5: Bildbytes in Datei speichern

Speichern Sie die Bildbytes in einer Datei, um die erfolgreiche Konvertierung von EPS zu PNG sicherzustellen.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

### Schritt 6: Metered‑Lizenz überprüfen

Prüfen Sie visuell, ob die Metered‑Lizenz erfolgreich angewendet wurde. Wenn das resultierende Bild keine rote Evaluations‑Nachricht enthält, ist die Lizenz korrekt aktiv.

Jetzt können Sie die vollen Möglichkeiten von Aspose.Page für .NET mit einer Metered‑Lizenz nutzen!

## Häufige Probleme und Lösungen

| Problem | Ursache | Lösung |
|---------|----------|--------|
| Rotes Evaluationsbanner erscheint weiterhin | Lizenz nicht gesetzt oder falsche Schlüssel | Überprüfen Sie die öffentlichen/privaten Schlüssel und stellen Sie sicher, dass `SetMeteredKey` vor jeglicher Dokumentenverarbeitung aufgerufen wird |
| Keine Ausgabedatei erstellt | Falscher `dataDir`‑Pfad oder Dateiberechtigungen | Vergewissern Sie sich, dass das Verzeichnis existiert und die Anwendung Schreibrechte hat |
| Mehrere Seiten nicht gespeichert | Nur die erste Seite geschrieben | Durchlaufen Sie `imagesBytes` und schreiben Sie jedes Array in eine separate PNG‑Datei |

## Häufig gestellte Fragen

**Q: Kann ich die Metered‑Lizenz in einer CI/CD‑Pipeline verwenden?**  
A: Ja, Sie können die Schlüssel sicher speichern (z. B. in Umgebungsvariablen) und `SetMeteredKey` während des Build‑Prozesses aufrufen.

**Q: Unterstützt Aspose.Page die Farbraum‑Erhaltung beim Konvertieren zu PNG?**  
A: Die PNG‑Ausgabe behält die ursprünglichen Farbinformationen bei, Sie können sie jedoch über `ImageSaveOptions` weiter anpassen.

**Q: Ist es möglich, EPS in andere Rasterformate (JPEG, BMP) zu konvertieren?**  
A: Absolut – ändern Sie einfach die `ImageSaveOptions` auf das gewünschte Format.

**Q: Wie groß ist die maximal unterstützte EPS‑Dateigröße?**  
A: Aspose.Page verarbeitet große Dateien, jedoch steigt der Speicherverbrauch mit der Bildauflösung. Für sehr große Dokumente empfiehlt sich die Verarbeitung einzelner Seiten.

**Q: Wie kann ich programmgesteuert die Anzahl der Seiten in der EPS‑Datei ermitteln?**  
A: Verwenden Sie `document.PagesCount` nach dem Laden des `PsDocument`.

## FAQ

### Q1: Wie erhalte ich eine Metered‑Lizenz für Aspose.Page für .NET?

A1: Besuchen Sie [purchase.aspose.com](https://purchase.aspose.com/buy), um eine gültige Lizenz zu erwerben.

### Q2: Wo finde ich die Dokumentation für Aspose.Page für .NET?

A2: Siehe [Aspose.Page .NET](https://reference.aspose.com/page/net/) für umfassende Dokumentation.

### Q3: Gibt es ein Forum für Aspose.Page Diskussionen und Support?

A3: Ja, besuchen Sie das [Forum](https://forum.aspose.com/c/page/39), um sich mit der Community auszutauschen und Unterstützung zu erhalten.

### Q4: Kann ich Aspose.Page für .NET vor dem Kauf testen?

A4: Absolut! Greifen Sie auf die kostenlose Testversion unter [hier](https://releases.aspose.com/) zu.

### Q5: Wie kann ich eine temporäre Lizenz für Aspose.Page für .NET erhalten?

A5: Besuchen Sie [temporary license/](https://purchase.aspose.com/temporary-license/), um eine temporäre Lizenz zu erhalten.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

---

**Zuletzt aktualisiert:** 2026-01-28  
**Getestet mit:** Aspose.Page 24.12 für .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}