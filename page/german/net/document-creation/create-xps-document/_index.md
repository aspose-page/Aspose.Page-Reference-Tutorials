---
date: 2026-01-12
description: Erfahren Sie, wie Sie ein XPS‑Dokument mit Aspose.Page für .NET erstellen
  – eine Schritt‑für‑Schritt‑Anleitung zur Erstellung hochwertiger elektronischer
  Dokumente.
linktitle: Create XPS Document
second_title: Aspose.Page .NET API
title: XPS-Dokument mit Aspose.Page für .NET erstellen
url: /de/net/document-creation/create-xps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS-Dokument mit Aspose.Page für .NET erstellen

## Einführung

Willkommen zu unserer Schritt‑für‑Schritt‑Anleitung, **wie man ein XPS‑Dokument** mit Aspose.Page für .NET erstellt. In diesem Tutorial zeigen wir den Prozess zur Erzeugung von XPS‑Dateien, einem weit verbreiteten Format für elektronische Dokumente. Egal, ob Sie ein erfahrener Entwickler sind oder gerade erst mit Aspose.Page beginnen – diese Anleitung hilft Ihnen, XPS‑Dokumente nahtlos zu erstellen, mit klaren Beispielen und ausführlichen Erklärungen.

## Schnellantworten
- **Welche Bibliothek benötige ich?** Aspose.Page für .NET  
- **Läuft das auf .NET Core?** Ja, die Bibliothek unterstützt .NET Core und .NET 5/6 vollständig  
- **Wie viele Code‑Zeilen?** Weniger als 20 Zeilen, um eine einfache XPS‑Datei zu erzeugen  
- **Brauche ich eine Lizenz für Tests?** Eine kostenlose Testversion ist verfügbar; für die Produktion ist eine Lizenz erforderlich  
- **Welches Format hat die Ausgabe?** XPS (XML Paper Specification)  

## Wie man ein XPS‑Dokument mit Aspose.Page für .NET erstellt

Im Folgenden finden Sie alles, was Sie vor dem Coden benötigen, gefolgt von einer knappen, nummerierten Schritt‑für‑Schritt‑Anleitung.

## Voraussetzungen

Bevor wir ins Tutorial einsteigen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Aspose.Page für .NET Bibliothek: Laden Sie die Aspose.Page‑Bibliothek von dem [Download‑Link](https://releases.aspose.com/page/net/) herunter und installieren Sie sie.  
2. Ihr Dokumenten‑Verzeichnis: Wählen Sie ein Verzeichnis auf Ihrem System aus oder erstellen Sie eines, in dem Sie die erzeugten XPS‑Dateien speichern möchten.

Jetzt geht’s los mit dem Tutorial!

## Namespaces importieren

Um Aspose.Page für .NET zu verwenden, müssen Sie die erforderlichen Namespaces in Ihr Projekt einbinden. Folgen Sie diesen Schritten:

### Schritt 1: Referenz zu Aspose.Page hinzufügen

Fügen Sie in Ihrem Projekt eine Referenz zur Aspose.Page‑für‑.NET‑Bibliothek hinzu. Die benötigte DLL finden Sie im heruntergeladenen Paket.

### Schritt 2: Namespaces importieren

Binden Sie die folgenden Namespaces in Ihrer Code‑Datei ein:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Nachdem wir die Voraussetzungen eingerichtet und die notwendigen Namespaces importiert haben, zerlegen wir den Prozess zur Erstellung eines XPS‑Dokuments in mehrere Schritte.

## Schritt 1: Dokumenten‑Verzeichnis festlegen

```csharp
string dir = "Your Document Directory";
```

Ersetzen Sie `"Your Document Directory"` durch den tatsächlichen Pfad, in dem Sie die XPS‑Ausgabedatei speichern möchten.

## Schritt 2: XPS‑Dokument erstellen

```csharp
XpsDocument xDocs = new XpsDocument();
```

Initialisieren Sie ein neues XPS‑Dokument mit der Klasse `XpsDocument`.

## Schritt 3: Glyphen zum Dokument hinzufügen

```csharp
var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
```

Verwenden Sie die Methode `AddGlyphs`, um Glyphen (Text) zum Dokument hinzuzufügen. Passen Sie Schriftart, Größe, Stil und Position nach Bedarf an.

## Schritt 4: Glyphen‑Füllfarbe festlegen

```csharp
glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);
```

Geben Sie die Füllfarbe für die hinzugefügten Glyphen an. In diesem Beispiel verwenden wir Schwarz, Sie können jedoch jede beliebige Farbe wählen.

## Schritt 5: Ergebnis speichern

```csharp
xDocs.Save(dir + "output.xps");
```

Speichern Sie schließlich das XPS‑Dokument im angegebenen Verzeichnis unter dem gewünschten Dateinamen. Die resultierende XPS‑Datei enthält den Text „Hello World!“.

Herzlichen Glückwunsch! Sie haben erfolgreich ein XPS‑Dokument mit Aspose.Page für .NET erstellt.

## Häufige Tipps & Stolperfallen

- **Verzeichnis‑Pfad** – Verwenden Sie `Path.Combine(dir, "output.xps")`, um fehlende Pfad‑Trennzeichen auf verschiedenen Betriebssystemen zu vermeiden.  
- **Schriftverfügbarkeit** – Die angegebene Schrift muss auf dem Rechner installiert sein, auf dem der Code ausgeführt wird; andernfalls ersetzt Aspose sie durch eine Standardschrift.  
- **Mehrere Seiten** – Um mehrseitige XPS‑Dateien zu erzeugen, instanziieren Sie zusätzliche `XpsPage`‑Objekte und fügen Sie jedem Seite Inhalte hinzu, bevor Sie speichern.

## Fazit

In diesem Tutorial haben wir den Prozess zur Erstellung von XPS‑Dokumenten mit Aspose.Page für .NET durchlaufen. Diese leistungsstarke Bibliothek ermöglicht eine nahtlose Generierung elektronischer Dokumente. Experimentieren Sie mit verschiedenen Schriften, Stilen und Inhalten, um Ihre XPS‑Dateien an Ihre spezifischen Anforderungen anzupassen.

## FAQ

### Q1: Kann ich benutzerdefinierte Schriften in meinem XPS‑Dokument verwenden?

A1: Ja, Sie können die Schriftfamilie und Größe beim Hinzufügen von Glyphen zu Ihrem XPS‑Dokument angeben.

### Q2: Ist Aspose.Page mit .NET Core kompatibel?

A2: Ja, Aspose.Page unterstützt .NET Core und kann in plattformübergreifenden Anwendungen eingesetzt werden.

### Q3: Wie kann ich Bilder zu einem XPS‑Dokument hinzufügen?

A3: Aspose.Page stellt Methoden zum Hinzufügen von Bildern zu Ihrem XPS‑Dokument bereit. Weitere Details finden Sie in der Dokumentation.

### Q4: Kann ich mehrseitige XPS‑Dokumente erstellen?

A4: Absolut! Sie können mehrere Seiten zu einem XPS‑Dokument hinzufügen, indem Sie die Aspose.Page‑Bibliothek verwenden.

### Q5: Gibt es eine Testversion?

A5: Ja, Sie können die Funktionen von Aspose.Page testen, indem Sie die [kostenlose Testversion](https://releases.aspose.com/) herunterladen.

---

**Zuletzt aktualisiert:** 2026-01-12  
**Getestet mit:** Aspose.Page 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}