---
date: 2025-12-20
description: Erfahren Sie, wie Sie XMP‑Metadaten in EPS‑Dateien mit Aspose.Page für
  Java erstellen. Schritt‑für‑Schritt‑Anleitung zum programmgesteuerten Hinzufügen
  einfacher XMP‑Eigenschaften.
linktitle: Add Simple Properties in XMP using Java
second_title: Aspose.Page Java API
title: Wie man XMP‑Metadaten in EPS mit Java erstellt
url: /de/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Einfache Eigenschaften in XMP mit Java hinzufügen

## Einleitung
In modernen Dokumenten‑Workflows ermöglicht das **programmatische Erstellen von XMP‑Metadaten‑EPS**‑Dateien die vollständige Kontrolle darüber, wie Ihre Grafiken beschrieben, durchsucht und archiviert werden. Mit Aspose.Page für Java können Sie XMP‑Pakete in EPS‑Dokumenten lesen, ändern und schreiben, ohne das Java‑Ökosystem zu verlassen. In diesem Tutorial führen wir Sie Schritt für Schritt durch das Hinzufügen einfacher XMP‑Eigenschaften zu einer EPS‑Datei, sodass Sie Ihre Grafiken schnell und zuverlässig mit benutzerdefinierten Metadaten anreichern können.

## Schnellantworten
- **Was bedeutet „create xmp metadata eps“?** Hinzufügen eines XMP‑Pakets (XML‑basierte Metadaten) zu einer EPS‑Datei.  
- **Welche Bibliothek wird benötigt?** Aspose.Page für Java (von der Aspose‑Website herunterladbar).  
- **Brauche ich eine Lizenz für Tests?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Wie viele Codezeilen?** Weniger als 30 Zeilen Java plus ein paar Import‑Anweisungen.  
- **Kann ich andere Datentypen hinzufügen?** Ja – Daten, Ganzzahlen, Gleitkommazahlen, Zeichenketten und sogar Arrays werden unterstützt.

## Was ist create xmp metadata eps?
XMP (Extensible Metadata Platform) ist ein Standard zum Einbetten umfangreicher Metadaten in Dateien. Wenn Sie **XMP‑Metadaten‑EPS erstellen**, betten Sie ein XML‑Paket in ein EPS‑(Encapsulated PostScript‑)Dokument ein, sodass nachgelagerte Anwendungen Autor, Erstellungsdatum, benutzerdefinierte Tags und mehr auslesen können.

## Warum XMP‑Metadaten zu EPS‑Dateien hinzufügen?
- **Durchsuchbarkeit:** Ermöglicht die automatische Indexierung durch DAM‑Systeme.  
- **Compliance:** Speichert rechtliche oder Lizenzinformationen direkt in der Datei.  
- **Automatisierung:** Ermöglicht nachgelagerten Pipelines Entscheidungen basierend auf eingebetteten Daten zu treffen.  
- **Portabilität:** Die Metadaten reisen mit der EPS‑Datei und gewährleisten Konsistenz über Plattformen hinweg.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Grundkenntnisse in Java‑Programmierung.  
- Aspose.Page für Java Bibliothek installiert. Sie können sie **[hier](https://releases.aspose.com/page/java/)** herunterladen.  
- Eine Beispiel‑EPS‑Datei, die Metadaten enthält. Wenn Sie keine haben, können Sie die bereitgestellte **`xmp3.eps`**‑Datei verwenden.

## Pakete importieren
Zuerst importieren Sie die Klassen, die Sie benötigen. Die Importe bleiben exakt gleich wie im Originalbeispiel:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Schritt 1: EPS-Dokument laden und XMP‑Metadaten abrufen
Wir öffnen die EPS‑Datei, erstellen eine `PsDocument`‑Instanz und rufen das XMP‑Paket ab (oder erzeugen es).

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Schritt 2: Datums‑Eigenschaft hinzufügen
Das Hinzufügen eines Datums ist so einfach wie das Erzeugen eines `Date`‑Objekts und das Einfügen in die XMP‑Map.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Schritt 3: Ganzzahl‑Eigenschaft hinzufügen
Sie können numerische Kennungen oder Versionsnummern mithilfe eines Ganzzahlwerts speichern.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Schritt 4: Gleitkomma‑Eigenschaft hinzufügen
Gleitkommazahlen sind nützlich für Messwerte oder Bewertungen.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Schritt 5: Zeichenketten‑Eigenschaft hinzufügen
Benutzerdefinierte Text‑Tags (z. B. Projekt‑Codes) werden als Zeichenketten gespeichert.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Schritt 6: Aktualisierte EPS-Datei speichern
Nachdem alle Eigenschaften hinzugefügt wurden, schreiben Sie das Dokument zurück auf die Festplatte.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Schritt 7: Ressourcen bereinigen
Schließen Sie stets den Eingabestream, um Dateihandhabungs‑Leaks zu vermeiden.

```java
// Close input EPS stream
psStream.close();
```

## Häufige Probleme und Lösungen
| Problem | Ursache | Lösung |
|---------|---------|--------|
| **Null XMP metadata** | Die EPS-Datei enthielt kein XMP-Paket und die Bibliothek konnte keine PS‑Kommentare ableiten. | Stellen Sie sicher, dass die Quell‑EPS mindestens einen PS‑Kommentar enthält (z. B. `%%Creator`). Die Bibliothek erzeugt automatisch ein minimales XMP-Paket. |
| **Time zone mismatch** | Datumsangaben erscheinen verschoben, wenn sie in einer anderen Anwendung geöffnet werden. | Setzen Sie `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` vor der Erstellung des `Date`‑Objekts, wie in Schritt 2 gezeigt. |
| **License exception** | Zur Laufzeit wird `LicenseException` ausgelöst. | Wenden Sie eine gültige Aspose.Page-Lizenz an, bevor Sie die API nutzen, oder führen Sie den Testmodus für die Evaluierung aus. |

## Fazit
Durch Befolgen dieser Schritte wissen Sie jetzt, wie Sie **XMP‑Metadaten‑EPS**‑Dateien mit Aspose.Page für Java erstellen. Das Hinzufügen einfacher Eigenschaften wie Datum, Ganzzahl, Gleitkomma und Zeichenkette ist unkompliziert, und die resultierenden EPS‑Dateien enthalten reiche, durchsuchbare Metadaten, die jedem nachgelagerten Workflow zugutekommen.

## Häufig gestellte Fragen
### Kann ich Aspose.Page für Java mit anderen Programmiersprachen verwenden?
Aspose.Page unterstützt hauptsächlich Java, es gibt jedoch Versionen für andere Sprachen wie .NET.

### Ist eine kostenlose Testversion für Aspose.Page für Java verfügbar?
Ja, Sie können die Funktionen von Aspose.Page erkunden, indem Sie eine kostenlose Testversion **[hier](https://releases.aspose.com/)** erhalten.

### Wo finde ich die ausführliche Dokumentation für Aspose.Page für Java?
Die Dokumentation ist **[hier](https://reference.aspose.com/page/java/)** verfügbar.

### Wie kann ich eine temporäre Lizenz für Aspose.Page für Java erhalten?
Eine temporäre Lizenz kann **[hier](https://purchase.aspose.com/temporary-license/)** erworben werden.

### Wo kann ich Aspose.Page für Java kaufen?
Sie können das Produkt **[hier](https://purchase.aspose.com/buy)** erwerben.

---

**Letzte Aktualisierung:** 2025-12-20  
**Getestet mit:** Aspose.Page für Java 24.11 (zum Zeitpunkt der Erstellung die neueste)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}