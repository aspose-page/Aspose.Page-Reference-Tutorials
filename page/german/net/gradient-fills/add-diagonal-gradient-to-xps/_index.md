---
date: 2026-02-23
description: Lernen Sie, wie Sie mit Aspose.Page für .NET diagonale Farbverlauf‑XPS‑Dokumente
  erstellen und Ihre visuellen Präsentationen mühelos aufwerten.
linktitle: Add Diagonal Gradient to XPS
second_title: Aspose.Page .NET API
title: Diagonalen Farbverlauf XPS mit Aspose.Page für .NET erstellen
url: /de/net/gradient-fills/add-diagonal-gradient-to-xps/
weight: 11
---

"

**Tested With:** Aspose.Page 24.11 for .NET => "**Getestet mit:** Aspose.Page 24.11 für .NET"

**Author:** Aspose => "**Autor:** Aspose"

Now produce final content with all unchanged shortcodes.

Make sure to keep markdown formatting.

Let's construct final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Diagonalverlauf XPS mit Aspose.Page für .NET erstellen

## Einführung

Wenn Sie **diagonal verlaufende XPS**‑Dateien erstellen möchten, die ins Auge fallen, macht Aspose.Page für .NET das ganz einfach. In diesem Tutorial lernen Sie, wie Sie Schritt für Schritt einen diagonalen Verlauf zu einem XPS‑Dokument hinzufügen, indem Sie die Aspose.Page‑API verwenden. Am Ende haben Sie ein wiederverwendbares Muster, das Sie an jede Form oder Farbschema anpassen können.

## Schnelle Antworten
- **Was macht die API‑Methode?** Sie erstellt einen linearen Verlaufs‑Pinsel, der diagonal über einen Pfad verläuft.  
- **Welche Klasse repräsentiert das XPS‑Dokument?** `XpsDocument`.  
- **Benötige ich eine Lizenz, um das Beispiel auszuführen?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine Lizenz erforderlich.  
- **Kann ich die Verlaufsrichtung ändern?** Ja – passen Sie die Start‑ und End‑`PointF`‑Werte an.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Was ist **create diagonal gradient xps**?
Ein diagonaler Verlauf ist ein sanfter Farbwechsel, der von einer Ecke einer Form zur gegenüberliegenden Ecke verläuft. In XPS wird dieser Effekt erzielt, indem ein `LinearGradientBrush` auf die Füll‑Eigenschaft eines Pfads angewendet wird. Die Aspose.Page‑Bibliothek abstrahiert das Low‑Level‑XPS‑Markup, sodass Sie sich auf Farben und Geometrie konzentrieren können.

## Warum Aspose.Page für diagonale Verläufe verwenden?
- **High‑Fidelity‑Rendering** – die Ausgabe entspricht exakt der XPS‑Spezifikation.  
- **Vollständige .NET‑Integration** – funktioniert mit C#, VB.NET und jeder .NET‑Sprache.  
- **Keine externen Abhängigkeiten** – alles wird im Prozess verarbeitet, kein COM oder Office erforderlich.  
- **Skalierbar für komplexe Dokumente** – Sie können mehrere Verläufe, Bilder und Text auf derselben Seite kombinieren.

## Voraussetzungen

1. **Aspose.Page for .NET Bibliothek** – laden Sie sie [hier](https://releases.aspose.com/page/net/) herunter.  
2. **Entwicklungsumgebung** – Visual Studio, Rider oder jeder Editor, der .NET‑Projekte unterstützt.  

Jetzt tauchen wir in den Code ein.

## Namespaces importieren

In Ihrem .NET‑Projekt binden Sie die erforderlichen Namespaces der Aspose.Page‑Bibliothek ein, um auf die benötigten Klassen und Methoden zuzugreifen. Fügen Sie die folgenden Namespaces am Anfang Ihres Codes hinzu:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Schritt 1: Dokumentverzeichnis festlegen

Beginnen Sie damit, den Pfad zu Ihrem Dokumentverzeichnis anzugeben. Dort wird das resultierende XPS‑Dokument mit dem diagonalen Verlauf gespeichert.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Schritt 2: Neues XPS‑Dokument erstellen

Initialisieren Sie ein neues `XpsDocument` mit der Aspose.Page‑Bibliothek.

```csharp
XpsDocument doc = new XpsDocument();
```

## Schritt 3: Verlaufsfarben definieren

Erstellen Sie eine Liste von `XpsGradientStop`‑Objekten, die jeweils eine Farbe im diagonalen Verlauf darstellen.

```csharp
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 142, 4), 0f));
// ... Repeat for other colors
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 199, 80), 1f));
```

## Schritt 4: Diagonalen Verlauf zu einem Pfad hinzufügen

Erstellen Sie einen neuen Pfad mit definierter Geometrie und wenden Sie den diagonalen Verlauf darauf an. Passen Sie bei Bedarf die Rendering‑Transformation und die Füll‑Eigenschaften an.

```csharp
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 10f), new PointF(228f, 100f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
```

## Schritt 5: Resultierendes XPS‑Dokument speichern

Speichern Sie schließlich das modifizierte XPS‑Dokument im angegebenen Verzeichnis.

```csharp
doc.Save(dataDir + "AddDiagonalGradient_outXPS.xps");
```

Sie haben nun erfolgreich eine **diagonal verlaufende XPS**‑Datei erstellt. Experimentieren Sie gern mit verschiedenen Farb‑Stops, Geometrie‑Strings oder Transformations‑Matrizen, um eine Vielzahl von visuellen Effekten zu erzeugen.

## Häufige Probleme und Lösungen
- **Verlauf nicht sichtbar** – Stellen Sie sicher, dass die Pfadgeometrie geschlossen ist und dass die Start‑/End‑Punkte des Pinsels innerhalb der Pfadgrenzen liegen.  
- **Falsche Farben** – Vergewissern Sie sich, dass Sie `CreateColor` mit den korrekten ARGB‑Werten verwenden; die Methode erwartet Werte im Bereich 0‑255.  
- **Datei nicht gespeichert** – Prüfen Sie, ob `dataDir` auf einen bestehenden Ordner zeigt und die Anwendung Schreibrechte hat.

## Häufig gestellte Fragen

**F: Kann ich mehrere Verläufe auf verschiedene Teile des Dokuments anwenden?**  
A: Ja, Sie können mehrere Pfade erstellen und jedem einen eigenen Verlauf zuweisen.

**F: Gibt es vordefinierte Verlaufs‑Stile?**  
A: Aspose.Page ermöglicht benutzerdefinierte Verläufe und gibt Ihnen die volle Kontrolle über Farbübergänge.

**F: Kann ich Aspose.Page für .NET mit anderen Dokumentformaten verwenden?**  
A: Aspose.Page konzentriert sich hauptsächlich auf die Manipulation von XPS‑Dokumenten.

**F: Wie kann ich Fehler bei der Dokumentverarbeitung behandeln?**  
A: Siehe die [Dokumentation](https://reference.aspose.com/page/net/) für bewährte Methoden zur Fehlerbehandlung.

**F: Gibt es eine Testversion vor dem Kauf?**  
A: Ja, Sie können die [kostenlose Testversion](https://releases.aspose.com/) ausprobieren, um Aspose.Page für .NET zu erleben.

**F: Wie ändere ich die Verlaufsrichtung zu vertikal oder horizontal?**  
A: Ändern Sie die `PointF`‑Argumente in `CreateLinearGradientBrush`, um neue Start‑ und Endpunkte festzulegen.

**F: Unterstützt die Bibliothek Transparenz in Verläufen?**  
A: Ja – fügen Sie beim Erstellen von Farben mit `CreateColor` einen Alpha‑Wert hinzu.

## Fazit

Aspose.Page für .NET vereinfacht den Prozess, XPS‑Dokumente mit diagonalen Verläufen zu verbessern. Dieser Leitfaden führte Sie von den Voraussetzungen bis zum Speichern der finalen Datei. Experimentieren Sie weiter mit verschiedenen Formen und Farbpaletten, um Ihre XPS‑Berichte, Broschüren oder Rechnungen wirklich hervorzuheben.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2026-02-23  
**Getestet mit:** Aspose.Page 24.11 für .NET  
**Autor:** Aspose  

---