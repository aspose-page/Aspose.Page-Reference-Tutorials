---
date: 2026-03-29
description: Erfahren Sie, wie Sie transparente Objekte zu XPS‑Dokumenten hinzufügen
  und anschließend XPS mit Aspose.Page für .NET in PDF exportieren. Schritt‑für‑Schritt‑Anleitung
  mit praktischen Tipps.
linktitle: Add Transparent Object to XPS Document
second_title: Aspose.Page .NET API
title: XPS nach PDF exportieren – Transparentes Objekt mit Aspose.Page hinzufügen
url: /de/net/transparency-effects/add-transparent-object-to-xps-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Export XPS nach PDF – Transparentes Objekt hinzufügen mit Aspose.Page

## Einführung

In diesem Tutorial lernen Sie, wie Sie transparente Objekte zu einem XPS-Dokument hinzufügen und anschließend **XPS nach PDF exportieren** mit Aspose.Page für .NET. Transparenz kann Ihre Dokumente moderner wirken lassen und Ihnen helfen, wichtige Informationen hervorzuheben. Wir gehen jeden Schritt durch, erklären die Logik hinter dem Code und zeigen Ihnen, wie Sie den Workflow abschließen, indem Sie die XPS-Datei in ein PDF konvertieren, das sich leicht teilen lässt.

## Schnelle Antworten
- **Was bedeutet „XPS nach PDF exportieren“?** Konvertieren einer XPS-Datei in eine PDF-Datei bei gleichzeitiger Beibehaltung von Layout, Farben und Transparenz.  
- **Warum zuerst Transparenz hinzufügen?** Transparente Objekte ermöglichen das Erstellen von geschichteten Grafiken, die im finalen PDF großartig aussehen.  
- **Benötige ich eine Lizenz?** Ja, eine gültige Aspose.Page-Lizenz ist für den Produktionseinsatz erforderlich.  
- **Läuft das auf .NET Core?** Absolut – Aspose.Page unterstützt .NET Core, .NET 5/6 und das vollständige .NET Framework.  
- **Wo finde ich weitere Beispiele?** Schauen Sie in die Aspose.Page‑Dokumentation und das Community‑Forum, die unten verlinkt sind.

## Voraussetzungen

Bevor Sie in das Tutorial einsteigen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Aspose.Page für .NET: Stellen Sie sicher, dass die Aspose.Page-Bibliothek für .NET installiert ist. Sie können sie von [Aspose.Page für .NET Dokumentation](https://reference.aspose.com/page/net/) herunterladen.

## Namespaces importieren

Um zu beginnen, fügen Sie die erforderlichen Namespaces in Ihr Projekt ein:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Jetzt fahren wir mit der Schritt‑für‑Schritt‑Anleitung fort.

## Schritt 1: Neues XPS-Dokument erstellen

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Dieser Code initialisiert ein neues XPS-Dokument mit Aspose.Page für .NET.

## Schritt 2: Transparenz demonstrieren

```csharp
// Just to demonstrate transparency
doc.AddPath(doc.CreatePathGeometry("M120,0 H400 v1000 H120")).Fill = doc.CreateSolidColorBrush(Color.Gray);
doc.AddPath(doc.CreatePathGeometry("M300,120 h600 V420 h-600")).Fill = doc.CreateSolidColorBrush(Color.Gray);
```

Diese Zeilen erzeugen zwei graue Pfade, die als Hintergrund für die später hinzuzufügenden transparenten Formen dienen.

## Schritt 3: Pfad mit geschlossener Rechteckgeometrie erstellen

```csharp
XpsPath path1 = doc.CreatePath(doc.CreatePathGeometry("M20,20 h200 v200 h-200 z"));
path1.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

Hier erstellen wir ein blaues Rechteck. Da wir später seine Opazität ändern, wird das Rechteck im finalen PDF halbtransparent erscheinen.

## Schritt 4: Pfade und Farben manipulieren

```csharp
XpsPath path2 = doc.Add(path1);
path2.Fill = doc.CreateSolidColorBrush(Color.Green);
```

Wir klonen das erste Rechteck, fügen es der Seite hinzu und ändern seine Füllfarbe zu Grün. Dies zeigt, wie einfach es ist, vorhandene Geometrie wiederzuverwenden.

## Schritt 5: Pfade klonen und transformieren

```csharp
XpsPath path3 = doc.Add(path2);
path3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 300);
path3.Fill = doc.CreateSolidColorBrush(Color.Red);
```

Der geklonte Pfad wird um 300 Einheiten nach unten verschoben und rot gefärbt, wodurch ein gestapelter Ebeneneffekt entsteht.

## Schritt 6: Pfade wiederholen und modifizieren

```csharp
XpsPath path4 = doc.AddPath(path2.Data);
path4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 300, 0);
path4.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

Wir verwenden die Geometriedaten von `path2` erneut, verschieben sie nach rechts und wenden erneut eine blaue Füllung an.

## Schritt 7: Opazität verwalten

```csharp
XpsPath path5 = doc.Add(path4);
path5.RenderTransform = path5.RenderTransform.Clone();
path5.RenderTransform.Translate(0, 300);
path5.Fill.Opacity = 0.8f;
```

Durch das Setzen der `Opacity`‑Eigenschaft auf 0,8 wird dieses Rechteck zu 80 % undurchsichtig, was zeigt, wie Sie die Transparenz jedes Elements feinabstimmen können.

## Schritt 8: XPS-Dokument speichern

```csharp
doc.Save(dataDir + "WorkingWithTransparency_out.xps");
```

Die XPS-Datei ist nun mit allen angewendeten transparenten Objekten gespeichert.  

**Export nach PDF:** Um **XPS nach PDF zu exportieren**, rufen Sie einfach `doc.Save` erneut mit der Erweiterung `.pdf` auf, z. B. `doc.Save(dataDir + "TransparentDocument.pdf");`. Die gleiche visuelle Treue, einschließlich der Opazitätseinstellungen, wird im resultierenden PDF beibehalten.

## Warum XPS nach PDF exportieren, nachdem Transparenz hinzugefügt wurde?

- **Universelle Kompatibilität:** PDF wird plattformübergreifend breit unterstützt, während XPS eher nischig ist.  
- **Erhaltene visuelle Effekte:** Aspose.Page bewahrt Transparenz, Verläufe und Matrix‑Transformationen während der Konvertierung.  
- **Einfaches Teilen:** PDFs können in Browsern, mobilen Geräten und vielen Drittanbieter‑Readern ohne zusätzliche Plugins geöffnet werden.

## Häufige Anwendungsfälle

- **Marketing‑Broschüren**, bei denen geschichtete Grafiken ein Premium‑Gefühl vermitteln.  
- **Technische Diagramme**, die hervorgehobene Abschnitte benötigen, ohne das Layout zu überladen.  
- **Berichtserstellung**, bei der Sie Wasserzeichen oder Logos mit teilweiser Opazität überlagern möchten.

## Tipps & Fallstricke

- **Pro‑Tipp:** Setzen Sie den `Opacity`‑Wert immer zwischen 0 und 1. Werte außerhalb dieses Bereichs werden abgeschnitten und können unerwartete Ergebnisse erzeugen.  
- **Performance‑Tipp:** Das Wiederverwenden von Geometrie (`path2.Data`) reduziert den Speicherverbrauch, wenn Sie viele ähnliche Formen benötigen.  
- **Fallstrick:** Das direkte Speichern als PDF nach dem Hinzufügen von Transparenz funktioniert sofort, aber wenn Sie das PDF später mit anderen Werkzeugen bearbeiten, können einige ältere Viewer die Opazität nicht korrekt darstellen.

## Fazit

Das Hinzufügen transparenter Objekte zu XPS-Dokumenten mit Aspose.Page für .NET bietet eine vielseitige Möglichkeit, visuelle Präsentationen zu verbessern. Sobald Ihre XPS-Datei wie gewünscht aussieht, können Sie **XPS nach PDF exportieren** mit einer einzigen Codezeile und dabei alle Transparenzeffekte für eine breite Verteilung beibehalten.

## FAQ

### Q1: Kann ich Transparenz auf jedes Objekt in einem XPS-Dokument anwenden?

A1: Ja, Transparenz kann auf verschiedene Objekte wie Pfade, Formen und Bilder in einem XPS-Dokument angewendet werden.

### Q2: Wie kann ich die Opazität eines bestimmten Elements anpassen?

A2: Sie können die Opazitäts‑Eigenschaft von Fill oder Stroke setzen, um die Transparenz eines bestimmten Elements anzupassen.

### Q3: Ist Aspose.Page mit .NET Core kompatibel?

A3: Ja, Aspose.Page unterstützt .NET Core und ermöglicht plattformübergreifende Entwicklung.

### Q4: Kann ich XPS-Dokumente mit Aspose.Page in andere Formate exportieren?

A4: Aspose.Page bietet Funktionen zum Exportieren von XPS-Dokumenten in verschiedene Formate, einschließlich PDF und Bilder.

### Q5: Wo finde ich zusätzliche Unterstützung und Community‑Diskussionen?

A5: Für zusätzliche Unterstützung und Community‑Diskussionen besuchen Sie das [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

### Q6: Behält die PDF-Konvertierung meine Transparenzeinstellungen bei?

A6: Absolut. Wenn Sie XPS mit Aspose.Page nach PDF exportieren, werden alle Opazitäts‑ und Misch‑Einstellungen beibehalten.

### Q7: Kann ich mehrere XPS-Dateien stapelweise zu PDF verarbeiten?

A7: Ja, Sie können durch eine Sammlung von XPS-Dateien iterieren und für jede `doc.Save(...".pdf")` aufrufen, um die Massenkonvertierung zu automatisieren.

---

**Zuletzt aktualisiert:** 2026-03-29  
**Getestet mit:** Aspose.Page 24.12 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}