---
date: 2026-05-20
description: Erfahren Sie, wie Sie XMP-Metadaten zu EPS-Dateien mit Aspose.Page für
  Java hinzufügen. Schritt‑für‑Schritt‑Anleitung zum programmgesteuerten Einbetten
  einfacher XMP‑Eigenschaften.
keywords:
- add xmp metadata
- how to add xmp
- Aspose.Page Java XMP
linktitle: Einfache Eigenschaften in XMP mit Java hinzufügen
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add XMP metadata to EPS files with Aspose.Page for Java.
    Step‑by‑step guide to embed simple XMP properties programmatically.
  headline: Add XMP Metadata to EPS Files Using Java
  type: TechArticle
- questions:
  - answer: Aspose.Page primarily supports Java, but equivalent libraries are available
      for .NET, C++, and Python.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore the features of Aspose.Page by obtaining a free trial
      **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Page for Java?
  - answer: The documentation is available **[here](https://reference.aspose.com/page/java/)**.
    question: Where can I find detailed documentation for Aspose.Page for Java?
  - answer: A temporary license can be acquired **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: You can purchase the product **[here](https://purchase.aspose.com/buy)**.
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: XMP-Metadaten zu EPS-Dateien mit Java hinzufügen
url: /de/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XMP-Metadaten zu EPS-Dateien mit Java hinzufügen

## Einführung
In modernen Grafik-Pipelines ermöglicht das programmatische **Hinzufügen von XMP-Metadaten** zu EPS-Dateien die vollständige Kontrolle darüber, wie Ihre Illustrationen beschrieben, durchsucht und archiviert werden. Mit Aspose.Page for Java können Sie XMP-Pakete in EPS-Dokumenten lesen, ändern und schreiben, ohne die Java-Umgebung zu verlassen. In diesem Tutorial führen wir Sie Schritt für Schritt durch das Hinzufügen einfacher XMP-Eigenschaften zu einer EPS-Datei, sodass Sie Ihre Grafiken schnell und zuverlässig mit benutzerdefinierten Metadaten anreichern können.

## Schnelle Antworten
- **Was bedeutet „add XMP metadata to EPS“?** Einbetten eines XMP-Pakets (XML‑basierte Metadaten) in eine EPS-Datei.  
- **Welche Bibliothek wird benötigt?** Aspose.Page for Java (herunterladbar von der Aspose-Website).  
- **Benötige ich eine Lizenz für Tests?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Wie viele Codezeilen?** Weniger als 30 Zeilen Java plus ein paar Import-Anweisungen.  
- **Kann ich andere Datentypen hinzufügen?** Ja – Daten, Ganzzahlen, Gleitkommazahlen, Zeichenketten und sogar Arrays werden unterstützt.

## Wie fügt man XMP-Metadaten zu EPS-Dateien mit Java hinzu?
Laden Sie die EPS-Datei mit `new PsDocument("input.eps")`, rufen Sie ihr XMP-Paket ab oder erstellen Sie es, fügen Sie die gewünschten Eigenschaften ein und speichern Sie das Dokument anschließend wieder auf die Festplatte – alles in weniger als zehn Zeilen Java-Code. Dieser Ansatz ermöglicht das Einbetten durchsuchbarer, standardkonformer Metadaten, ohne das EPS-Quellmaterial manuell bearbeiten zu müssen.

## Was ist XMP-Metadaten in EPS?
XMP-Metadaten in EPS sind ein XML-Paket, das innerhalb der EPS-Datei liegt und Informationen wie Autor, Erstellungsdatum und benutzerdefinierte Tags speichert. Das Einbetten dieses Pakets ermöglicht es nachgelagerten Tools, die Daten zu lesen und zu nutzen, ohne separate Begleitdateien zu benötigen.

## Warum XMP-Metadaten zu EPS-Dateien hinzufügen?
Das Einbetten von XMP-Metadaten macht EPS-Assets sofort durchsuchbar, sorgt für Konformität, indem Lizenzinformationen in der Datei gespeichert werden, ermöglicht automatisierten Pipelines Entscheidungen basierend auf eingebetteten Tags zu treffen, und garantiert, dass die Metadaten mit der Grafik über alle Plattformen hinweg mitgereist werden. Aspose.Page kann Dateien bis zu 500 MB verarbeiten, ohne das gesamte Dokument in den Speicher zu laden, und liefert damit hohe Leistung für groß angelegte Workloads.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Grundkenntnisse in Java-Programmierung.  
- Aspose.Page for Java Bibliothek installiert. Sie können sie **[hier](https://releases.aspose.com/page/java/)** herunterladen.  
- Eine Beispiel‑EPS-Datei mit Metadaten. Falls Sie keine haben, können Sie die bereitgestellte **`xmp3.eps`**-Datei verwenden.

## Pakete importieren
Zuerst importieren Sie die benötigten Klassen. Die Import-Anweisungen bleiben exakt gleich wie im Originalbeispiel:

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

## Schritt 1: EPS-Dokument laden und XMP-Metadaten abrufen
Die Klasse `PsDocument` repräsentiert eine EPS-Datei und bietet Methoden zum Zugriff auf deren Inhalt und Metadaten.  
Das Objekt `XmpMetadata` enthält das mit dem Dokument verbundene XMP-Paket.

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
Die Klasse `Date` repräsentiert einen bestimmten Zeitpunkt mit Millisekunden‑Präzision.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Schritt 3: Ganzzahl‑Eigenschaft hinzufügen
Die Klasse `Integer` kapselt einen primitiven `int`‑Wert als Objekt.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Schritt 4: Gleitkomma‑Eigenschaft hinzufügen
Die Klasse `Double` kapselt einen primitiven `double`‑Wert als Objekt.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Schritt 5: String‑Eigenschaft hinzufügen
Die Klasse `String` repräsentiert eine Zeichenkette.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Schritt 6: Aktualisierte EPS-Datei speichern
Die Methode `save` schreibt das geänderte Dokument zurück auf die Festplatte und bewahrt dabei die EPS-Struktur.

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
Schließen Sie stets Streams, um Dateihandle-Lecks zu vermeiden und sicherzustellen, dass alle Puffer geleert werden.

```java
// Close input EPS stream
psStream.close();
```

## Häufige Probleme und Lösungen
| Problem | Grund | Lösung |
|-------|--------|-----|
| **Null XMP-Metadaten** | Die EPS-Datei enthielt kein XMP-Paket und die Bibliothek konnte keine PS-Kommentare ableiten. | Stellen Sie sicher, dass die Quell‑EPS mindestens einen PS‑Kommentar enthält (z. B. `%%Creator`). Die Bibliothek erzeugt automatisch ein minimales XMP-Paket. |
| **Zeitzonen‑Abweichung** | Datumsangaben erscheinen verschoben, wenn sie in einer anderen Anwendung geöffnet werden. | Setzen Sie `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` bevor Sie das `Date`‑Objekt erstellen, wie in Schritt 2 gezeigt. |
| **Lizenz‑Ausnahme** | Zur Laufzeit wird `LicenseException` ausgelöst. | Wenden Sie eine gültige Aspose.Page‑Lizenz an, bevor Sie die API nutzen, oder führen Sie im Testmodus (Trial) aus. |

## Häufig gestellte Fragen
**Q:** Kann ich Aspose.Page for Java mit anderen Programmiersprachen verwenden?  
**A:** Aspose.Page unterstützt hauptsächlich Java, aber äquivalente Bibliotheken sind für .NET, C++ und Python verfügbar.

**Q:** Ist eine kostenlose Testversion für Aspose.Page for Java verfügbar?  
**A:** Ja, Sie können die Funktionen von Aspose.Page durch eine kostenlose Testversion **[hier](https://releases.aspose.com/)** erkunden.

**Q:** Wo finde ich die ausführliche Dokumentation für Aspose.Page for Java?  
**A:** Die Dokumentation ist **[hier](https://reference.aspose.com/page/java/)** verfügbar.

**Q:** Wie kann ich eine temporäre Lizenz für Aspose.Page for Java erhalten?  
**A:** Eine temporäre Lizenz kann **[hier](https://purchase.aspose.com/temporary-license/)** erworben werden.

**Q:** Wo kann ich Aspose.Page for Java kaufen?  
**A:** Das Produkt können Sie **[hier](https://purchase.aspose.com/buy)** erwerben.

---

**Zuletzt aktualisiert:** 2026-05-20  
**Getestet mit:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Wie man XMP-Metadaten mit Java liest – Aspose.Page Anleitung](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page XMP-Tutorial – Namespace in XMP mit Java hinzufügen](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Array-Elemente zu XMP-Metadaten mit Java hinzufügen](/page/java/xmp-metadata-manipulation/add-array-items/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}