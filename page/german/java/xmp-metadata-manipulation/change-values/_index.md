---
date: 2025-12-21
description: Erfahren Sie, wie Sie mit Aspose.Page XMP in EPS‑Dokumenten mithilfe
  von Java ändern. Verbessern Sie Metadaten schnell mit Aspose.Page für Java.
linktitle: Change Values in XMP using Java
second_title: Aspose.Page Java API
title: aspose.page XMP ändern – Werte in XMP mit Java ändern
url: /de/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XMP-Werte mit Java ändern

## Einführung
Wenn Sie **aspose.page modify xmp**‑Daten in einer EPS‑Datei ändern müssen, sind Sie hier genau richtig. In diesem Tutorial führen wir Sie Schritt für Schritt durch das Lesen, Aktualisieren und Speichern von XMP‑Werten (Extensible Metadata Platform) mit der Aspose.Page‑Bibliothek für Java. Am Ende können Sie Dokument‑Metadaten – wie Ersteller, Titel und Änderungsdatum – an die Anforderungen Ihres Projekts anpassen.

## Schnelle Antworten
- **Was macht “aspose.page modify xmp”?** Es ermöglicht das Lesen und Schreiben von XMP‑Metadaten in EPS‑Dateien über die Aspose.Page Java‑API.  
- **Welche Bibliotheksversion wird benötigt?** Jede aktuelle Aspose.Page‑Version für Java (die API ist versionsübergreifend stabil).  
- **Benötige ich eine Lizenz, um das Beispiel auszuführen?** Eine kostenlose Testversion reicht für die Evaluierung; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich mehrere XMP‑Felder gleichzeitig ändern?** Ja – rufen Sie `put` für jedes Feld auf, bevor Sie das Dokument speichern.  
- **Ist eine Zeitzonen‑Behandlung nötig?** Das Setzen der Standardzeitzone (z. B. UTC) sorgt für konsistente Datumswerte.

## Was ist XMP und warum es ändern?
XMP (Extensible Metadata Platform) ist ein standardisiertes Verfahren, um reichhaltige Metadaten direkt in Dateien wie EPS, PDF und Bilder einzubetten. Durch das Aktualisieren von XMP können Sie steuern, wie Dokumente indiziert, angezeigt und durchsucht werden – entscheidend für Markenbildung, Compliance und Workflow‑Automatisierung.

## Warum Aspose.Page für Java verwenden?
- **Vollständige API** – Keine externen Werkzeuge nötig; alles wird im Prozess verarbeitet.  
- **Plattformübergreifend** – Funktioniert auf jedem Betriebssystem, das Java unterstützt.  
- **Keine nativen Abhängigkeiten** – Reine Java‑Implementierung vereinfacht die Bereitstellung.  
- **Robuste Unterstützung** – Verarbeitet vorhandene XMP‑Blöcke und erstellt bei Bedarf neue aus PS‑Kommentar‑Metadaten.

## Voraussetzungen
Bevor Sie mit diesem Tutorial beginnen, stellen Sie sicher, dass folgende Voraussetzungen erfüllt sind:
1. **Java‑Entwicklungsumgebung** – Ein JDK (8 oder höher) sowie eine IDE oder ein Build‑Tool Ihrer Wahl.  
2. **Aspose.Page für Java Bibliothek** – Laden Sie die Aspose.Page‑Bibliothek für Java herunter und installieren Sie sie. Das benötigte Paket finden Sie [hier](https://releases.aspose.com/page/java/).

## Pakete importieren
Beginnen Sie damit, die erforderlichen Pakete in Ihr Java‑Projekt zu importieren. Diese Pakete sind entscheidend für die Interaktion mit und die Manipulation von EPS‑Dokumenten.

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

## Schritt 1: XMP‑Metadaten abrufen
Rufen Sie die XMP‑Metadaten aus dem EPS‑Dokument ab. Wenn die EPS‑Datei keine XMP‑Metadaten enthält, wird ein neuer Block mit Werten aus PS‑Metadaten‑Kommentaren wie %%Creator, %%CreateDate und %%Title erstellt.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## Schritt 2: Wert „ModifyDate“ ändern
Ändern Sie den Wert „ModifyDate“ in den XMP‑Metadaten, um das gewünschte Datum widerzuspiegeln.

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## Schritt 3: Wert „Creator“ ändern
Aktualisieren Sie den Wert „Creator“ in den XMP‑Metadaten, um den Ersteller des Dokuments anzugeben.

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## Schritt 4: Wert „Title“ ändern
Ändern Sie den Wert „Title“ in den XMP‑Metadaten, um einen passenden Titel für das Dokument festzulegen.

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## Schritt 5: Dokument mit geänderten XMP‑Metadaten speichern
Speichern Sie das Dokument mit den aktualisierten XMP‑Metadaten in einer neuen EPS‑Datei.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Häufige Probleme und Lösungen
- **Fehlender XMP‑Block** – Die API erstellt automatisch einen Block aus PS‑Kommentaren, Sie können bei Bedarf jedoch auch manuell `XmpMetadata` instanziieren.  
- **Zeitzonen‑Inkonsistenzen – Setzen Sie immer `TimeZone.setDefault`, bevor Sie das `Date`‑Objekt erzeugen, um unerwartete Verschiebungen zu vermeiden.  
- **Dateizugriffs‑Fehler** – Stellen Sie sicher, dass Eingabe‑ und Ausgabepfade korrekt sind und Ihre Anwendung über Lese‑/Schreibrechte verfügt.

## Häufig gestellte Fragen

**Q: Wie kann ich Zeitzonen‑Überlegungen beim Ändern von XMP‑Werten berücksichtigen?**  
A: Verwenden Sie `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))`, um Konsistenz bei den Zeitzoneneinstellungen sicherzustellen.

**Q: Kann ich mehrere XMP‑Werte in einem einzigen Vorgang ändern?**  
A: Ja, indem Sie die `put`‑Methode für jeden gewünschten Wert aufrufen, können Sie mehrere XMP‑Werte gleichzeitig ändern.

**Q: Wo finde ich zusätzliche Dokumentation für Aspose.Page für Java?**  
A: Erkunden Sie die umfassende Dokumentation [hier](https://reference.aspose.com/page/java/).

**Q: Gibt es eine kostenlose Testversion für Aspose.Page für Java?**  
A: Ja, Sie können die kostenlose Testversion [hier](https://releases.aspose.com/) abrufen.

**Q: Wie erhalte ich eine temporäre Lizenz für Aspose.Page für Java?**  
A: Eine temporäre Lizenz erhalten Sie [hier](https://purchase.aspose.com/temporary-license/).

**Q: Wirkt sich das Ändern von XMP auf den visuellen Inhalt des EPS aus?**  
A: Nein. XMP‑Änderungen betreffen ausschließlich Metadaten und verändern die grafischen Elemente der EPS‑Datei nicht.

**Q: Kann ich die aktualisierten Werte programmgesteuert auslesen, um die Änderung zu überprüfen?**  
A: Absolut – rufen Sie nach dem Speichern und vor dem Schließen des Dokuments einfach `xmp.get("dc:creator")` (oder den entsprechenden Schlüssel) auf.

## Fazit
Herzlichen Glückwunsch! Sie haben erfolgreich **aspose.page modify xmp**‑Werte in EPS‑Dokumenten mit Aspose.Page für Java geändert. Dieses Tutorial hat Ihnen das nötige Wissen vermittelt, um Metadaten zu bearbeiten und sicherzustellen, dass Ihre Dokumente nahtlos Ihren spezifischen Anforderungen entsprechen.

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Page for Java (latest release)  
**Author:** Aspose