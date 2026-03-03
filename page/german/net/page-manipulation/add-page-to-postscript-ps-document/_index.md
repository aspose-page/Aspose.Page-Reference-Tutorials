---
date: 2026-03-03
description: Erfahren Sie, wie Sie eine benutzerdefinierte Seitengröße festlegen und
  einer PostScript-Datei eine zweite PS‑Seite hinzufügen, indem Sie Aspose.Page für
  .NET verwenden.
linktitle: Add Page to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Benutzerdefinierte Seitengröße im PS-Dokument mit Aspose.Page festlegen
url: /de/net/page-manipulation/add-page-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Seite zu PostScript (PS)-Dokument hinzufügen mit Aspose.Page

## Einführung

In der .NET-Entwicklung ermöglicht das **Festlegen einer benutzerdefinierten Seitengröße** und das **Hinzufügen einer zweiten PS-Seite** zu einem PostScript (PS)-Dokument eine feinkörnige Kontrolle über das Layout von erzeugten Drucken, Berichten oder Grafiken. Aspose.Page für .NET macht diese Aufgabe einfach mit einer sauberen, objektorientierten API. In diesem Tutorial lernen Sie, wie Sie eine mehrseitige PS-Datei erstellen, eine benutzerdefinierte Größe für jede Seite definieren und das Ergebnis speichern – alles mit nur wenigen Zeilen C#‑Code.

## Schnelle Antworten
- **Kann ich eine benutzerdefinierte Seitengröße festlegen?** Ja – übergeben Sie einfach Breite und Höhe beim Öffnen einer Seite.  
- **Wie füge ich eine zweite PS-Seite hinzu?** Rufen Sie `document.OpenPage(width, height)` ein zweites Mal auf.  
- **Welche .NET-Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Benötige ich eine Lizenz?** Eine temporäre Lizenz funktioniert für Tests; für die Produktion ist eine Vollversion erforderlich.  
- **Wo kann ich Aspose.Page herunterladen?** Von der offiziellen Download‑Seite, die unten verlinkt ist.

## Voraussetzungen

Bevor Sie in das Tutorial einsteigen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:

- Fundierte Kenntnisse in der .NET-Entwicklung.  
- Visual Studio auf Ihrem Rechner installiert.  
- Aspose.Page für .NET Bibliothek, die Sie [hier](https://releases.aspose.com/page/net/) herunterladen können.  
- Ihr bevorzugtes Dokumentverzeichnis für Tests.

## Namespaces importieren

Stellen Sie sicher, dass Sie die erforderlichen Namespaces in Ihrem Projekt einbinden, um auf die von Aspose.Page bereitgestellten Funktionen zuzugreifen. Im gegebenen Beispiel sind die Namespaces implizit enthalten, aber es ist wichtig, sie zu überprüfen und ggf. an Ihre Projektstruktur anzupassen.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Schritt 1: Projekt einrichten

Erstellen Sie ein neues .NET-Projekt in Visual Studio und richten Sie die notwendigen Konfigurationen ein. Stellen Sie sicher, dass Sie die Aspose.Page-Bibliothek in Ihrem Projekt referenzieren.

## Benutzerdefinierte Seitengröße festlegen und zweite PS-Seite hinzufügen

Dieser Abschnitt zeigt genau, wie Sie für jede Seite **eine benutzerdefinierte Seitengröße festlegen** und wie Sie **eine zweite PS-Seite** zum selben Dokument **hinzufügen**.

### Schritt 2: Dokument initialisieren

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "document1.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create a new 2-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, 2);
```

### Schritt 3: Erste Seite hinzufügen (Standardgröße)

```csharp
    // Add the first page
    document.OpenPage();

    // Add content

    // Close the first page
    document.ClosePage();
```

### Schritt 4: Zweite Seite mit anderer (benutzerdefinierter) Größe hinzufügen

```csharp
    // Add the second page with a different size
    document.OpenPage(400, 700);

    // Add content

    // Close the second page
    document.ClosePage();
```

### Schritt 5: Dokument speichern

```csharp
    // Save the document
    document.Save();
}
// ExEnd:1
```

Befolgen Sie diese Schritte sorgfältig, und Sie werden erfolgreich **eine benutzerdefinierte Seitengröße festlegen** und eine **zweite PS-Seite** zu einem PostScript-Dokument hinzufügen, indem Sie Aspose.Page für .NET verwenden.

## Warum das wichtig ist

- **Präzises Layout** – Benutzerdefinierte Seitenabmessungen ermöglichen es, Druckerspezifikationen zu entsprechen oder einzigartige Broschürenformate zu erstellen.  
- **Mehrere Seiten** – Das Hinzufügen einer zweiten Seite (oder mehr) ermöglicht mehrseitige Berichte ohne externe Zusammenführungs‑Tools.  
- **Plattformübergreifend** – Die erzeugte PS-Datei kann auf jedem PostScript‑kompatiblen Gerät gerendert oder später in PDF konvertiert werden.

## Häufige Fallstricke & Fehlerbehebung

- **Falscher Pfad** – Stellen Sie sicher, dass `dataDir` mit einem Pfadtrennzeichen endet oder verwenden Sie `Path.Combine`.  
- **Lizenzprobleme** – Ohne gültige Lizenz kann die Bibliothek ein Wasserzeichen hinzufügen oder die Seitenzahl begrenzen.  
- **Einheiten‑Verwirrung** – Breite und Höhe werden in Punkten gemessen (1 Punkt = 1/72 Zoll). Passen Sie die Werte entsprechend an.

## Häufig gestellte Fragen

**Q1: Ist Aspose.Page mit verschiedenen Dokumentformaten kompatibel?**  
A1: Aspose.Page konzentriert sich hauptsächlich auf die Manipulation von PostScript‑Dokumenten. Für andere Formate können Sie die entsprechenden Aspose‑Bibliotheken erkunden.

**Q2: Kann ich die Seitengröße in Aspose.Page anpassen?**  
A2: Auf jeden Fall! Wie im Tutorial gezeigt, können Sie für jede Seite unterschiedliche Größen nach Ihren Anforderungen festlegen.

**Q3: Wo finde ich weitere Beispiele und Dokumentation?**  
A3: Besuchen Sie die [Dokumentation](https://reference.aspose.com/page/net/) für umfassende Informationen und zahlreiche Beispiele.

**Q4: Wie erhalte ich eine temporäre Lizenz für Aspose.Page?**  
A4: Gehen Sie zu [diesem Link](https://purchase.aspose.com/temporary-license/), um eine temporäre Lizenz für Testzwecke zu erhalten.

**Q5: Wo kann ich Community‑Support erhalten oder Fragen stellen?**  
A5: Treten Sie dem [Aspose.Page Community‑Forum](https://forum.aspose.com/c/page/39) bei, um sich mit anderen Entwicklern zu vernetzen, Erfahrungen auszutauschen und Unterstützung zu erhalten.

---

**Zuletzt aktualisiert:** 2026-03-03  
**Getestet mit:** Aspose.Page 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}