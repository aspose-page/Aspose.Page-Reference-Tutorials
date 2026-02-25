---
date: 2026-02-25
description: Lernen Sie, wie Sie einen linearen Farbverlauf-Pinsel in C# verwenden,
  um einem PS‑Datei einen Farbverlauf hinzuzufügen und ein Rechteck mit einem Farbverlauf
  zu füllen, mithilfe von Aspose.Page für .NET.
linktitle: Add Vertical Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: c# Linear Gradient Brush – Vertikalen Verlauf zu PostScript (PS) mit Aspose.Page
  hinzufügen
url: /de/net/gradient-fills/add-vertical-gradient-to-postscript-ps/
weight: 14
---

 bullet list under Quick Answers, table, FAQ.

Make sure to keep markdown syntax.

Let's produce the translated content.

Check shortcodes at top and bottom: keep same.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# c# Linear Gradient Brush – Vertikalen Farbverlauf zu PostScript (PS) mit Aspose.Page hinzufügen

## Einführung

Im Bereich der Dokumentenmanipulation und -erstellung zeichnet sich **Aspose.Page for .NET** als leistungsstarkes Werkzeug für Entwickler aus. In diesem Leitfaden erfahren Sie, wie Sie **einen Farbverlauf zu PS**‑Dateien hinzufügen, indem Sie einen **C# linear gradient brush** verwenden, um ein **Rechteck mit Farbverlauf zu füllen**. Am Ende dieses Tutorials besitzen Sie ein klares, schritt‑für‑Schritt‑Verständnis des erforderlichen Codes und wissen, warum diese Technik einen sanften vertikalen Farbverlauf in Ihrer PostScript‑Ausgabe erzeugt.

## Schnellantworten
- **Was macht ein C# linear gradient brush?** Er erzeugt einen sanften Übergang zwischen mehreren Farben über einer Form.
- **Kann ich das mit jeder .NET‑Version verwenden?** Ja, Aspose.Page unterstützt .NET Framework 4.5+ und .NET Core/5+.
- **Benötige ich eine Lizenz für die Produktion?** Für Nicht‑Evaluierungs‑Builds ist eine kommerzielle Lizenz erforderlich.
- **Ist der Farbverlauf wirklich vertikal?** Der Pinsel wird um 90° gedreht, wodurch ein vertikaler Verlauf entsteht.
- **Wo wird die Ausgabe gespeichert?** Im Pfad, den Sie in `dataDir` angeben (z. B. `VerticalGradient_outPS.ps`).

## Was ist ein C# Linear Gradient Brush?
Ein **C# linear gradient brush** ist ein GDI+‑Objekt (`LinearGradientBrush`), das einen linearen Farbwechsel zwischen definierten Punkten malt. In Kombination mit der Zeichen‑API von Aspose.Page ermöglicht er das Rendern anspruchsvoller Farbverläufe direkt in ein PostScript‑(PS‑)Dokument.

## Warum einen Linear Gradient Brush für PostScript verwenden?
- **Hochwertige Ausgabe:** Farbverläufe werden auf Druckerebene gerendert und behalten ihre Detailtreue.
- **Volle Kontrolle:** Sie können benutzerdefinierte Farb‑Stops, Drehung und Skalierung festlegen.
- **Wiederverwendbarer Code:** Die gleiche Pinsel‑Logik funktioniert für PDF, SVG und andere von Aspose.Page unterstützte Formate.

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Folgendes vorhanden ist:

- Aspose.Page for .NET: Vergewissern Sie sich, dass die Aspose.Page‑Bibliothek installiert ist. Die notwendigen Ressourcen und die Dokumentation finden Sie [hier](https://reference.aspose.com/page/net/).
- Entwicklungsumgebung: Richten Sie eine geeignete Entwicklungsumgebung ein, einschließlich einer integrierten Entwicklungsumgebung (IDE) für .NET‑Entwicklung.
- Grundkenntnisse: Machen Sie sich mit den Grundlagen der .NET‑Entwicklung vertraut, insbesondere im Umgang mit Streams, Graphics‑Paths und Farbmanipulation.

## Namespaces importieren

Fügen Sie in Ihrem C#‑Projekt zu Beginn Ihrer Code‑Datei die erforderlichen Namespaces ein:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Schritt 1: Dokumentverzeichnis festlegen

Geben Sie den Pfad zu Ihrem Dokumentverzeichnis an. Dort wird Ihr PS‑Dokument gespeichert.

```csharp
string dataDir = "Your Document Directory";
```

## Schritt 2: Ausgabestream für das PostScript‑Dokument erstellen

Erzeugen Sie einen Ausgabestream für das PostScript‑Dokument mithilfe der Klasse `FileStream`.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
```

## Schritt 3: Speicheroptionen und PS‑Dokument erstellen

Erstellen Sie Speicheroptionen mit A4‑Größe und initialisieren Sie ein neues einseitiges PS‑Dokument.

```csharp
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Schritt 4: Rechteck‑Abmessungen definieren

Geben Sie die Abmessungen und die Position des Rechtecks an, in dem der vertikale Farbverlauf angewendet werden soll.

```csharp
float offsetX = 200;
float offsetY = 100;
float width = 200;
float height = 100;
```

## Schritt 5: Graphics‑Path erstellen

Erstellen Sie einen Graphics‑Path aus dem definierten Rechteck.

```csharp
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(offsetX, offsetY, width, height));
```

## Schritt 6: Interpolationsfarben festlegen

Definieren Sie ein Array von Interpolationsfarben und -positionen für den Farbverlauf.

```csharp
Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
ColorBlend colorBlend = new ColorBlend();
colorBlend.Colors = colors;
colorBlend.Positions = positions;
```

## Schritt 7: Linear Gradient Brush erstellen

Erzeugen Sie einen linear gradient brush mit dem Rechteck als Begrenzung sowie Start‑ und Endfarbe.

```csharp
LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
brush.InterpolationColors = colorBlend;
```

## Schritt 8: Brush‑Transformation setzen

Legen Sie eine Transformation für den Pinsel fest, sodass die X‑ und Y‑Skalierungskomponenten der Breite und Höhe des Rechtecks entsprechen.

```csharp
Matrix brushTransform = new Matrix(width, 0, 0, height, offsetX, offsetY);
brushTransform.Rotate(90);
brush.Transform = brushTransform;
```

## Schritt 9: Paint setzen und das Rechteck füllen

Setzen Sie das Paint für das Dokument und **füllen Sie das Rechteck mit Farbverlauf** mithilfe des zuvor definierten Pfads.

```csharp
document.SetPaint(brush);
document.Fill(path);
```

## Schritt 10: Aktuelle Seite schließen und Dokument speichern

Schließen Sie die aktuelle Seite und speichern Sie das PostScript‑Dokument.

```csharp
document.ClosePage();
document.Save();
```

Herzlichen Glückwunsch! Sie haben erfolgreich **einen vertikalen Farbverlauf zu einem PostScript‑Dokument** mithilfe eines **C# linear gradient brush** mit Aspose.Page for .NET hinzugefügt. Experimentieren Sie mit verschiedenen Parametern und Farben, um unterschiedliche visuelle Effekte in Ihren Dokumenten zu erzielen.

## Häufige Probleme und Lösungen

| Problem | Warum es passiert | Wie man es behebt |
|---------|-------------------|-------------------|
| Farbverlauf erscheint horizontal | Pinsel‑Drehung nicht angewendet | Stellen Sie sicher, dass `brushTransform.Rotate(90);` vor der Zuweisung zu `brush.Transform` aufgerufen wird. |
| Farben wirken ausgewaschen | Ausgabestream mit niedriger Auflösung | Verwenden Sie ein höher aufgelöstes `PsSaveOptions` oder erhöhen Sie die Dokumentgröße. |
| Ausgabedatei ist leer | Stream nicht geleert | Vergewissern Sie sich, dass `document.Save();` außerhalb des `using`‑Blocks aufgerufen wird. |

## Häufig gestellte Fragen

**F1: Kann ich mehrere Farbverläufe auf verschiedene Bereiche desselben Dokuments anwenden?**  
A: Ja, das ist möglich. Wiederholen Sie einfach die Schritte für jeden Bereich mit den jeweiligen Abmessungen und Farbschemata.

**F2: Wie integriere ich diesen Code in mein bestehendes .NET‑Projekt?**  
A: Kopieren Sie den Code in Ihre Projektdatei und stellen Sie sicher, dass die Aspose.Page‑Bibliothek referenziert wird.

**F3: Gibt es weitere Farbverlaufstypen in Aspose.Page für .NET?**  
A: Aspose.Page unterstützt verschiedene Farbverlaufstypen, einschließlich radialer und Pfad‑Farbverläufe. Weitere Details finden Sie in der Dokumentation.

**F4: Kann ich Aspose.Page für kommerzielle Projekte nutzen?**  
A: Ja, das können Sie. Besuchen Sie [hier](https://purchase.aspose.com/buy), um Lizenzoptionen zu prüfen.

**F5: Gibt es ein Community‑Forum für Aspose.Page, in dem ich Hilfe finden kann?**  
A: Natürlich! Gehen Sie zum [Aspose.Page‑Forum](https://forum.aspose.com/c/page/39), um sich mit anderen Entwicklern auszutauschen und Unterstützung zu erhalten.

---

**Zuletzt aktualisiert:** 2026-02-25  
**Getestet mit:** Aspose.Page 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}