---
date: 2026-03-29
description: Erfahren Sie, wie Sie einen linearen Farbverlauf‑Pinsel in C# verwenden,
  um Pseudo‑Transparenz in PostScript mit Aspose.Page für .NET zu erzeugen.
linktitle: Show Pseudo-Transparency in PostScript (PS)
second_title: Aspose.Page .NET API
title: Linearer Farbverlauf-Pinsel C# für Pseudo‑Transparenz in PS
url: /de/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Linear Gradient Brush C# für Pseudo‑Transparenz in PostScript (PS)

## Einführung

Wenn Sie Ihren PostScript‑ (PS‑) Dateien einen dezenten Durchsichtigkeitseffekt hinzufügen möchten, ist der **linear gradient brush C#** das perfekte Werkzeug. Aspose.Page für .NET ermöglicht es Ihnen, Rechtecke sowohl mit undurchsichtigen als auch mit transluzenten Farbverlauf‑Füllungen zu malen und verleiht Ihren Dokumenten ein modernes, geschichtetes Aussehen. In diesem Tutorial führen wir Sie Schritt für Schritt durch die Erstellung von Pseudo‑Transparenz mithilfe eines linearen Farbverlaufs‑Pinsels in C#.

## Schnelle Antworten
- **Welche Bibliothek stellt den linearen Farbverlaufs‑Pinsel bereit?** Aspose.Page für .NET
- **Welche Grafik‑Klasse erzeugt den Verlauf?** `LinearGradientBrush`
- **Kann ich die Opazität pro Farbe steuern?** Ja, mittels `Color.FromArgb(alpha, …)`
- **Benötige ich eine Lizenz für den Produktionseinsatz?** Eine gültige Aspose.Page‑Lizenz ist erforderlich
- **Unterstützte .NET‑Versionen?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## Was ist ein linear gradient brush C#?

Ein `LinearGradientBrush` ist ein GDI+‑Objekt, das einen sanften Übergang zwischen zwei Farben entlang einer geraden Linie malt. Wenn Sie den Alphakanal (0‑255) für jede Farbe angeben, können Sie transluzente Verläufe erzeugen – genau das, was wir für Pseudo‑Transparenz in PostScript benötigen.

## Warum einen linear gradient brush C# für Pseudo‑Transparenz verwenden?

- **Fein abgestimmte Opazitätssteuerung:** Passen Sie den Alpha‑Wert jeder Farbe an, um das gewünschte Durchsichtigkeitsniveau zu erreichen.  
- **Geräteunabhängige Darstellung:** Der Pinsel funktioniert identisch auf Bildschirm, PDF, EPS und PS‑Ausgaben.  
- **Einfache API:** Wenige Zeilen C#‑Code erzeugen professionelle visuelle Effekte.

## Voraussetzungen

Bevor Sie in den Code eintauchen, stellen Sie sicher, dass Sie:

- Aspose.Page für .NET installiert haben. Sie können es von der [Aspose.Page Dokumentation](https://reference.aspose.com/page/net/) herunterladen.
- Einen beschreibbaren Ordner besitzen, in dem das erzeugte PostScript‑Dokument gespeichert wird.

Jetzt, wo Sie die notwendigen Werkzeuge haben, können wir mit dem Aufbau der pseudo‑transparenten Rechtecke beginnen.

## Namespaces importieren

Bevor wir beginnen, importieren Sie die Namespaces, die die Klassen enthalten, die wir verwenden werden:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Schritt 1: Erstellen des Ausgabestreams für das PostScript‑Dokument

Wir beginnen damit, einen Dateistream zu erstellen, der die resultierende PS‑Datei enthält, und initialisieren anschließend das `PsDocument`.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();

	// Create new 1‑paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Schritt 2: Erstellen eines Rechtecks mit einer **undurchsichtigen** Farbverlauf‑Füllung

Hier bauen wir einen `LinearGradientBrush`, dessen Farben vollständig undurchsichtig sind (Alpha = 255). Dieses Rechteck dient als Hintergrundschicht.

```csharp
	float offsetX = 50;
	float offsetY = 100;
	float width = 200;
	float height = 100;

	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	LinearGradientBrush opaqueBrush = new LinearGradientBrush(new RectangleF(0, 0, 200, 100), Color.FromArgb(0, 0, 0),
		Color.FromArgb(40, 128, 70), 0f);
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	opaqueBrush.Transform = brushTransform;
	Aspose.Page.EPS.GradientBrush gradientBrush = new GradientBrush(opaqueBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Schritt 3: Erstellen eines Rechtecks mit einer **transluzenten** Farbverlauf‑Füllung

Jetzt verwenden wir einen **linear gradient brush C#**, bei dem die Alpha‑Werte kleiner als 255 sind (z. B. 150 und 50). Dadurch wird das Rechteck teilweise durchsichtig und erzielt den Pseudo‑Transparenz‑Effekt.

```csharp
	offsetX = 350;

	//Create graphics path from the first rectangle
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Create linear gradient brush colors which transparency are not 255, but 150 and 50. So it are translucent.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Schritt 4: Seite schließen und Dokument speichern

Abschließend beenden wir die Seite und schreiben die PS‑Datei auf die Festplatte.

```csharp
	document.ClosePage();
	document.Save();
}
// ExEnd:1
```

Durch das Befolgen dieser vier Schritte können Sie nahtlos undurchsichtige und transluzente Rechtecke mischen und so einen überzeugenden Pseudo‑Transparenz‑Effekt in jeder PostScript‑Ausgabe erzeugen.

## Häufige Probleme und Lösungen

| Problem | Warum es passiert | Lösung |
|---------|-------------------|--------|
| Farben erscheinen vollständig undurchsichtig | Alphawert versehentlich auf 255 gesetzt | Verwenden Sie `Color.FromArgb(alpha, …)` mit `alpha` < 255 |
| Verlauf wird falsch gestreckt | Falsche Transformationsmatrix | Überprüfen Sie, ob die Matrixparameter mit den Rechteckabmessungen übereinstimmen |
| Ausgabedatei ist leer | Stream nicht geschlossen oder `Save()` nicht aufgerufen | Stellen Sie sicher, dass `document.ClosePage()` und `document.Save()` innerhalb des `using`‑Blocks ausgeführt werden |

## Häufig gestellte Fragen

**F: Ist Aspose.Page mit allen .NET‑Versionen kompatibel?**  
**A:** Aspose.Page für .NET ist mit verschiedenen Versionen des .NET‑Frameworks kompatibel und bietet damit Flexibilität und einfache Integration.

**F: Kann ich Pseudo‑Transparenz auf andere Formen als Rechtecke anwenden?**  
**A:** Ja, dieselben Prinzipien können auf jede Form angewendet werden, indem der `GraphicsPath` entsprechend angepasst wird.

**F: Wo finde ich weitere Beispiele und Dokumentation?**  
**A:** Durchsuchen Sie die [Aspose.Page Dokumentation](https://reference.aspose.com/page/net/) für umfassende Beispiele und detaillierte API‑Referenzen.

**F: Gibt es eine kostenlose Testversion für Aspose.Page?**  
**A:** Ja, Sie können eine kostenlose Testversion von Aspose.Page über [diesen Link](https://releases.aspose.com/) erhalten.

**F: Wie kann ich eine temporäre Lizenz für Aspose.Page erhalten?**  
**A:** Besuchen Sie [diesen Link](https://purchase.aspose.com/temporary-license/), um eine temporäre Lizenz für Aspose.Page zu erhalten.

---

**Zuletzt aktualisiert:** 2026-03-29  
**Getestet mit:** Aspose.Page 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}