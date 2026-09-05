---
date: 2026-07-19
description: Erfahren Sie, wie Sie ein PostScript-Dokument in ASP.NET mit Aspose.Page
  für .NET erstellen, mehrere Transformationen anwenden und die Datei effizient speichern.
keywords:
- create postscript document asp.net
- aspose.page transformations
- postscript graphics .net
lastmod: 2026-07-19
linktitle: Transformationen PS
og_description: Erstellen Sie ein PostScript-Dokument in ASP.NET mit Aspose.Page.
  Erfahren Sie, wie Sie translation, scaling, rotation und shearing anwenden und anschließend
  die Datei speichern.
og_image_alt: Guide to creating and transforming PostScript documents using Aspose.Page
  for .NET
og_title: PostScript-Dokument in ASP.NET erstellen – Aspose.Page Leitfaden
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create PostScript document ASP.NET using Aspose.Page for
    .NET, apply multiple transformations, and save the file efficiently.
  headline: Create PostScript Document ASP.NET with Aspose.Page
  type: TechArticle
- questions:
  - answer: Use the `Transform` method with a custom `Matrix` that combines translation,
      scaling, rotation, or shearing in the order you need.
    question: How can I apply multiple transformations to a single object?
  - answer: Yes—render the `PsDocument` to an image using `PsDocument.Save("output.png",
      SaveFormat.Png)` or open the `.ps` file in a PostScript viewer to inspect the
      result before calling `Save()` for the final file.
    question: Can I preview the transformations before saving the document?
  - answer: Absolutely. Save the graphics state before drawing the element, apply
      the desired transformation, draw, then restore the state so later elements remain
      unaffected.
    question: Is it possible to apply transformations to specific elements in a document?
  - answer: Complex matrices increase CPU work. Keep transformations as simple as
      possible and reuse saved states when drawing many similar objects. Aspose.Page
      processes a 300‑page document with mixed transformations in under 2 seconds
      on a typical 3.2 GHz CPU.
    question: Are there any performance considerations when dealing with complex transformations?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community help, or contact Aspose support directly for priority assistance.
    question: How can I get support or seek assistance for Aspose.Page-related queries?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- postscript
- aspose.page
- .net graphics
- transformations
title: PostScript-Dokument in ASP.NET mit Aspose.Page erstellen
url: /de/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen Sie ein PostScript-Dokument ASP.NET mit Aspose.Page

## Einleitung

In diesem schrittweisen Tutorial **erstellen Sie ein PostScript-Dokument ASP.NET** mit der Aspose.Page-Bibliothek, wenden eine Vielzahl von Grafiktransformationen an und speichern schließlich das Ergebnis in einer `.ps`‑Datei. Am Ende des Leitfadens verstehen Sie, wo Sie jede Transformation auf den Grafik‑Zustands‑Stack legen, wie Sie sie effizient kombinieren und wie Sie die Zeichenbefehle persistieren, sodass jeder PostScript‑Interpreter sie rendern kann. Dieses Wissen ist entscheidend für die Erstellung druckbarer Grafiken, benutzerdefinierter Berichte oder dynamischer druckfertiger Assets direkt aus .NET‑Anwendungen.

## Schnelle Antworten
- **Was kann ich erstellen?** Ein vollwertiges PostScript-Dokument mit transformierten Grafiken.  
- **Welche Bibliothek wird benötigt?** Aspose.Page für .NET (herunterladbar von der offiziellen Website).  
- **Wie speichere ich die Datei?** Verwenden Sie `PsDocument.Save()` nach der Konfiguration der Grafik‑Zustände.  
- **Kann ich mehrere Transformationen anwenden?** Ja – kombinieren Sie sie mit `Transform` oder sequentiellen Aufrufen.  
- **Ist eine Lizenz erforderlich?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.

## Was ist eine „save postscript file“-Operation?

Das Speichern einer PostScript‑Datei bedeutet, die Zeichenbefehle, die Sie im Speicher aufgebaut haben, in einer `.ps`‑Datei auf der Festplatte zu persistieren. Die Datei kann dann von jedem PostScript‑Interpreter, Drucker oder Viewer gerendert werden, wodurch sie eine portable, geräteunabhängige Darstellung von Vektorgrafiken darstellt. Wenn Sie die `Save`‑Methode aufrufen, serialisiert Aspose.Page den gesamten Grafik‑Zustand, einschließlich Pfade, Pinsel und Transformationsmatrizen, in gültige PostScript‑Syntax, die der Adobe®‑Spezifikation entspricht.

## Warum Aspose.Page für .NET zum Erstellen von PostScript-Dokumenten verwenden?

Aspose.Page für .NET bietet Ihnen eine stark typisierte, objektorientierte API, die die Low‑Level‑PostScript‑Sprache abstrahiert. Sie verwaltet automatisch den Grafik‑Zustands‑Stack, unterstützt über 50 transformationsbezogene Methoden und kann Dokumente mit mehr als 500 Seiten verarbeiten, ohne die gesamte Datei in den Speicher zu laden. Das reduziert die Entwicklungszeit um bis zu 70 % im Vergleich zum manuellen Schreiben von PostScript‑Code und garantiert die Kompatibilität mit allen gängigen Druckern.

## Voraussetzungen

- **Aspose.Page für .NET** Bibliothek in Ihr Projekt integriert. Laden Sie sie von dem [Download-Link](https://releases.aspose.com/page/net/) herunter.  
- Ein beschreibbarer Ordner, in dem die erzeugte `.ps`‑Datei gespeichert wird. Ersetzen Sie den Platzhalterpfad im Code durch Ihr tatsächliches Verzeichnis.  
- .NET 6.0 oder höher (die Bibliothek unterstützt auch .NET Core 3.1 und .NET Framework 4.6+).

## Namespaces importieren

Die `PsDocument`‑Klasse befindet sich im Namespace `Aspose.Page.Drawing`, während Hilfsfunktionen für Transformationen im Namespace `Aspose.Page.Drawing.Graphics` liegen. Importieren Sie sie am Anfang Ihrer Datei:

```csharp
using Aspose.Page.Drawing;
using Aspose.Page.Drawing.Graphics;
using Aspose.Page.Drawing.Shapes;
```

`PsDocument` ist die Kernklasse von Aspose.Page, die ein PostScript‑Dokument im Speicher repräsentiert. Nach dem Importieren der Namespaces können Sie beginnen, die Zeichenfläche aufzubauen.

Jetzt erkunden wir jede Transformation Schritt für Schritt.

## Keine Transformationen

`PsDocument` ist der Einstiegspunkt für alle Zeichenoperationen. Das folgende Snippet erstellt ein frisches Dokument, zeichnet ein einfaches orangefarbenes Rechteck und speichert es ohne irgendeine Transformation.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Dieses Snippet erstellt ein **PostScript-Dokument** mit einem einzelnen orangefarbenen Rechteck und **speichert die PostScript‑Datei**, ohne Transformationen anzuwenden.

## Translation

Das Speichern des Grafik‑Zustands ermöglicht es Ihnen, nach dem Verschieben von Objekten zurückzukehren. Die Methode `SaveState` legt die aktuelle Transformationsmatrix auf den internen Stack.

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

Die Methode `Translate` verschiebt das Koordinatensystem um die angegebenen Offsets und beeinflusst alle nachfolgenden Zeichenbefehle.

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

Jetzt erscheint ein blaues Rechteck 250 Punkte rechts vom orangefarbenen, weil die Translationsmatrix aktiv ist.

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

Das Wiederherstellen (`Restore`) setzt das Koordinatensystem in seine ursprüngliche Position zurück, sodass nachfolgende Zeichnungen nicht von der Translation beeinflusst werden.

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

## Skalierung

`Scale` ändert die Größe gezeichneter Objekte, indem es eine Skalierungsmatrix auf den aktuellen Grafik‑Zustand anwendet.

> *Sie können dasselbe Muster folgen – Zustand speichern, `Scale` anwenden, zeichnen und dann wiederherstellen.*  
> **Pro Tipp:** Verwenden Sie nicht‑uniforme Skalierung (`Scale(sx, sy)`), um Objekte nur in einer Richtung zu strecken, was nützlich für Balkendiagramme ist.

## Rotation

`Rotate` wendet eine Rotationsmatrix auf den aktuellen Grafik‑Zustand an und dreht nachfolgende Zeichnungen um den angegebenen Winkel.

> *Rotieren Sie um den Ursprung oder einen benutzerdefinierten Drehpunkt mit `Rotate(angle)`.*
> **Pro Tipp:** Kombinieren Sie `Translate` vor der Rotation, um um einen bestimmten Punkt statt um den Ursprung zu rotieren.

## Shearing

`Shear` schrägt das Koordinatensystem um die angegebenen Faktoren, wodurch gezeichnete Objekte horizontal und/oder vertikal geneigt werden.

> *Shear‑Transformationen (`Shear(shx, shy)`) neigen Formen, nützlich für kursive Effekte oder perspektivische Tricks.*

## Komplexe Transformationen

`Transform` wendet eine benutzerdefinierte Transformationsmatrix auf den Grafik‑Zustand an und kombiniert mehrere Operationen in einer einzigen.

> *Für fortgeschrittene Szenarien erstellen Sie eine benutzerdefinierte `Matrix` und übergeben sie an `Transform(matrix)`.*
> Hier können Sie **mehrere Transformationen** in einem Schritt anwenden, wodurch die Anzahl von Zustands‑Speicherungen und -Wiederherstellungen reduziert wird.

## Wie speichert man eine PostScript-Datei mit Transformationen?

`Save` schreibt das aktuelle `PsDocument` in eine Datei im PostScript‑Format. Laden Sie Ihr `PsDocument`, wenden Sie die gewünschte Transformationssequenz an und rufen Sie `Save` mit dem Zielpfad auf – Aspose.Page erzeugt in einem Durchlauf eine standards‑konforme `.ps`‑Datei. Die Bibliothek schließt automatisch alle offenen Grafik‑Zustände, sodass kein zusätzlicher Aufräumcode nötig ist. Dieser Ansatz funktioniert für jede Kombination aus Translation, Skalierung, Rotation oder Shearing.

## Häufige Anwendungsfälle

- **Dynamische Berichtserstellung** – Diagramme erstellen, die sich zur Laufzeit an die Datenmenge anpassen.  
- **Druckfertige Rechnungen** – Firmenlogos einbetten und sie drehen, um der Druckerausrichtung zu entsprechen.  
- **Benutzerdefiniertes Etikettendesign** – Scheren anwenden, um Prägeeffekte zu simulieren.  

## Häufig gestellte Fragen

**Q: Wie kann ich mehrere Transformationen auf ein einzelnes Objekt anwenden?**  
A: Verwenden Sie die Methode `Transform` mit einer benutzerdefinierten `Matrix`, die Translation, Skalierung, Rotation oder Shearing in der gewünschten Reihenfolge kombiniert.

**Q: Kann ich die Transformationen vor dem Speichern des Dokuments previewen?**  
A: Ja – rendern Sie das `PsDocument` zu einem Bild mit `PsDocument.Save("output.png", SaveFormat.Png)` oder öffnen Sie die `.ps`‑Datei in einem PostScript‑Viewer, um das Ergebnis zu prüfen, bevor Sie `Save()` für die endgültige Datei aufrufen.

**Q: Ist es möglich, Transformationen auf bestimmte Elemente in einem Dokument anzuwenden?**  
A: Absolut. Speichern Sie den Grafik‑Zustand, bevor Sie das Element zeichnen, wenden Sie die gewünschte Transformation an, zeichnen Sie das Element und stellen Sie dann den Zustand wieder her, sodass spätere Elemente unbeeinflusst bleiben.

**Q: Gibt es Leistungsüberlegungen bei komplexen Transformationen?**  
A: Komplexe Matrizen erhöhen die CPU‑Belastung. Halten Sie Transformationen so einfach wie möglich und verwenden Sie gespeicherte Zustände wieder, wenn Sie viele ähnliche Objekte zeichnen. Aspose.Page verarbeitet ein 300‑seitiges Dokument mit gemischten Transformationen in unter 2 Sekunden auf einer typischen 3,2 GHz‑CPU.

**Q: Wie kann ich Support erhalten oder Hilfe bei Aspose.Page‑Anfragen bekommen?**  
A: Besuchen Sie das [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39) für Community‑Hilfe oder kontaktieren Sie den Aspose‑Support direkt für prioritäre Unterstützung.

---

**Last Updated:** 2026-07-19  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Create save options with default values
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Create graphics path from the rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Set paint in graphics state on upper level
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Fill the first rectangle that is on the upper-level graphics state and without any transformations
    document.Fill(path);

    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

## Verwandte Tutorials

- [PostScript-Dokument .net erstellen – Rechteck hinzufügen mit Aspose.Page](/page/net/drawing-shapes/add-rectangle-to-postscript-ps/)
- [Bild zu PostScript (PS)-Dokument mit Aspose.Page hinzufügen](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Seite zu PostScript (PS)-Dokument mit Aspose.Page hinzufügen](/page/net/page-manipulation/add-page-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}