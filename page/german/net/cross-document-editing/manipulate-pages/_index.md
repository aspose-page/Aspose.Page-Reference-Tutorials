---
date: 2026-01-10
description: Erfahren Sie, wie Sie XPS‑Dokumente mit Aspose.Page für .NET zusammenführen.
  Diese Schritt‑für‑Schritt‑Anleitung zeigt Techniken zur Seitenmanipulation für effiziente
  Ergebnisse.
linktitle: Manipulate Pages
second_title: Aspose.Page .NET API
title: XPS‑Dokumente mit Aspose.Page für .NET zusammenführen
url: /de/net/cross-document-editing/manipulate-pages/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS-Dokumente mit Aspose.Page für .NET zusammenführen

## Einführung

In diesem Tutorial erfahren Sie, wie Sie **XPS-Dokumente zusammenführen** und deren Seiten mit der Aspose.Page‑Bibliothek in einer .NET‑Umgebung manipulieren können. Egal, ob Sie mehrere Berichte zu einer einzigen XPS‑Datei kombinieren oder Seiten für ein professionelles Ergebnis neu anordnen müssen – diese Anleitung führt Sie Schritt für Schritt mit klaren Erklärungen und sofort ausführbarem Code.

## Schnelle Antworten
- **Was kann ich mit Aspose.Page tun?** XPS-Dokumente zusammenführen, Seiten einfügen, hinzufügen oder entfernen und das Ergebnis speichern.  
- **Benötige ich für Tests eine Lizenz?** Eine temporäre Lizenz steht für die Evaluierung zur Verfügung.  
- **Welche .NET-Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Ist Visual Studio erforderlich?** Nein, jede IDE, die C# unterstützt, funktioniert, aber Visual Studio wird empfohlen.  
- **Wie lange dauert das Zusammenführen?** In der Regel ein paar Sekunden für XPS-Dateien Standardgröße.

## Was bedeutet das Zusammenführen von XPS-Dokumenten?
Das Zusammenführen von XPS-Dokumenten bedeutet, Seiten aus zwei oder mehr bestehenden XPS‑Dateien zu nehmen und sie zu einem einzigen XPS‑Dokument zu kombinieren. Das ist nützlich, um konsolidierte Berichte zu erstellen, mehrseitige Handbücher zusammenzustellen oder druckfertige Pakete vorzubereiten, ohne in ein anderes Format zu konvertieren.

## Warum Aspose.Page für .NET verwenden?
Aspose.Page bietet eine **reine .NET‑API**, die direkt mit XPS‑Dateien arbeitet – ohne externe Tools oder Drittanbieter‑Komponenten. Sie erhalten feinkörnige Kontrolle über Seitenreihenfolge, Einfügepositionen und die Erhaltung des Inhalts, wodurch der Merge‑Prozess zuverlässig und schnell ist.

## Voraussetzungen

- **Aspose.Page für .NET** – herunterladen von der [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/).  
- **Entwicklungsumgebung** – Visual Studio, Rider oder jede IDE, die C# unterstützt.  
- **Eingabe‑XPS‑Dateien** – drei Beispieldateien (`input1.xps`, `input2.xps`, `input3.xps`) in einem bekannten Ordner abgelegt.

## Namespaces importieren

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Diese Namespaces geben Ihnen Zugriff auf die Kern‑XPS‑Dokumentklassen, Seitenmodelle und grundlegende Zeichen‑Hilfsmittel.

## Schritt 1: Dokumentverzeichnis festlegen

```csharp
string dataDir = "Your Document Directory";
```

Ersetzen Sie **Your Document Directory** durch den vollständigen Pfad, in dem Ihre XPS‑Dateien gespeichert sind, z. B. `C:\\Docs\\XpsFiles\\`.

## Schritt 2: XPS‑Dokumentinstanzen erstellen

```csharp
XpsDocument doc1 = new XpsDocument(dataDir + "input1.xps");
XpsDocument doc2 = new XpsDocument(dataDir + "input2.xps");
XpsDocument doc3 = new XpsDocument(dataDir + "input3.xps");
XpsDocument doc4 = new XpsDocument();
```

- `doc1`, `doc2` und `doc3` repräsentieren die Quell‑Dokumente, die Sie zusammenführen möchten.  
- `doc4` ist ein leeres XPS‑Dokument, das das zusammengeführte Ergebnis enthält.

## Schritt 3: Seiten einfügen, hinzufügen und entfernen

```csharp
doc4.InsertPage(1, doc2.Page, false);
doc4.AddPage(doc3.Page, false);
doc4.RemovePageAt(2);
doc4.InsertPage(2, doc1.SelectActivePage(3), false);
```

Hier ist, was jede Zeile bewirkt:

1. **InsertPage(1, doc2.Page, false)** – fügt die erste Seite von `doc2` an Position 1 in `doc4` ein.  
2. **AddPage(doc3.Page, false)** – fügt die erste Seite von `doc3` am Ende von `doc4` an.  
3. **RemovePageAt(2)** – entfernt die Seite, die sich jetzt an Index 2 befindet (nützlich zum Entfernen unerwünschter Seiten).  
4. **InsertPage(2, doc1.SelectActivePage(3), false)** – fügt die dritte Seite von `doc1` an Position 2 ein und vervollständigt das Zusammenführen.

Diese Vorgänge zeigen, wie Sie **XPS-Dokumente zusammenführen** können, während Sie Seiten nach Bedarf neu anordnen oder entfernen.

## Schritt 4: Zusammengeführtes Dokument speichern

```csharp
doc4.Save(dataDir + "out.xps");
```

Die endgültige zusammengeführte XPS‑Datei (`out.xps`) wird in dasselbe Verzeichnis geschrieben. Sie können sie nun in jedem XPS‑Viewer öffnen oder weiter mit Aspose.Page verarbeiten.

## Häufige Probleme und Lösungen
- **Datei nicht gefunden** – überprüfen Sie den `dataDir`‑Pfad und stellen Sie sicher, dass die Eingabedateien vorhanden sind.  
- **Ungültiger Seitenindex** – Seitenindizes beginnen bei 1; der Versuch, eine nicht vorhandene Seite einzufügen, löst eine Ausnahme aus.  
- **Lizenzfehler** – verwenden Sie eine temporäre oder vollständige Lizenz, bevor Sie in die Produktion gehen.

## FAQ

### Q1: Kann ich Seiten aus verschiedenen XPS-Dokumenten manipulieren?

A1: Ja, wie im Tutorial gezeigt, können Sie Seiten aus mehreren XPS-Dokumenten in ein neues Dokument einfügen.

### Q2: Wie kann ich eine bestimmte Seite aus einem Dokument entfernen?

A2: Verwenden Sie die Methode `RemovePageAt` und geben Sie den Index der zu entfernenden Seite an.

### Q3: Ist Aspose.Page mit Visual Studio kompatibel?

A3: Ja, Aspose.Page ist vollständig mit Visual Studio kompatibel, sodass es sich leicht in Ihre .NET-Projekte integrieren lässt.

### Q4: Gibt es Lizenzoptionen?

A4: Ja, Sie können Lizenzoptionen erkunden und eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erhalten.

### Q5: Wo kann ich Unterstützung erhalten oder Fragen stellen?

A5: Besuchen Sie das [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39), um Unterstützung zu erhalten und sich mit der Community auszutauschen.

## Häufig gestellte Fragen

**F: Kann ich mehr als drei XPS‑Dateien zusammenführen?**  
**A:** Absolut. Erstellen Sie zusätzliche `XpsDocument`‑Instanzen und verwenden Sie `InsertPage` oder `AddPage` wiederholt, um ein größeres zusammengeführtes Dokument zu bauen.

**F: Behält das Zusammenführen das ursprüngliche Layout und die Grafiken bei?**  
**A:** Ja. Aspose.Page kopiert den Seiteninhalt byte‑für‑byte, sodass Text, Bilder und Vektorgrafiken unverändert bleiben.

**F: Wie füge ich eine Seite am Ende ein, ohne einen Index anzugeben?**  
**A:** Verwenden Sie `AddPage(sourcePage, false)`, das die Seite an das Dokumentende anhängt.

**F: Ist es möglich, XPS‑Dokumente auf einem Server ohne UI zusammenzuführen?**  
**A:** Die API ist vollständig headless; Sie können denselben Code in ASP.NET, Azure Functions oder jeder serverseitigen .NET‑Umgebung ausführen.

**F: Was ist, wenn meine XPS‑Dateien passwortgeschützt sind?**  
**A:** Aspose.Page unterstützt derzeit keine verschlüsselten XPS‑Dateien; Sie müssen sie vor dem Zusammenführen entschlüsseln.

**Zuletzt aktualisiert:** 2026-01-10  
**Getestet mit:** Aspose.Page für .NET 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}