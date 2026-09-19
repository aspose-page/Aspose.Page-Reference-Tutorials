---
date: 2026-09-19
description: Erfahren Sie, wie Sie XMP‑benannte Werte zu EPS‑Dateien mit Aspose.Page
  für Java hinzufügen – eine Schritt‑für‑Schritt‑Anleitung mit Codebeispielen.
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
- EPS XMP manipulation
- Java metadata API
lastmod: 2026-09-19
linktitle: Benannten Wert in XMP mit Java hinzufügen
og_description: Wie Sie XMP‑benannte Werte zu EPS‑Dateien mit Aspose.Page für Java
  hinzufügen. Folgen Sie dieser kompakten Anleitung, um benutzerdefinierte Metadaten
  in wenigen Minuten zu integrieren.
og_image_alt: Screenshot of Java code adding XMP named value to an EPS file with Aspose.Page
og_title: So fügen Sie XMP‑benannte Werte in EPS‑Dateien mit Java hinzu
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  headline: How to add XMP named value in EPS files using Java
  type: TechArticle
- description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  name: How to add XMP named value in EPS files using Java
  steps:
  - name: Initialize input EPS file stream
    text: '**FileInputStream** is a Java I/O class that reads raw bytes from a file.
      Load the source EPS file into a `FileInputStream`. This stream feeds the document
      into Aspose’s API. > **Pro tip:** Keep the `dataDir` variable configurable so
      the same code works across environments.'
  - name: Obtain XMP metadata
    text: '**XmpMetadata** represents the XMP packet associated with an EPS document.
      Retrieve the existing XMP packet; if the EPS file lacks one, Aspose creates
      a fresh XMP object populated from the PS comments.'
  - name: Add named value
    text: '**NamedValue** is a key‑value pair stored within the XMP metadata namespace.
      Insert a custom named value into the XMP structure. In this example we add a
      new key under the `xmpTPg:MaxPageSize` namespace. > **Why this matters:** Named
      values let you store arbitrary key‑value pairs that downstream app'
  - name: Initialize output EPS file stream
    text: '**FileOutputStream** is a Java I/O class that writes raw bytes to a file.
      Prepare a `FileOutputStream` where the modified EPS will be saved.'
  - name: Save document
    text: The `save` method persists the changes. It writes the updated XMP packet
      back into the EPS file, guaranteeing that the new named value becomes part of
      the document’s metadata.
  - name: Close input EPS stream
    text: Closing the original file handle prevents resource leaks and ensures that
      the file is not locked for subsequent operations. By following these six steps,
      you have successfully **added a named value in XMP metadata** using **Aspose.Page
      for Java**.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly with other Java
      libraries, providing flexibility in your development environment.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can access a free trial of Aspose.Page for Java on the [Aspose
      releases page](https://releases.aspose.com/).
    question: Is a free trial available for Aspose.Page for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to obtain a temporary license for Aspose.Page for Java.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Explore the [documentation](https://reference.aspose.com/page/java/) for
      comprehensive tutorials and examples.
    question: Where can I find more tutorials and examples for Aspose.Page for Java?
  - answer: Absolutely, Aspose.Page for Java is designed to handle large‑scale projects
      efficiently, providing robust document manipulation capabilities.
    question: Is Aspose.Page for Java suitable for large‑scale projects?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- XMP metadata
- Aspose.Page
- Java EPS
- document automation
title: So fügen Sie XMP‑benannte Werte in EPS‑Dateien mit Java hinzu
url: /de/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Benannten Wert in XMP-Metadaten mit Java hinzufügen

## Einführung
In der modernen Java‑Entwicklung ist das Erlernen **wie man XMP** Metadaten in EPS‑Dateien hinzufügt, entscheidend, um die Herkunft von Dokumenten zu bewahren und die Durchsuchbarkeit zu verbessern. Mit **Aspose.Page for Java** können Sie mühelos benutzerdefinierte benannte Werte in das XMP‑Paket einfügen. Dieses Tutorial führt Sie Schritt für Schritt durch die genauen Vorgänge — inklusive Code‑Snippets — damit Sie noch heute XMP‑Metadaten zu Ihren EPS‑Dokumenten hinzufügen können.

## Schnelle Antworten
- **Welche Bibliothek wird benötigt?** Aspose.Page for Java (Aspose)  
- **Welcher Dateityp wird angesprochen?** EPS‑Dateien, die XMP‑Metadaten enthalten  
- **Primärer Anwendungsfall?** Benutzerdefinierte benannte Werte hinzufügen (z. B. Seitenbegrenzungen) zu XMP  
- **Voraussetzungen?** JDK 8+ und die Aspose.Page for Java Bibliothek  
- **Typische Implementierungszeit?** 5–10 Minuten, sobald die Bibliothek eingerichtet ist  

## Was ist asp?
Aspose ist die Kurzform für Aspose, eine Suite von APIs, die Entwicklern ermöglicht, eine Vielzahl von Dokumentformaten zu erstellen, zu bearbeiten, zu konvertieren und zu rendern, ohne externe Software zu benötigen. Die Komponente Aspose.Page for Java konzentriert sich speziell auf die Verarbeitung von PostScript und EPS und bietet programmatischen Zugriff auf Seiteninhalte, Grafiken und Metadaten wie XMP.

## Warum benannte Werte zu XMP-Metadaten hinzufügen?
Benannte Werte erlauben das Speichern beliebiger Schlüssel‑Wert‑Paare direkt im XMP‑Paket, sodass nachgelagerte Werkzeuge sie sofort lesen können. Das erhöht die Suchmaschinenfreundlichkeit, ermöglicht Workflow‑Automatisierung und erfüllt Compliance‑Anforderungen, indem regulatorische Informationen eingebettet werden, ohne den visuellen Inhalt zu verändern.

## Warum das wichtig ist
Durch das Hinzufügen benannter Werte zu XMP können Sie beliebige Schlüssel‑Wert‑Paare speichern, die ohne Parsen der gesamten EPS‑Datei gelesen werden können. Diese Fähigkeit ist besonders wertvoll in automatisierten Publishing‑Pipelines, Digital‑Asset‑Management‑Systemen und compliance‑getriebenen Workflows, bei denen Metadaten nachgelagerte Aktionen steuern.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- **Java Development Kit (JDK):** Ein aktuelles JDK (8 oder höher) auf Ihrem Rechner installiert.  
- **Aspose.Page for Java Library:** Laden Sie es von der offiziellen [Aspose.Page for Java download](https://releases.aspose.com/page/java/) herunter. Fügen Sie die JAR‑Datei dem Klassenpfad Ihres Projekts hinzu.  
- **Eine EPS-Datei**, die bereits XMP‑Metadaten enthält oder automatisch generiert wird.

## Pakete importieren
Beginnen Sie mit dem Import der notwendigen Java‑Pakete. Diese Importe geben Ihnen Zugriff auf Dateiströme, das EPS‑Dokumentenmodell und XMP‑Verarbeitungsklassen.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Wie man XMP-benannte Werte in EPS-Dateien mit Java hinzufügt
Um einen benannten Wert hinzuzufügen, laden Sie die EPS‑Datei mit einem `FileInputStream`, holen oder erstellen das zugehörige `XmpMetadata`‑Objekt, fügen den gewünschten `NamedValue` im passenden Namensraum ein und schreiben das modifizierte Dokument anschließend mit einem `FileOutputStream` zurück. Aspose.Page erstellt bei Bedarf automatisch ein XMP‑Paket, sodass die neuen Metadaten korrekt eingebettet werden.

### Schritt 1: Eingabestream für EPS-Datei initialisieren
**FileInputStream** ist eine Java‑I/O‑Klasse, die Rohbytes aus einer Datei liest. Laden Sie die Quell‑EPS‑Datei in einen `FileInputStream`. Dieser Stream liefert das Dokument an die API von Aspose.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **Pro Tipp:** Halten Sie die Variable `dataDir` konfigurierbar, damit derselbe Code in verschiedenen Umgebungen funktioniert.

### Schritt 2: XMP-Metadaten erhalten
**XmpMetadata** repräsentiert das XMP‑Paket, das einem EPS‑Dokument zugeordnet ist. Rufen Sie das vorhandene XMP‑Paket ab; fehlt es, erzeugt Aspose ein frisches XMP‑Objekt, das aus den PS‑Kommentaren gefüllt wird.

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### Schritt 3: Benannten Wert hinzufügen
**NamedValue** ist ein Schlüssel‑Wert‑Paar, das im XMP‑Metadaten‑Namensraum gespeichert wird. Fügen Sie einen benutzerdefinierten benannten Wert in die XMP‑Struktur ein. In diesem Beispiel fügen wir einen neuen Schlüssel unter dem Namensraum `xmpTPg:MaxPageSize` hinzu.

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **Warum das wichtig ist:** Benannte Werte ermöglichen das Speichern beliebiger Schlüssel‑Wert‑Paare, die nachgelagerte Anwendungen lesen können, ohne das gesamte Dokument zu parsen.

### Schritt 4: Ausgabestream für EPS-Datei initialisieren
**FileOutputStream** ist eine Java‑I/O‑Klasse, die Rohbytes in eine Datei schreibt. Bereiten Sie einen `FileOutputStream` vor, in dem das modifizierte EPS gespeichert wird.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### Schritt 5: Dokument speichern
Die `save`‑Methode schreibt die Änderungen. Sie schreibt das aktualisierte XMP‑Paket zurück in die EPS‑Datei und stellt sicher, dass der neue benannte Wert Teil der Metadaten des Dokuments wird.

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### Schritt 6: Eingabestream für EPS schließen
Das Schließen des ursprünglichen Dateihandles verhindert Ressourcen‑Lecks und sorgt dafür, dass die Datei nicht für nachfolgende Vorgänge gesperrt bleibt.

```java
psStream.close();
```

Durch das Befolgen dieser sechs Schritte haben Sie erfolgreich **einen benannten Wert in XMP-Metadaten** mit **Aspose.Page for Java** **hinzugefügt**.

## Häufige Probleme & Lösungen
| Problem | Ursache | Lösung |
|---------|---------|--------|
| `NullPointerException` bei `xmp` | EPS-Datei hat kein XMP und Aspose konnte keines erzeugen | Stellen Sie sicher, dass die EPS mindestens einen PS‑Kommentar enthält oder erstellen Sie manuell eine neue `XmpMetadata`‑Instanz. |
| Ausgabedatei ist leer | Ausgabestream nicht geleert/geschlossen | Vergewissern Sie sich, dass `outPsStream.close()` in einem `finally`‑Block aufgerufen wird (wie gezeigt). |
| Fehler wegen doppeltem Schlüssel | Derselbe benannte Wert wurde zweimal hinzugefügt | Prüfen Sie, ob der Schlüssel bereits mit `xmp.containsNamedValue(...)` existiert, bevor Sie ihn hinzufügen. |

## Häufig gestellte Fragen

**F: Kann ich Aspose.Page for Java mit anderen Java‑Bibliotheken verwenden?**  
**A:** Ja, Aspose.Page for Java ist so konzipiert, dass es nahtlos mit anderen Java‑Bibliotheken zusammenarbeitet und Flexibilität in Ihrer Entwicklungsumgebung bietet.

**F: Ist eine kostenlose Testversion von Aspose.Page for Java verfügbar?**  
**A:** Ja, Sie können eine kostenlose Testversion von Aspose.Page for Java auf der [Aspose releases page](https://releases.aspose.com/) erhalten.

**F: Wie kann ich eine temporäre Lizenz für Aspose.Page for Java erhalten?**  
**A:** Besuchen Sie die [temporary license page](https://purchase.aspose.com/temporary-license/), um eine temporäre Lizenz für Aspose.Page for Java zu erhalten.

**F: Wo finde ich weitere Tutorials und Beispiele für Aspose.Page for Java?**  
**A:** Durchsuchen Sie die [documentation](https://reference.aspose.com/page/java/) für umfassende Tutorials und Beispiele.

**F: Ist Aspose.Page for Java für Großprojekte geeignet?**  
**A:** Absolut, Aspose.Page for Java ist darauf ausgelegt, Großprojekte effizient zu bewältigen und bietet robuste Dokumenten‑Manipulationsfunktionen.

## Fazit
In diesem Leitfaden haben wir gezeigt, wie **Aspose.Page for Java** das **Hinzufügen benannter Werte zu XMP‑Metadaten** in EPS‑Dateien unkompliziert macht. Mit den oben beschriebenen Schritten können Sie Ihre Dokumente mit benutzerdefinierten Metadaten anreichern, die Durchsuchbarkeit verbessern und intelligentere nachgelagerte Verarbeitungen ermöglichen.

---

**Zuletzt aktualisiert:** 2026-09-19  
**Getestet mit:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man XMP-Namespace in EPS-Dateien mit Aspose.Page – Java‑Tutorial](/page/java/xmp-metadata-manipulation/add-namespace/)
- [XMP-Metadaten zu EPS-Dateien mit Java hinzufügen](/page/java/xmp-metadata-manipulation/add-simple-properties/)
- [XMP mit Aspose.Page lesen – Java‑Leitfaden](/page/java/xmp-metadata-manipulation/get-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}