---
date: 2026-05-25
description: Erfahren Sie, wie Sie XMP in EPS-Dokumenten mit Java und Aspose.Page
  ändern. Aktualisieren Sie Metadaten schnell und zuverlässig.
keywords:
- how to modify xmp
- Aspose.Page Java
- XMP metadata EPS
linktitle: Werte in XMP mit Java ändern
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to modify xmp in EPS documents using Java with Aspose.Page.
    Update metadata quickly and reliably.
  headline: how to modify xmp with Aspose.Page – Change Values in XMP using Java
  type: TechArticle
- questions:
  - answer: Utilize `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` to ensure consistency
      in time zone settings.
    question: How can I handle time zone considerations when modifying XMP values?
  - answer: Yes, by using the `put` method for each desired value, you can modify
      multiple XMP values concurrently.
    question: Can I change multiple XMP values in a single operation?
  - answer: Explore the comprehensive documentation [here](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation for Aspose.Page for Java?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: Wie man XMP mit Aspose.Page ändert – Werte in XMP mit Java ändern
url: /de/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Werte in XMP mit Java ändern

## Einführung
Wenn Sie **wie man XMP ändert** in einer EPS‑Datei mit Java suchen, sind Sie hier genau richtig. Dieses Tutorial führt Sie durch jeden Schritt – das Lesen des vorhandenen XMP‑Blocks, das Aktualisieren von Feldern wie Ersteller, Titel und Änderungsdatum und schließlich das Persistieren der Änderungen zurück in das EPS‑Dokument. Am Ende haben Sie ein wiederverwendbares Snippet, das in jeden automatisierten Workflow passt und sicherstellt, dass Ihre Dateien die korrekten Metadaten für Branding, Compliance oder Suchmaschinen‑Indexierung tragen.

## Schnelle Antworten
- **Was macht “aspose.page modify xmp”?** Es ermöglicht das Lesen und Schreiben von XMP‑Metadaten in EPS‑Dateien über die Aspose.Page Java API.  
- **Welche Bibliotheksversion wird benötigt?** Jede aktuelle Aspose.Page für Java‑Version (die API ist versionsübergreifend stabil).  
- **Benötige ich eine Lizenz, um das Beispiel auszuführen?** Eine kostenlose Testversion reicht für die Evaluierung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich mehrere XMP‑Felder gleichzeitig ändern?** Ja – rufen Sie `put` für jedes Feld auf, bevor Sie das Dokument speichern.  
- **Ist eine Zeitzonenbehandlung erforderlich?** Das Festlegen der Standardzeitzone (z. B. UTC) sorgt für konsistente Datumswerte.

## Was ist XMP und warum es ändern?
XMP (Extensible Metadata Platform) ist ein standardisiertes, XML‑basiertes Format zum Einbetten umfangreicher Metadaten direkt in Dateien wie EPS, PDF und Bilder. Das Aktualisieren von XMP ermöglicht es Ihnen, zu steuern, wie Dokumente indexiert, angezeigt und durchsucht werden – entscheidend für Markenkonsistenz, regulatorische Konformität und automatisierte Content‑Pipelines.

## Warum Aspose.Page für Java verwenden?
Aspose.Page bietet eine **vollwertige, reine Java‑API**, die die Notwendigkeit externer Werkzeuge oder nativer Bibliotheken eliminiert. Sie unterstützt **mehr als 50 Eingabe‑ und Ausgabeformate** und kann EPS‑Dateien bis zu **500 MB** verarbeiten, ohne das gesamte Dokument in den Speicher zu laden, und liefert schnelle, speichereffiziente Metadaten‑Manipulation auf jedem OS, das Java ausführt.

## Voraussetzungen
Bevor wir mit diesem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:
1. **Java-Entwicklungsumgebung** – Ein JDK (8 oder höher) und eine IDE oder ein Build‑Tool Ihrer Wahl.  
2. **Aspose.Page für Java‑Bibliothek** – Laden Sie die Aspose.Page für Java‑Bibliothek herunter und installieren Sie sie. Das benötigte Paket finden Sie [hier](https://releases.aspose.com/page/java/).

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

## Wie man XMP in EPS mit Java ändert?
`Document` ist die Aspose.Page‑Klasse, die eine EPS‑Datei repräsentiert und Zugriff auf deren Inhalt und Metadaten bietet. `XmpMetadata` stellt den an das Dokument angehängten XMP‑Block dar und ermöglicht das Lesen und Schreiben von Metadatenfeldern. `put` fügt einen Metadaten‑Eintrag hinzu oder aktualisiert ihn im XmpMetadata‑Objekt. `save` schreibt das modifizierte Dokument, einschließlich aller aktualisierten XMP‑Metadaten, in eine Datei.

Laden Sie die EPS‑Datei mit `new Document("input.eps")`, holen Sie ihr `XmpMetadata`‑Objekt, aktualisieren Sie die gewünschten Schlüssel mittels `put` und rufen Sie schließlich `save` auf, um die Änderungen in eine neue Datei zu schreiben. Dieser kompakte Ablauf behandelt fehlende XMP‑Blöcke automatisch, erstellt bei Bedarf einen aus PostScript‑Kommentaren und sorgt für zeitzonen‑konforme Datumsangaben.

## Schritt 1: XMP‑Metadaten abrufen
Die Klasse `XmpMetadata` repräsentiert den XMP‑Block, der an ein EPS‑Dokument angehängt ist. Wenn Sie `document.getXmpMetadata()` aufrufen, liefert die API entweder den bestehenden Block oder erzeugt einen neuen aus PS‑Kommentaren wie `%%Creator`, `%%CreateDate` und `%%Title`.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## Schritt 2: Wert von "ModifyDate" ändern
Aktualisieren Sie den Eintrag `"ModifyDate"` mit dem neuen Änderungszeitstempel. Verwenden Sie `java.util.Date` in Kombination mit `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))`, um sicherzustellen, dass der gespeicherte Wert zeitzonenunabhängig ist.

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## Schritt 3: Wert von "Creator" ändern
Der Schlüssel `"Creator"` speichert den Namen der Anwendung oder Person, die die EPS‑Datei erzeugt hat. Rufen Sie `xmp.put("dc:creator", "Your Company Name")` auf, um den vorhandenen Wert durch einen benutzerdefinierten Bezeichner zu ersetzen.

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## Schritt 4: Wert von "Title" ändern
Das Feld `"Title"` wird von vielen Asset‑Management‑Systemen angezeigt. Durch `xmp.put("dc:title", "New Document Title")` stellen Sie sicher, dass das Dokument in Katalogen und Suchergebnissen korrekt erscheint.

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## Schritt 5: Dokument mit geänderten XMP‑Metadaten speichern
Nachdem alle Änderungen vorgenommen wurden, rufen Sie `document.save("output.eps")` auf. Die Bibliothek schreibt den aktualisierten XMP‑Block zurück in den EPS‑Strom, während der ursprüngliche Grafikinhalt unverändert bleibt.

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
- **Missing XMP block** – Die API erstellt automatisch einen aus PS‑Kommentaren, Sie können jedoch bei Bedarf auch manuell ein `XmpMetadata`‑Objekt instanziieren.  
- **Timezone mismatches** – Setzen Sie immer `TimeZone.setDefault`, bevor Sie das `Date`‑Objekt erstellen, um unerwartete Verschiebungen zu vermeiden.  
- **File access errors** – Stellen Sie sicher, dass die Eingabe‑ und Ausgabepfade korrekt sind und Ihre Anwendung Lese‑/Schreibrechte besitzt.

## Häufig gestellte Fragen

**Q: Wie kann ich Zeitzonen‑Überlegungen beim Ändern von XMP‑Werten berücksichtigen?**  
A: Nutzen Sie `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))`, um Konsistenz bei den Zeitzoneneinstellungen zu gewährleisten.

**Q: Kann ich mehrere XMP‑Werte in einem einzigen Vorgang ändern?**  
A: Ja, indem Sie die `put`‑Methode für jeden gewünschten Wert verwenden, können Sie mehrere XMP‑Werte gleichzeitig ändern.

**Q: Wo finde ich zusätzliche Dokumentation für Aspose.Page für Java?**  
A: Erkunden Sie die umfassende Dokumentation [hier](https://reference.aspose.com/page/java/).

**Q: Gibt es eine kostenlose Testversion für Aspose.Page für Java?**  
A: Ja, Sie können die kostenlose Testversion [hier](https://releases.aspose.com/) nutzen.

**Q: Wie kann ich eine temporäre Lizenz für Aspose.Page für Java erhalten?**  
A: Eine temporäre Lizenz erhalten Sie [hier](https://purchase.aspose.com/temporary-license/).

**Q: Wirkt sich das Ändern von XMP auf den visuellen Inhalt des EPS aus?**  
A: Nein. XMP‑Änderungen betreffen ausschließlich Metadaten und verändern die grafischen Elemente der EPS‑Datei nicht.

**Q: Kann ich die aktualisierten Werte programmgesteuert auslesen, um die Änderung zu verifizieren?**  
A: Absolut – rufen Sie einfach `xmp.get("dc:creator")` (oder den entsprechenden Schlüssel) nach dem Speichern und vor dem Schließen des Dokuments auf.

## Fazit
Herzlichen Glückwunsch! Sie haben **wie man XMP‑Werte** in EPS‑Dokumenten mit Aspose.Page für Java ändert, gemeistert. Durch das Einbetten genauer Ersteller‑, Titel‑ und Änderungs‑Datums‑Metadaten stellen Sie sicher, dass Ihre Assets durchsuchbar, konform und im Einklang mit Ihren Markenstandards sind. Integrieren Sie dieses Muster gern in Batch‑Verarbeitungspipelines, CI/CD‑Schritte oder jede automatisierte Dokument‑Generierungs‑Workflow.

---

**Zuletzt aktualisiert:** 2026-05-25  
**Getestet mit:** Aspose.Page for Java (latest release)  
**Autor:** Aspose

## Verwandte Tutorials

- [Aspose Page Java Tutorial – XMP-Metadaten zu EPS-Dateien hinzufügen](/page/java/xmp-metadata-manipulation/add-metadata/)
- [Wie man XMP-Metadaten mit Java liest – Aspose.Page‑Leitfaden](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page xmp java – Array‑Elemente in XMP mit Java ändern](/page/java/xmp-metadata-manipulation/change-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}