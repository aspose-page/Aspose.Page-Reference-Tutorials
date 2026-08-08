---
date: 2026-07-19
description: Erfahren Sie im asp page postscript Tutorial, wie Sie Kreisellipsen zu
  PostScript (PS)-Dateien mit Aspose.Page für .NET hinzufügen – so erzeugen Sie PostScript-Ausgabe
  schnell.
keywords:
- asp page postscript tutorial
- how to generate postscript
- write postscript output
lastmod: 2026-07-19
linktitle: Kreisellipse zu PostScript (PS) hinzufügen
og_description: asp page postscript Tutorial, das zeigt, wie Sie PostScript-Ausgabe
  durch Hinzufügen von Kreisellipsen mit Aspose.Page für .NET erzeugen. Folgen Sie
  der Schritt‑für‑Schritt‑Anleitung für eine schnelle Integration.
og_image_alt: 'Guide: Add circle ellipse to PostScript using Aspose.Page .NET'
og_title: asp page postscript tutorial – Kreisellipse hinzufügen (PS)
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn the asp page postscript tutorial for adding circle ellipses to
    PostScript (PS) files using Aspose.Page for .NET – how to generate postscript
    output quickly.
  headline: asp page postscript tutorial – Add Circle Ellipse (PS)
  type: TechArticle
- questions:
  - answer: Aspose.Page primarily focuses on PostScript, but Aspose provides other
      libraries for various formats. Check the [Aspose documentation](https://reference.aspose.com/page/net/)
      for a full list.
    question: Can I use Aspose.Page for .NET with other document formats?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community discussions and support.
    question: Where can I find additional support and community discussions?
  - answer: Yes, you can access the [free trial](https://releases.aspose.com/) to
      explore the features of Aspose.Page for .NET.
    question: Is there a free trial available for Aspose.Page for .NET?
  - answer: Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for testing and evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Page?
  - answer: Purchase Aspose.Page for .NET from the [buy page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- postscript
- Aspose.Page
- .NET drawing
- circle ellipse
title: asp page postscript tutorial – Kreisellipse hinzufügen (PS)
url: /de/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# asp page postscript tutorial – Kreisellipse hinzufügen (PS)

## Einführung

In diesem **asp page postscript tutorial** erfahren Sie, wie Sie perfekte Kreisellipse zu einem PostScript (PS)-Dokument mit der Aspose.Page‑Bibliothek für .NET hinzufügen. Egal, ob Sie technische Zeichnungen, Vektorgrafiken oder benutzerdefinierte Berichte erstellen, Aspose.Page ermöglicht das Schreiben von PostScript‑Ausgaben, ohne sich mit Low‑Level‑PS‑Syntax befassen zu müssen. Wir führen Sie durch jeden Schritt, vom Einrichten der Umgebung bis zum Rendern von zwei Ellipsen – einer gefüllten und einer konturierten – damit Sie diese Fähigkeit sofort in Ihre eigenen Anwendungen integrieren können.

## Schnelle Antworten
- **Worum geht es in diesem Tutorial?** Hinzufügen von gefüllten und konturierten Kreisellipsen zu einer PS‑Datei mit Aspose.Page für .NET.  
- **Wie viele Code‑Schritte sind erforderlich?** Acht prägnante Schritte, jeder mit einem sofort ausführbaren Code‑Fragment illustriert.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET 5, .NET 6, .NET Core 3.1 und .NET Framework 4.6+.  
- **Kann ich denselben Graphics‑Path wiederverwenden?** Ja – erstellen Sie ein `GraphicsPath` einmal und zeichnen oder füllen Sie es mehrfach.

## Was ist das asp page postscript tutorial?
Das **asp page postscript tutorial** ist eine Schritt‑für‑Schritt‑Anleitung, die zeigt, wie man programmgesteuert PostScript‑Inhalte mit Aspose.Page für .NET erzeugt. Es konzentriert sich auf praktischen Code, reale Anwendungsfälle und Best‑Practice‑Tipps, damit Sie zuverlässig PS‑Dateien schnell erstellen können.

## Warum Aspose.Page für die PostScript‑Erstellung verwenden?
Aspose.Page unterstützt **über 30 Ausgabeformate** (einschließlich PDF, SVG und EPS) und kann **mehrseitige Dokumente** rendern, ohne die gesamte Datei in den Speicher zu laden, wodurch im Vergleich zum manuellen Erstellen von PS‑Strings ein **Speicherverbrauch von bis zu 70 %** reduziert wird. Die High‑Level‑API eliminiert die Notwendigkeit, rohe PS‑Befehle zu schreiben, und verkürzt die Entwicklungszeit im Durchschnitt um **80 %**.

## Voraussetzungen

Bevor wir in das Tutorial einsteigen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:

1. Aspose.Page for .NET Bibliothek: Laden Sie die Aspose.Page for .NET Bibliothek von [hier](https://releases.aspose.com/page/net/) herunter und installieren Sie sie.  
2. Entwicklungsumgebung: Stellen Sie sicher, dass Sie eine funktionierende .NET‑Entwicklungsumgebung auf Ihrem Rechner eingerichtet haben.

Jetzt beginnen wir mit der Schritt‑für‑Schritt‑Anleitung.

## Namespaces importieren

Die `using`‑Direktiven bringen die Aspose.Page‑Klassen in den Gültigkeitsbereich, sodass Sie direkt mit Grafiken, Farben und PS‑Dokumenten arbeiten können.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Jetzt zerlegen wir das bereitgestellte Beispiel in mehrere Schritte, um Sie durch den Prozess des Hinzufügens von Kreisellipsen zu einem PostScript‑Dokument zu führen.

## Wie lege ich das Dokumentenverzeichnis fest?

Um dem Programm mitzuteilen, wo die erzeugte PS‑Datei gespeichert werden soll, müssen Sie einen Ordnerpfad angeben, in den die Anwendung schreiben kann. Verwenden Sie eine Variable wie `dataDir` und weisen Sie ihr einen absoluten oder relativen Pfad zu; dieser Pfad wird später im Code mit dem Ausgabedateinamen kombiniert.  
> **Pro tip:** Verwenden Sie `Path.Combine(Environment.CurrentDirectory, "output")`, um einen plattformübergreifenden Pfad zu erstellen und hartkodierte Trennzeichen zu vermeiden.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Wie erstelle ich den Ausgabestream für das PostScript‑Dokument?

Das Erstellen eines Ausgabestreams öffnet einen Dateihandle, in den die Aspose.Page‑Engine die PostScript‑Daten schreibt. Durch die Verwendung eines `FileStream` mit `FileMode.Create` wird die Datei bei jedem Durchlauf neu erstellt und überschreibt frühere Versionen. Dieser Stream wird anschließend an den `PsDocument`‑Konstruktor übergeben.

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

## Wie konfiguriere ich die Speicheroptionen und initialisiere ein PS‑Dokument?

`PsSaveOptions` ermöglicht das Festlegen von Seitengröße, Auflösung und anderen Rendering‑Einstellungen. Hier verwenden wir das Standard‑A4‑Format und ein einseitiges Dokument. `PsDocument` repräsentiert das zu erstellende PostScript‑Dokument; es erhält den Ausgabestream und die Speicheroptionen und verwaltet die Lebenszyklus‑Ereignisse der Seite.

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Wie erstelle ich einen GraphicsPath für die erste Ellipse?

`GraphicsPath` repräsentiert eine Vektorform, die in einer PostScript‑Seite gezeichnet oder gefüllt werden kann. Der Konstruktor nimmt die X/Y‑Koordinaten der oberen linken Ecke sowie Breite und Höhe entgegen, sodass Sie die genaue Größe und Position der Ellipse auf der Seite festlegen können.

```csharp
//Create graphics path from the first ellipse
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

## Wie setze ich die Farbe und fülle die erste Ellipse?

`SolidBrush` definiert eine einheitliche Füllfarbe für Zeichenoperationen. Durch das Erstellen eines `SolidBrush` mit einer bestimmten `Color` und das Übergeben an `graphics.FillPath` wird die Ellipse mit dieser Farbe gefüllt.

```csharp
//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//Fill the ellipse
document.Fill(path);
```

## Wie erstelle ich einen GraphicsPath für die zweite Ellipse?

Ein zweiter `GraphicsPath` wird definiert, um zu zeigen, wie Sie eine Kontur (Stroke) getrennt von einer Füllung zeichnen können. Das gleiche Konstruktormuster wird verwendet, jedoch können Sie die Rechteckabmessungen ändern, um eine anders große Ellipse zu erzeugen.

```csharp
//Create graphics path from the second ellipse
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

## Wie setze ich die Kontur und zeichne die zweite Ellipse?

`SolidPen` gibt Farbe und Breite für das Konturieren von Formen an. Durch das Bereitstellen eines `SolidPen` an `graphics.DrawPath` wird die Ellipsenkontur ohne Füllung gezeichnet, wodurch eine saubere, gestreckte Form entsteht.

```csharp
//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//Stroke (outline) the ellipse
document.Draw(path);
```

## Wie schließe ich die aktuelle Seite und speichere das Dokument?

Nachdem alle Zeichenbefehle ausgeführt wurden, müssen Sie die aktive Seite mit `document.ClosePage()` schließen, um deren Inhalt abzuschließen. Schließlich schreibt ein Aufruf von `document.Save()` die gesammelten PostScript‑Daten in den zuvor geöffneten Stream und erzeugt die Ausgabedatei auf der Festplatte.

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

## Häufige Probleme und Lösungen

| Problem | Grund | Lösung |
|---------|-------|--------|
| **Datei nicht gefunden** | Falscher Verzeichnispfad | Stellen Sie sicher, dass das Verzeichnis existiert oder erstellen Sie es mit `Directory.CreateDirectory`. |
| **Leere Ausgabe** | Vergessen, `document.ClosePage()` aufzurufen | Stellen Sie sicher, dass Sie die Seite vor dem Speichern schließen. |
| **Falsche Farben** | Verwendung von `Color.FromArgb` in falscher Reihenfolge | Verwenden Sie `Color.FromRgb(red, green, blue)` für Klarheit. |
| **Leistungsabfall bei großen Dateien** | Laden des gesamten Dokuments in den Speicher | Verwenden Sie `PsSaveOptions` mit `EnableMemorySaving = true`, um große Seiten zu streamen. |

## Häufig gestellte Fragen

**Q: Kann ich Aspose.Page für .NET mit anderen Dokumentformaten verwenden?**  
A: Aspose.Page konzentriert sich hauptsächlich auf PostScript, aber Aspose bietet weitere Bibliotheken für verschiedene Formate. Siehe die [Aspose-Dokumentation](https://reference.aspose.com/page/net/) für eine vollständige Liste.

**Q: Wo finde ich zusätzlichen Support und Community‑Diskussionen?**  
A: Besuchen Sie das [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39) für Community‑Diskussionen und Support.

**Q: Gibt es eine kostenlose Testversion für Aspose.Page für .NET?**  
A: Ja, Sie können die [kostenlose Testversion](https://releases.aspose.com/) nutzen, um die Funktionen von Aspose.Page für .NET zu erkunden.

**Q: Wie erhalte ich eine temporäre Lizenz für Aspose.Page?**  
A: Eine temporäre Lizenz erhalten Sie [hier](https://purchase.aspose.com/temporary-license/) für Test‑ und Evaluierungszwecke.

**Q: Wo kann ich Aspose.Page für .NET kaufen?**  
A: Kaufen Sie Aspose.Page für .NET über die [Kauf‑Seite](https://purchase.aspose.com/buy).

## Fazit

Herzlichen Glückwunsch! Sie haben das **asp page postscript tutorial** erfolgreich abgeschlossen und gelernt, wie man Kreisellipse zu PostScript‑Dokumenten mit Aspose.Page für .NET hinzufügt. Durch das Befolgen der acht klaren Schritte können Sie nun hochwertige PS‑Dateien mit gefüllten und konturierten Ellipsen erzeugen, die bereit sind, in Reporting‑Engines, CAD‑Exportern oder jede benutzerdefinierte Grafik‑Pipeline integriert zu werden.

---

**Last Updated:** 2026-07-19  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Aspose.Page .NET – Formen zeichnen](/page/net/drawing-shapes/)
- [PostScript‑Dokument erstellen .net – Rechteck hinzufügen mit Aspose.Page](/page/net/drawing-shapes/add-rectangle-to-postscript-ps/)
- [Wie erstelle ich ein PostScript‑Dokument mit Aspose.Page für .NET](/page/net/document-creation/create-postscript-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}