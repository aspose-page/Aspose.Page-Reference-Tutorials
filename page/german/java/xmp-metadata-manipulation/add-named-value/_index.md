---
date: 2026-05-05
description: Erfahren Sie, wie Sie XMP‑benannte Werte zu EPS‑Dateien mit Aspose.Page
  für Java hinzufügen – ein Schritt‑für‑Schritt‑Leitfaden mit Codebeispielen.
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
linktitle: Benannten Wert in XMP mit Java hinzufügen
second_title: Aspose.Page Java API
title: Wie man mit Java einen benannten XMP‑Wert zu EPS‑Dateien hinzufügt
url: /de/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Benannten Wert in XMP-Metadaten mit Java hinzufügen

## Einführung
In der modernen Java-Entwicklung ist das Erlernen **wie man XMP**-Metadaten in EPS-Dateien hinzufügt, entscheidend, um die Herkunft von Dokumenten zu bewahren und die Durchsuchbarkeit zu verbessern. Mit **asp** (Aspose.Page for Java) können Sie mühelos benutzerdefinierte benannte Werte in das XMP-Paket einfügen. Dieses Tutorial führt Sie durch die genauen Schritte – komplett mit Code‑Snippets – sodass Sie noch heute XMP‑Metadaten zu Ihren EPS-Dokumenten hinzufügen können.

## Schnelle Antworten
- **Welche Bibliothek wird benötigt?** Aspose.Page for Java (asp)  
- **Welcher Dateityp wird angesprochen?** EPS-Dateien, die XMP-Metadaten enthalten  
- **Primärer Anwendungsfall?** Benutzerdefinierte benannte Werte (z. B. Seiten­größen‑Grenzen) zu XMP hinzufügen  
- **Voraussetzungen?** JDK 8+ und die Aspose.Page for Java‑Bibliothek  
- **Typische Implementierungszeit?** 5–10 Minuten, sobald die Bibliothek eingerichtet ist  

## Was ist asp?
*asp* ist die Kurzform für **Aspose**, eine Familie von .NET‑ und Java‑APIs, die die Dokumentenverarbeitung vereinfachen. Die Komponente Aspose.Page for Java ermöglicht das Erstellen, Bearbeiten und Konvertieren von PostScript‑ und EPS‑Dateien und bietet vollständigen programmatischen Zugriff auf deren Metadaten, einschließlich XMP.

## Warum benannte Werte zu XMP-Metadaten hinzufügen?
- **Suchmaschinenfreundlichkeit:** Benutzerdefinierte Tags verbessern die Auffindbarkeit.  
- **Workflow‑Automatisierung:** Nachgelagerte Tools können Ihre benutzerdefinierten Werte auslesen und Entscheidungen treffen.  
- **Compliance:** Regulatorische Informationen direkt im Dokumentpaket einbetten.  

## Warum das wichtig ist
Das Hinzufügen benannter Werte zu XMP ermöglicht das Speichern beliebiger Schlüssel‑Wert‑Paare, die gelesen werden können, ohne die gesamte EPS‑Datei zu parsen. Diese Fähigkeit ist besonders wertvoll in automatisierten Publishing‑Pipelines, Digital‑Asset‑Management‑Systemen und compliance‑getriebenen Workflows, bei denen Metadaten nachgelagerte Aktionen steuern.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- **Java Development Kit (JDK):** Ein aktuelles JDK (8 oder höher) auf Ihrem Rechner installiert.  
- **Aspose.Page for Java Library:** Laden Sie sie über den offiziellen [download link](https://releases.aspose.com/page/java/) herunter. Fügen Sie die JAR‑Datei dem Klassenpfad Ihres Projekts hinzu.  
- **Eine EPS‑Datei**, die bereits XMP‑Metadaten enthält oder bei der diese automatisch erzeugt werden.

## Pakete importieren
Beginnen Sie mit dem Import der notwendigen Java‑Pakete. Diese Importe geben Ihnen Zugriff auf Dateistreams, das EPS‑Dokumentenmodell und XMP‑Verarbeitungsklassen.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## So fügen Sie benannte XMP‑Werte in EPS-Dateien mit Java hinzu
Im Folgenden finden Sie eine kompakte, nummerierte Schritt‑für‑Schritt‑Anleitung, die exakt zeigt, **wie man XMP**‑benannte Werte zu einem EPS‑Dokument hinzufügt.

### Schritt 1: Eingabestream für EPS-Datei initialisieren
Laden Sie die Quell‑EPS‑Datei in einen `FileInputStream`. Dieser Stream liefert das Dokument an Asposes API.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **Profi‑Tipp:** Halten Sie die Variable `dataDir` konfigurierbar, damit derselbe Code in verschiedenen Umgebungen funktioniert.

### Schritt 2: XMP-Metadaten abrufen
Rufen Sie das vorhandene XMP‑Paket ab. Wenn die EPS‑Datei keines enthält, erzeugt Aspose ein frisches XMP‑Objekt, das aus den PS‑Kommentaren befüllt wird.

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### Schritt 3: Benannten Wert hinzufügen
Fügen Sie einen benutzerdefinierten benannten Wert in die XMP‑Struktur ein. In diesem Beispiel wird ein neuer Schlüssel unter dem Namespace `xmpTPg:MaxPageSize` hinzugefügt.

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **Warum das wichtig ist:** Benannte Werte ermöglichen das Speichern beliebiger Schlüssel‑Wert‑Paare, die nachgelagerte Anwendungen auslesen können, ohne das gesamte Dokument zu parsen.

### Schritt 4: Ausgabestream für EPS-Datei initialisieren

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### Schritt 5: Dokument speichern

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### Schritt 6: Eingabe‑EPS‑Stream schließen

```java
psStream.close();
```

Durch das Befolgen dieser sechs Schritte haben Sie erfolgreich **einen benannten Wert in XMP‑Metadaten** mit **asp** (Aspose.Page for Java) **hinzugefügt**.

## Häufige Probleme & Lösungen
| Problem | Ursache | Lösung |
|---------|---------|--------|
| `NullPointerException` on `xmp` | EPS-Datei hat kein XMP und Aspose konnte keines erzeugen | Stellen Sie sicher, dass die EPS mindestens einen PS‑Kommentar enthält oder erstellen Sie manuell eine neue `XmpMetadata`‑Instanz. |
| Output file is empty | Ausgabestream nicht gespült/geschlossen | Vergewissern Sie sich, dass `outPsStream.close()` in einem `finally`‑Block aufgerufen wird (wie gezeigt). |
| Duplicate key error | Derselbe benannte Wert wurde zweimal hinzugefügt | Prüfen Sie mit `xmp.containsNamedValue(...)`, ob der Schlüssel bereits existiert, bevor Sie ihn hinzufügen. |

## Häufig gestellte Fragen

**Q: Kann ich Aspose.Page for Java mit anderen Java-Bibliotheken verwenden?**  
A: Ja, Aspose.Page for Java ist so konzipiert, dass es nahtlos mit anderen Java-Bibliotheken zusammenarbeitet und Ihnen Flexibilität in Ihrer Entwicklungsumgebung bietet.

**Q: Ist eine kostenlose Testversion von Aspose.Page for Java verfügbar?**  
A: Ja, Sie können eine kostenlose Testversion von Aspose.Page for Java [hier](https://releases.aspose.com/) erhalten.

**Q: Wie kann ich eine temporäre Lizenz für Aspose.Page for Java erhalten?**  
A: Besuchen Sie [diesen Link](https://purchase.aspose.com/temporary-license/), um eine temporäre Lizenz für Aspose.Page for Java zu erhalten.

**Q: Wo finde ich weitere Tutorials und Beispiele für Aspose.Page for Java?**  
A: Durchstöbern Sie die [Dokumentation](https://reference.aspose.com/page/java/) für umfassende Tutorials und Beispiele.

**Q: Ist Aspose.Page for Java für groß angelegte Projekte geeignet?**  
A: Absolut, Aspose.Page for Java ist darauf ausgelegt, groß angelegte Projekte effizient zu bewältigen und bietet robuste Funktionen zur Dokumentenmanipulation.

## Fazit
In diesem Leitfaden haben wir gezeigt, wie **asp** (Aspose.Page for Java) das **Hinzufügen benannter Werte zu XMP‑Metadaten** in EPS‑Dateien unkompliziert macht. Mit den oben beschriebenen Schritten können Sie Ihre Dokumente mit benutzerdefinierten Metadaten anreichern, die Durchsuchbarkeit verbessern und intelligentere nachgelagerte Prozesse ermöglichen.

---

**Last Updated:** 2026-05-05  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}